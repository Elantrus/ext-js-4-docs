# Ext.Loader

## Descrição

Ext.Loader is the heart of the new dynamic dependency loading capability in Ext JS 4+. It is most commonly used
via the Ext.require shorthand. Ext.Loader supports both asynchronous and synchronous loading
approaches, and leverage their advantages for the best development flow. We'll discuss about the pros and cons of each approach:

Advantages:

Disadvantages:

// Syntax
Ext.require({String/Array} expressions);

// Example: Single alias
Ext.require('widget.window');

// Example: Single class name
Ext.require('Ext.window.Window');

// Example: Multiple aliases / class names mix
Ext.require(['widget.window', 'layout.border', 'Ext.data.Connection']);

// Wildcards
Ext.require(['widget.*', 'layout.*', 'Ext.data.*']);


Method 2: Explicitly exclude what you don't need:

// Syntax: Note that it must be in this chaining format.
Ext.exclude({String/Array} expressions)
   .require({String/Array} expressions);

// Include everything except Ext.data.*
Ext.exclude('Ext.data.*').require('*');

// Include all widgets except widget.checkbox*,
// which will match widget.checkbox, widget.checkboxfield, widget.checkboxgroup, etc.
Ext.exclude('widget.checkbox*').require('widget.*');


Synchronous Loading on Demand


Advantages:

Disadvantages:

There's one simple rule to follow: Instantiate everything with Ext.create instead of the `new` keyword

Ext.create('widget.window', { ... }); // Instead of new Ext.window.Window({...});

Ext.create('Ext.window.Window', {}); // Same as above, using full class name instead of alias

Ext.widget('window', {}); // Same as above, all you need is the traditional `xtype`


Behind the scene, Ext.ClassManager will automatically check whether the given class name / alias has already
 existed on the page. If it's not, Ext.Loader will immediately switch itself to synchronous mode and automatic load the given
 class and all its dependencies.

It has all the advantages combined from asynchronous and synchronous loading. The development flow is simple:

Ext.Loader will automatically fetch all dependencies on demand as they're needed during run-time. For example:

Ext.onReady(function(){
    var window = Ext.widget('window', {
        width: 500,
        height: 300,
        layout: {
            type: 'border',
            padding: 5
        },
        title: 'Hello Dialog',
        items: [{
            title: 'Navigation',
            collapsible: true,
            region: 'west',
            width: 200,
            html: 'Hello',
            split: true
        }, {
            title: 'TabPanel',
            region: 'center'
        }]
    });

    window.show();
})


Step 2: Along the way, when you need better debugging ability, watch the console for warnings like these:

[Ext.Loader] Synchronously loading 'Ext.window.Window'; consider adding Ext.require('Ext.window.Window') before your application's code
ClassManager.js:432
[Ext.Loader] Synchronously loading 'Ext.layout.container.Border'; consider adding Ext.require('Ext.layout.container.Border') before your application's code


Simply copy and paste the suggested code above `Ext.onReady`, i.e:

Ext.require('Ext.window.Window');
Ext.require('Ext.layout.container.Border');

Ext.onReady(...);


Everything should now load via asynchronous mode.

It's important to note that dynamic loading should only be used during development on your local machines.
During production, all dependencies should be combined into one single JavaScript file. Ext.Loader makes
the whole process of transitioning from / to between development / maintenance and production as easy as
possible. Internally Ext.Loader.history maintains the list of all dependencies your application
needs in the exact loading sequence. It's as simple as concatenating all files in this array into one,
then include it on top of your application.

This process will be automated with Sencha Command, to be released and documented towards Ext JS 4 Final.

## Config options

### disableCaching

**Tipo:** Boolean

Appends current timestamp to script files to prevent caching. ...

Appends current timestamp to script files to prevent caching.
Defaults to: `true`


### disableCachingParam

**Tipo:** String

The get parameter name for the cache buster's timestamp. ...

The get parameter name for the cache buster's timestamp.
Defaults to: `'_dc'`


### enabled

**Tipo:** Boolean

Whether or not to enable the dynamic dependency loading feature. ...

Whether or not to enable the dynamic dependency loading feature.
Defaults to: `false`


### garbageCollect

**Tipo:** Boolean

True to prepare an asynchronous script tag for garbage collection (effective only
if preserveScripts is false) ...

True to prepare an asynchronous script tag for garbage collection (effective only
if preserveScripts is false)
Defaults to: `false`


### paths

**Tipo:** Object

The mapping from namespaces to file paths

{
    'Ext': '.', // This is set by default, Ext.layout.container.Containe...

The mapping from namespaces to file paths

{
    'Ext': '.', // This is set by default, Ext.layout.container.Container will be
                // loaded from ./layout/Container.js

    'My': './src/my_own_folder' // My.layout.Container will be loaded from
                                // ./src/my_own_folder/layout/Container.js
}


Note that all relative paths are relative to the current HTML document.
If not being specified, for example, `Other.awesome.Class`
will simply be loaded from `./Other/awesome/Class.js`
Defaults to: `{'Ext': '.'}`


### preserveScripts

**Tipo:** Boolean

False to remove and optionally garbage-collect asynchronously loaded scripts,
True to retain script element for brows...

False to remove and optionally garbage-collect asynchronously loaded scripts,
True to retain script element for browser debugger compatibility and improved load performance.
Defaults to: `true`


### scriptChainDelay

**Tipo:** Boolean

millisecond delay between asynchronous script injection (prevents stack overflow on some user agents)
'false' disable...

millisecond delay between asynchronous script injection (prevents stack overflow on some user agents)
'false' disables delay but potentially increases stack load.
Defaults to: `false`


### scriptCharset

**Tipo:** String

Optional charset to specify encoding of dynamic script content.


### classNameToFilePathMap

**Tipo:** Object


### config

**Tipo:** Object

Configuration


### documentHead

**Tipo:** Object


### hasFileLoadError

**Tipo:** Boolean

...

Defaults to: `false`


### history

**Tipo:** Array

An array of class names to keep track of the dependency loading order. ...

An array of class names to keep track of the dependency loading order.
This is not guaranteed to be the same everytime due to the asynchronous
nature of the Loader.


### isClassFileLoaded

**Tipo:** Object

Maintain the list of files that have already been handled so that they never get double-loaded


### isFileLoaded

**Tipo:** Object


### isInHistory

**Tipo:** Object


### isLoading

**Tipo:** Boolean

Flag indicating whether there are still files being loaded ...

Flag indicating whether there are still files being loaded
Defaults to: `false`


### numLoadedFiles

**Tipo:** Number

...

Defaults to: `0`


### numPendingFiles

**Tipo:** Number

...

Defaults to: `0`


### optionalRequires

**Tipo:** Object

Contains classes referenced in `uses` properties.


### queue

**Tipo:** Object

Maintain the queue for all dependencies. ...

Maintain the queue for all dependencies. Each item in the array is an object of the format:

{
     requires: [...], // The required classes for this queue item
     callback: function() { ... } // The function to execute when all classes specified in requires exist
}


### readyListeners

**Tipo:** Object

Maintain the list of listeners to execute when all required scripts are fully loaded


### requiresMap

**Tipo:** Object

Map of fully qualified class names to an array of dependent classes.


### scriptsLoading

**Tipo:** Number

The number of scripts loading via loadScript. ...

The number of scripts loading via loadScript.
Defaults to: `0`


### syncModeEnabled

**Tipo:** Boolean

...

Defaults to: `false`


### addClassPathMappings

Sets a batch of path entries ...

Sets a batch of path entries
Parameterspaths : Object a set of className: path mappings


### addUsedClasses

Ensure that any classes referenced in the uses property are loaded. ...

Ensure that any classes referenced in the `uses` property are loaded.
Parametersclasses : Object


### cleanupScriptElement

...

Parametersscript : Object


### disableCacheBuster

Turns on or off the "cache buster" applied to dynamically loaded scripts. ...

Turns on or off the "cache buster" applied to dynamically loaded scripts. Normally
dynamically loaded scripts have an extra query parameter appended to avoid stale
cached scripts. This method can be used to disable this mechanism, and is primarily
useful for testing. This is done using a cookie.
Parametersdisable : BooleanTrue to disable the cache buster.


### exclude

Explicitly exclude files from being loaded. ...

Explicitly exclude files from being loaded. Useful when used in conjunction with a broad include expression.
Can be chained with more `require` and `exclude` methods, eg:

Ext.exclude('Ext.data.*').require('*');

Ext.exclude('widget.button*').require('widget.*');


Ext.exclude is alias for exclude.
Parametersexcludes : Array


### getConfig

Get the config value corresponding to the specified name. ...

Get the config value corresponding to the specified name. If no name is given, will return the config object
Parametersname : StringThe config property name


### getPath

Translates a className to a file path by adding the
the proper prefix and converting the .'s to /'s. ...

Translates a className to a file path by adding the
the proper prefix and converting the .'s to /'s. For example:

Ext.Loader.setPath('My', '/path/to/My');

alert(Ext.Loader.getPath('My.awesome.Class')); // alerts '/path/to/My/awesome/Class.js'


Note that the deeper namespace levels, if explicitly set, are always resolved first. For example:

Ext.Loader.setPath({
    'My': '/path/to/lib',
    'My.awesome': '/other/path/for/awesome/stuff',
    'My.awesome.more': '/more/awesome/path'
});

alert(Ext.Loader.getPath('My.awesome.Class')); // alerts '/other/path/for/awesome/stuff/Class.js'

alert(Ext.Loader.getPath('My.awesome.more.Class')); // alerts '/more/awesome/path/Class.js'

alert(Ext.Loader.getPath('My.cool.Class')); // alerts '/path/to/lib/cool/Class.js'

alert(Ext.Loader.getPath('Unknown.strange.Stuff')); // alerts 'Unknown/strange/Stuff.js'

ParametersclassName : String


### getPrefix

...

ParametersclassName : String


### historyPush

...

ParametersclassName : String


### injectScriptElement

Inject a script element to document's head, call onLoad and onError accordingly ...

Inject a script element to document's head, call onLoad and onError accordingly
Parametersurl : Object


### isAClassNameWithAKnownPrefix

...

ParametersclassName : String


### loadScript

Loads the specified script URL and calls the supplied callbacks. ...

Loads the specified script URL and calls the supplied callbacks. If this method
is called before Ext.isReady, the script's load will delay the transition
to ready. This can be used to load arbitrary scripts that may contain further
Ext.require calls.
Parametersoptions : Object/StringThe options object or simply the URL to load.
url : StringThe URL from which to load the script.


### loadScriptFile

Load a script file, supports both asynchronous and synchronous approaches ...

Load a script file, supports both asynchronous and synchronous approaches
Parametersurl : Object


### onFileLoadError

...

ParametersclassName : Object


### onFileLoaded

...

ParametersclassName : String


### onReady

Add a new listener to be executed when all required scripts are fully loaded ...

Add a new listener to be executed when all required scripts are fully loaded
Parametersfn : FunctionThe function callback to be executed


### refreshQueue

Refresh all items in the queue. ...

Refresh all items in the queue. If all dependencies for an item exist during looping,
it will execute the callback and call refreshQueue again. Triggers onReady when the queue is
empty


### removeScriptElement

...

Parametersurl : Object


### require

Loads all classes by the given names and all their direct dependencies; optionally executes
the given callback functi...

Loads all classes by the given names and all their direct dependencies; optionally executes
the given callback function when finishes, within the optional scope.

Ext.require is alias for require.
Parametersexpressions : String/ArrayCan either be a string or an array of string


### setConfig

Set the configuration for the loader. ...

Set the configuration for the loader. This should be called right after ext-(debug).js
is included in the page, and before Ext.onReady. i.e:

<script type="text/javascript" src="ext-core-debug.js"></script>
<script type="text/javascript">
    Ext.Loader.setConfig({
      enabled: true,
      paths: {
          'My': 'my_own_path'
      }
    });
</script>
<script type="text/javascript">
    Ext.require(...);

    Ext.onReady(function() {
      // application code here
    });
</script>


Refer to config options of Ext.Loader for the list of possible properties
Parametersconfig : ObjectThe config object to override the default values


### setPath

Sets the path of a namespace. ...

Sets the path of a namespace.
For Example:

Ext.Loader.setPath('Ext', '.');

Parametersname : String/ObjectSee flexSetter


### syncRequire

Synchronously loads all classes by the given names and all their direct dependencies; optionally
executes the given c...

Synchronously loads all classes by the given names and all their direct dependencies; optionally
executes the given callback function when finishes, within the optional scope.

Ext.syncRequire is alias for syncRequire.
Parametersexpressions : String/ArrayCan either be a string or an array of string


### triggerReady

...


## Properties

### classNameToFilePathMap

**Tipo:** Object


### config

**Tipo:** Object

Configuration


### documentHead

**Tipo:** Object


### hasFileLoadError

**Tipo:** Boolean

...

Defaults to: `false`


### history

**Tipo:** Array

An array of class names to keep track of the dependency loading order. ...

An array of class names to keep track of the dependency loading order.
This is not guaranteed to be the same everytime due to the asynchronous
nature of the Loader.


### isClassFileLoaded

**Tipo:** Object

Maintain the list of files that have already been handled so that they never get double-loaded


### isFileLoaded

**Tipo:** Object


### isInHistory

**Tipo:** Object


### isLoading

**Tipo:** Boolean

Flag indicating whether there are still files being loaded ...

Flag indicating whether there are still files being loaded
Defaults to: `false`


### numLoadedFiles

**Tipo:** Number

...

Defaults to: `0`


### numPendingFiles

**Tipo:** Number

...

Defaults to: `0`


### optionalRequires

**Tipo:** Object

Contains classes referenced in `uses` properties.


### queue

**Tipo:** Object

Maintain the queue for all dependencies. ...

Maintain the queue for all dependencies. Each item in the array is an object of the format:

{
     requires: [...], // The required classes for this queue item
     callback: function() { ... } // The function to execute when all classes specified in requires exist
}


### readyListeners

**Tipo:** Object

Maintain the list of listeners to execute when all required scripts are fully loaded


### requiresMap

**Tipo:** Object

Map of fully qualified class names to an array of dependent classes.


### scriptsLoading

**Tipo:** Number

The number of scripts loading via loadScript. ...

The number of scripts loading via loadScript.
Defaults to: `0`


### syncModeEnabled

**Tipo:** Boolean

...

Defaults to: `false`


### addClassPathMappings

Sets a batch of path entries ...

Sets a batch of path entries
Parameterspaths : Object a set of className: path mappings


### addUsedClasses

Ensure that any classes referenced in the uses property are loaded. ...

Ensure that any classes referenced in the `uses` property are loaded.
Parametersclasses : Object


### cleanupScriptElement

...

Parametersscript : Object


### disableCacheBuster

Turns on or off the "cache buster" applied to dynamically loaded scripts. ...

Turns on or off the "cache buster" applied to dynamically loaded scripts. Normally
dynamically loaded scripts have an extra query parameter appended to avoid stale
cached scripts. This method can be used to disable this mechanism, and is primarily
useful for testing. This is done using a cookie.
Parametersdisable : BooleanTrue to disable the cache buster.


### exclude

Explicitly exclude files from being loaded. ...

Explicitly exclude files from being loaded. Useful when used in conjunction with a broad include expression.
Can be chained with more `require` and `exclude` methods, eg:

Ext.exclude('Ext.data.*').require('*');

Ext.exclude('widget.button*').require('widget.*');


Ext.exclude is alias for exclude.
Parametersexcludes : Array


### getConfig

Get the config value corresponding to the specified name. ...

Get the config value corresponding to the specified name. If no name is given, will return the config object
Parametersname : StringThe config property name


### getPath

Translates a className to a file path by adding the
the proper prefix and converting the .'s to /'s. ...

Translates a className to a file path by adding the
the proper prefix and converting the .'s to /'s. For example:

Ext.Loader.setPath('My', '/path/to/My');

alert(Ext.Loader.getPath('My.awesome.Class')); // alerts '/path/to/My/awesome/Class.js'


Note that the deeper namespace levels, if explicitly set, are always resolved first. For example:

Ext.Loader.setPath({
    'My': '/path/to/lib',
    'My.awesome': '/other/path/for/awesome/stuff',
    'My.awesome.more': '/more/awesome/path'
});

alert(Ext.Loader.getPath('My.awesome.Class')); // alerts '/other/path/for/awesome/stuff/Class.js'

alert(Ext.Loader.getPath('My.awesome.more.Class')); // alerts '/more/awesome/path/Class.js'

alert(Ext.Loader.getPath('My.cool.Class')); // alerts '/path/to/lib/cool/Class.js'

alert(Ext.Loader.getPath('Unknown.strange.Stuff')); // alerts 'Unknown/strange/Stuff.js'

ParametersclassName : String


### getPrefix

...

ParametersclassName : String


### historyPush

...

ParametersclassName : String


### injectScriptElement

Inject a script element to document's head, call onLoad and onError accordingly ...

Inject a script element to document's head, call onLoad and onError accordingly
Parametersurl : Object


### isAClassNameWithAKnownPrefix

...

ParametersclassName : String


### loadScript

Loads the specified script URL and calls the supplied callbacks. ...

Loads the specified script URL and calls the supplied callbacks. If this method
is called before Ext.isReady, the script's load will delay the transition
to ready. This can be used to load arbitrary scripts that may contain further
Ext.require calls.
Parametersoptions : Object/StringThe options object or simply the URL to load.
url : StringThe URL from which to load the script.


### loadScriptFile

Load a script file, supports both asynchronous and synchronous approaches ...

Load a script file, supports both asynchronous and synchronous approaches
Parametersurl : Object


### onFileLoadError

...

ParametersclassName : Object


### onFileLoaded

...

ParametersclassName : String


### onReady

Add a new listener to be executed when all required scripts are fully loaded ...

Add a new listener to be executed when all required scripts are fully loaded
Parametersfn : FunctionThe function callback to be executed


### refreshQueue

Refresh all items in the queue. ...

Refresh all items in the queue. If all dependencies for an item exist during looping,
it will execute the callback and call refreshQueue again. Triggers onReady when the queue is
empty


### removeScriptElement

...

Parametersurl : Object


### require

Loads all classes by the given names and all their direct dependencies; optionally executes
the given callback functi...

Loads all classes by the given names and all their direct dependencies; optionally executes
the given callback function when finishes, within the optional scope.

Ext.require is alias for require.
Parametersexpressions : String/ArrayCan either be a string or an array of string


### setConfig

Set the configuration for the loader. ...

Set the configuration for the loader. This should be called right after ext-(debug).js
is included in the page, and before Ext.onReady. i.e:

<script type="text/javascript" src="ext-core-debug.js"></script>
<script type="text/javascript">
    Ext.Loader.setConfig({
      enabled: true,
      paths: {
          'My': 'my_own_path'
      }
    });
</script>
<script type="text/javascript">
    Ext.require(...);

    Ext.onReady(function() {
      // application code here
    });
</script>


Refer to config options of Ext.Loader for the list of possible properties
Parametersconfig : ObjectThe config object to override the default values


### setPath

Sets the path of a namespace. ...

Sets the path of a namespace.
For Example:

Ext.Loader.setPath('Ext', '.');

Parametersname : String/ObjectSee flexSetter


### syncRequire

Synchronously loads all classes by the given names and all their direct dependencies; optionally
executes the given c...

Synchronously loads all classes by the given names and all their direct dependencies; optionally
executes the given callback function when finishes, within the optional scope.

Ext.syncRequire is alias for syncRequire.
Parametersexpressions : String/ArrayCan either be a string or an array of string


### triggerReady

...


## Methods

### addClassPathMappings

Sets a batch of path entries ...

Sets a batch of path entries
Parameterspaths : Object a set of className: path mappings


### addUsedClasses

Ensure that any classes referenced in the uses property are loaded. ...

Ensure that any classes referenced in the `uses` property are loaded.
Parametersclasses : Object


### cleanupScriptElement

...

Parametersscript : Object


### disableCacheBuster

Turns on or off the "cache buster" applied to dynamically loaded scripts. ...

Turns on or off the "cache buster" applied to dynamically loaded scripts. Normally
dynamically loaded scripts have an extra query parameter appended to avoid stale
cached scripts. This method can be used to disable this mechanism, and is primarily
useful for testing. This is done using a cookie.
Parametersdisable : BooleanTrue to disable the cache buster.


### exclude

Explicitly exclude files from being loaded. ...

Explicitly exclude files from being loaded. Useful when used in conjunction with a broad include expression.
Can be chained with more `require` and `exclude` methods, eg:

Ext.exclude('Ext.data.*').require('*');

Ext.exclude('widget.button*').require('widget.*');


Ext.exclude is alias for exclude.
Parametersexcludes : Array


### getConfig

Get the config value corresponding to the specified name. ...

Get the config value corresponding to the specified name. If no name is given, will return the config object
Parametersname : StringThe config property name


### getPath

Translates a className to a file path by adding the
the proper prefix and converting the .'s to /'s. ...

Translates a className to a file path by adding the
the proper prefix and converting the .'s to /'s. For example:

Ext.Loader.setPath('My', '/path/to/My');

alert(Ext.Loader.getPath('My.awesome.Class')); // alerts '/path/to/My/awesome/Class.js'


Note that the deeper namespace levels, if explicitly set, are always resolved first. For example:

Ext.Loader.setPath({
    'My': '/path/to/lib',
    'My.awesome': '/other/path/for/awesome/stuff',
    'My.awesome.more': '/more/awesome/path'
});

alert(Ext.Loader.getPath('My.awesome.Class')); // alerts '/other/path/for/awesome/stuff/Class.js'

alert(Ext.Loader.getPath('My.awesome.more.Class')); // alerts '/more/awesome/path/Class.js'

alert(Ext.Loader.getPath('My.cool.Class')); // alerts '/path/to/lib/cool/Class.js'

alert(Ext.Loader.getPath('Unknown.strange.Stuff')); // alerts 'Unknown/strange/Stuff.js'

ParametersclassName : String


### getPrefix

...

ParametersclassName : String


### historyPush

...

ParametersclassName : String


### injectScriptElement

Inject a script element to document's head, call onLoad and onError accordingly ...

Inject a script element to document's head, call onLoad and onError accordingly
Parametersurl : Object


### isAClassNameWithAKnownPrefix

...

ParametersclassName : String


### loadScript

Loads the specified script URL and calls the supplied callbacks. ...

Loads the specified script URL and calls the supplied callbacks. If this method
is called before Ext.isReady, the script's load will delay the transition
to ready. This can be used to load arbitrary scripts that may contain further
Ext.require calls.
Parametersoptions : Object/StringThe options object or simply the URL to load.
url : StringThe URL from which to load the script.


### loadScriptFile

Load a script file, supports both asynchronous and synchronous approaches ...

Load a script file, supports both asynchronous and synchronous approaches
Parametersurl : Object


### onFileLoadError

...

ParametersclassName : Object


### onFileLoaded

...

ParametersclassName : String


### onReady

Add a new listener to be executed when all required scripts are fully loaded ...

Add a new listener to be executed when all required scripts are fully loaded
Parametersfn : FunctionThe function callback to be executed


### refreshQueue

Refresh all items in the queue. ...

Refresh all items in the queue. If all dependencies for an item exist during looping,
it will execute the callback and call refreshQueue again. Triggers onReady when the queue is
empty


### removeScriptElement

...

Parametersurl : Object


### require

Loads all classes by the given names and all their direct dependencies; optionally executes
the given callback functi...

Loads all classes by the given names and all their direct dependencies; optionally executes
the given callback function when finishes, within the optional scope.

Ext.require is alias for require.
Parametersexpressions : String/ArrayCan either be a string or an array of string


### setConfig

Set the configuration for the loader. ...

Set the configuration for the loader. This should be called right after ext-(debug).js
is included in the page, and before Ext.onReady. i.e:

<script type="text/javascript" src="ext-core-debug.js"></script>
<script type="text/javascript">
    Ext.Loader.setConfig({
      enabled: true,
      paths: {
          'My': 'my_own_path'
      }
    });
</script>
<script type="text/javascript">
    Ext.require(...);

    Ext.onReady(function() {
      // application code here
    });
</script>


Refer to config options of Ext.Loader for the list of possible properties
Parametersconfig : ObjectThe config object to override the default values


### setPath

Sets the path of a namespace. ...

Sets the path of a namespace.
For Example:

Ext.Loader.setPath('Ext', '.');

Parametersname : String/ObjectSee flexSetter


### syncRequire

Synchronously loads all classes by the given names and all their direct dependencies; optionally
executes the given c...

Synchronously loads all classes by the given names and all their direct dependencies; optionally
executes the given callback function when finishes, within the optional scope.

Ext.syncRequire is alias for syncRequire.
Parametersexpressions : String/ArrayCan either be a string or an array of string


### triggerReady

...


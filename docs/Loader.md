# Ext.Loader

## Description

Ext.Loader is the heart of the new dynamic dependency loading capability in Ext JS 4+. It is most commonly used via the Ext.require shorthand. Ext.Loader supports both asynchronous and synchronous loading approaches, and leverage their advantages for the best development flow. We'll discuss about the pros and cons of each approach:

Advantages:

Disadvantages:

// Syntax Ext.require({String/Array} expressions); // Example: Single alias Ext.require('widget.window'); // Example: Single class name Ext.require('Ext.window.Window'); // Example: Multiple aliases / class names mix Ext.require(['widget.window', 'layout.border', 'Ext.data.Connection']); // Wildcards Ext.require(['widget.*', 'layout.*', 'Ext.data.*']); Method 2: Explicitly exclude what you don't need: Synchronous Loading on Demand Advantages:

Disadvantages:

There's one simple rule to follow: Instantiate everything with Ext.create instead of the `new` keyword

Ext.create('widget.window', { ... }); // Instead of new Ext.window.Window({...}); Ext.create('Ext.window.Window', {}); // Same as above, using full class name instead of alias Ext.widget('window', {}); // Same as above, all you need is the traditional `xtype` Behind the scene, Ext.ClassManager will automatically check whether the given class name / alias has already existed on the page. If it's not, Ext.Loader will immediately switch itself to synchronous mode and automatic load the given class and all its dependencies.

It has all the advantages combined from asynchronous and synchronous loading. The development flow is simple:

Ext.Loader will automatically fetch all dependencies on demand as they're needed during run-time. For example:

Ext.onReady(function(){ var window = Ext.widget('window', { width: 500, height: 300, layout: { type: 'border', padding: 5 }, title: 'Hello Dialog', items: [{ title: 'Navigation', collapsible: true, region: 'west', width: 200, html: 'Hello', split: true }, { title: 'TabPanel', region: 'center' }] }); window.show(); }) Step 2: Along the way, when you need better debugging ability, watch the console for warnings like these: Simply copy and paste the suggested code above `Ext.onReady`, i.e:

Ext.require('Ext.window.Window'); Ext.require('Ext.layout.container.Border'); Ext.onReady(...); Everything should now load via asynchronous mode.

It's important to note that dynamic loading should only be used during development on your local machines. During production, all dependencies should be combined into one single JavaScript file. Ext.Loader makes the whole process of transitioning from / to between development / maintenance and production as easy as possible. Internally Ext.Loader.history maintains the list of all dependencies your application needs in the exact loading sequence. It's as simple as concatenating all files in this array into one, then include it on top of your application.

This process will be automated with Sencha Command, to be released and documented towards Ext JS 4 Final.

## Config options

### disableCaching

**Type:** Boolean

Appends current timestamp to script files to prevent caching. ...

Appends current timestamp to script files to prevent caching. Defaults to: `true`


### disableCachingParam

**Type:** String

The get parameter name for the cache buster's timestamp. ...

The get parameter name for the cache buster's timestamp. Defaults to: `'_dc'`


### enabled

**Type:** Boolean

Whether or not to enable the dynamic dependency loading feature. ...

Whether or not to enable the dynamic dependency loading feature. Defaults to: `false`


### garbageCollect

**Type:** Boolean

True to prepare an asynchronous script tag for garbage collection (effective only if preserveScripts is false) ...

True to prepare an asynchronous script tag for garbage collection (effective only if preserveScripts is false) Defaults to: `false`


### paths

**Type:** Object

The mapping from namespaces to file paths { 'Ext': '.', // This is set by default, Ext.layout.container.Containe...

The mapping from namespaces to file paths Note that all relative paths are relative to the current HTML document. If not being specified, for example, `Other.awesome.Class` will simply be loaded from `./Other/awesome/Class.js` Defaults to: `{'Ext': '.'}`


### preserveScripts

**Type:** Boolean

False to remove and optionally garbage-collect asynchronously loaded scripts, True to retain script element for brows...

False to remove and optionally garbage-collect asynchronously loaded scripts, True to retain script element for browser debugger compatibility and improved load performance. Defaults to: `true`


### scriptChainDelay

**Type:** Boolean

millisecond delay between asynchronous script injection (prevents stack overflow on some user agents) 'false' disable...

millisecond delay between asynchronous script injection (prevents stack overflow on some user agents) 'false' disables delay but potentially increases stack load. Defaults to: `false`


### scriptCharset

**Type:** String

Optional charset to specify encoding of dynamic script content.


### classNameToFilePathMap

**Type:** Object


### config

**Type:** Object

Configuration


### documentHead

**Type:** Object


### hasFileLoadError

**Type:** Boolean

...

Defaults to: `false`


### history

**Type:** Array

An array of class names to keep track of the dependency loading order. ...

An array of class names to keep track of the dependency loading order. This is not guaranteed to be the same everytime due to the asynchronous nature of the Loader.


### isClassFileLoaded

**Type:** Object

Maintain the list of files that have already been handled so that they never get double-loaded


### isFileLoaded

**Type:** Object


### isInHistory

**Type:** Object


### isLoading

**Type:** Boolean

Flag indicating whether there are still files being loaded ...

Flag indicating whether there are still files being loaded Defaults to: `false`


### numLoadedFiles

**Type:** Number

...

Defaults to: `0`


### numPendingFiles

**Type:** Number

...

Defaults to: `0`


### optionalRequires

**Type:** Object

Contains classes referenced in `uses` properties.


### queue

**Type:** Object

Maintain the queue for all dependencies. ...

Maintain the queue for all dependencies. Each item in the array is an object of the format:


### readyListeners

**Type:** Object

Maintain the list of listeners to execute when all required scripts are fully loaded


### requiresMap

**Type:** Object

Map of fully qualified class names to an array of dependent classes.


### scriptsLoading

**Type:** Number

The number of scripts loading via loadScript. ...

The number of scripts loading via loadScript. Defaults to: `0`


### syncModeEnabled

**Type:** Boolean

...

Defaults to: `false`


### addClassPathMappings

Sets a batch of path entries ...

Sets a batch of path entries

**Parameters:** paths : Object a set of className: path mappings


### addUsedClasses

Ensure that any classes referenced in the uses property are loaded. ...

Ensure that any classes referenced in the `uses` property are loaded.

**Parameters:** classes : Object


### cleanupScriptElement

...

**Parameters:** script : Object


### disableCacheBuster

Turns on or off the "cache buster" applied to dynamically loaded scripts. ...

Turns on or off the "cache buster" applied to dynamically loaded scripts. Normally dynamically loaded scripts have an extra query parameter appended to avoid stale cached scripts. This method can be used to disable this mechanism, and is primarily useful for testing. This is done using a cookie.

**Parameters:** disable : BooleanTrue to disable the cache buster.


### exclude

Explicitly exclude files from being loaded. ...

Explicitly exclude files from being loaded. Useful when used in conjunction with a broad include expression. Can be chained with more `require` and `exclude` methods, eg: Ext.exclude is alias for exclude.

**Parameters:** excludes : Array


### getConfig

Get the config value corresponding to the specified name. ...

Get the config value corresponding to the specified name. If no name is given, will return the config object

**Parameters:** name : StringThe config property name


### getPath

Translates a className to a file path by adding the the proper prefix and converting the .'s to /'s. ...

Translates a className to a file path by adding the the proper prefix and converting the .'s to /'s. For example: Note that the deeper namespace levels, if explicitly set, are always resolved first. For example:

**Parameters:** className : String


### getPrefix

...

**Parameters:** className : String


### historyPush

...

**Parameters:** className : String


### injectScriptElement

Inject a script element to document's head, call onLoad and onError accordingly ...

Inject a script element to document's head, call onLoad and onError accordingly

**Parameters:** url : Object


### isAClassNameWithAKnownPrefix

...

**Parameters:** className : String


### loadScript

Loads the specified script URL and calls the supplied callbacks. ...

Loads the specified script URL and calls the supplied callbacks. If this method is called before Ext.isReady, the script's load will delay the transition to ready. This can be used to load arbitrary scripts that may contain further Ext.require calls.

**Parameters:** options : Object/StringThe options object or simply the URL to load. url : StringThe URL from which to load the script.


### loadScriptFile

Load a script file, supports both asynchronous and synchronous approaches ...

Load a script file, supports both asynchronous and synchronous approaches

**Parameters:** url : Object


### onFileLoadError

...

**Parameters:** className : Object


### onFileLoaded

...

**Parameters:** className : String


### onReady

Add a new listener to be executed when all required scripts are fully loaded ...

Add a new listener to be executed when all required scripts are fully loaded

**Parameters:** fn : FunctionThe function callback to be executed


### refreshQueue

Refresh all items in the queue. ...

Refresh all items in the queue. If all dependencies for an item exist during looping, it will execute the callback and call refreshQueue again. Triggers onReady when the queue is empty


### removeScriptElement

...

**Parameters:** url : Object


### require

Loads all classes by the given names and all their direct dependencies; optionally executes the given callback functi...

Loads all classes by the given names and all their direct dependencies; optionally executes the given callback function when finishes, within the optional scope. Ext.require is alias for require.

**Parameters:** expressions : String/ArrayCan either be a string or an array of string


### setConfig

Set the configuration for the loader. ...

Set the configuration for the loader. This should be called right after ext-(debug).js is included in the page, and before Ext.onReady. i.e: Refer to config options of Ext.Loader for the list of possible properties

**Parameters:** config : ObjectThe config object to override the default values


### setPath

Sets the path of a namespace. ...

Sets the path of a namespace. For Example:

**Parameters:** name : String/ObjectSee flexSetter


### syncRequire

Synchronously loads all classes by the given names and all their direct dependencies; optionally executes the given c...

Synchronously loads all classes by the given names and all their direct dependencies; optionally executes the given callback function when finishes, within the optional scope. Ext.syncRequire is alias for syncRequire.

**Parameters:** expressions : String/ArrayCan either be a string or an array of string


### triggerReady

...


## Properties

### classNameToFilePathMap

**Type:** Object


### config

**Type:** Object

Configuration


### documentHead

**Type:** Object


### hasFileLoadError

**Type:** Boolean

...

Defaults to: `false`


### history

**Type:** Array

An array of class names to keep track of the dependency loading order. ...

An array of class names to keep track of the dependency loading order. This is not guaranteed to be the same everytime due to the asynchronous nature of the Loader.


### isClassFileLoaded

**Type:** Object

Maintain the list of files that have already been handled so that they never get double-loaded


### isFileLoaded

**Type:** Object


### isInHistory

**Type:** Object


### isLoading

**Type:** Boolean

Flag indicating whether there are still files being loaded ...

Flag indicating whether there are still files being loaded Defaults to: `false`


### numLoadedFiles

**Type:** Number

...

Defaults to: `0`


### numPendingFiles

**Type:** Number

...

Defaults to: `0`


### optionalRequires

**Type:** Object

Contains classes referenced in `uses` properties.


### queue

**Type:** Object

Maintain the queue for all dependencies. ...

Maintain the queue for all dependencies. Each item in the array is an object of the format:


### readyListeners

**Type:** Object

Maintain the list of listeners to execute when all required scripts are fully loaded


### requiresMap

**Type:** Object

Map of fully qualified class names to an array of dependent classes.


### scriptsLoading

**Type:** Number

The number of scripts loading via loadScript. ...

The number of scripts loading via loadScript. Defaults to: `0`


### syncModeEnabled

**Type:** Boolean

...

Defaults to: `false`


### addClassPathMappings

Sets a batch of path entries ...

Sets a batch of path entries

**Parameters:** paths : Object a set of className: path mappings


### addUsedClasses

Ensure that any classes referenced in the uses property are loaded. ...

Ensure that any classes referenced in the `uses` property are loaded.

**Parameters:** classes : Object


### cleanupScriptElement

...

**Parameters:** script : Object


### disableCacheBuster

Turns on or off the "cache buster" applied to dynamically loaded scripts. ...

Turns on or off the "cache buster" applied to dynamically loaded scripts. Normally dynamically loaded scripts have an extra query parameter appended to avoid stale cached scripts. This method can be used to disable this mechanism, and is primarily useful for testing. This is done using a cookie.

**Parameters:** disable : BooleanTrue to disable the cache buster.


### exclude

Explicitly exclude files from being loaded. ...

Explicitly exclude files from being loaded. Useful when used in conjunction with a broad include expression. Can be chained with more `require` and `exclude` methods, eg: Ext.exclude is alias for exclude.

**Parameters:** excludes : Array


### getConfig

Get the config value corresponding to the specified name. ...

Get the config value corresponding to the specified name. If no name is given, will return the config object

**Parameters:** name : StringThe config property name


### getPath

Translates a className to a file path by adding the the proper prefix and converting the .'s to /'s. ...

Translates a className to a file path by adding the the proper prefix and converting the .'s to /'s. For example: Note that the deeper namespace levels, if explicitly set, are always resolved first. For example:

**Parameters:** className : String


### getPrefix

...

**Parameters:** className : String


### historyPush

...

**Parameters:** className : String


### injectScriptElement

Inject a script element to document's head, call onLoad and onError accordingly ...

Inject a script element to document's head, call onLoad and onError accordingly

**Parameters:** url : Object


### isAClassNameWithAKnownPrefix

...

**Parameters:** className : String


### loadScript

Loads the specified script URL and calls the supplied callbacks. ...

Loads the specified script URL and calls the supplied callbacks. If this method is called before Ext.isReady, the script's load will delay the transition to ready. This can be used to load arbitrary scripts that may contain further Ext.require calls.

**Parameters:** options : Object/StringThe options object or simply the URL to load. url : StringThe URL from which to load the script.


### loadScriptFile

Load a script file, supports both asynchronous and synchronous approaches ...

Load a script file, supports both asynchronous and synchronous approaches

**Parameters:** url : Object


### onFileLoadError

...

**Parameters:** className : Object


### onFileLoaded

...

**Parameters:** className : String


### onReady

Add a new listener to be executed when all required scripts are fully loaded ...

Add a new listener to be executed when all required scripts are fully loaded

**Parameters:** fn : FunctionThe function callback to be executed


### refreshQueue

Refresh all items in the queue. ...

Refresh all items in the queue. If all dependencies for an item exist during looping, it will execute the callback and call refreshQueue again. Triggers onReady when the queue is empty


### removeScriptElement

...

**Parameters:** url : Object


### require

Loads all classes by the given names and all their direct dependencies; optionally executes the given callback functi...

Loads all classes by the given names and all their direct dependencies; optionally executes the given callback function when finishes, within the optional scope. Ext.require is alias for require.

**Parameters:** expressions : String/ArrayCan either be a string or an array of string


### setConfig

Set the configuration for the loader. ...

Set the configuration for the loader. This should be called right after ext-(debug).js is included in the page, and before Ext.onReady. i.e: Refer to config options of Ext.Loader for the list of possible properties

**Parameters:** config : ObjectThe config object to override the default values


### setPath

Sets the path of a namespace. ...

Sets the path of a namespace. For Example:

**Parameters:** name : String/ObjectSee flexSetter


### syncRequire

Synchronously loads all classes by the given names and all their direct dependencies; optionally executes the given c...

Synchronously loads all classes by the given names and all their direct dependencies; optionally executes the given callback function when finishes, within the optional scope. Ext.syncRequire is alias for syncRequire.

**Parameters:** expressions : String/ArrayCan either be a string or an array of string


### triggerReady

...


## Methods

### addClassPathMappings

Sets a batch of path entries ...

Sets a batch of path entries

**Parameters:** paths : Object a set of className: path mappings


### addUsedClasses

Ensure that any classes referenced in the uses property are loaded. ...

Ensure that any classes referenced in the `uses` property are loaded.

**Parameters:** classes : Object


### cleanupScriptElement

...

**Parameters:** script : Object


### disableCacheBuster

Turns on or off the "cache buster" applied to dynamically loaded scripts. ...

Turns on or off the "cache buster" applied to dynamically loaded scripts. Normally dynamically loaded scripts have an extra query parameter appended to avoid stale cached scripts. This method can be used to disable this mechanism, and is primarily useful for testing. This is done using a cookie.

**Parameters:** disable : BooleanTrue to disable the cache buster.


### exclude

Explicitly exclude files from being loaded. ...

Explicitly exclude files from being loaded. Useful when used in conjunction with a broad include expression. Can be chained with more `require` and `exclude` methods, eg: Ext.exclude is alias for exclude.

**Parameters:** excludes : Array


### getConfig

Get the config value corresponding to the specified name. ...

Get the config value corresponding to the specified name. If no name is given, will return the config object

**Parameters:** name : StringThe config property name


### getPath

Translates a className to a file path by adding the the proper prefix and converting the .'s to /'s. ...

Translates a className to a file path by adding the the proper prefix and converting the .'s to /'s. For example: Note that the deeper namespace levels, if explicitly set, are always resolved first. For example:

**Parameters:** className : String


### getPrefix

...

**Parameters:** className : String


### historyPush

...

**Parameters:** className : String


### injectScriptElement

Inject a script element to document's head, call onLoad and onError accordingly ...

Inject a script element to document's head, call onLoad and onError accordingly

**Parameters:** url : Object


### isAClassNameWithAKnownPrefix

...

**Parameters:** className : String


### loadScript

Loads the specified script URL and calls the supplied callbacks. ...

Loads the specified script URL and calls the supplied callbacks. If this method is called before Ext.isReady, the script's load will delay the transition to ready. This can be used to load arbitrary scripts that may contain further Ext.require calls.

**Parameters:** options : Object/StringThe options object or simply the URL to load. url : StringThe URL from which to load the script.


### loadScriptFile

Load a script file, supports both asynchronous and synchronous approaches ...

Load a script file, supports both asynchronous and synchronous approaches

**Parameters:** url : Object


### onFileLoadError

...

**Parameters:** className : Object


### onFileLoaded

...

**Parameters:** className : String


### onReady

Add a new listener to be executed when all required scripts are fully loaded ...

Add a new listener to be executed when all required scripts are fully loaded

**Parameters:** fn : FunctionThe function callback to be executed


### refreshQueue

Refresh all items in the queue. ...

Refresh all items in the queue. If all dependencies for an item exist during looping, it will execute the callback and call refreshQueue again. Triggers onReady when the queue is empty


### removeScriptElement

...

**Parameters:** url : Object


### require

Loads all classes by the given names and all their direct dependencies; optionally executes the given callback functi...

Loads all classes by the given names and all their direct dependencies; optionally executes the given callback function when finishes, within the optional scope. Ext.require is alias for require.

**Parameters:** expressions : String/ArrayCan either be a string or an array of string


### setConfig

Set the configuration for the loader. ...

Set the configuration for the loader. This should be called right after ext-(debug).js is included in the page, and before Ext.onReady. i.e: Refer to config options of Ext.Loader for the list of possible properties

**Parameters:** config : ObjectThe config object to override the default values


### setPath

Sets the path of a namespace. ...

Sets the path of a namespace. For Example:

**Parameters:** name : String/ObjectSee flexSetter


### syncRequire

Synchronously loads all classes by the given names and all their direct dependencies; optionally executes the given c...

Synchronously loads all classes by the given names and all their direct dependencies; optionally executes the given callback function when finishes, within the optional scope. Ext.syncRequire is alias for syncRequire.

**Parameters:** expressions : String/ArrayCan either be a string or an array of string


### triggerReady

...


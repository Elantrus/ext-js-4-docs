# Ext.Ajax

**Extends:** Ext.data.Connection

## Description

A singleton instance of an Ext.data.Connection. This class is used to communicate with your server side code. It can be used as follows:

Ext.Ajax.request({ url: 'page.php', params: { id: 1 }, success: function(response){ var text = response.responseText; // process server response here } }); Default options for all requests can be set by changing a property on the Ext.Ajax class:

Ext.Ajax.timeout = 60000; // 60 seconds Any options specified in the request method for the Ajax request will override any defaults set on the Ext.Ajax class. In the code sample below, the timeout for the request will be 60 seconds.

Ext.Ajax.timeout = 120000; // 120 seconds Ext.Ajax.request({ url: 'page.aspx', timeout: 60000 }); In general, this class will be used for all Ajax requests in your application. The main reason for creating a separate Ext.data.Connection is for a series of requests that share common settings that are different to all other requests in the application.

## Config options

### binary

**Type:** Boolean

True if the response should be treated as binary data. ...

True if the response should be treated as binary data. If true, the binary data will be accessible as a "responseBytes" property on the response object. Defaults to: `false`


### cors

**Type:** Boolean

True to enable CORS support on the XHR object. ...

True to enable CORS support on the XHR object. Currently the only effect of this option is to use the XDomainRequest object instead of XMLHttpRequest if the browser is IE8 or above. Defaults to: `false`


### disableCachingParam

**Type:** String

Change the parameter which is sent went disabling caching through a cache buster. ...

Change the parameter which is sent went disabling caching through a cache buster. Defaults to: `'_dc'`


### listeners

**Type:** Object

A config object containing one or more event handlers to be added to this object during initialization. ...

A config object containing one or more event handlers to be added to this object during initialization. This should be a valid listeners config object as specified in the addListener example for attaching multiple handlers at once. **DOM events from Ext JS Components** While *some* Ext JS Component classes export selected DOM events (e.g. "click", "mouseover" etc), this is usually only done when extra value can be added. For example the DataView's **`itemclick`** event passing the node clicked on. To access DOM events directly from a child element of a Component, we need to specify the `element` option to identify the Component property to add a DOM listener to:


### withCredentials

**Type:** Boolean

True to set withCredentials = true on the XHR object ...

True to set `withCredentials = true` on the XHR object Defaults to: `false`


### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### async

**Type:** Boolean

...

Defaults to: `true`


### autoAbort

**Type:** Boolean

Whether a new request should abort any pending requests. ...

Whether a new request should abort any pending requests. Defaults to: `false`


### configMap

**Type:** Object

...

Defaults to: `{}`


### defaultHeaders

**Type:** Object

An object containing request headers which are added to each request made by this object.


### defaultPostHeader

**Type:** String

...

Defaults to: `'application/x-www-form-urlencoded; charset=UTF-8'`


### defaultXdrContentType

**Type:** String

...

Defaults to: `'text/plain'`


### defaultXhrHeader

**Type:** String

...

Defaults to: `'XMLHttpRequest'`


### disableCaching

**Type:** Boolean

True to add a unique cache-buster param to GET requests. ...

True to add a unique cache-buster param to GET requests. Defaults to true.


### eventsSuspended

**Type:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called. Defaults to: `0`


### extraParams

**Type:** Object

An object containing properties which are used as extra parameters to each request made by this object. ...

An object containing properties which are used as extra parameters to each request made by this object. Session information and other data that you need to pass with each request are commonly put here.


### getXhrInstance

**Type:** Object

Creates the appropriate XHR transport for this browser.


### hasListeners

**Type:** Object

This object holds a key for any event that has a listener. ...

This object holds a key for any event that has a listener. The listener may be set directly on the instance, or on its class or a super class (via observe) or on the MVC EventBus. The values of this object are truthy (a non-zero number) and falsy (0 or undefined). They do not represent an exact count of listeners. The value for an event is truthy if the event must be fired and is falsy if there is no need to fire the event. The intended use of this property is to avoid the expense of fireEvent calls when there are no listeners. This can be particularly helpful when one would otherwise have to call fireEvent hundreds or thousands of times. It is used like this:


### initConfigList

**Type:** Array

...

Defaults to: `[]`


### initConfigMap

**Type:** Object

...

Defaults to: `{}`


### isInstance

**Type:** Boolean

...

Defaults to: `true`


### isObservable

**Type:** Boolean

true in this class to identify an object as an instantiated Observable, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Observable, or subclass thereof. Defaults to: `true`


### isXdr

**Type:** Boolean

...

Defaults to: `false`


### method

**Type:** String

The default HTTP method to be used for requests. ...

The default HTTP method to be used for requests. Note that this is case-sensitive and should be all caps (if not set but params are present will use "POST", otherwise will use "GET".) Overrides: Ext.data.Connection.method


### password

**Type:** String

...

Defaults to: `''`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### timeout

**Type:** Number

The timeout in milliseconds to be used for requests. ...

The timeout in milliseconds to be used for requests. Defaults to 30000.


### url

**Type:** String

The default URL to be used for requests to the server. ...

The default URL to be used for requests to the server. If the server receives all requests through one URL, setting this once is easier than entering it on every request. Overrides: Ext.data.Connection.url


### useDefaultXhrHeader

**Type:** Boolean

...

Defaults to: `true`


### username

**Type:** String

...

Defaults to: `''`


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.Ajax

...

**Parameters:** config : Object


### abort

Aborts an active request. ...

Aborts an active request.

**Parameters:** request : Object (optional)Defaults to the last request


### abortAll

Aborts all active requests ...

Aborts all active requests


### addEvents

Adds the specified events to the list of events which this Observable may fire. ...

Adds the specified events to the list of events which this Observable may fire.

**Parameters:** eventNames : Object/String...Either an object with event names as properties with a value of `true`. For example: Or any number of event names as separate parameters. For example:


### addListener

Appends an event handler to this object. ...

Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### addManagedListener

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destr...

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### callOverridden

Call the original method that was previously overridden with override Ext.define('My.Cat', { constructor: functi...

Call the original method that was previously overridden with override This method has been **deprecated** as of 4.1. Use callParent instead.


### callParent

Call the "parent" method of the current method. ...

Call the "parent" method of the current method. That is the method previously overridden by derivation or by an override (see Ext.define). This can be used with an override as follows: This also works with static methods. Lastly, it also works with overridden static methods. To override a method and replace it and also call the superclass method, use callSuper. This is often done to patch a method to fix a bug.

**Parameters:** args : Array/ArgumentsThe arguments, either an array or the `arguments` object from the current method, for example: `this.callParent(arguments)`


### callSuper

This method is used by an override to call the superclass method but bypass any overridden method. ...

This method is used by an override to call the superclass method but bypass any overridden method. This is often done to "patch" a method that contains a bug but for whatever reason cannot be fixed directly. Consider: To patch the bug in `DerivedClass.method`, the typical solution is to create an override: The patch method cannot use `callParent` to call the superclass `method` since that would call the overridden method containing the bug. In other words, the above patch would only produce "Fixed" then "Good" in the console log, whereas, using `callParent` would produce "Fixed" then "Bad" then "Good".

**Parameters:** args : Array/ArgumentsThe arguments, either an array or the `arguments` object from the current method, for example: `this.callSuper(arguments)`


### captureArgs

...

**Parameters:** o : Object


### cleanup

Cleans up any left over information from the request ...

Cleans up any left over information from the request

**Parameters:** request : ObjectThe request


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### clearTimeout

Clears the timeout on the request ...

Clears the timeout on the request

**Parameters:** request : ObjectThe request


### configClass

...


### continueFireEvent

Continue to fire event. ...

Continue to fire event.

**Parameters:** eventName : String


### createException

Creates the exception object ...

Creates the exception object

**Parameters:** request : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### createResponse

Creates the response object ...

Creates the response object

**Parameters:** request : Object


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if present. There is no implementation in the Observable base class. This is commonly used by Ext.Components to bubble events to owner Containers. See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the Component's immediate owner. But if a known target is required, this can be overridden to access the required target more quickly. Example:

**Parameters:** eventNames : String/String[]The event name to bubble, or an Array of event names.


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed to addListener). An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list. An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getByteArray

Gets binary data from the xhr response object and returns it as a byte array ...

Gets binary data from the xhr response object and returns it as a byte array

**Parameters:** xhr : Objectthe xhr response object


### getConfig

...

**Parameters:** name : Object


### getForm

Gets the form object from options. ...

Gets the form object from options.

**Parameters:** options : ObjectThe request options


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getLatest

Gets the most recent request ...

Gets the most recent request

**Returns:** ObjectThe request. Null if there is no recent request


### getXdrInstance

Creates the appropriate XDR transport for this browser. ...

Creates the appropriate XDR transport for this browser. - IE 7 and below don't support CORS - IE 8 and 9 support CORS with native XDomainRequest object - IE 10 (and above?) supports CORS with native XMLHttpRequest object


### hasConfig

...

**Parameters:** config : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer indicates whether the event needs firing or not.

**Parameters:** eventName : StringThe name of the event to check for


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### injectVBScript

Injects a vbscript tag containing a 'getIEByteArray' method for reading binary data from an xhr response in IE8 and b...

Injects a vbscript tag containing a 'getIEByteArray' method for reading binary data from an xhr response in IE8 and below.


### isFormUpload

Detects whether the form is intended to be used for an upload. ...

Detects whether the form is intended to be used for an upload.

**Parameters:** options : Object


### isLoading

Determines whether this object has a request outstanding. ...

Determines whether this object has a request outstanding.

**Parameters:** request : Object (optional)Defaults to the last transaction


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener. Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener. Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### nativeBinaryPostSupport

...

**Returns:** booleantrue if the browser can natively post binary data.


### newRequest

Creates the appropriate XHR transport for a given request on this browser. ...

Creates the appropriate XHR transport for a given request on this browser. On IE this may be an `XDomainRequest` rather than an `XMLHttpRequest`.

**Parameters:** options : Object


### on

Shorthand for addListener. ...

Shorthand for addListener. Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### onComplete

To be called when the request has come back from the server ...

To be called when the request has come back from the server

**Parameters:** request : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onStateChange

Fires when the state of the xhr changes ...

Fires when the state of the xhr changes

**Parameters:** request : ObjectThe request


### onUploadComplete

Callback handler for the upload function. ...

Callback handler for the upload function. After we've submitted the form via the iframe this creates a bogus response object to simulate an XHR and populates its responseText from the now-loaded iframe's document body (or a textarea inside the body). We then clean up by removing the iframe

**Parameters:** frame : Object


### openRequest

Creates and opens an appropriate XHR transport for a given request on this browser. ...

Creates and opens an appropriate XHR transport for a given request on this browser. This logic is contained in an individual method to allow for overrides to process all of the parameters and options and return a suitable, open connection.

**Parameters:** options : Object


### parseStatus

Checks if the response status was successful ...

Checks if the response status was successful

**Parameters:** status : NumberThe status code


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a class derives from this class or uses this class as a mixin.

**Parameters:** T : FunctionThe class constructor to prepare.


### processXdrRequest

...

**Parameters:** request : Object


### processXdrResponse

...

**Parameters:** response : Object


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`. For example if you are extending Grid, you might decide to forward some events from store. So you can do this inside your initComponent: The grid instance will then have an observable 'load' event which will be passed the parameters of the store's load event and any function fired with the grid's load event would have access to the grid using the `this` keyword.

**Parameters:** origin : ObjectThe Observable whose events this object is to relay.


### removeListener

Removes an event handler. ...

Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### removeManagedListener

Removes listeners that were added by the mon method. ...

Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### removeManagedListenerItem

Remove a single managed listener item ...

Remove a single managed listener item

**Parameters:** isClear : BooleanTrue if this is being called during a clear


### request

Sends an HTTP request to a remote server. ...

Sends an HTTP request to a remote server. **Important:** Ajax server requests are asynchronous, and this call will return before the response has been received. Process any returned data in a callback function. To execute a callback function in the correct scope, use the `scope` option.

**Parameters:** options : ObjectAn object which may contain the following properties: (The options object may also contain any other property which might be needed to perform postprocessing in a callback because it is passed to callback functions.) url : String/FunctionThe URL to which to send the request, or a function to call which returns a URL string. The scope of the function is specified by the `scope` option. Defaults to the configured `url`.


### resumeEvent

Resumes firing of the named event(s). ...

Resumes firing of the named event(s). After calling this method to resume events, the events will fire when requested to fire. Note that if the suspendEvent method is called multiple times for a certain event, this converse method will have to be called the same number of times for it to resume firing.

**Parameters:** eventName : String...Multiple event names to resume.


### resumeEvents

Resumes firing events (see suspendEvents). ...

Resumes firing events (see suspendEvents). If events were suspended using the `queueSuspended` parameter, then all events fired during event suspension will be sent to any listeners now.


### setConfig

...

**Parameters:** config : Object


### setOptions

Sets various options such as the url, params for the request ...

Sets various options such as the url, params for the request

**Parameters:** options : ObjectThe initial options


### setupHeaders

Setup all the headers for the request ...

Setup all the headers for the request

**Parameters:** xhr : ObjectThe xhr object


### setupMethod

Template method for overriding method ...

Template method for overriding method This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### setupParams

Template method for overriding params ...

Template method for overriding params This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### setupUrl

Template method for overriding url ...

Template method for overriding url This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### suspendEvent

Suspends firing of the named event(s). ...

Suspends firing of the named event(s). After calling this method to suspend events, the events will no longer fire when requested to fire. Note that if this is called multiple times for a certain event, the converse method resumeEvent will have to be called the same number of times for it to resume firing.

**Parameters:** eventName : String...Multiple event names to suspend.


### suspendEvents

Suspends the firing of all events. ...

Suspends the firing of all events. (see resumeEvents)

**Parameters:** queueSuspended : BooleanPass as true to queue up suspended events to be fired after the resumeEvents call instead of discarding all suspended events.


### un

Shorthand for removeListener. ...

Shorthand for removeListener. Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### upload

Uploads a form using a hidden iframe. ...

Uploads a form using a hidden iframe.

**Parameters:** form : String/HTMLElement/Ext.ElementThe form to upload


### addConfig

...

**Parameters:** config : Object


### addInheritableStatics

...

**Parameters:** members : Object


### addMember

...

**Parameters:** name : Object


### addMembers

Add methods / properties to the prototype of this class. ...

Add methods / properties to the prototype of this class.

**Parameters:** members : Object


### addStatics

Add / override static properties of this class. ...

Add / override static properties of this class.

**Parameters:** members : Object


### addXtype

...

**Parameters:** xtype : Object


### borrow

Borrow another class' members to the prototype of this class. ...

Borrow another class' members to the prototype of this class.

**Parameters:** fromClass : Ext.BaseThe class to borrow members from


### create

Create a new instance of this Class. ...

Create a new instance of this Class. All parameters are passed to the constructor of the class.

**Returns:** Objectthe created instance.


### createAlias

Create aliases for existing prototype methods. ...

Create aliases for existing prototype methods. Example:

**Parameters:** alias : String/ObjectThe new method name, or an object to set multiple aliases. See flexSetter


### extend

...

**Parameters:** config : Object


### getName

Get the current class' name in string format. ...

Get the current class' name in string format.

**Returns:** StringclassName


### implement

Adds members to class. ...

Adds members to class. This method has been **deprecated** since 4.1 Use addMembers instead.


### mixin

Used internally by the mixins pre-processor ...

Used internally by the mixins pre-processor

**Parameters:** name : Object


### onExtended

...

**Parameters:** fn : Object


### override

Override members of this class. ...

Override members of this class. Overridden methods can be invoked via callParent. As of 4.1, direct use of this method is deprecated. Use Ext.define instead: The above accomplishes the same result but can be managed by the Ext.Loader which can properly order the override and its target class and the build process can determine whether the override is needed based on the required state of the target class (My.Cat). This method has been **deprecated** since 4.1.0 Use Ext.define instead


### triggerExtended

...


### beforerequest

Fires before a network request is made to retrieve a data object. ...

Fires before a network request is made to retrieve a data object.

**Parameters:** conn : Ext.data.ConnectionThis Connection object.


### requestcomplete

Fires if the request was successfully completed. ...

Fires if the request was successfully completed.

**Parameters:** conn : Ext.data.ConnectionThis Connection object.


### requestexception

Fires if an error HTTP status was returned from the server. ...

Fires if an error HTTP status was returned from the server. This event may also be listened to in the event that a request has timed out or has been aborted. See HTTP Status Code Definitions for details of HTTP status codes.

**Parameters:** conn : Ext.data.ConnectionThis Connection object.


## Properties

### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### async

**Type:** Boolean

...

Defaults to: `true`


### autoAbort

**Type:** Boolean

Whether a new request should abort any pending requests. ...

Whether a new request should abort any pending requests. Defaults to: `false`


### configMap

**Type:** Object

...

Defaults to: `{}`


### defaultHeaders

**Type:** Object

An object containing request headers which are added to each request made by this object.


### defaultPostHeader

**Type:** String

...

Defaults to: `'application/x-www-form-urlencoded; charset=UTF-8'`


### defaultXdrContentType

**Type:** String

...

Defaults to: `'text/plain'`


### defaultXhrHeader

**Type:** String

...

Defaults to: `'XMLHttpRequest'`


### disableCaching

**Type:** Boolean

True to add a unique cache-buster param to GET requests. ...

True to add a unique cache-buster param to GET requests. Defaults to true.


### eventsSuspended

**Type:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called. Defaults to: `0`


### extraParams

**Type:** Object

An object containing properties which are used as extra parameters to each request made by this object. ...

An object containing properties which are used as extra parameters to each request made by this object. Session information and other data that you need to pass with each request are commonly put here.


### getXhrInstance

**Type:** Object

Creates the appropriate XHR transport for this browser.


### hasListeners

**Type:** Object

This object holds a key for any event that has a listener. ...

This object holds a key for any event that has a listener. The listener may be set directly on the instance, or on its class or a super class (via observe) or on the MVC EventBus. The values of this object are truthy (a non-zero number) and falsy (0 or undefined). They do not represent an exact count of listeners. The value for an event is truthy if the event must be fired and is falsy if there is no need to fire the event. The intended use of this property is to avoid the expense of fireEvent calls when there are no listeners. This can be particularly helpful when one would otherwise have to call fireEvent hundreds or thousands of times. It is used like this:


### initConfigList

**Type:** Array

...

Defaults to: `[]`


### initConfigMap

**Type:** Object

...

Defaults to: `{}`


### isInstance

**Type:** Boolean

...

Defaults to: `true`


### isObservable

**Type:** Boolean

true in this class to identify an object as an instantiated Observable, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Observable, or subclass thereof. Defaults to: `true`


### isXdr

**Type:** Boolean

...

Defaults to: `false`


### method

**Type:** String

The default HTTP method to be used for requests. ...

The default HTTP method to be used for requests. Note that this is case-sensitive and should be all caps (if not set but params are present will use "POST", otherwise will use "GET".) Overrides: Ext.data.Connection.method


### password

**Type:** String

...

Defaults to: `''`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### timeout

**Type:** Number

The timeout in milliseconds to be used for requests. ...

The timeout in milliseconds to be used for requests. Defaults to 30000.


### url

**Type:** String

The default URL to be used for requests to the server. ...

The default URL to be used for requests to the server. If the server receives all requests through one URL, setting this once is easier than entering it on every request. Overrides: Ext.data.Connection.url


### useDefaultXhrHeader

**Type:** Boolean

...

Defaults to: `true`


### username

**Type:** String

...

Defaults to: `''`


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.Ajax

...

**Parameters:** config : Object


### abort

Aborts an active request. ...

Aborts an active request.

**Parameters:** request : Object (optional)Defaults to the last request


### abortAll

Aborts all active requests ...

Aborts all active requests


### addEvents

Adds the specified events to the list of events which this Observable may fire. ...

Adds the specified events to the list of events which this Observable may fire.

**Parameters:** eventNames : Object/String...Either an object with event names as properties with a value of `true`. For example: Or any number of event names as separate parameters. For example:


### addListener

Appends an event handler to this object. ...

Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### addManagedListener

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destr...

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### callOverridden

Call the original method that was previously overridden with override Ext.define('My.Cat', { constructor: functi...

Call the original method that was previously overridden with override This method has been **deprecated** as of 4.1. Use callParent instead.


### callParent

Call the "parent" method of the current method. ...

Call the "parent" method of the current method. That is the method previously overridden by derivation or by an override (see Ext.define). This can be used with an override as follows: This also works with static methods. Lastly, it also works with overridden static methods. To override a method and replace it and also call the superclass method, use callSuper. This is often done to patch a method to fix a bug.

**Parameters:** args : Array/ArgumentsThe arguments, either an array or the `arguments` object from the current method, for example: `this.callParent(arguments)`


### callSuper

This method is used by an override to call the superclass method but bypass any overridden method. ...

This method is used by an override to call the superclass method but bypass any overridden method. This is often done to "patch" a method that contains a bug but for whatever reason cannot be fixed directly. Consider: To patch the bug in `DerivedClass.method`, the typical solution is to create an override: The patch method cannot use `callParent` to call the superclass `method` since that would call the overridden method containing the bug. In other words, the above patch would only produce "Fixed" then "Good" in the console log, whereas, using `callParent` would produce "Fixed" then "Bad" then "Good".

**Parameters:** args : Array/ArgumentsThe arguments, either an array or the `arguments` object from the current method, for example: `this.callSuper(arguments)`


### captureArgs

...

**Parameters:** o : Object


### cleanup

Cleans up any left over information from the request ...

Cleans up any left over information from the request

**Parameters:** request : ObjectThe request


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### clearTimeout

Clears the timeout on the request ...

Clears the timeout on the request

**Parameters:** request : ObjectThe request


### configClass

...


### continueFireEvent

Continue to fire event. ...

Continue to fire event.

**Parameters:** eventName : String


### createException

Creates the exception object ...

Creates the exception object

**Parameters:** request : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### createResponse

Creates the response object ...

Creates the response object

**Parameters:** request : Object


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if present. There is no implementation in the Observable base class. This is commonly used by Ext.Components to bubble events to owner Containers. See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the Component's immediate owner. But if a known target is required, this can be overridden to access the required target more quickly. Example:

**Parameters:** eventNames : String/String[]The event name to bubble, or an Array of event names.


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed to addListener). An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list. An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getByteArray

Gets binary data from the xhr response object and returns it as a byte array ...

Gets binary data from the xhr response object and returns it as a byte array

**Parameters:** xhr : Objectthe xhr response object


### getConfig

...

**Parameters:** name : Object


### getForm

Gets the form object from options. ...

Gets the form object from options.

**Parameters:** options : ObjectThe request options


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getLatest

Gets the most recent request ...

Gets the most recent request

**Returns:** ObjectThe request. Null if there is no recent request


### getXdrInstance

Creates the appropriate XDR transport for this browser. ...

Creates the appropriate XDR transport for this browser. - IE 7 and below don't support CORS - IE 8 and 9 support CORS with native XDomainRequest object - IE 10 (and above?) supports CORS with native XMLHttpRequest object


### hasConfig

...

**Parameters:** config : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer indicates whether the event needs firing or not.

**Parameters:** eventName : StringThe name of the event to check for


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### injectVBScript

Injects a vbscript tag containing a 'getIEByteArray' method for reading binary data from an xhr response in IE8 and b...

Injects a vbscript tag containing a 'getIEByteArray' method for reading binary data from an xhr response in IE8 and below.


### isFormUpload

Detects whether the form is intended to be used for an upload. ...

Detects whether the form is intended to be used for an upload.

**Parameters:** options : Object


### isLoading

Determines whether this object has a request outstanding. ...

Determines whether this object has a request outstanding.

**Parameters:** request : Object (optional)Defaults to the last transaction


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener. Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener. Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### nativeBinaryPostSupport

...

**Returns:** booleantrue if the browser can natively post binary data.


### newRequest

Creates the appropriate XHR transport for a given request on this browser. ...

Creates the appropriate XHR transport for a given request on this browser. On IE this may be an `XDomainRequest` rather than an `XMLHttpRequest`.

**Parameters:** options : Object


### on

Shorthand for addListener. ...

Shorthand for addListener. Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### onComplete

To be called when the request has come back from the server ...

To be called when the request has come back from the server

**Parameters:** request : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onStateChange

Fires when the state of the xhr changes ...

Fires when the state of the xhr changes

**Parameters:** request : ObjectThe request


### onUploadComplete

Callback handler for the upload function. ...

Callback handler for the upload function. After we've submitted the form via the iframe this creates a bogus response object to simulate an XHR and populates its responseText from the now-loaded iframe's document body (or a textarea inside the body). We then clean up by removing the iframe

**Parameters:** frame : Object


### openRequest

Creates and opens an appropriate XHR transport for a given request on this browser. ...

Creates and opens an appropriate XHR transport for a given request on this browser. This logic is contained in an individual method to allow for overrides to process all of the parameters and options and return a suitable, open connection.

**Parameters:** options : Object


### parseStatus

Checks if the response status was successful ...

Checks if the response status was successful

**Parameters:** status : NumberThe status code


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a class derives from this class or uses this class as a mixin.

**Parameters:** T : FunctionThe class constructor to prepare.


### processXdrRequest

...

**Parameters:** request : Object


### processXdrResponse

...

**Parameters:** response : Object


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`. For example if you are extending Grid, you might decide to forward some events from store. So you can do this inside your initComponent: The grid instance will then have an observable 'load' event which will be passed the parameters of the store's load event and any function fired with the grid's load event would have access to the grid using the `this` keyword.

**Parameters:** origin : ObjectThe Observable whose events this object is to relay.


### removeListener

Removes an event handler. ...

Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### removeManagedListener

Removes listeners that were added by the mon method. ...

Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### removeManagedListenerItem

Remove a single managed listener item ...

Remove a single managed listener item

**Parameters:** isClear : BooleanTrue if this is being called during a clear


### request

Sends an HTTP request to a remote server. ...

Sends an HTTP request to a remote server. **Important:** Ajax server requests are asynchronous, and this call will return before the response has been received. Process any returned data in a callback function. To execute a callback function in the correct scope, use the `scope` option.

**Parameters:** options : ObjectAn object which may contain the following properties: (The options object may also contain any other property which might be needed to perform postprocessing in a callback because it is passed to callback functions.) url : String/FunctionThe URL to which to send the request, or a function to call which returns a URL string. The scope of the function is specified by the `scope` option. Defaults to the configured `url`.


### resumeEvent

Resumes firing of the named event(s). ...

Resumes firing of the named event(s). After calling this method to resume events, the events will fire when requested to fire. Note that if the suspendEvent method is called multiple times for a certain event, this converse method will have to be called the same number of times for it to resume firing.

**Parameters:** eventName : String...Multiple event names to resume.


### resumeEvents

Resumes firing events (see suspendEvents). ...

Resumes firing events (see suspendEvents). If events were suspended using the `queueSuspended` parameter, then all events fired during event suspension will be sent to any listeners now.


### setConfig

...

**Parameters:** config : Object


### setOptions

Sets various options such as the url, params for the request ...

Sets various options such as the url, params for the request

**Parameters:** options : ObjectThe initial options


### setupHeaders

Setup all the headers for the request ...

Setup all the headers for the request

**Parameters:** xhr : ObjectThe xhr object


### setupMethod

Template method for overriding method ...

Template method for overriding method This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### setupParams

Template method for overriding params ...

Template method for overriding params This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### setupUrl

Template method for overriding url ...

Template method for overriding url This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### suspendEvent

Suspends firing of the named event(s). ...

Suspends firing of the named event(s). After calling this method to suspend events, the events will no longer fire when requested to fire. Note that if this is called multiple times for a certain event, the converse method resumeEvent will have to be called the same number of times for it to resume firing.

**Parameters:** eventName : String...Multiple event names to suspend.


### suspendEvents

Suspends the firing of all events. ...

Suspends the firing of all events. (see resumeEvents)

**Parameters:** queueSuspended : BooleanPass as true to queue up suspended events to be fired after the resumeEvents call instead of discarding all suspended events.


### un

Shorthand for removeListener. ...

Shorthand for removeListener. Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### upload

Uploads a form using a hidden iframe. ...

Uploads a form using a hidden iframe.

**Parameters:** form : String/HTMLElement/Ext.ElementThe form to upload


### addConfig

...

**Parameters:** config : Object


### addInheritableStatics

...

**Parameters:** members : Object


### addMember

...

**Parameters:** name : Object


### addMembers

Add methods / properties to the prototype of this class. ...

Add methods / properties to the prototype of this class.

**Parameters:** members : Object


### addStatics

Add / override static properties of this class. ...

Add / override static properties of this class.

**Parameters:** members : Object


### addXtype

...

**Parameters:** xtype : Object


### borrow

Borrow another class' members to the prototype of this class. ...

Borrow another class' members to the prototype of this class.

**Parameters:** fromClass : Ext.BaseThe class to borrow members from


### create

Create a new instance of this Class. ...

Create a new instance of this Class. All parameters are passed to the constructor of the class.

**Returns:** Objectthe created instance.


### createAlias

Create aliases for existing prototype methods. ...

Create aliases for existing prototype methods. Example:

**Parameters:** alias : String/ObjectThe new method name, or an object to set multiple aliases. See flexSetter


### extend

...

**Parameters:** config : Object


### getName

Get the current class' name in string format. ...

Get the current class' name in string format.

**Returns:** StringclassName


### implement

Adds members to class. ...

Adds members to class. This method has been **deprecated** since 4.1 Use addMembers instead.


### mixin

Used internally by the mixins pre-processor ...

Used internally by the mixins pre-processor

**Parameters:** name : Object


### onExtended

...

**Parameters:** fn : Object


### override

Override members of this class. ...

Override members of this class. Overridden methods can be invoked via callParent. As of 4.1, direct use of this method is deprecated. Use Ext.define instead: The above accomplishes the same result but can be managed by the Ext.Loader which can properly order the override and its target class and the build process can determine whether the override is needed based on the required state of the target class (My.Cat). This method has been **deprecated** since 4.1.0 Use Ext.define instead


### triggerExtended

...


### beforerequest

Fires before a network request is made to retrieve a data object. ...

Fires before a network request is made to retrieve a data object.

**Parameters:** conn : Ext.data.ConnectionThis Connection object.


### requestcomplete

Fires if the request was successfully completed. ...

Fires if the request was successfully completed.

**Parameters:** conn : Ext.data.ConnectionThis Connection object.


### requestexception

Fires if an error HTTP status was returned from the server. ...

Fires if an error HTTP status was returned from the server. This event may also be listened to in the event that a request has timed out or has been aborted. See HTTP Status Code Definitions for details of HTTP status codes.

**Parameters:** conn : Ext.data.ConnectionThis Connection object.


## Methods

### Ext.Ajax

...

**Parameters:** config : Object


### abort

Aborts an active request. ...

Aborts an active request.

**Parameters:** request : Object (optional)Defaults to the last request


### abortAll

Aborts all active requests ...

Aborts all active requests


### addEvents

Adds the specified events to the list of events which this Observable may fire. ...

Adds the specified events to the list of events which this Observable may fire.

**Parameters:** eventNames : Object/String...Either an object with event names as properties with a value of `true`. For example: Or any number of event names as separate parameters. For example:


### addListener

Appends an event handler to this object. ...

Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### addManagedListener

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destr...

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### callOverridden

Call the original method that was previously overridden with override Ext.define('My.Cat', { constructor: functi...

Call the original method that was previously overridden with override This method has been **deprecated** as of 4.1. Use callParent instead.


### callParent

Call the "parent" method of the current method. ...

Call the "parent" method of the current method. That is the method previously overridden by derivation or by an override (see Ext.define). This can be used with an override as follows: This also works with static methods. Lastly, it also works with overridden static methods. To override a method and replace it and also call the superclass method, use callSuper. This is often done to patch a method to fix a bug.

**Parameters:** args : Array/ArgumentsThe arguments, either an array or the `arguments` object from the current method, for example: `this.callParent(arguments)`


### callSuper

This method is used by an override to call the superclass method but bypass any overridden method. ...

This method is used by an override to call the superclass method but bypass any overridden method. This is often done to "patch" a method that contains a bug but for whatever reason cannot be fixed directly. Consider: To patch the bug in `DerivedClass.method`, the typical solution is to create an override: The patch method cannot use `callParent` to call the superclass `method` since that would call the overridden method containing the bug. In other words, the above patch would only produce "Fixed" then "Good" in the console log, whereas, using `callParent` would produce "Fixed" then "Bad" then "Good".

**Parameters:** args : Array/ArgumentsThe arguments, either an array or the `arguments` object from the current method, for example: `this.callSuper(arguments)`


### captureArgs

...

**Parameters:** o : Object


### cleanup

Cleans up any left over information from the request ...

Cleans up any left over information from the request

**Parameters:** request : ObjectThe request


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### clearTimeout

Clears the timeout on the request ...

Clears the timeout on the request

**Parameters:** request : ObjectThe request


### configClass

...


### continueFireEvent

Continue to fire event. ...

Continue to fire event.

**Parameters:** eventName : String


### createException

Creates the exception object ...

Creates the exception object

**Parameters:** request : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### createResponse

Creates the response object ...

Creates the response object

**Parameters:** request : Object


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if present. There is no implementation in the Observable base class. This is commonly used by Ext.Components to bubble events to owner Containers. See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the Component's immediate owner. But if a known target is required, this can be overridden to access the required target more quickly. Example:

**Parameters:** eventNames : String/String[]The event name to bubble, or an Array of event names.


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed to addListener). An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list. An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getByteArray

Gets binary data from the xhr response object and returns it as a byte array ...

Gets binary data from the xhr response object and returns it as a byte array

**Parameters:** xhr : Objectthe xhr response object


### getConfig

...

**Parameters:** name : Object


### getForm

Gets the form object from options. ...

Gets the form object from options.

**Parameters:** options : ObjectThe request options


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getLatest

Gets the most recent request ...

Gets the most recent request

**Returns:** ObjectThe request. Null if there is no recent request


### getXdrInstance

Creates the appropriate XDR transport for this browser. ...

Creates the appropriate XDR transport for this browser. - IE 7 and below don't support CORS - IE 8 and 9 support CORS with native XDomainRequest object - IE 10 (and above?) supports CORS with native XMLHttpRequest object


### hasConfig

...

**Parameters:** config : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer indicates whether the event needs firing or not.

**Parameters:** eventName : StringThe name of the event to check for


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### injectVBScript

Injects a vbscript tag containing a 'getIEByteArray' method for reading binary data from an xhr response in IE8 and b...

Injects a vbscript tag containing a 'getIEByteArray' method for reading binary data from an xhr response in IE8 and below.


### isFormUpload

Detects whether the form is intended to be used for an upload. ...

Detects whether the form is intended to be used for an upload.

**Parameters:** options : Object


### isLoading

Determines whether this object has a request outstanding. ...

Determines whether this object has a request outstanding.

**Parameters:** request : Object (optional)Defaults to the last transaction


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener. Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener. Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### nativeBinaryPostSupport

...

**Returns:** booleantrue if the browser can natively post binary data.


### newRequest

Creates the appropriate XHR transport for a given request on this browser. ...

Creates the appropriate XHR transport for a given request on this browser. On IE this may be an `XDomainRequest` rather than an `XMLHttpRequest`.

**Parameters:** options : Object


### on

Shorthand for addListener. ...

Shorthand for addListener. Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### onComplete

To be called when the request has come back from the server ...

To be called when the request has come back from the server

**Parameters:** request : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onStateChange

Fires when the state of the xhr changes ...

Fires when the state of the xhr changes

**Parameters:** request : ObjectThe request


### onUploadComplete

Callback handler for the upload function. ...

Callback handler for the upload function. After we've submitted the form via the iframe this creates a bogus response object to simulate an XHR and populates its responseText from the now-loaded iframe's document body (or a textarea inside the body). We then clean up by removing the iframe

**Parameters:** frame : Object


### openRequest

Creates and opens an appropriate XHR transport for a given request on this browser. ...

Creates and opens an appropriate XHR transport for a given request on this browser. This logic is contained in an individual method to allow for overrides to process all of the parameters and options and return a suitable, open connection.

**Parameters:** options : Object


### parseStatus

Checks if the response status was successful ...

Checks if the response status was successful

**Parameters:** status : NumberThe status code


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a class derives from this class or uses this class as a mixin.

**Parameters:** T : FunctionThe class constructor to prepare.


### processXdrRequest

...

**Parameters:** request : Object


### processXdrResponse

...

**Parameters:** response : Object


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`. For example if you are extending Grid, you might decide to forward some events from store. So you can do this inside your initComponent: The grid instance will then have an observable 'load' event which will be passed the parameters of the store's load event and any function fired with the grid's load event would have access to the grid using the `this` keyword.

**Parameters:** origin : ObjectThe Observable whose events this object is to relay.


### removeListener

Removes an event handler. ...

Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### removeManagedListener

Removes listeners that were added by the mon method. ...

Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### removeManagedListenerItem

Remove a single managed listener item ...

Remove a single managed listener item

**Parameters:** isClear : BooleanTrue if this is being called during a clear


### request

Sends an HTTP request to a remote server. ...

Sends an HTTP request to a remote server. **Important:** Ajax server requests are asynchronous, and this call will return before the response has been received. Process any returned data in a callback function. To execute a callback function in the correct scope, use the `scope` option.

**Parameters:** options : ObjectAn object which may contain the following properties: (The options object may also contain any other property which might be needed to perform postprocessing in a callback because it is passed to callback functions.) url : String/FunctionThe URL to which to send the request, or a function to call which returns a URL string. The scope of the function is specified by the `scope` option. Defaults to the configured `url`.


### resumeEvent

Resumes firing of the named event(s). ...

Resumes firing of the named event(s). After calling this method to resume events, the events will fire when requested to fire. Note that if the suspendEvent method is called multiple times for a certain event, this converse method will have to be called the same number of times for it to resume firing.

**Parameters:** eventName : String...Multiple event names to resume.


### resumeEvents

Resumes firing events (see suspendEvents). ...

Resumes firing events (see suspendEvents). If events were suspended using the `queueSuspended` parameter, then all events fired during event suspension will be sent to any listeners now.


### setConfig

...

**Parameters:** config : Object


### setOptions

Sets various options such as the url, params for the request ...

Sets various options such as the url, params for the request

**Parameters:** options : ObjectThe initial options


### setupHeaders

Setup all the headers for the request ...

Setup all the headers for the request

**Parameters:** xhr : ObjectThe xhr object


### setupMethod

Template method for overriding method ...

Template method for overriding method This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### setupParams

Template method for overriding params ...

Template method for overriding params This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### setupUrl

Template method for overriding url ...

Template method for overriding url This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### suspendEvent

Suspends firing of the named event(s). ...

Suspends firing of the named event(s). After calling this method to suspend events, the events will no longer fire when requested to fire. Note that if this is called multiple times for a certain event, the converse method resumeEvent will have to be called the same number of times for it to resume firing.

**Parameters:** eventName : String...Multiple event names to suspend.


### suspendEvents

Suspends the firing of all events. ...

Suspends the firing of all events. (see resumeEvents)

**Parameters:** queueSuspended : BooleanPass as true to queue up suspended events to be fired after the resumeEvents call instead of discarding all suspended events.


### un

Shorthand for removeListener. ...

Shorthand for removeListener. Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### upload

Uploads a form using a hidden iframe. ...

Uploads a form using a hidden iframe.

**Parameters:** form : String/HTMLElement/Ext.ElementThe form to upload


### addConfig

...

**Parameters:** config : Object


### addInheritableStatics

...

**Parameters:** members : Object


### addMember

...

**Parameters:** name : Object


### addMembers

Add methods / properties to the prototype of this class. ...

Add methods / properties to the prototype of this class.

**Parameters:** members : Object


### addStatics

Add / override static properties of this class. ...

Add / override static properties of this class.

**Parameters:** members : Object


### addXtype

...

**Parameters:** xtype : Object


### borrow

Borrow another class' members to the prototype of this class. ...

Borrow another class' members to the prototype of this class.

**Parameters:** fromClass : Ext.BaseThe class to borrow members from


### create

Create a new instance of this Class. ...

Create a new instance of this Class. All parameters are passed to the constructor of the class.

**Returns:** Objectthe created instance.


### createAlias

Create aliases for existing prototype methods. ...

Create aliases for existing prototype methods. Example:

**Parameters:** alias : String/ObjectThe new method name, or an object to set multiple aliases. See flexSetter


### extend

...

**Parameters:** config : Object


### getName

Get the current class' name in string format. ...

Get the current class' name in string format.

**Returns:** StringclassName


### implement

Adds members to class. ...

Adds members to class. This method has been **deprecated** since 4.1 Use addMembers instead.


### mixin

Used internally by the mixins pre-processor ...

Used internally by the mixins pre-processor

**Parameters:** name : Object


### onExtended

...

**Parameters:** fn : Object


### override

Override members of this class. ...

Override members of this class. Overridden methods can be invoked via callParent. As of 4.1, direct use of this method is deprecated. Use Ext.define instead: The above accomplishes the same result but can be managed by the Ext.Loader which can properly order the override and its target class and the build process can determine whether the override is needed based on the required state of the target class (My.Cat). This method has been **deprecated** since 4.1.0 Use Ext.define instead


### triggerExtended

...


### beforerequest

Fires before a network request is made to retrieve a data object. ...

Fires before a network request is made to retrieve a data object.

**Parameters:** conn : Ext.data.ConnectionThis Connection object.


### requestcomplete

Fires if the request was successfully completed. ...

Fires if the request was successfully completed.

**Parameters:** conn : Ext.data.ConnectionThis Connection object.


### requestexception

Fires if an error HTTP status was returned from the server. ...

Fires if an error HTTP status was returned from the server. This event may also be listened to in the event that a request has timed out or has been aborted. See HTTP Status Code Definitions for details of HTTP status codes.

**Parameters:** conn : Ext.data.ConnectionThis Connection object.


## Events

### beforerequest

Fires before a network request is made to retrieve a data object. ...

Fires before a network request is made to retrieve a data object.

**Parameters:** conn : Ext.data.ConnectionThis Connection object.


### requestcomplete

Fires if the request was successfully completed. ...

Fires if the request was successfully completed.

**Parameters:** conn : Ext.data.ConnectionThis Connection object.


### requestexception

Fires if an error HTTP status was returned from the server. ...

Fires if an error HTTP status was returned from the server. This event may also be listened to in the event that a request has timed out or has been aborted. See HTTP Status Code Definitions for details of HTTP status codes.

**Parameters:** conn : Ext.data.ConnectionThis Connection object.


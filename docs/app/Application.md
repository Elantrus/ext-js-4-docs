# Ext.app.Application

**Extends:** Ext.app.Controller

## Description

Represents an Ext JS 4 application, which is typically a single page app using a Viewport. A typical Ext.app.Application might look like this:

Ext.application({ name: 'MyApp', launch: function() { Ext.create('Ext.container.Viewport', { items: { html: 'My App' } }); } }); This does several things. First it creates a global variable called 'MyApp' - all of your Application's classes (such as its Models, Views and Controllers) will reside under this single namespace, which drastically lowers the chances of colliding global variables. The MyApp global will also have a getApplication method to get a reference to the current application:

var app = MyApp.getApplication(); When the page is ready and all of your JavaScript has loaded, your Application's launch function is called, at which time you can run the code that starts your app. Usually this consists of creating a Viewport, as we do in the example above.

Because an Ext.app.Application represents an entire app, we should tell it about the other parts of the app - namely the Models, Views and Controllers that are bundled with the application. Let's say we have a blog management app; we might have Models and Controllers for Posts and Comments, and Views for listing, adding and editing Posts and Comments. Here's how we'd tell our Application about all these things:

Ext.application({ name: 'Blog', models: ['Post', 'Comment'], controllers: ['Posts', 'Comments'], launch: function() { ... } }); Note that we didn't actually list the Views directly in the Application itself. This is because Views are managed by Controllers, so it makes sense to keep those dependencies there. The Application will load each of the specified Controllers using the pathing conventions laid out in the application architecture guide - in this case expecting the controllers to reside in app/controller/Posts.js and app/controller/Comments.js. In turn, each Controller simply needs to list the Views it uses and they will be automatically loaded. Here's how our Posts controller like be defined:

Ext.define('MyApp.controller.Posts', { extend: 'Ext.app.Controller', views: ['posts.List', 'posts.Edit'], //the rest of the Controller here }); Because we told our Application about our Models and Controllers, and our Controllers about their Views, Ext JS will automatically load all of our app files for us. This means we don't have to manually add script tags into our html files whenever we add a new class, but more importantly it enables us to create a minimized build of our entire application using Sencha Cmd.

Typically, applications do not derive directly from Ext.app.Application. Rather, the configuration passed to `Ext.application` mimics what you might do in a derived class. In some cases, however, it can be desirable to share logic by using a derived class from `Ext.app.Application`.

Derivation works as you would expect, but using the derived class should still be the job of the `Ext.application` method.

Ext.define('MyApp.app.Application', { extend: 'Ext.app.Application', name: 'MyApp', ... }); Ext.application('MyApp.app.Application'); For more information about writing Ext JS 4 applications, please see the application architecture guide.

## Config options

### appFolder

**Type:** String

The path to the directory which contains all application's classes. ...

The path to the directory which contains all application's classes. This path will be registered via Ext.Loader.setPath for the namespace specified in the name config. Defaults to: `'app'`


### appProperty

**Type:** String

The name of a property to be assigned to the main namespace to gain a reference to this application. ...

The name of a property to be assigned to the main namespace to gain a reference to this application. Can be set to an empty value to prevent the reference from being created Defaults to: `'app'`


### autoCreateViewport

**Type:** Boolean

True to automatically load and instantiate AppName.view.Viewport before firing the launch function. ...

True to automatically load and instantiate AppName.view.Viewport before firing the launch function. Defaults to: `false`


### controllers

**Type:** String/String[]

Names of controllers that the app uses.


### enableQuickTips

**Type:** Boolean

True to automatically set up Ext.tip.QuickTip support. ...

True to automatically set up Ext.tip.QuickTip support. Defaults to: `true`


### id

**Type:** String

The id of this controller. ...

The id of this controller. You can use this id when dispatching.


### listeners

**Type:** Object

A config object containing one or more event handlers to be added to this object during initialization. ...

A config object containing one or more event handlers to be added to this object during initialization. This should be a valid listeners config object as specified in the addListener example for attaching multiple handlers at once. **DOM events from Ext JS Components** While *some* Ext JS Component classes export selected DOM events (e.g. "click", "mouseover" etc), this is usually only done when extra value can be added. For example the DataView's **`itemclick`** event passing the node clicked on. To access DOM events directly from a child element of a Component, we need to specify the `element` option to identify the Component property to add a DOM listener to:


### models

**Type:** String/String[]

Array of models to require from AppName.model namespace. ...

Array of models to require from AppName.model namespace. For example: This is equivalent of:


### name

**Type:** String

The name of your application. ...

The name of your application. This will also be the namespace for your views, controllers models and stores. Don't use spaces or special characters in the name. Application name is mandatory.


### namespaces

**Type:** String/String[]

The list of namespace prefixes used in the application to resolve dependencies like Views and Stores: Ext.applicati...

The list of namespace prefixes used in the application to resolve dependencies like Views and Stores: You don't need to include main namespace (MyApp), it will be added to the list automatically. Defaults to: `[]`


### paths

**Type:** Object

Additional load paths to add to Ext.Loader. ...

Additional load paths to add to Ext.Loader. See Ext.Loader.paths config for more details.


### refs

**Type:** Object[]

Array of configs to build up references to views on page. ...

Array of configs to build up references to views on page. For example: This will add method `getList` to the controller which will internally use Ext.ComponentQuery to reference the grid component on page. The following fields can be used in ref definition: - `ref` - name of the reference. - `selector` - Ext.ComponentQuery selector to access the component. - `autoCreate` - True to create the component automatically if not found on page. - `forceCreate` - Forces the creation of the component every time reference is accessed (when `get<REFNAME>` is called). - `xtype` - Used to create component by its xtype with autoCreate or forceCreate. If you don't provide xtype, an Ext.Component instance will be created.


### scope

**Type:** Object

The scope to execute the launch function in. ...

The scope to execute the launch function in. Defaults to the Application instance.


### stores

**Type:** String/String[]

Array of stores to require from AppName.store namespace and to generate getter methods for. ...

Array of stores to require from AppName.store namespace and to generate getter methods for. For example: This is equivalent to:


### views

**Type:** String/String[]

Array of views to require from AppName.view namespace and to generate getter methods for. ...

Array of views to require from AppName.view namespace and to generate getter methods for. For example: This is equivalent of:


### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### application

**Type:** Ext.app.Application

The Ext.app.Application for this controller.


### configMap

**Type:** Object

...

Defaults to: `{}`


### eventsSuspended

**Type:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called. Defaults to: `0`


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


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.app.Application

Creates new Application. ...

Creates new Application.

**Parameters:** config : Object (optional)Config object.


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


### addRef

Registers one or more references. ...

Registers one or more references.

**Parameters:** refs : Object/Object[]


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


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### configClass

...


### continueFireEvent

Continue to fire event. ...

Continue to fire event.

**Parameters:** eventName : String


### control

Adds listeners to components selected via Ext.ComponentQuery. ...

Adds listeners to components selected via Ext.ComponentQuery. Accepts an object containing component paths mapped to a hash of listener functions. In the following example the `updateUser` function is mapped to to the `click` event on a button component, which is a child of the `useredit` component. Or alternatively one call `control` with two arguments: See Ext.ComponentQuery for more information on component selectors.

**Parameters:** selectors : String/ObjectIf a String, the second argument is used as the listeners, otherwise an object of selectors -> listeners is assumed


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### doInit

...

**Parameters:** app : Object


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if present. There is no implementation in the Observable base class. This is commonly used by Ext.Components to bubble events to owner Containers. See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the Component's immediate owner. But if a known target is required, this can be overridden to access the required target more quickly. Example:

**Parameters:** eventNames : String/String[]The event name to bubble, or an Array of event names.


### finishInit

...

**Parameters:** app : Object


### finishInitControllers

...


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed to addListener). An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list. An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### getApplication

Returns the base Ext.app.Application for this controller. ...

**Returns:** the base Ext.app.Application for this controller. ReturnsExt.app.Applicationthe application


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getConfig

...

**Parameters:** name : Object


### getController

Returns instance of a Controller with the given id. ...

**Parameters:** id : String

**Returns:** instance of a Controller with the given id. When controller doesn't exist yet, it's created. Note that this method depends on Application instance and will return undefined when Application is not accessible. The only exception is when this Controller instance's id is requested; in that case we always return the instance even if Application is no available.


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getModel

Returns a Model class with the given name. ...

**Parameters:** name : String

**Returns:** a Model class with the given name. A shorthand for using Ext.ModelManager.getModel.


### getModuleClassName

...

**Parameters:** name : Object


### getRef

...

**Parameters:** ref : Object


### getStore

Returns instance of a Store with the given name. ...

**Parameters:** name : String

**Returns:** instance of a Store with the given name. When store doesn't exist yet, it's created.


### getView

Returns a View class with the given name. ...

**Parameters:** name : String

**Returns:** a View class with the given name. To create an instance of the view, you can use it like it's used by Application to create the Viewport:


### hasConfig

...

**Parameters:** config : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer indicates whether the event needs firing or not.

**Parameters:** eventName : StringThe name of the event to check for


### hasRef

Returns true if a reference is registered. ...

**Parameters:** ref : Object

**Returns:** `true` if a reference is registered.


### init

A template method that is called when your application boots. ...

A template method that is called when your application boots. It is called before the Application's launch function is executed so gives a hook point to run any code before your Viewport is created. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### initAutoGetters

...


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initControllers

...


### initNamespace

...


### initQuickTips

...


### initViewport

...


### launch

Called automatically when the page has completely loaded. ...

Called automatically when the page has completely loaded. This is an empty function that should be overridden by each application that needs to take action on page load. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### listen

Adds listeners to different event sources (also called "event domains"). ...

Adds listeners to different event sources (also called "event domains"). The primary event domain is that of components, but there are also other event domains: Global domain that intercepts events fired from Ext.globalEvents Observable instance, Controller domain can be used to listen to events fired by other Controllers, Store domain gives access to Store events, and Direct domain can be used with Ext.Direct Providers to listen to their events. To listen to "bar" events fired by a controller with id="foo": To listen to "bar" events fired by any controller, and "baz" events fired by Store with storeId="baz": To listen to "idle" events fired by Ext.globalEvents when other event processing is complete and Ext JS is about to return control to the browser: As this relates to components, the following example: Is equivalent to: Of course, these can all be combined in a single call and used instead of `control`, like so:

**Parameters:** to : ObjectConfig object containing domains, selectors and listeners.


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener. Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener. Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### on

Shorthand for addListener. ...

Shorthand for addListener. Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### onBeforeLaunch

...


### onClassExtended

...

**Parameters:** cls : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onLaunch

A template method like init, but called after the viewport is created. ...

A template method like init, but called after the viewport is created. This is called after the launch method of Application is executed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a class derives from this class or uses this class as a mixin.

**Parameters:** T : FunctionThe class constructor to prepare.


### ref

...

**Parameters:** refs : Object


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


## Properties

### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### application

**Type:** Ext.app.Application

The Ext.app.Application for this controller.


### configMap

**Type:** Object

...

Defaults to: `{}`


### eventsSuspended

**Type:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called. Defaults to: `0`


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


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.app.Application

Creates new Application. ...

Creates new Application.

**Parameters:** config : Object (optional)Config object.


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


### addRef

Registers one or more references. ...

Registers one or more references.

**Parameters:** refs : Object/Object[]


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


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### configClass

...


### continueFireEvent

Continue to fire event. ...

Continue to fire event.

**Parameters:** eventName : String


### control

Adds listeners to components selected via Ext.ComponentQuery. ...

Adds listeners to components selected via Ext.ComponentQuery. Accepts an object containing component paths mapped to a hash of listener functions. In the following example the `updateUser` function is mapped to to the `click` event on a button component, which is a child of the `useredit` component. Or alternatively one call `control` with two arguments: See Ext.ComponentQuery for more information on component selectors.

**Parameters:** selectors : String/ObjectIf a String, the second argument is used as the listeners, otherwise an object of selectors -> listeners is assumed


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### doInit

...

**Parameters:** app : Object


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if present. There is no implementation in the Observable base class. This is commonly used by Ext.Components to bubble events to owner Containers. See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the Component's immediate owner. But if a known target is required, this can be overridden to access the required target more quickly. Example:

**Parameters:** eventNames : String/String[]The event name to bubble, or an Array of event names.


### finishInit

...

**Parameters:** app : Object


### finishInitControllers

...


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed to addListener). An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list. An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### getApplication

Returns the base Ext.app.Application for this controller. ...

**Returns:** the base Ext.app.Application for this controller. ReturnsExt.app.Applicationthe application


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getConfig

...

**Parameters:** name : Object


### getController

Returns instance of a Controller with the given id. ...

**Parameters:** id : String

**Returns:** instance of a Controller with the given id. When controller doesn't exist yet, it's created. Note that this method depends on Application instance and will return undefined when Application is not accessible. The only exception is when this Controller instance's id is requested; in that case we always return the instance even if Application is no available.


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getModel

Returns a Model class with the given name. ...

**Parameters:** name : String

**Returns:** a Model class with the given name. A shorthand for using Ext.ModelManager.getModel.


### getModuleClassName

...

**Parameters:** name : Object


### getRef

...

**Parameters:** ref : Object


### getStore

Returns instance of a Store with the given name. ...

**Parameters:** name : String

**Returns:** instance of a Store with the given name. When store doesn't exist yet, it's created.


### getView

Returns a View class with the given name. ...

**Parameters:** name : String

**Returns:** a View class with the given name. To create an instance of the view, you can use it like it's used by Application to create the Viewport:


### hasConfig

...

**Parameters:** config : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer indicates whether the event needs firing or not.

**Parameters:** eventName : StringThe name of the event to check for


### hasRef

Returns true if a reference is registered. ...

**Parameters:** ref : Object

**Returns:** `true` if a reference is registered.


### init

A template method that is called when your application boots. ...

A template method that is called when your application boots. It is called before the Application's launch function is executed so gives a hook point to run any code before your Viewport is created. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### initAutoGetters

...


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initControllers

...


### initNamespace

...


### initQuickTips

...


### initViewport

...


### launch

Called automatically when the page has completely loaded. ...

Called automatically when the page has completely loaded. This is an empty function that should be overridden by each application that needs to take action on page load. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### listen

Adds listeners to different event sources (also called "event domains"). ...

Adds listeners to different event sources (also called "event domains"). The primary event domain is that of components, but there are also other event domains: Global domain that intercepts events fired from Ext.globalEvents Observable instance, Controller domain can be used to listen to events fired by other Controllers, Store domain gives access to Store events, and Direct domain can be used with Ext.Direct Providers to listen to their events. To listen to "bar" events fired by a controller with id="foo": To listen to "bar" events fired by any controller, and "baz" events fired by Store with storeId="baz": To listen to "idle" events fired by Ext.globalEvents when other event processing is complete and Ext JS is about to return control to the browser: As this relates to components, the following example: Is equivalent to: Of course, these can all be combined in a single call and used instead of `control`, like so:

**Parameters:** to : ObjectConfig object containing domains, selectors and listeners.


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener. Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener. Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### on

Shorthand for addListener. ...

Shorthand for addListener. Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### onBeforeLaunch

...


### onClassExtended

...

**Parameters:** cls : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onLaunch

A template method like init, but called after the viewport is created. ...

A template method like init, but called after the viewport is created. This is called after the launch method of Application is executed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a class derives from this class or uses this class as a mixin.

**Parameters:** T : FunctionThe class constructor to prepare.


### ref

...

**Parameters:** refs : Object


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


## Methods

### Ext.app.Application

Creates new Application. ...

Creates new Application.

**Parameters:** config : Object (optional)Config object.


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


### addRef

Registers one or more references. ...

Registers one or more references.

**Parameters:** refs : Object/Object[]


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


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### configClass

...


### continueFireEvent

Continue to fire event. ...

Continue to fire event.

**Parameters:** eventName : String


### control

Adds listeners to components selected via Ext.ComponentQuery. ...

Adds listeners to components selected via Ext.ComponentQuery. Accepts an object containing component paths mapped to a hash of listener functions. In the following example the `updateUser` function is mapped to to the `click` event on a button component, which is a child of the `useredit` component. Or alternatively one call `control` with two arguments: See Ext.ComponentQuery for more information on component selectors.

**Parameters:** selectors : String/ObjectIf a String, the second argument is used as the listeners, otherwise an object of selectors -> listeners is assumed


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### doInit

...

**Parameters:** app : Object


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if present. There is no implementation in the Observable base class. This is commonly used by Ext.Components to bubble events to owner Containers. See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the Component's immediate owner. But if a known target is required, this can be overridden to access the required target more quickly. Example:

**Parameters:** eventNames : String/String[]The event name to bubble, or an Array of event names.


### finishInit

...

**Parameters:** app : Object


### finishInitControllers

...


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed to addListener). An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list. An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### getApplication

Returns the base Ext.app.Application for this controller. ...

**Returns:** the base Ext.app.Application for this controller. ReturnsExt.app.Applicationthe application


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getConfig

...

**Parameters:** name : Object


### getController

Returns instance of a Controller with the given id. ...

**Parameters:** id : String

**Returns:** instance of a Controller with the given id. When controller doesn't exist yet, it's created. Note that this method depends on Application instance and will return undefined when Application is not accessible. The only exception is when this Controller instance's id is requested; in that case we always return the instance even if Application is no available.


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getModel

Returns a Model class with the given name. ...

**Parameters:** name : String

**Returns:** a Model class with the given name. A shorthand for using Ext.ModelManager.getModel.


### getModuleClassName

...

**Parameters:** name : Object


### getRef

...

**Parameters:** ref : Object


### getStore

Returns instance of a Store with the given name. ...

**Parameters:** name : String

**Returns:** instance of a Store with the given name. When store doesn't exist yet, it's created.


### getView

Returns a View class with the given name. ...

**Parameters:** name : String

**Returns:** a View class with the given name. To create an instance of the view, you can use it like it's used by Application to create the Viewport:


### hasConfig

...

**Parameters:** config : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer indicates whether the event needs firing or not.

**Parameters:** eventName : StringThe name of the event to check for


### hasRef

Returns true if a reference is registered. ...

**Parameters:** ref : Object

**Returns:** `true` if a reference is registered.


### init

A template method that is called when your application boots. ...

A template method that is called when your application boots. It is called before the Application's launch function is executed so gives a hook point to run any code before your Viewport is created. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### initAutoGetters

...


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initControllers

...


### initNamespace

...


### initQuickTips

...


### initViewport

...


### launch

Called automatically when the page has completely loaded. ...

Called automatically when the page has completely loaded. This is an empty function that should be overridden by each application that needs to take action on page load. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### listen

Adds listeners to different event sources (also called "event domains"). ...

Adds listeners to different event sources (also called "event domains"). The primary event domain is that of components, but there are also other event domains: Global domain that intercepts events fired from Ext.globalEvents Observable instance, Controller domain can be used to listen to events fired by other Controllers, Store domain gives access to Store events, and Direct domain can be used with Ext.Direct Providers to listen to their events. To listen to "bar" events fired by a controller with id="foo": To listen to "bar" events fired by any controller, and "baz" events fired by Store with storeId="baz": To listen to "idle" events fired by Ext.globalEvents when other event processing is complete and Ext JS is about to return control to the browser: As this relates to components, the following example: Is equivalent to: Of course, these can all be combined in a single call and used instead of `control`, like so:

**Parameters:** to : ObjectConfig object containing domains, selectors and listeners.


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener. Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener. Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### on

Shorthand for addListener. ...

Shorthand for addListener. Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### onBeforeLaunch

...


### onClassExtended

...

**Parameters:** cls : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onLaunch

A template method like init, but called after the viewport is created. ...

A template method like init, but called after the viewport is created. This is called after the launch method of Application is executed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a class derives from this class or uses this class as a mixin.

**Parameters:** T : FunctionThe class constructor to prepare.


### ref

...

**Parameters:** refs : Object


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


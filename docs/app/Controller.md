# Ext.app.Controller

**Extends:** Ext.Base

## Description

Controllers are the glue that binds an application together. All they really do is listen for events (usually from views) and take some action. Here's how we might create a Controller to manage Users:

Ext.define('MyApp.controller.Users', { extend: 'Ext.app.Controller', init: function() { console.log('Initialized Users! This happens before ' + 'the Application launch() function is called'); } }); The init function is a special method that is called when your application boots. It is called before the Application's launch function is executed so gives a hook point to run any code before your Viewport is created.

The init function is a great place to set up how your controller interacts with the view, and is usually used in conjunction with another Controller function - control. The control function makes it easy to listen to events on your view classes and take some action with a handler function. Let's update our Users controller to tell us when the panel is rendered:

Ext.define('MyApp.controller.Users', { extend: 'Ext.app.Controller', init: function() { this.control({ 'viewport > panel': { render: this.onPanelRendered } }); }, onPanelRendered: function() { console.log('The panel was rendered'); } }); We've updated the init function to use control method to set up listeners on views in our application. The control method uses the ComponentQuery engine to quickly and easily get references to components on the page. If you are not familiar with ComponentQuery yet, be sure to check out the documentation. In brief though, it allows us to pass a CSS-like selector that will find every matching component on the page.

In our init function above we supplied 'viewport > panel', which translates to "find me every Panel that is a direct child of a Viewport". We then supplied an object that maps event names (just 'render' in this case) to handler functions. The overall effect is that whenever any component that matches our selector fires a 'render' event, our onPanelRendered function is called.

In Ext JS 4.2, we introduced the concept of event domains. In terms of MVC, an event domain is one or more base classes that fire events to which a Controller wants to listen. Besides Component event domain that encompass Ext.Component-descended Views, Controllers now can listen to events from data Stores, Ext.Direct Providers, other Controllers, and Ext.globalEvents. This feature provides a way to communicate between parts of the whole application without the need to bind controllers together tightly, and allows to develop and test application parts in isolation.

See usage examples in listen method documentation.

One of the most useful parts of Controllers is the ref system. These use the Ext.ComponentQuery to make it really easy to get references to Views on your page. Let's look at an example of this now:

Ext.define('MyApp.controller.Users', { extend: 'Ext.app.Controller', refs: [{ ref: 'list', selector: 'grid' }], init: function() { this.control({ 'button': { click: this.refreshGrid } }); }, refreshGrid: function() { this.getList().store.load(); } }); This example assumes the existence of a Grid on the page, which contains a single button to refresh the Grid when clicked. In our refs array, we set up a reference to the grid. There are two parts to this - the 'selector', which is a ComponentQuery selector which finds any grid on the page and assigns it to the reference 'list'.

By giving the reference a name, we get a number of things for free. The first is the getList function that we use in the refreshGrid method above. This is generated automatically by the Controller based on the name of our ref, which was capitalized and prepended with get to go from 'list' to 'getList'.

The way this works is that the first time getList is called by your code, the ComponentQuery selector is run and the first component that matches the selector ('grid' in this case) will be returned. All future calls to getList will use a cached reference to that grid. Usually it is advised to use a specific ComponentQuery selector that will only match a single View in your application (in the case above our selector will match any grid on the page).

Bringing it all together, our init function is called when the application boots, at which time we call this.control to listen to any click on a button and call our refreshGrid function (again, this will match any button on the page so we advise a more specific selector than just 'button', but have left it this way for simplicity). When the button is clicked we use out getList function to refresh the grid.

You can create any number of refs and control any number of components this way, simply adding more functions to your Controller as you go. For an example of real-world usage of Controllers see the Feed Viewer example in the examples/app/feed-viewer folder in the SDK download.

Refs aren't the only thing that generate convenient getter methods. Controllers often have to deal with Models and Stores so the framework offers a couple of easy ways to get access to those too. Let's look at another example:

Ext.define('MyApp.controller.Users', { extend: 'Ext.app.Controller', models: ['User'], stores: ['AllUsers', 'AdminUsers'], init: function() { var User, allUsers, ed; User = this.getUserModel(); allUsers = this.getAllUsersStore(); ed = new User({ name: 'Ed' }); allUsers.add(ed); } }); By specifying Models and Stores that the Controller cares about, it again dynamically loads them from the appropriate locations (app/model/User.js, app/store/AllUsers.js and app/store/AdminUsers.js in this case) and creates getter functions for them all. The example above will create a new User model instance and add it to the AllUsers Store. Of course, you could do anything in this function but in this case we just did something simple to demonstrate the functionality.

For more information about writing Ext JS 4 applications, please see the application architecture guide. Also see the Ext.app.Application documentation.

## Config options

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


### refs

**Type:** Object[]

Array of configs to build up references to views on page. ...

Array of configs to build up references to views on page. For example: This will add method `getList` to the controller which will internally use Ext.ComponentQuery to reference the grid component on page. The following fields can be used in ref definition: - `ref` - name of the reference. - `selector` - Ext.ComponentQuery selector to access the component. - `autoCreate` - True to create the component automatically if not found on page. - `forceCreate` - Forces the creation of the component every time reference is accessed (when `get<REFNAME>` is called). - `xtype` - Used to create component by its xtype with autoCreate or forceCreate. If you don't provide xtype, an Ext.Component instance will be created.


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


### controllerRegex

**Type:** RegExp

...

Defaults to: `/^(.*)\.controller\./`


### strings

**Type:** Object

...

Defaults to: `{model: {getter: 'getModel', upper: 'Model'}, view: {getter: 'getView', upper: 'View'}, controller: {getter: 'getController', upper: 'Controller'}, store: {getter: 'getStore', upper: 'Store'}}`


### Ext.app.Controller

Creates new Controller. ...

Creates new Controller.

**Parameters:** config : Object (optional)Configuration object.


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


### createGetter

...

**Parameters:** baseGetter : Object


### extend

...

**Parameters:** config : Object


### getFullName

...

**Parameters:** name : Object


### getGetterName

...

**Parameters:** name : Object


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


### processDependencies

This method is called like so: Ext.app.Controller.processDependencies(proto, requiresArray, 'MyApp', 'model', [ ...

This method is called like so: Required dependencies are added to requiresArray.

**Parameters:** cls : Object


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


### controllerRegex

**Type:** RegExp

...

Defaults to: `/^(.*)\.controller\./`


### strings

**Type:** Object

...

Defaults to: `{model: {getter: 'getModel', upper: 'Model'}, view: {getter: 'getView', upper: 'View'}, controller: {getter: 'getController', upper: 'Controller'}, store: {getter: 'getStore', upper: 'Store'}}`


### Ext.app.Controller

Creates new Controller. ...

Creates new Controller.

**Parameters:** config : Object (optional)Configuration object.


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


### createGetter

...

**Parameters:** baseGetter : Object


### extend

...

**Parameters:** config : Object


### getFullName

...

**Parameters:** name : Object


### getGetterName

...

**Parameters:** name : Object


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


### processDependencies

This method is called like so: Ext.app.Controller.processDependencies(proto, requiresArray, 'MyApp', 'model', [ ...

This method is called like so: Required dependencies are added to requiresArray.

**Parameters:** cls : Object


### triggerExtended

...


## Methods

### Ext.app.Controller

Creates new Controller. ...

Creates new Controller.

**Parameters:** config : Object (optional)Configuration object.


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


### createGetter

...

**Parameters:** baseGetter : Object


### extend

...

**Parameters:** config : Object


### getFullName

...

**Parameters:** name : Object


### getGetterName

...

**Parameters:** name : Object


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


### processDependencies

This method is called like so: Ext.app.Controller.processDependencies(proto, requiresArray, 'MyApp', 'model', [ ...

This method is called like so: Required dependencies are added to requiresArray.

**Parameters:** cls : Object


### triggerExtended

...


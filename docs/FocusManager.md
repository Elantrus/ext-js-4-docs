# Ext.FocusManager

**Extends:** Ext.Base

**Alternate Names:** Ext.FocusMgr

## Description

The FocusManager is responsible for globally:

To activate the FocusManager, simply call `Ext.FocusManager.enable();`. In turn, you may deactivate the FocusManager by subsequently calling `Ext.FocusManager.disable();`. The FocusManager is disabled by default.

To enable the optional focus frame, pass `true` or `{focusFrame: true}` to enable.

Another feature of the FocusManager is to provide basic keyboard focus navigation scoped to any Ext.container.Container that would like to have navigation between its child Ext.Component's.

## Config options

### listeners

**Type:** Object

A config object containing one or more event handlers to be added to this object during initialization. ...

A config object containing one or more event handlers to be added to this object during initialization. This should be a valid listeners config object as specified in the addListener example for attaching multiple handlers at once. **DOM events from Ext JS Components** While *some* Ext JS Component classes export selected DOM events (e.g. "click", "mouseover" etc), this is usually only done when extra value can be added. For example the DataView's **`itemclick`** event passing the node clicked on. To access DOM events directly from a child element of a Component, we need to specify the `element` option to identify the Component property to add a DOM listener to:


### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### configMap

**Type:** Object

...

Defaults to: `{}`


### enabled

**Type:** Boolean

Whether or not the FocusManager is currently enabled ...

Whether or not the FocusManager is currently enabled Defaults to: `false`


### eventsSuspended

**Type:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called. Defaults to: `0`


### focusFrameCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'focus-frame'`


### focusedCmp

**Type:** Ext.Component

The currently focused component.


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


### whitelist

**Type:** String[]

A list of xtypes that should ignore certain navigation input keys and allow for the default browser event/behavior. ...

A list of xtypes that should ignore certain navigation input keys and allow for the default browser event/behavior. These input keys include: - Backspace - Delete - Left - Right - Up - Down The FocusManager will not attempt to navigate when a component is an xtype (or descendents thereof) that belongs to this whitelist. E.g., an Ext.form.field.Text should allow the user to move the input cursor left and right, and to delete characters, etc. Defaults to: `['textfield']`


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.FocusManager

...

**Parameters:** config : Object


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


### addXTypeToWhitelist

Adds the specified xtype to the whitelist. ...

Adds the specified xtype to the whitelist.

**Parameters:** xtype : String/String[]Adds the xtype(s) to the whitelist.


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


### clearComponent

...

**Parameters:** cmp : Object


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


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### disable

Disables the FocusManager by turning of all automatic focus management and keyboard navigation ...

Disables the FocusManager by turning of all automatic focus management and keyboard navigation


### enable

Enables the FocusManager by turning on all automatic focus management and keyboard navigation ...

Enables the FocusManager by turning on all automatic focus management and keyboard navigation

**Parameters:** options : Boolean/ObjectEither `true`/`false` to turn on the focus frame, or an object with the following options: focusFrame : Boolean (optional)`true` to show the focus frame around a component when it is focused. Defaults to: `false`


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


### focusLast

...

**Parameters:** e : Object


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getConfig

...

**Parameters:** name : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getRootComponents

...


### handleComponentFocus

...

**Parameters:** cmp : Object


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


### initDOM

...

**Parameters:** options : Object


### isWhitelisted

...

**Parameters:** cmp : Object


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener. Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener. Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### navigateIn

...

**Parameters:** e : Object


### navigateOut

...

**Parameters:** e : Object


### navigateSiblings

...

**Parameters:** e : Object


### on

Shorthand for addListener. ...

Shorthand for addListener. Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### onComponentBlur

...

**Parameters:** cmp : Object


### onComponentDestroy

...


### onComponentFocus

...

**Parameters:** cmp : Object


### onComponentHide

...

**Parameters:** cmp : Object


### onConfigUpdate

...

**Parameters:** names : Object


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a class derives from this class or uses this class as a mixin.

**Parameters:** T : FunctionThe class constructor to prepare.


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`. For example if you are extending Grid, you might decide to forward some events from store. So you can do this inside your initComponent: The grid instance will then have an observable 'load' event which will be passed the parameters of the store's load event and any function fired with the grid's load event would have access to the grid using the `this` keyword.

**Parameters:** origin : ObjectThe Observable whose events this object is to relay.


### removeDOM

...


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


### removeXTypeFromWhitelist

Removes the specified xtype from the whitelist. ...

Removes the specified xtype from the whitelist.

**Parameters:** xtype : String/String[]Removes the xtype(s) from the whitelist.


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


### setupSubscriberKeys

...

**Parameters:** container : Object


### shouldShowFocusFrame

...

**Parameters:** cmp : Object


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


### beforecomponentfocus

Fires before a component becomes focused. ...

Fires before a component becomes focused. Return `false` to prevent the component from gaining focus.

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### componentfocus

Fires after a component becomes focused. ...

Fires after a component becomes focused.

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### disable

Fires when the FocusManager is disabled ...

Fires when the FocusManager is disabled

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### enable

Fires when the FocusManager is enabled ...

Fires when the FocusManager is enabled

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### $focus-frame-color

**Type:** color

The border-color of the focusFrame. ...

The border-color of the focusFrame. See enable. Defaults to: `rgb ( 21 , 66 , 139 )`


### $focus-frame-style

**Type:** color

The border-style of the focusFrame. ...

The border-style of the focusFrame. See enable. Defaults to: `solid`


### $focus-frame-width

**Type:** color

The border-width of the focusFrame. ...

The border-width of the focusFrame. See enable. Defaults to: `2px`


## Properties

### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### configMap

**Type:** Object

...

Defaults to: `{}`


### enabled

**Type:** Boolean

Whether or not the FocusManager is currently enabled ...

Whether or not the FocusManager is currently enabled Defaults to: `false`


### eventsSuspended

**Type:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called. Defaults to: `0`


### focusFrameCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'focus-frame'`


### focusedCmp

**Type:** Ext.Component

The currently focused component.


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


### whitelist

**Type:** String[]

A list of xtypes that should ignore certain navigation input keys and allow for the default browser event/behavior. ...

A list of xtypes that should ignore certain navigation input keys and allow for the default browser event/behavior. These input keys include: - Backspace - Delete - Left - Right - Up - Down The FocusManager will not attempt to navigate when a component is an xtype (or descendents thereof) that belongs to this whitelist. E.g., an Ext.form.field.Text should allow the user to move the input cursor left and right, and to delete characters, etc. Defaults to: `['textfield']`


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.FocusManager

...

**Parameters:** config : Object


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


### addXTypeToWhitelist

Adds the specified xtype to the whitelist. ...

Adds the specified xtype to the whitelist.

**Parameters:** xtype : String/String[]Adds the xtype(s) to the whitelist.


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


### clearComponent

...

**Parameters:** cmp : Object


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


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### disable

Disables the FocusManager by turning of all automatic focus management and keyboard navigation ...

Disables the FocusManager by turning of all automatic focus management and keyboard navigation


### enable

Enables the FocusManager by turning on all automatic focus management and keyboard navigation ...

Enables the FocusManager by turning on all automatic focus management and keyboard navigation

**Parameters:** options : Boolean/ObjectEither `true`/`false` to turn on the focus frame, or an object with the following options: focusFrame : Boolean (optional)`true` to show the focus frame around a component when it is focused. Defaults to: `false`


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


### focusLast

...

**Parameters:** e : Object


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getConfig

...

**Parameters:** name : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getRootComponents

...


### handleComponentFocus

...

**Parameters:** cmp : Object


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


### initDOM

...

**Parameters:** options : Object


### isWhitelisted

...

**Parameters:** cmp : Object


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener. Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener. Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### navigateIn

...

**Parameters:** e : Object


### navigateOut

...

**Parameters:** e : Object


### navigateSiblings

...

**Parameters:** e : Object


### on

Shorthand for addListener. ...

Shorthand for addListener. Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### onComponentBlur

...

**Parameters:** cmp : Object


### onComponentDestroy

...


### onComponentFocus

...

**Parameters:** cmp : Object


### onComponentHide

...

**Parameters:** cmp : Object


### onConfigUpdate

...

**Parameters:** names : Object


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a class derives from this class or uses this class as a mixin.

**Parameters:** T : FunctionThe class constructor to prepare.


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`. For example if you are extending Grid, you might decide to forward some events from store. So you can do this inside your initComponent: The grid instance will then have an observable 'load' event which will be passed the parameters of the store's load event and any function fired with the grid's load event would have access to the grid using the `this` keyword.

**Parameters:** origin : ObjectThe Observable whose events this object is to relay.


### removeDOM

...


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


### removeXTypeFromWhitelist

Removes the specified xtype from the whitelist. ...

Removes the specified xtype from the whitelist.

**Parameters:** xtype : String/String[]Removes the xtype(s) from the whitelist.


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


### setupSubscriberKeys

...

**Parameters:** container : Object


### shouldShowFocusFrame

...

**Parameters:** cmp : Object


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


### beforecomponentfocus

Fires before a component becomes focused. ...

Fires before a component becomes focused. Return `false` to prevent the component from gaining focus.

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### componentfocus

Fires after a component becomes focused. ...

Fires after a component becomes focused.

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### disable

Fires when the FocusManager is disabled ...

Fires when the FocusManager is disabled

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### enable

Fires when the FocusManager is enabled ...

Fires when the FocusManager is enabled

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### $focus-frame-color

**Type:** color

The border-color of the focusFrame. ...

The border-color of the focusFrame. See enable. Defaults to: `rgb ( 21 , 66 , 139 )`


### $focus-frame-style

**Type:** color

The border-style of the focusFrame. ...

The border-style of the focusFrame. See enable. Defaults to: `solid`


### $focus-frame-width

**Type:** color

The border-width of the focusFrame. ...

The border-width of the focusFrame. See enable. Defaults to: `2px`


## Methods

### Ext.FocusManager

...

**Parameters:** config : Object


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


### addXTypeToWhitelist

Adds the specified xtype to the whitelist. ...

Adds the specified xtype to the whitelist.

**Parameters:** xtype : String/String[]Adds the xtype(s) to the whitelist.


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


### clearComponent

...

**Parameters:** cmp : Object


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


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### disable

Disables the FocusManager by turning of all automatic focus management and keyboard navigation ...

Disables the FocusManager by turning of all automatic focus management and keyboard navigation


### enable

Enables the FocusManager by turning on all automatic focus management and keyboard navigation ...

Enables the FocusManager by turning on all automatic focus management and keyboard navigation

**Parameters:** options : Boolean/ObjectEither `true`/`false` to turn on the focus frame, or an object with the following options: focusFrame : Boolean (optional)`true` to show the focus frame around a component when it is focused. Defaults to: `false`


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


### focusLast

...

**Parameters:** e : Object


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getConfig

...

**Parameters:** name : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getRootComponents

...


### handleComponentFocus

...

**Parameters:** cmp : Object


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


### initDOM

...

**Parameters:** options : Object


### isWhitelisted

...

**Parameters:** cmp : Object


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener. Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener. Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### navigateIn

...

**Parameters:** e : Object


### navigateOut

...

**Parameters:** e : Object


### navigateSiblings

...

**Parameters:** e : Object


### on

Shorthand for addListener. ...

Shorthand for addListener. Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### onComponentBlur

...

**Parameters:** cmp : Object


### onComponentDestroy

...


### onComponentFocus

...

**Parameters:** cmp : Object


### onComponentHide

...

**Parameters:** cmp : Object


### onConfigUpdate

...

**Parameters:** names : Object


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a class derives from this class or uses this class as a mixin.

**Parameters:** T : FunctionThe class constructor to prepare.


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`. For example if you are extending Grid, you might decide to forward some events from store. So you can do this inside your initComponent: The grid instance will then have an observable 'load' event which will be passed the parameters of the store's load event and any function fired with the grid's load event would have access to the grid using the `this` keyword.

**Parameters:** origin : ObjectThe Observable whose events this object is to relay.


### removeDOM

...


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


### removeXTypeFromWhitelist

Removes the specified xtype from the whitelist. ...

Removes the specified xtype from the whitelist.

**Parameters:** xtype : String/String[]Removes the xtype(s) from the whitelist.


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


### setupSubscriberKeys

...

**Parameters:** container : Object


### shouldShowFocusFrame

...

**Parameters:** cmp : Object


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


### beforecomponentfocus

Fires before a component becomes focused. ...

Fires before a component becomes focused. Return `false` to prevent the component from gaining focus.

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### componentfocus

Fires after a component becomes focused. ...

Fires after a component becomes focused.

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### disable

Fires when the FocusManager is disabled ...

Fires when the FocusManager is disabled

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### enable

Fires when the FocusManager is enabled ...

Fires when the FocusManager is enabled

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### $focus-frame-color

**Type:** color

The border-color of the focusFrame. ...

The border-color of the focusFrame. See enable. Defaults to: `rgb ( 21 , 66 , 139 )`


### $focus-frame-style

**Type:** color

The border-style of the focusFrame. ...

The border-style of the focusFrame. See enable. Defaults to: `solid`


### $focus-frame-width

**Type:** color

The border-width of the focusFrame. ...

The border-width of the focusFrame. See enable. Defaults to: `2px`


## Events

### beforecomponentfocus

Fires before a component becomes focused. ...

Fires before a component becomes focused. Return `false` to prevent the component from gaining focus.

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### componentfocus

Fires after a component becomes focused. ...

Fires after a component becomes focused.

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### disable

Fires when the FocusManager is disabled ...

Fires when the FocusManager is disabled

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### enable

Fires when the FocusManager is enabled ...

Fires when the FocusManager is enabled

**Parameters:** fm : Ext.FocusManagerA reference to the FocusManager singleton


### $focus-frame-color

**Type:** color

The border-color of the focusFrame. ...

The border-color of the focusFrame. See enable. Defaults to: `rgb ( 21 , 66 , 139 )`


### $focus-frame-style

**Type:** color

The border-style of the focusFrame. ...

The border-style of the focusFrame. See enable. Defaults to: `solid`


### $focus-frame-width

**Type:** color

The border-width of the focusFrame. ...

The border-width of the focusFrame. See enable. Defaults to: `2px`


## CSS Variables

### $focus-frame-color

**Type:** color

The border-color of the focusFrame. ...

The border-color of the focusFrame. See enable. Defaults to: `rgb ( 21 , 66 , 139 )`


### $focus-frame-style

**Type:** color

The border-style of the focusFrame. ...

The border-style of the focusFrame. See enable. Defaults to: `solid`


### $focus-frame-width

**Type:** color

The border-width of the focusFrame. ...

The border-width of the focusFrame. See enable. Defaults to: `2px`


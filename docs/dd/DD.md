# Ext.dd.DD

**Extends:** Ext.dd.DragDrop

## Description

A DragDrop implementation where the linked element follows the mouse cursor during a drag.

## Properties

### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### __ygDragDrop

**Type:** Boolean

Internal typeof flag ...

Internal typeof flag Defaults to: `true`


### _domRef

**Type:** Object

Cached reference to the linked element


### available

**Type:** Boolean

The available property is false until the linked dom element is accessible. ...

The available property is false until the linked dom element is accessible. Defaults to: `false`


### config

**Type:** Object

Configuration attributes passed into the constructor


### configMap

**Type:** Object

...

Defaults to: `{}`


### constrainX

**Type:** Boolean

Set to true when horizontal contraints are applied ...

Set to true when horizontal contraints are applied Defaults to: `false`


### constrainY

**Type:** Boolean

Set to true when vertical contraints are applied ...

Set to true when vertical contraints are applied Defaults to: `false`


### defaultPadding

**Type:** Object

Provides default constraint padding to "constrainTo" elements. ...

Provides default constraint padding to "constrainTo" elements. Defaults to: `{left: 0, right: 0, top: 0, bottom: 0}`


### dragElId

**Type:** String

The id of the element that will be dragged. ...

The id of the element that will be dragged. By default this is same as the linked element, but could be changed to another element. Ex: Ext.dd.DDProxy


### groups

**Type:** Object

The group defines a logical collection of DragDrop objects that are related. ...

The group defines a logical collection of DragDrop objects that are related. Instances only get events when interacting with other DragDrop object in the same group. This lets us define multiple groups using a single DragDrop subclass if we want. An object in the format {'group1':true, 'group2':true}


### handleElId

**Type:** String

The ID of the element that initiates the drag operation. ...

The ID of the element that initiates the drag operation. By default this is the linked element, but could be changed to be a child of this element. This lets us do things like only starting the drag when the header element within the linked html element is clicked.


### hasOuterHandles

**Type:** Boolean

By default, drags can only be initiated if the mousedown occurs in the region the linked element is. ...

By default, drags can only be initiated if the mousedown occurs in the region the linked element is. This is done in part to work around a bug in some browsers that mis-report the mousedown if the previous mouseup happened outside of the window. This property is set to true if outer handles are defined. Defaults to false. Defaults to: `false`


### id

**Type:** String

The id of the element associated with this object. ...

The id of the element associated with this object. This is what we refer to as the "linked element" because the size and position of this element is used to determine when the drag and drop objects have interacted.


### ignoreSelf

**Type:** Boolean

Set to false to enable a DragDrop object to fire drag events while dragging over its own Element. ...

Set to false to enable a DragDrop object to fire drag events while dragging over its own Element. Defaults to true - DragDrop objects do not by default fire drag events to themselves.


### initConfigList

**Type:** Array

...

Defaults to: `[]`


### initConfigMap

**Type:** Object

...

Defaults to: `{}`


### invalidHandleClasses

**Type:** String[]

An Array of CSS class names for elements to be considered in valid as drag handles.


### invalidHandleIds

**Type:** Object

An object who's property names identify the IDs of elements to be considered invalid as drag handles. ...

An object who's property names identify the IDs of elements to be considered invalid as drag handles. A non-null property value identifies the ID as invalid. For example, to prevent dragging from being initiated on element ID "foo", use:


### invalidHandleTypes

**Type:** Object

An object who's property names identify HTML tags to be considered invalid as drag handles. ...

An object who's property names identify HTML tags to be considered invalid as drag handles. A non-null property value identifies the tag as invalid. Defaults to the following value which prevents drag operations from being initiated by `<a>` elements:


### isInstance

**Type:** Boolean

...

Defaults to: `true`


### isTarget

**Type:** Boolean

By default, all instances can be a drop target. ...

By default, all instances can be a drop target. This can be disabled by setting isTarget to false. Defaults to: `true`


### locked

**Type:** Boolean

Individual drag/drop instances can be locked. ...

Individual drag/drop instances can be locked. This will prevent onmousedown start drag. Defaults to: `false`


### maintainOffset

**Type:** Boolean

Maintain offsets when we resetconstraints. ...

Maintain offsets when we resetconstraints. Set to true when you want the position of the element relative to its parent to stay the same when the page changes Defaults to: `false`


### maxX

**Type:** Number

The right constraint ...

The right constraint Defaults to: `0`


### maxY

**Type:** Number

The down constraint ...

The down constraint Defaults to: `0`


### minX

**Type:** Number

The left constraint ...

The left constraint Defaults to: `0`


### minY

**Type:** Number

The up constraint ...

The up constraint Defaults to: `0`


### moveOnly

**Type:** Boolean

When set to true, other DD objects in cooperating DDGroups do not receive notification events when this DD object is ...

When set to true, other DD objects in cooperating DDGroups do not receive notification events when this DD object is dragged over them. Defaults to: `false`


### padding

**Type:** Number[]

The padding configured for this drag and drop object for calculating the drop zone intersection with this object. ...

The padding configured for this drag and drop object for calculating the drop zone intersection with this object. An array containing the 4 padding values: [top, right, bottom, left]


### primaryButtonOnly

**Type:** Boolean

By default the drag and drop instance will only respond to the primary button click (left button for a right-handed m...

By default the drag and drop instance will only respond to the primary button click (left button for a right-handed mouse). Set to true to allow drag and drop to start with any mouse click that is propogated by the browser Defaults to: `true`


### scroll

**Type:** Boolean

When set to true, the utility automatically tries to scroll the browser window when a drag and drop element is dragge...

When set to true, the utility automatically tries to scroll the browser window when a drag and drop element is dragged near the viewport boundary. Defaults to: `true`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### startPageX

**Type:** Number

The linked element's absolute X position at the time the drag was started ...

The linked element's absolute X position at the time the drag was started Defaults to: `0`


### startPageY

**Type:** Number

The linked element's absolute X position at the time the drag was started ...

The linked element's absolute X position at the time the drag was started Defaults to: `0`


### xTicks

**Type:** Number[]

Array of pixel locations the element will snap to if we specified a horizontal graduation/interval. ...

Array of pixel locations the element will snap to if we specified a horizontal graduation/interval. This array is generated automatically when you define a tick interval.


### yTicks

**Type:** Number[]

Array of pixel locations the element will snap to if we specified a vertical graduation/interval. ...

Array of pixel locations the element will snap to if we specified a vertical graduation/interval. This array is generated automatically when you define a tick interval.


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.dd.DD

Creates new DD instance. ...

Creates new DD instance.

**Parameters:** id : Stringthe id of the linked element


### addInvalidHandleClass

Lets you specify a css class of elements that will not initiate a drag ...

Lets you specify a css class of elements that will not initiate a drag

**Parameters:** cssClass : Stringthe class of the elements you wish to ignore


### addInvalidHandleId

Lets you to specify an element id for a child of a drag handle that should not initiate a drag ...

Lets you to specify an element id for a child of a drag handle that should not initiate a drag

**Parameters:** id : Stringthe element id of the element you wish to ignore


### addInvalidHandleType

Allows you to specify a tag name that should not start a drag operation when clicked. ...

Allows you to specify a tag name that should not start a drag operation when clicked. This is designed to facilitate embedding links within a drag handle that do something other than start the drag.

**Parameters:** tagName : Stringthe type of element to exclude


### addToGroup

Adds this instance to a group of related drag/drop objects. ...

Adds this instance to a group of related drag/drop objects. All instances belong to at least one group, and can belong to as many groups as needed.

**Parameters:** sGroup : Stringthe name of the group


### alignElWithMouse

Sets the element to the location of the mousedown or click event, maintaining the cursor location relative to the loc...

Sets the element to the location of the mousedown or click event, maintaining the cursor location relative to the location on the element that was clicked. Override this if you want to place the element in a location other than where the cursor is.

**Parameters:** el : HTMLElementthe element to move


### applyConfig

Sets up config options specific to this class. ...

Sets up config options specific to this class. Overrides Ext.dd.DragDrop, but all versions of this method through the inheritance chain are called Overrides: Ext.dd.DragDrop.applyConfig


### autoOffset

Sets the pointer offset to the distance between the linked element's top left corner and the location the element was...

Sets the pointer offset to the distance between the linked element's top left corner and the location the element was clicked.

**Parameters:** iPageX : Numberthe X coordinate of the click


### autoScroll

Auto-scroll the window if the dragged object has been moved beyond the visible window boundary. ...

Auto-scroll the window if the dragged object has been moved beyond the visible window boundary.

**Parameters:** x : Numberthe drag element's x position


### b4Drag

Event that fires prior to the onDrag event. ...

Event that fires prior to the onDrag event. Overrides Ext.dd.DragDrop.

**Parameters:** e : Object


### b4DragDrop

Code that executes immediately before the onDragDrop event ...

Code that executes immediately before the onDragDrop event

**Parameters:** e : Object


### b4DragOut

Code that executes immediately before the onDragOut event ...

Code that executes immediately before the onDragOut event

**Parameters:** e : Object


### b4DragOver

Code that executes immediately before the onDragOver event ...

Code that executes immediately before the onDragOver event

**Parameters:** e : Object


### b4EndDrag

Code that executes immediately before the endDrag event ...

Code that executes immediately before the endDrag event

**Parameters:** e : Object


### b4MouseDown

Event that fires prior to the onMouseDown event. ...

Event that fires prior to the onMouseDown event. Overrides Ext.dd.DragDrop.

**Parameters:** e : Object


### b4StartDrag

Code that executes immediately before the startDrag event ...

Code that executes immediately before the startDrag event

**Parameters:** x : Object


### cachePosition

Saves the most recent position so that we can reset the constraints and tick marks on-demand. ...

Saves the most recent position so that we can reset the constraints and tick marks on-demand. We need to know this so that we can calculate the number of pixels the element is offset from its original position.

**Parameters:** iPageX : Number (optional)the current x position (this just makes it so we don't have to look it up again)


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


### clearConstraints

Clears any constraints applied to this instance. ...

Clears any constraints applied to this instance. Also clears ticks since they can't exist independent of a constraint at this time.


### clearTicks

Clears any tick interval defined for this instance ...

Clears any tick interval defined for this instance


### clickValidator

...

**Parameters:** e : Object


### configClass

...


### constrainTo

Initializes the drag drop object's constraints to restrict movement to a certain element. ...

Initializes the drag drop object's constraints to restrict movement to a certain element. Usage: Or you can initalize it using the Ext.Element object:

**Parameters:** constrainTo : String/HTMLElement/Ext.ElementThe element or element ID to constrain to.


### destroy

Destroy this DragDrop instance ...

Destroy this DragDrop instance Overrides: Ext.Base.destroy


### endDrag

Called when we are done dragging the object ...

Called when we are done dragging the object

**Parameters:** e : Eventthe mouseup event


### getConfig

...

**Parameters:** name : Object


### getDragEl

Returns a reference to the actual element to drag. ...

**Returns:** a reference to the actual element to drag. By default this is the same as the html element, but it can be assigned to another element. An example of this can be found in Ext.dd.DDProxy ReturnsHTMLElementthe html element


### getEl

Returns a reference to the linked element ...

**Returns:** a reference to the linked element ReturnsHTMLElementthe html element


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getLocalX

...

**Parameters:** el : Object


### getTargetCoord

Finds the location the element should be placed if we want to move it to where the mouse location less the click offs...

Finds the location the element should be placed if we want to move it to where the mouse location less the click offset would place us.

**Parameters:** iPageX : Numberthe X coordinate of the click


### getTick

Normally the drag element is moved pixel by pixel, but we can specify that it move a number of pixels at a time. ...

Normally the drag element is moved pixel by pixel, but we can specify that it move a number of pixels at a time. This method resolves the location when we have it set up like this.

**Parameters:** val : Numberwhere we want to place the object


### handleMouseDown

Called when this object is clicked ...

Called when this object is clicked

**Parameters:** e : Event


### handleOnAvailable

Executed when the linked element is available ...

Executed when the linked element is available


### hasConfig

...

**Parameters:** config : Object


### init

Sets up the DragDrop object. ...

Sets up the DragDrop object. Must be called in the constructor of any Ext.dd.DragDrop subclass

**Parameters:** id : Stringthe id of the linked element


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initTarget

Initializes Targeting functionality only... ...

Initializes Targeting functionality only... the object does not get a mousedown handler.

**Parameters:** id : Stringthe id of the linked element


### isLocked

Returns true if this instance is locked, or the drag drop mgr is locked (meaning that all drag/drop is disabled on th...

**Returns:** true if this instance is locked, or the drag drop mgr is locked (meaning that all drag/drop is disabled on the page.) ReturnsBooleantrue if this obj or all drag/drop is locked, else false


### isValidHandleChild

Checks the tag exclusion list to see if this click should be ignored ...

Checks the tag exclusion list to see if this click should be ignored

**Parameters:** node : HTMLElementthe HTMLElement to evaluate


### lock

Locks this instance ...

Locks this instance


### onAvailable

Override the onAvailable method to do what is needed after the initial position was determined. ...

Override the onAvailable method to do what is needed after the initial position was determined.


### onConfigUpdate

...

**Parameters:** names : Object


### onDrag

Abstract method called during the onMouseMove event while dragging an object. ...

Abstract method called during the onMouseMove event while dragging an object.

**Parameters:** e : Eventthe mousemove event


### onDragDrop

Abstract method called when this item is dropped on another DragDrop obj ...

Abstract method called when this item is dropped on another DragDrop obj

**Parameters:** e : Eventthe mouseup event


### onDragEnter

Abstract method called when this element fist begins hovering over another DragDrop obj ...

Abstract method called when this element fist begins hovering over another DragDrop obj

**Parameters:** e : Eventthe mousemove event


### onDragOut

Abstract method called when we are no longer hovering over an element ...

Abstract method called when we are no longer hovering over an element

**Parameters:** e : Eventthe mousemove event


### onDragOver

Abstract method called when this element is hovering over another DragDrop obj ...

Abstract method called when this element is hovering over another DragDrop obj

**Parameters:** e : Eventthe mousemove event


### onInvalidDrop

Abstract method called when this item is dropped on an area with no drop target ...

Abstract method called when this item is dropped on an area with no drop target

**Parameters:** e : Eventthe mouseup event


### onMouseDown

Called when a drag/drop obj gets a mousedown ...

Called when a drag/drop obj gets a mousedown

**Parameters:** e : Eventthe mousedown event


### onMouseUp

Called when a drag/drop obj gets a mouseup ...

Called when a drag/drop obj gets a mouseup

**Parameters:** e : Eventthe mouseup event


### removeFromGroup

Removes this instance from the supplied interaction group ...

Removes this instance from the supplied interaction group

**Parameters:** sGroup : StringThe group to drop


### removeInvalidHandleClass

Unsets an invalid css class ...

Unsets an invalid css class

**Parameters:** cssClass : Stringthe class of the element(s) you wish to re-enable


### removeInvalidHandleId

Unsets an invalid handle id ...

Unsets an invalid handle id

**Parameters:** id : Stringthe id of the element to re-enable


### removeInvalidHandleType

Unsets an excluded tag name set by addInvalidHandleType ...

Unsets an excluded tag name set by addInvalidHandleType

**Parameters:** tagName : Stringthe type of element to unexclude


### resetConstraints

Must be called if you manually reposition a dd element. ...

Must be called if you manually reposition a dd element.

**Parameters:** maintainOffset : Boolean


### setConfig

...

**Parameters:** config : Object


### setDelta

Sets the pointer offset. ...

Sets the pointer offset. You can call this directly to force the offset to be in a particular location (e.g., pass in 0,0 to set it to the center of the object)

**Parameters:** iDeltaX : Numberthe distance from the left


### setDragElId

Allows you to specify that an element other than the linked element will be moved with the cursor during a drag ...

Allows you to specify that an element other than the linked element will be moved with the cursor during a drag

**Parameters:** id : Stringthe id of the element that will be used to initiate the drag


### setDragElPos

Sets the drag element to the location of the mousedown or click event, maintaining the cursor location relative to th...

Sets the drag element to the location of the mousedown or click event, maintaining the cursor location relative to the location on the element that was clicked. Override this if you want to place the element in a location other than where the cursor is.

**Parameters:** iPageX : Numberthe X coordinate of the mousedown or drag event


### setHandleElId

Allows you to specify a child of the linked element that should be used to initiate the drag operation. ...

Allows you to specify a child of the linked element that should be used to initiate the drag operation. An example of this would be if you have a content div with text and links. Clicking anywhere in the content area would normally start the drag operation. Use this method to specify that an element inside of the content div is the element that starts the drag operation.

**Parameters:** id : Stringthe id of the element that will be used to initiate the drag.


### setInitPosition

Stores the initial placement of the linked element. ...

Stores the initial placement of the linked element.

**Parameters:** diffX : Numberthe X offset, default 0


### setLocalXY

...

**Parameters:** el : Object


### setOuterHandleElId

Allows you to set an element outside of the linked element as a drag handle ...

Allows you to set an element outside of the linked element as a drag handle

**Parameters:** id : Stringthe id of the element that will be used to initiate the drag


### setPadding

Configures the padding for the target zone in px. ...

Configures the padding for the target zone in px. Effectively expands (or reduces) the virtual object size for targeting calculations. Supports css-style shorthand; if only one parameter is passed, all sides will have that padding, and if only two are passed, the top and bottom will have the first param, the left and right the second.

**Parameters:** iTop : NumberTop pad


### setStartPosition

Sets the start position of the element. ...

Sets the start position of the element. This is set when the obj is initialized, the reset when a drag is started.

**Parameters:** pos : Objectcurrent position (from previous lookup)


### setXConstraint

By default, the element can be dragged any place on the screen. ...

By default, the element can be dragged any place on the screen. Use this method to limit the horizontal travel of the element. Pass in 0,0 for the parameters if you want to lock the drag to the y axis.

**Parameters:** iLeft : Numberthe number of pixels the element can move to the left


### setXTicks

Creates the array of horizontal tick marks if an interval was specified in setXConstraint(). ...

Creates the array of horizontal tick marks if an interval was specified in setXConstraint().

**Parameters:** iStartX : Object


### setYConstraint

By default, the element can be dragged any place on the screen. ...

By default, the element can be dragged any place on the screen. Set this to limit the vertical travel of the element. Pass in 0,0 for the parameters if you want to lock the drag to the x axis.

**Parameters:** iUp : Numberthe number of pixels the element can move up


### setYTicks

Creates the array of vertical tick marks if an interval was specified in setYConstraint(). ...

Creates the array of vertical tick marks if an interval was specified in setYConstraint().

**Parameters:** iStartY : Object


### startDrag

Abstract method called after a drag/drop object is clicked and the drag or mousedown time thresholds have beeen met. ...

Abstract method called after a drag/drop object is clicked and the drag or mousedown time thresholds have beeen met.

**Parameters:** x : NumberX click location


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### toString

toString method ...

toString method

**Returns:** Stringstring representation of the dd obj


### unlock

Unlocks this instace ...

Unlocks this instace


### unreg

Removes all drag and drop hooks for this element ...

Removes all drag and drop hooks for this element


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

### Ext.dd.DD

Creates new DD instance. ...

Creates new DD instance.

**Parameters:** id : Stringthe id of the linked element


### addInvalidHandleClass

Lets you specify a css class of elements that will not initiate a drag ...

Lets you specify a css class of elements that will not initiate a drag

**Parameters:** cssClass : Stringthe class of the elements you wish to ignore


### addInvalidHandleId

Lets you to specify an element id for a child of a drag handle that should not initiate a drag ...

Lets you to specify an element id for a child of a drag handle that should not initiate a drag

**Parameters:** id : Stringthe element id of the element you wish to ignore


### addInvalidHandleType

Allows you to specify a tag name that should not start a drag operation when clicked. ...

Allows you to specify a tag name that should not start a drag operation when clicked. This is designed to facilitate embedding links within a drag handle that do something other than start the drag.

**Parameters:** tagName : Stringthe type of element to exclude


### addToGroup

Adds this instance to a group of related drag/drop objects. ...

Adds this instance to a group of related drag/drop objects. All instances belong to at least one group, and can belong to as many groups as needed.

**Parameters:** sGroup : Stringthe name of the group


### alignElWithMouse

Sets the element to the location of the mousedown or click event, maintaining the cursor location relative to the loc...

Sets the element to the location of the mousedown or click event, maintaining the cursor location relative to the location on the element that was clicked. Override this if you want to place the element in a location other than where the cursor is.

**Parameters:** el : HTMLElementthe element to move


### applyConfig

Sets up config options specific to this class. ...

Sets up config options specific to this class. Overrides Ext.dd.DragDrop, but all versions of this method through the inheritance chain are called Overrides: Ext.dd.DragDrop.applyConfig


### autoOffset

Sets the pointer offset to the distance between the linked element's top left corner and the location the element was...

Sets the pointer offset to the distance between the linked element's top left corner and the location the element was clicked.

**Parameters:** iPageX : Numberthe X coordinate of the click


### autoScroll

Auto-scroll the window if the dragged object has been moved beyond the visible window boundary. ...

Auto-scroll the window if the dragged object has been moved beyond the visible window boundary.

**Parameters:** x : Numberthe drag element's x position


### b4Drag

Event that fires prior to the onDrag event. ...

Event that fires prior to the onDrag event. Overrides Ext.dd.DragDrop.

**Parameters:** e : Object


### b4DragDrop

Code that executes immediately before the onDragDrop event ...

Code that executes immediately before the onDragDrop event

**Parameters:** e : Object


### b4DragOut

Code that executes immediately before the onDragOut event ...

Code that executes immediately before the onDragOut event

**Parameters:** e : Object


### b4DragOver

Code that executes immediately before the onDragOver event ...

Code that executes immediately before the onDragOver event

**Parameters:** e : Object


### b4EndDrag

Code that executes immediately before the endDrag event ...

Code that executes immediately before the endDrag event

**Parameters:** e : Object


### b4MouseDown

Event that fires prior to the onMouseDown event. ...

Event that fires prior to the onMouseDown event. Overrides Ext.dd.DragDrop.

**Parameters:** e : Object


### b4StartDrag

Code that executes immediately before the startDrag event ...

Code that executes immediately before the startDrag event

**Parameters:** x : Object


### cachePosition

Saves the most recent position so that we can reset the constraints and tick marks on-demand. ...

Saves the most recent position so that we can reset the constraints and tick marks on-demand. We need to know this so that we can calculate the number of pixels the element is offset from its original position.

**Parameters:** iPageX : Number (optional)the current x position (this just makes it so we don't have to look it up again)


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


### clearConstraints

Clears any constraints applied to this instance. ...

Clears any constraints applied to this instance. Also clears ticks since they can't exist independent of a constraint at this time.


### clearTicks

Clears any tick interval defined for this instance ...

Clears any tick interval defined for this instance


### clickValidator

...

**Parameters:** e : Object


### configClass

...


### constrainTo

Initializes the drag drop object's constraints to restrict movement to a certain element. ...

Initializes the drag drop object's constraints to restrict movement to a certain element. Usage: Or you can initalize it using the Ext.Element object:

**Parameters:** constrainTo : String/HTMLElement/Ext.ElementThe element or element ID to constrain to.


### destroy

Destroy this DragDrop instance ...

Destroy this DragDrop instance Overrides: Ext.Base.destroy


### endDrag

Called when we are done dragging the object ...

Called when we are done dragging the object

**Parameters:** e : Eventthe mouseup event


### getConfig

...

**Parameters:** name : Object


### getDragEl

Returns a reference to the actual element to drag. ...

**Returns:** a reference to the actual element to drag. By default this is the same as the html element, but it can be assigned to another element. An example of this can be found in Ext.dd.DDProxy ReturnsHTMLElementthe html element


### getEl

Returns a reference to the linked element ...

**Returns:** a reference to the linked element ReturnsHTMLElementthe html element


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getLocalX

...

**Parameters:** el : Object


### getTargetCoord

Finds the location the element should be placed if we want to move it to where the mouse location less the click offs...

Finds the location the element should be placed if we want to move it to where the mouse location less the click offset would place us.

**Parameters:** iPageX : Numberthe X coordinate of the click


### getTick

Normally the drag element is moved pixel by pixel, but we can specify that it move a number of pixels at a time. ...

Normally the drag element is moved pixel by pixel, but we can specify that it move a number of pixels at a time. This method resolves the location when we have it set up like this.

**Parameters:** val : Numberwhere we want to place the object


### handleMouseDown

Called when this object is clicked ...

Called when this object is clicked

**Parameters:** e : Event


### handleOnAvailable

Executed when the linked element is available ...

Executed when the linked element is available


### hasConfig

...

**Parameters:** config : Object


### init

Sets up the DragDrop object. ...

Sets up the DragDrop object. Must be called in the constructor of any Ext.dd.DragDrop subclass

**Parameters:** id : Stringthe id of the linked element


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initTarget

Initializes Targeting functionality only... ...

Initializes Targeting functionality only... the object does not get a mousedown handler.

**Parameters:** id : Stringthe id of the linked element


### isLocked

Returns true if this instance is locked, or the drag drop mgr is locked (meaning that all drag/drop is disabled on th...

**Returns:** true if this instance is locked, or the drag drop mgr is locked (meaning that all drag/drop is disabled on the page.) ReturnsBooleantrue if this obj or all drag/drop is locked, else false


### isValidHandleChild

Checks the tag exclusion list to see if this click should be ignored ...

Checks the tag exclusion list to see if this click should be ignored

**Parameters:** node : HTMLElementthe HTMLElement to evaluate


### lock

Locks this instance ...

Locks this instance


### onAvailable

Override the onAvailable method to do what is needed after the initial position was determined. ...

Override the onAvailable method to do what is needed after the initial position was determined.


### onConfigUpdate

...

**Parameters:** names : Object


### onDrag

Abstract method called during the onMouseMove event while dragging an object. ...

Abstract method called during the onMouseMove event while dragging an object.

**Parameters:** e : Eventthe mousemove event


### onDragDrop

Abstract method called when this item is dropped on another DragDrop obj ...

Abstract method called when this item is dropped on another DragDrop obj

**Parameters:** e : Eventthe mouseup event


### onDragEnter

Abstract method called when this element fist begins hovering over another DragDrop obj ...

Abstract method called when this element fist begins hovering over another DragDrop obj

**Parameters:** e : Eventthe mousemove event


### onDragOut

Abstract method called when we are no longer hovering over an element ...

Abstract method called when we are no longer hovering over an element

**Parameters:** e : Eventthe mousemove event


### onDragOver

Abstract method called when this element is hovering over another DragDrop obj ...

Abstract method called when this element is hovering over another DragDrop obj

**Parameters:** e : Eventthe mousemove event


### onInvalidDrop

Abstract method called when this item is dropped on an area with no drop target ...

Abstract method called when this item is dropped on an area with no drop target

**Parameters:** e : Eventthe mouseup event


### onMouseDown

Called when a drag/drop obj gets a mousedown ...

Called when a drag/drop obj gets a mousedown

**Parameters:** e : Eventthe mousedown event


### onMouseUp

Called when a drag/drop obj gets a mouseup ...

Called when a drag/drop obj gets a mouseup

**Parameters:** e : Eventthe mouseup event


### removeFromGroup

Removes this instance from the supplied interaction group ...

Removes this instance from the supplied interaction group

**Parameters:** sGroup : StringThe group to drop


### removeInvalidHandleClass

Unsets an invalid css class ...

Unsets an invalid css class

**Parameters:** cssClass : Stringthe class of the element(s) you wish to re-enable


### removeInvalidHandleId

Unsets an invalid handle id ...

Unsets an invalid handle id

**Parameters:** id : Stringthe id of the element to re-enable


### removeInvalidHandleType

Unsets an excluded tag name set by addInvalidHandleType ...

Unsets an excluded tag name set by addInvalidHandleType

**Parameters:** tagName : Stringthe type of element to unexclude


### resetConstraints

Must be called if you manually reposition a dd element. ...

Must be called if you manually reposition a dd element.

**Parameters:** maintainOffset : Boolean


### setConfig

...

**Parameters:** config : Object


### setDelta

Sets the pointer offset. ...

Sets the pointer offset. You can call this directly to force the offset to be in a particular location (e.g., pass in 0,0 to set it to the center of the object)

**Parameters:** iDeltaX : Numberthe distance from the left


### setDragElId

Allows you to specify that an element other than the linked element will be moved with the cursor during a drag ...

Allows you to specify that an element other than the linked element will be moved with the cursor during a drag

**Parameters:** id : Stringthe id of the element that will be used to initiate the drag


### setDragElPos

Sets the drag element to the location of the mousedown or click event, maintaining the cursor location relative to th...

Sets the drag element to the location of the mousedown or click event, maintaining the cursor location relative to the location on the element that was clicked. Override this if you want to place the element in a location other than where the cursor is.

**Parameters:** iPageX : Numberthe X coordinate of the mousedown or drag event


### setHandleElId

Allows you to specify a child of the linked element that should be used to initiate the drag operation. ...

Allows you to specify a child of the linked element that should be used to initiate the drag operation. An example of this would be if you have a content div with text and links. Clicking anywhere in the content area would normally start the drag operation. Use this method to specify that an element inside of the content div is the element that starts the drag operation.

**Parameters:** id : Stringthe id of the element that will be used to initiate the drag.


### setInitPosition

Stores the initial placement of the linked element. ...

Stores the initial placement of the linked element.

**Parameters:** diffX : Numberthe X offset, default 0


### setLocalXY

...

**Parameters:** el : Object


### setOuterHandleElId

Allows you to set an element outside of the linked element as a drag handle ...

Allows you to set an element outside of the linked element as a drag handle

**Parameters:** id : Stringthe id of the element that will be used to initiate the drag


### setPadding

Configures the padding for the target zone in px. ...

Configures the padding for the target zone in px. Effectively expands (or reduces) the virtual object size for targeting calculations. Supports css-style shorthand; if only one parameter is passed, all sides will have that padding, and if only two are passed, the top and bottom will have the first param, the left and right the second.

**Parameters:** iTop : NumberTop pad


### setStartPosition

Sets the start position of the element. ...

Sets the start position of the element. This is set when the obj is initialized, the reset when a drag is started.

**Parameters:** pos : Objectcurrent position (from previous lookup)


### setXConstraint

By default, the element can be dragged any place on the screen. ...

By default, the element can be dragged any place on the screen. Use this method to limit the horizontal travel of the element. Pass in 0,0 for the parameters if you want to lock the drag to the y axis.

**Parameters:** iLeft : Numberthe number of pixels the element can move to the left


### setXTicks

Creates the array of horizontal tick marks if an interval was specified in setXConstraint(). ...

Creates the array of horizontal tick marks if an interval was specified in setXConstraint().

**Parameters:** iStartX : Object


### setYConstraint

By default, the element can be dragged any place on the screen. ...

By default, the element can be dragged any place on the screen. Set this to limit the vertical travel of the element. Pass in 0,0 for the parameters if you want to lock the drag to the x axis.

**Parameters:** iUp : Numberthe number of pixels the element can move up


### setYTicks

Creates the array of vertical tick marks if an interval was specified in setYConstraint(). ...

Creates the array of vertical tick marks if an interval was specified in setYConstraint().

**Parameters:** iStartY : Object


### startDrag

Abstract method called after a drag/drop object is clicked and the drag or mousedown time thresholds have beeen met. ...

Abstract method called after a drag/drop object is clicked and the drag or mousedown time thresholds have beeen met.

**Parameters:** x : NumberX click location


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### toString

toString method ...

toString method

**Returns:** Stringstring representation of the dd obj


### unlock

Unlocks this instace ...

Unlocks this instace


### unreg

Removes all drag and drop hooks for this element ...

Removes all drag and drop hooks for this element


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


# Ext.layout.ContextItem

**Extends:** Ext.Base

## Description

**NOTE** This is a private utility class for internal use by the framework. Don't rely on its existence.

This class manages state information for a component or element during a layout.

A "block" is a required value that is preventing further calculation. When a layout has encountered a situation where it cannot possibly calculate results, it can associate itself with the context item and missing property so that it will not be rescheduled until that property is set.

Blocks are a one-shot registration. Once the property changes, the block is removed.

Be careful with blocks. If *any* further calculations can be made, a block is not the right choice.

Whenever any call to getProp, getDomProp, hasProp or hasDomProp is made, the current layout is automatically registered as being dependent on that property in the appropriate state. Any changes to the property will trigger the layout and it will be queued in the Ext.layout.Context.

Triggers, once added, remain for the entire layout. Any changes to the property will reschedule all unfinished layouts in their trigger set.

## Properties

### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### borderNames

**Type:** Array

...

Defaults to: `['border-top-width', 'border-right-width', 'border-bottom-width', 'border-left-width']`


### boxChildren

**Type:** Object

plaed here by AbstractComponent.getSizeModel


### boxParent

**Type:** Object


### cacheMissHandlers

**Type:** Object


### children

**Type:** Array

...

Defaults to: `[]`


### configMap

**Type:** Object

...

Defaults to: `{}`


### consumersContainerHeight

**Type:** Number

...

Defaults to: `0`


### consumersContainerWidth

**Type:** Number

...

Defaults to: `0`


### consumersContentHeight

**Type:** Number

...

Defaults to: `0`


### consumersContentWidth

**Type:** Number

...

Defaults to: `0`


### consumersHeight

**Type:** Number

...

Defaults to: `0`


### consumersWidth

**Type:** Number

...

Defaults to: `0`


### dirty

**Type:** Object


### dirtyCount

**Type:** Number

The number of dirty properties ...

The number of dirty properties Defaults to: `0`


### hasRawContent

**Type:** Boolean

...

Defaults to: `true`


### heightModel

**Type:** Object


### initConfigList

**Type:** Array

...

Defaults to: `[]`


### initConfigMap

**Type:** Object

...

Defaults to: `{}`


### isBorderBoxValue

**Type:** Object


### isContextItem

**Type:** Boolean

...

Defaults to: `true`


### isInstance

**Type:** Boolean

...

Defaults to: `true`


### isTopLevel

**Type:** Boolean

...

Defaults to: `false`


### marginNames

**Type:** Array

...

Defaults to: `['margin-top', 'margin-right', 'margin-bottom', 'margin-left']`


### optOut

**Type:** Boolean

There are several cases that allow us to skip (opt out) of laying out a component and its children as long as its las...

There are several cases that allow us to skip (opt out) of laying out a component and its children as long as its `lastBox` is not marked as `invalid`. If anything happens to change things, the `lastBox` is marked as `invalid` by `updateLayout` as it ascends the component hierarchy. Defaults to: `false`


### ownerCtContext

**Type:** Object


### ownerSizePolicy

**Type:** Object


### paddingNames

**Type:** Array

...

Defaults to: `['padding-top', 'padding-right', 'padding-bottom', 'padding-left']`


### props

**Type:** Object

the current set of property values:


### remainingChildDimensions

**Type:** Number

...

Defaults to: `0`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### sizeModel

**Type:** Object


### state

**Type:** Object

State variables that are cleared when invalidated. ...

State variables that are cleared when invalidated. Only applies to component items.


### styles

**Type:** Object

Adds x and y values from a props object to a styles object as "left" and "top" values. ...

Adds x and y values from a props object to a styles object as "left" and "top" values. Overridden to add the x property as "right" in rtl mode. A styles object for an Element A ContextItem props object


### translateProps

**Type:** Object

...

Defaults to: `{x: 'left', y: 'top'}`


### trblNames

**Type:** Array

...

Defaults to: `['top', 'right', 'bottom', 'left']`


### widthModel

**Type:** Object


### wrapsComponent

**Type:** Boolean

True if this item wraps a Component (rather than an Element). ...

True if this item wraps a Component (rather than an Element). Defaults to: `false`


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.layout.ContextItem

...

**Parameters:** config : Object


### addBlock

Adds a block. ...

Adds a block. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** name : StringThe name of the block list ('blocks' or 'domBlocks').


### addBoxChild

Overridden in Ext.diag.layout.ContextItem. ...

**Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** boxChildItem : Object


### addCls

Queue the addition of a class name (or array of class names) to this ContextItem's target when next flushed. ...

Queue the addition of a class name (or array of class names) to this ContextItem's target when next flushed.

**Parameters:** newCls : Object


### addTrigger

Adds a trigger. ...

Adds a trigger. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** propName : StringThe property name that triggers the layout (e.g., 'width').


### block

Registers a layout in the block list for the given property. ...

Registers a layout in the block list for the given property. Once the property is set in the Ext.layout.Context, the layout is unblocked.

**Parameters:** layout : Ext.layout.Layout


### boxChildMeasured

...


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


### checkAuthority

Defined in override Ext.diag.layout.ContextItem. ...

**Defined in override Ext.diag.layout.ContextItem.**

**Parameters:** prop : Object


### checkCache

...

**Parameters:** entry : Object


### clearAllBlocks

...

**Parameters:** name : Object


### clearBlocks

Removes any blocks on a property in the specified set. ...

Removes any blocks on a property in the specified set. Any layouts that were blocked by this property and are not still blocked (by other properties) will be rescheduled. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** name : StringThe name of the block list ('blocks' or 'domBlocks').


### clearMarginCache

clears the margin cache so that marginInfo get re-read from the dom on the next call to getMarginInfo() This is neede...

clears the margin cache so that marginInfo get re-read from the dom on the next call to getMarginInfo() This is needed in some special cases where the margins have changed since the last layout, making the cached values invalid. For example collapsed window headers have different margin than expanded ones.


### configClass

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### domBlock

Registers a layout in the DOM block list for the given property. ...

Registers a layout in the DOM block list for the given property. Once the property flushed to the DOM by the Ext.layout.Context, the layout is unblocked.

**Parameters:** layout : Ext.layout.Layout


### fireTriggers

Reschedules any layouts associated with a given trigger. ...

Reschedules any layouts associated with a given trigger.

**Parameters:** name : StringThe name of the trigger list ('triggers' or 'domTriggers').


### flush

Flushes any updates in the dirty collection to the DOM. ...

Flushes any updates in the dirty collection to the DOM. This is only called if there are dirty entries because this object is only added to the flushQueue of the Ext.layout.Context when entries become dirty.


### flushAnimations

...


### getBorderInfo

Gets the border information for the element as an object with left, top, right and bottom properties holding border s...

Gets the border information for the element as an object with left, top, right and bottom properties holding border size in pixels. This object is only read from the DOM on first request and is cached.

**Returns:** Object


### getClassList

Returns a ClassList-like object to buffer access to this item's element's classes. ...

**Returns:** a ClassList-like object to buffer access to this item's element's classes.


### getConfig

...

**Parameters:** name : Object


### getDomProp

Gets a property of this object if it is correct in the DOM. ...

Gets a property of this object if it is correct in the DOM. Also tracks the current layout as dependent on this property so that DOM writes of it will trigger the layout to be recalculated.

**Parameters:** propName : StringThe property name (e.g., 'width').


### getEl

Returns the context item for an owned element. ...

**Parameters:** nameOrEl : String/Ext.dom.ElementThe element or the name of an owned element

**Returns:** the context item for an owned element. This should only be called on a component's item. The list of child items is used to manage invalidating calculated results. **Overridden in Ext.diag.layout.ContextItem.**


### getFrameInfo

Gets the "frame" information for the element as an object with left, top, right and bottom properties holding border+...

Gets the "frame" information for the element as an object with left, top, right and bottom properties holding border+framing size in pixels. This object is calculated on first request and is cached.

**Returns:** Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getMarginInfo

Gets the margin information for the element as an object with left, top, right and bottom properties holding margin s...

Gets the margin information for the element as an object with left, top, right and bottom properties holding margin size in pixels. This object is only read from the DOM on first request and is cached.

**Returns:** Object


### getPaddingInfo

Gets the padding information for the element as an object with left, top, right and bottom properties holding padding...

Gets the padding information for the element as an object with left, top, right and bottom properties holding padding size in pixels. This object is only read from the DOM on first request and is cached.

**Returns:** Object


### getProp

Gets a property of this object. ...

Gets a property of this object. Also tracks the current layout as dependent on this property so that changes to it will trigger the layout to be recalculated.

**Parameters:** propName : StringThe property name that blocked the layout (e.g., 'width').


### getStyle

Returns a style for this item. ...

**Parameters:** styleName : StringThe CSS style name.

**Returns:** a style for this item. Each style is read from the DOM only once on first request and is then cached. If the value is an integer, it is parsed automatically (so '5px' is not returned, but rather 5).


### getStyles

Returns styles for this item. ...

**Parameters:** styleNames : String[]The CSS style names.

**Returns:** styles for this item. Each style is read from the DOM only once on first request and is then cached. If the value is an integer, it is parsed automatically (so '5px' is not returned, but rather 5).


### hasConfig

...

**Parameters:** config : Object


### hasDomProp

Returns true if the given property is correct in the DOM. ...

**Parameters:** propName : StringThe property name (e.g., 'width').

**Returns:** true if the given property is correct in the DOM. This is equivalent to calling getDomProp and not getting an undefined result. In particular, this call registers the current layout to be triggered by flushes of this property.


### hasProp

Returns true if the given property has been set. ...

**Parameters:** propName : StringThe property name (e.g., 'width').

**Returns:** true if the given property has been set. This is equivalent to calling getProp and not getting an undefined result. In particular, this call registers the current layout to be triggered by changes to this property.


### init

Clears all properties on this object except (perhaps) those not calculated by this component. ...

Clears all properties on this object except (perhaps) those not calculated by this component. This is more complex than it would seem because a layout can decide to invalidate its results and run the component's layouts again, but since some of the values may be calculated by the container, care must be taken to preserve those values. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** full : BooleanTrue if all properties are to be invalidated, false to keep those calculated by the ownerCt.


### initAnimation

...


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initContinue

...

**Parameters:** full : Object


### initDone

...

**Parameters:** containerLayoutDone : Object


### invalidate

Invalidates the component associated with this item. ...

Invalidates the component associated with this item. The layouts for this component and all of its contained items will be re-run after first clearing any computed values. If state needs to be carried forward beyond the invalidation, the `options` parameter can be used. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** options : ObjectAn object describing how to handle the invalidation. state : ObjectAn object to Ext.apply to the state of this item after invalidation clears all other properties.


### markDirty

...


### onBoxMeasured

...


### onConfigUpdate

...

**Parameters:** names : Object


### parseMargins

...

**Parameters:** comp : Object


### peek

...

**Parameters:** propName : Object


### recoverProp

Recovers a property value from the last computation and restores its value and dirty state. ...

Recovers a property value from the last computation and restores its value and dirty state.

**Parameters:** propName : StringThe name of the property to recover.


### redo

...

**Parameters:** deep : Object


### removeCls

Queue the removal of a class name (or array of class names) from this ContextItem's target when next flushed. ...

Queue the removal of a class name (or array of class names) from this ContextItem's target when next flushed.

**Parameters:** removeCls : Object


### removeEl

Removes a cached ContextItem that was created using getEl. ...

Removes a cached ContextItem that was created using getEl. It may be necessary to call this method if the dom reference for owned element changes so that getEl can be called again to reinitialize the ContextItem with the new element.

**Parameters:** nameOrEl : String/Ext.dom.ElementThe element or the name of an owned element


### revertProps

...

**Parameters:** props : Object


### setAttribute

Queue the setting of a DOM attribute on this ContextItem's target when next flushed. ...

Queue the setting of a DOM attribute on this ContextItem's target when next flushed.

**Parameters:** name : Object


### setBox

...

**Parameters:** box : Object


### setConfig

...

**Parameters:** config : Object


### setContentHeight

Sets the contentHeight property. ...

Sets the contentHeight property. If the component uses raw content, then only the measured height is acceptable. Calculated values can sometimes be NaN or undefined, which generally mean the calculation is not done. To indicate that such as value was passed, 0 is returned. Otherwise, 1 is returned. If the caller is not measuring (i.e., they are calculating) and the component has raw content, 1 is returned indicating that the caller is done.

**Parameters:** height : Object


### setContentSize

Sets the contentWidth and contentHeight properties. ...

Sets the contentWidth and contentHeight properties. If the component uses raw content, then only the measured values are acceptable. Calculated values can sometimes be NaN or undefined, which generally means that the calculation is not done. To indicate that either passed value was such a value, false returned. Otherwise, true is returned. If the caller is not measuring (i.e., they are calculating) and the component has raw content, true is returned indicating that the caller is done.

**Parameters:** width : Object


### setContentWidth

Sets the contentWidth property. ...

Sets the contentWidth property. If the component uses raw content, then only the measured width is acceptable. Calculated values can sometimes be NaN or undefined, which generally means that the calculation is not done. To indicate that such as value was passed, 0 is returned. Otherwise, 1 is returned. If the caller is not measuring (i.e., they are calculating) and the component has raw content, 1 is returned indicating that the caller is done.

**Parameters:** width : Object


### setHeight

Sets the height and constrains the height to min/maxHeight range. ...

Sets the height and constrains the height to min/maxHeight range. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** height : NumberThe height.


### setProp

Sets a property value. ...

Sets a property value. This will unblock and/or trigger dependent layouts if the property value is being changed. Values of NaN and undefined are not accepted by this method. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** propName : StringThe property name (e.g., 'width').


### setSize

...

**Parameters:** width : Object


### setWidth

Sets the height and constrains the width to min/maxWidth range. ...

Sets the height and constrains the width to min/maxWidth range. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** width : NumberThe width.


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### undo

...

**Parameters:** deep : Object


### unsetProp

...

**Parameters:** propName : Object


### writeProps

...

**Parameters:** dirtyProps : Object


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

### Ext.layout.ContextItem

...

**Parameters:** config : Object


### addBlock

Adds a block. ...

Adds a block. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** name : StringThe name of the block list ('blocks' or 'domBlocks').


### addBoxChild

Overridden in Ext.diag.layout.ContextItem. ...

**Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** boxChildItem : Object


### addCls

Queue the addition of a class name (or array of class names) to this ContextItem's target when next flushed. ...

Queue the addition of a class name (or array of class names) to this ContextItem's target when next flushed.

**Parameters:** newCls : Object


### addTrigger

Adds a trigger. ...

Adds a trigger. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** propName : StringThe property name that triggers the layout (e.g., 'width').


### block

Registers a layout in the block list for the given property. ...

Registers a layout in the block list for the given property. Once the property is set in the Ext.layout.Context, the layout is unblocked.

**Parameters:** layout : Ext.layout.Layout


### boxChildMeasured

...


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


### checkAuthority

Defined in override Ext.diag.layout.ContextItem. ...

**Defined in override Ext.diag.layout.ContextItem.**

**Parameters:** prop : Object


### checkCache

...

**Parameters:** entry : Object


### clearAllBlocks

...

**Parameters:** name : Object


### clearBlocks

Removes any blocks on a property in the specified set. ...

Removes any blocks on a property in the specified set. Any layouts that were blocked by this property and are not still blocked (by other properties) will be rescheduled. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** name : StringThe name of the block list ('blocks' or 'domBlocks').


### clearMarginCache

clears the margin cache so that marginInfo get re-read from the dom on the next call to getMarginInfo() This is neede...

clears the margin cache so that marginInfo get re-read from the dom on the next call to getMarginInfo() This is needed in some special cases where the margins have changed since the last layout, making the cached values invalid. For example collapsed window headers have different margin than expanded ones.


### configClass

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### domBlock

Registers a layout in the DOM block list for the given property. ...

Registers a layout in the DOM block list for the given property. Once the property flushed to the DOM by the Ext.layout.Context, the layout is unblocked.

**Parameters:** layout : Ext.layout.Layout


### fireTriggers

Reschedules any layouts associated with a given trigger. ...

Reschedules any layouts associated with a given trigger.

**Parameters:** name : StringThe name of the trigger list ('triggers' or 'domTriggers').


### flush

Flushes any updates in the dirty collection to the DOM. ...

Flushes any updates in the dirty collection to the DOM. This is only called if there are dirty entries because this object is only added to the flushQueue of the Ext.layout.Context when entries become dirty.


### flushAnimations

...


### getBorderInfo

Gets the border information for the element as an object with left, top, right and bottom properties holding border s...

Gets the border information for the element as an object with left, top, right and bottom properties holding border size in pixels. This object is only read from the DOM on first request and is cached.

**Returns:** Object


### getClassList

Returns a ClassList-like object to buffer access to this item's element's classes. ...

**Returns:** a ClassList-like object to buffer access to this item's element's classes.


### getConfig

...

**Parameters:** name : Object


### getDomProp

Gets a property of this object if it is correct in the DOM. ...

Gets a property of this object if it is correct in the DOM. Also tracks the current layout as dependent on this property so that DOM writes of it will trigger the layout to be recalculated.

**Parameters:** propName : StringThe property name (e.g., 'width').


### getEl

Returns the context item for an owned element. ...

**Parameters:** nameOrEl : String/Ext.dom.ElementThe element or the name of an owned element

**Returns:** the context item for an owned element. This should only be called on a component's item. The list of child items is used to manage invalidating calculated results. **Overridden in Ext.diag.layout.ContextItem.**


### getFrameInfo

Gets the "frame" information for the element as an object with left, top, right and bottom properties holding border+...

Gets the "frame" information for the element as an object with left, top, right and bottom properties holding border+framing size in pixels. This object is calculated on first request and is cached.

**Returns:** Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getMarginInfo

Gets the margin information for the element as an object with left, top, right and bottom properties holding margin s...

Gets the margin information for the element as an object with left, top, right and bottom properties holding margin size in pixels. This object is only read from the DOM on first request and is cached.

**Returns:** Object


### getPaddingInfo

Gets the padding information for the element as an object with left, top, right and bottom properties holding padding...

Gets the padding information for the element as an object with left, top, right and bottom properties holding padding size in pixels. This object is only read from the DOM on first request and is cached.

**Returns:** Object


### getProp

Gets a property of this object. ...

Gets a property of this object. Also tracks the current layout as dependent on this property so that changes to it will trigger the layout to be recalculated.

**Parameters:** propName : StringThe property name that blocked the layout (e.g., 'width').


### getStyle

Returns a style for this item. ...

**Parameters:** styleName : StringThe CSS style name.

**Returns:** a style for this item. Each style is read from the DOM only once on first request and is then cached. If the value is an integer, it is parsed automatically (so '5px' is not returned, but rather 5).


### getStyles

Returns styles for this item. ...

**Parameters:** styleNames : String[]The CSS style names.

**Returns:** styles for this item. Each style is read from the DOM only once on first request and is then cached. If the value is an integer, it is parsed automatically (so '5px' is not returned, but rather 5).


### hasConfig

...

**Parameters:** config : Object


### hasDomProp

Returns true if the given property is correct in the DOM. ...

**Parameters:** propName : StringThe property name (e.g., 'width').

**Returns:** true if the given property is correct in the DOM. This is equivalent to calling getDomProp and not getting an undefined result. In particular, this call registers the current layout to be triggered by flushes of this property.


### hasProp

Returns true if the given property has been set. ...

**Parameters:** propName : StringThe property name (e.g., 'width').

**Returns:** true if the given property has been set. This is equivalent to calling getProp and not getting an undefined result. In particular, this call registers the current layout to be triggered by changes to this property.


### init

Clears all properties on this object except (perhaps) those not calculated by this component. ...

Clears all properties on this object except (perhaps) those not calculated by this component. This is more complex than it would seem because a layout can decide to invalidate its results and run the component's layouts again, but since some of the values may be calculated by the container, care must be taken to preserve those values. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** full : BooleanTrue if all properties are to be invalidated, false to keep those calculated by the ownerCt.


### initAnimation

...


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initContinue

...

**Parameters:** full : Object


### initDone

...

**Parameters:** containerLayoutDone : Object


### invalidate

Invalidates the component associated with this item. ...

Invalidates the component associated with this item. The layouts for this component and all of its contained items will be re-run after first clearing any computed values. If state needs to be carried forward beyond the invalidation, the `options` parameter can be used. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** options : ObjectAn object describing how to handle the invalidation. state : ObjectAn object to Ext.apply to the state of this item after invalidation clears all other properties.


### markDirty

...


### onBoxMeasured

...


### onConfigUpdate

...

**Parameters:** names : Object


### parseMargins

...

**Parameters:** comp : Object


### peek

...

**Parameters:** propName : Object


### recoverProp

Recovers a property value from the last computation and restores its value and dirty state. ...

Recovers a property value from the last computation and restores its value and dirty state.

**Parameters:** propName : StringThe name of the property to recover.


### redo

...

**Parameters:** deep : Object


### removeCls

Queue the removal of a class name (or array of class names) from this ContextItem's target when next flushed. ...

Queue the removal of a class name (or array of class names) from this ContextItem's target when next flushed.

**Parameters:** removeCls : Object


### removeEl

Removes a cached ContextItem that was created using getEl. ...

Removes a cached ContextItem that was created using getEl. It may be necessary to call this method if the dom reference for owned element changes so that getEl can be called again to reinitialize the ContextItem with the new element.

**Parameters:** nameOrEl : String/Ext.dom.ElementThe element or the name of an owned element


### revertProps

...

**Parameters:** props : Object


### setAttribute

Queue the setting of a DOM attribute on this ContextItem's target when next flushed. ...

Queue the setting of a DOM attribute on this ContextItem's target when next flushed.

**Parameters:** name : Object


### setBox

...

**Parameters:** box : Object


### setConfig

...

**Parameters:** config : Object


### setContentHeight

Sets the contentHeight property. ...

Sets the contentHeight property. If the component uses raw content, then only the measured height is acceptable. Calculated values can sometimes be NaN or undefined, which generally mean the calculation is not done. To indicate that such as value was passed, 0 is returned. Otherwise, 1 is returned. If the caller is not measuring (i.e., they are calculating) and the component has raw content, 1 is returned indicating that the caller is done.

**Parameters:** height : Object


### setContentSize

Sets the contentWidth and contentHeight properties. ...

Sets the contentWidth and contentHeight properties. If the component uses raw content, then only the measured values are acceptable. Calculated values can sometimes be NaN or undefined, which generally means that the calculation is not done. To indicate that either passed value was such a value, false returned. Otherwise, true is returned. If the caller is not measuring (i.e., they are calculating) and the component has raw content, true is returned indicating that the caller is done.

**Parameters:** width : Object


### setContentWidth

Sets the contentWidth property. ...

Sets the contentWidth property. If the component uses raw content, then only the measured width is acceptable. Calculated values can sometimes be NaN or undefined, which generally means that the calculation is not done. To indicate that such as value was passed, 0 is returned. Otherwise, 1 is returned. If the caller is not measuring (i.e., they are calculating) and the component has raw content, 1 is returned indicating that the caller is done.

**Parameters:** width : Object


### setHeight

Sets the height and constrains the height to min/maxHeight range. ...

Sets the height and constrains the height to min/maxHeight range. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** height : NumberThe height.


### setProp

Sets a property value. ...

Sets a property value. This will unblock and/or trigger dependent layouts if the property value is being changed. Values of NaN and undefined are not accepted by this method. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** propName : StringThe property name (e.g., 'width').


### setSize

...

**Parameters:** width : Object


### setWidth

Sets the height and constrains the width to min/maxWidth range. ...

Sets the height and constrains the width to min/maxWidth range. **Overridden in Ext.diag.layout.ContextItem.**

**Parameters:** width : NumberThe width.


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### undo

...

**Parameters:** deep : Object


### unsetProp

...

**Parameters:** propName : Object


### writeProps

...

**Parameters:** dirtyProps : Object


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


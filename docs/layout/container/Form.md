# Ext.layout.container.Form

**Extends:** Ext.layout.container.Container

**Alternate Names:** Ext.layout.FormLayout

## Description

This is a layout that will render form Fields, one under the other all stretched to the Container width.

Ext.create('Ext.Panel', { width: 500, height: 300, title: "FormLayout Panel", layout: 'form', renderTo: Ext.getBody(), bodyPadding: 5, defaultType: 'textfield', items: [{ fieldLabel: 'First Name', name: 'first', allowBlank:false },{ fieldLabel: 'Last Name', name: 'last' },{ fieldLabel: 'Company', name: 'company' }, { fieldLabel: 'Email', name: 'email', vtype:'email' }, { fieldLabel: 'DOB', name: 'dob', xtype: 'datefield' }, { fieldLabel: 'Age', name: 'age', xtype: 'numberfield', minValue: 0, maxValue: 100 }, { xtype: 'timefield', fieldLabel: 'Time', name: 'time', minValue: '8:00am', maxValue: '6:00pm' }] }); Note that any configured padding will be ignored on items within a Form layout.

## Examples

### Example 1

```javascript
Ext.create('Ext.Panel', { width: 500, height: 300, title: "FormLayout Panel", layout: 'form', renderTo: Ext.getBody(), bodyPadding: 5, defaultType: 'textfield', items: [{ fieldLabel: 'First Name', name: 'first', allowBlank:false },{ fieldLabel: 'Last Name', name: 'last' },{ fieldLabel: 'Company', name: 'company' }, { fieldLabel: 'Email', name: 'email', vtype:'email' }, { fieldLabel: 'DOB', name: 'dob', xtype: 'datefield' }, { fieldLabel: 'Age', name: 'age', xtype: 'numberfield', minValue: 0, maxValue: 100 }, { xtype: 'timefield', fieldLabel: 'Time', name: 'time', minValue: '8:00am', maxValue: '6:00pm' }] });
```

## Config options

### itemCls

**Type:** String

An optional extra CSS class that will be added to the container. ...

An optional extra CSS class that will be added to the container. This can be useful for adding customized styles to the container or any of its children using standard CSS rules. See Ext.Component.componentCls also.


### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### animatePolicy

**Type:** Object

An object which contains boolean properties specifying which properties are to be animated upon flush of child Compon...

An object which contains boolean properties specifying which properties are to be animated upon flush of child Component ContextItems. For example, Accordion would have:


### autoSizePolicy

**Type:** Object

...

Defaults to: `{readsWidth: 1, readsHeight: 1, setsWidth: 0, setsHeight: 0}`


### childEls

**Type:** Array

...

Defaults to: `['formTable']` Overrides: Ext.layout.container.Container.childEls


### configMap

**Type:** Object

...

Defaults to: `{}`


### createsInnerCt

**Type:** Boolean

...

Defaults to: `true`


### done

**Type:** Boolean

Used only during a layout run, this value indicates that a layout has finished its calculations. ...

Used only during a layout run, this value indicates that a layout has finished its calculations. This flag is set to true prior to the call to calculate and should be set to false if this layout has more work to do.


### getScrollRangeFlags

**Type:** Object

Returns flags indicating cross-browser handling of scrollHeight/Width. ...

**Returns:** flags indicating cross-browser handling of scrollHeight/Width. In particular, IE has issues with padding-bottom in a scrolling element (it does not include that padding in the scrollHeight). Also, margin-bottom on a child in a scrolling element can be lost. All browsers seem to ignore margin-right on children and padding-right on the parent element (the one with the overflow) This method returns a number with the follow bit positions set based on things not accounted for in scrollHeight and scrollWidth: - 1: Scrolling element's padding-bottom is not included in scrollHeight. - 2: Last child's margin-bottom is not included in scrollHeight. - 4: Scrolling element's padding-right is not included in scrollWidth. - 8: Child's margin-right is not included in scrollWidth. To work around the margin-bottom issue, it is sufficient to create a 0px tall last child that will "hide" the margin. This can also be handled by wrapping the children in an element, again "hiding" the margin. Wrapping the elements is about the only way to preserve their right margins. This is the strategy used by Column layout. To work around the padding-bottom problem, since it is comes from a style on the parent element, about the only simple fix is to create a last child with height equal to padding-bottom. To preserve the right padding, the sizing element needs to have a width that includes the right padding.


### initConfigList

**Type:** Array

...

Defaults to: `[]`


### initConfigMap

**Type:** Object

...

Defaults to: `{}`


### initialized

**Type:** Boolean

...

Defaults to: `false`


### isInstance

**Type:** Boolean

...

Defaults to: `true`


### isLayout

**Type:** Boolean

true in this class to identify an object as an instantiated Layout, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Layout, or subclass thereof. Defaults to: `true`


### lastOverflowAdjust

**Type:** Object

Begin with no previous adjustments ...

Begin with no previous adjustments Defaults to: `{width: 0, height: 0}`


### manageOverflow

**Type:** Boolean

...

Defaults to: `true`


### overflowPadderEl

**Type:** Ext.Element

The element used to correct body padding during overflow.


### padRow

**Type:** String

...

Defaults to: `'<tr><td class="' + Ext.baseCSSPrefix + 'form-item-pad" colspan="3"></td></tr>'`


### renderTpl

**Type:** Array

...

Defaults to: `['<table id="{ownerId}-formTable" class="{tableCls}" style="width:100%" cellpadding="0">', '{%this.renderBody(out,values)%}', '</table>', '{%this.renderPadder(out,values)%}']` Overrides: Ext.layout.container.Container.renderTpl


### running

**Type:** Boolean

...

Defaults to: `false`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### tableCls

**Type:** String

End Definitions ...

End Definitions Defaults to: `Ext.baseCSSPrefix + 'form-layout-table'`


### type

**Type:** String

...

Defaults to: `'form'` Overrides: Ext.layout.container.Container.type


### usesContainerHeight

**Type:** Boolean

...

Defaults to: `true`


### usesContainerWidth

**Type:** Boolean

...

Defaults to: `true`


### usesHeight

**Type:** Boolean

...

Defaults to: `true`


### usesWidth

**Type:** Boolean

...

Defaults to: `true`


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.layout.container.Form

...

**Returns:** Ext.layout.container.Container


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### afterRemove

Removes layout's itemCls and owning Container's itemCls. ...

Removes layout's itemCls and owning Container's itemCls. Clears the managed dimensions flags

**Parameters:** item : Object


### afterRenderItem

...


### applyChildEls

Sets references to elements inside the component. ...

Sets references to elements inside the component.

**Parameters:** el : Object


### beginCollapse

Called by an owning Panel before the Panel begins its collapse process. ...

Called by an owning Panel before the Panel begins its collapse process. Most layouts will not need to override the default Ext.emptyFn implementation.


### beginExpand

Called by an owning Panel before the Panel begins its expand process. ...

Called by an owning Panel before the Panel begins its expand process. Most layouts will not need to override the default Ext.emptyFn implementation.


### beginLayout

In addition to work done by our base classes, containers benefit from some extra cached data. ...

In addition to work done by our base classes, containers benefit from some extra cached data. The following properties are added to the ownerContext: - visibleItems: the result of getVisibleItems - childItems: the ContextItem[] for each visible item - targetContext: the ContextItem for the getTarget element

**Parameters:** ownerContext : Object


### beginLayoutCycle

All of the below methods are old methods moved here from Container layout TODO: remove these methods once Form layout...

All of the below methods are old methods moved here from Container layout TODO: remove these methods once Form layout extends Auto layout Called before any calculation cycles to reset DOM values and prepare for calculation. This is a write phase and DOM reads should be strictly avoided when overridding this method.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### cacheChildItems

...

**Parameters:** ownerContext : Object


### cacheElements

...


### calculate

Called to perform the calculations for this layout. ...

Called to perform the calculations for this layout. This method will be called at least once and may be called repeatedly if the done property is cleared before return to indicate that this layout is not yet done. The done property is always set to `true` before entering this method. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### calculateOverflow

Handles overflow processing for a container. ...

Handles overflow processing for a container. This should be called once the layout has determined contentWidth/Height. In addition to the ownerContext passed to the calculate method, this method also needs the containerSize (the object returned by getContainerSize).

**Parameters:** ownerContext : Ext.layout.ContextItem


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


### completeLayout

This method (if implemented) is called at the end of the cycle in which this layout completes (by not setting done to...

This method (if implemented) is called at the end of the cycle in which this layout completes (by not setting done to `false` in calculate). It is possible for the layout to complete and yet become invalid before the end of the cycle, in which case, this method will not be called. It is also possible for this method to be called and then later the layout becomes invalidated. This will result in calculate being called again, followed by another call to this method. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### configClass

...


### configureItem

Adds layout's itemCls and owning Container's itemCls ...

Adds layout's itemCls and owning Container's itemCls

**Parameters:** item : Object


### destroy

...

Overrides: Ext.util.ElementContainer.destroy


### doRenderBody

...

**Parameters:** out : Object


### doRenderContainer

...

**Parameters:** out : Object


### doRenderItems

...

**Parameters:** out : Object


### doRenderPadder

Creates an element that makes bottom/right body padding consistent across browsers. ...

Creates an element that makes bottom/right body padding consistent across browsers. This element is sized based on the need for scrollbars in calculateOverflow. If the manageOverflow option is false, this element is not created. See getScrollRangeFlags for more details.

**Parameters:** out : Object


### finalizeLayout

This method (if implemented) is called after all layouts have completed. ...

This method (if implemented) is called after all layouts have completed. In most ways this is similar to completeLayout. This call can cause this (or any layout) to be become invalid (see Ext.layout.Context.invalidate), but this is best avoided. This method is intended to be where final reads are made and so it is best to avoid invalidating layouts at this point whenever possible. Even so, this method can be used to perform final checks that may require all other layouts to be complete and then invalidate some results. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### finishRender

...

Overrides: Ext.layout.Layout.finishRender


### finishRenderItems

...

**Parameters:** target : Object


### finishedLayout

This method is called after all layouts are complete and their calculations flushed to the DOM. ...

This method is called after all layouts are complete and their calculations flushed to the DOM. No further layouts will be run and this method is only called once per layout run. The base component layout caches `lastComponentSize`. This is a write phase and DOM reads should be avoided if possible when overridding this method. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### getAnimatePolicy

...


### getChildEls

...


### getClassChildEls

...

**Parameters:** cls : Object


### getConfig

...

**Parameters:** name : Object


### getContainerSize

Returns the container size (that of the target). ...

**Parameters:** ownerContext : Ext.layout.ContextItemThe owner's context item.

**Returns:** the container size (that of the target). Only the fixed-sized dimensions can be returned because the shrinkWrap dimensions are based on the contentWidth/Height as determined by the container layout. If the calculateOverflow method is used and if manageOverflow is true, this may adjust the width/height by the size of scrollbars.


### getContentTarget

...


### getElementTarget

Returns the element into which extra functional DOM elements can be inserted. ...

**Returns:** the element into which extra functional DOM elements can be inserted. Defaults to the owner Component's encapsulating element. May be overridden in Component layout managers which implement a component render target which must only contain child components. ReturnsExt.Element


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getItemSizePolicy

Returns an object describing how this layout manages the size of the given component. ...

**Parameters:** item : Ext.Component

**Returns:** an object describing how this layout manages the size of the given component. This method must be implemented by any layout that manages components.


### getItemsRenderTree

...

**Parameters:** items : Object


### getLayoutItems

Returns an array of child components either for a render phase (Performed in the beforeLayout method of the layout's ...

**Returns:** an array of child components either for a render phase (Performed in the beforeLayout method of the layout's base class), or the layout phase (onLayout). ReturnsExt.Component[]of child components


### getOverflowXStyle

returns the overflow-x style of the render target ...

returns the overflow-x style of the render target

**Parameters:** ownerContext : Ext.layout.ContextItem


### getOverflowYStyle

returns the overflow-y style of the render target ...

returns the overflow-y style of the render target

**Parameters:** ownerContext : Ext.layout.ContextItem


### getPositionOffset

This method is used to offset the DOM position when checking whether the element is a certain child of the target. ...

This method is used to offset the DOM position when checking whether the element is a certain child of the target. This is required in cases where the extra elements prepended to the target before any of the items. An example of this is when using labelAlign: 'top' on a field. The label appears first in the DOM before any child items are created, so when we check the position we need to add an extra offset. Containers that create an innerCt are exempt because this new element preserves the order

**Parameters:** position : Object


### getRenderData

...

Overrides: Ext.layout.container.Container.getRenderData


### getRenderTarget

Returns the element into which rendering must take place. ...

**Returns:** the element into which rendering must take place. Defaults to the owner Container's target element. May be overridden in layout managers which implement an inner element. ReturnsExt.Element


### getRenderTpl

...


### getRenderTree

...

Overrides: Ext.layout.container.Container.getRenderTree


### getRenderedItems

Returns all items that are rendered ...

**Returns:** all items that are rendered ReturnsArrayAll matching items


### getScrollbarsNeeded

...

**Parameters:** width : Object


### getTarget

Returns the owner component's resize element. ...

**Returns:** the owner component's resize element. ReturnsExt.Element


### getVisibleItems

Returns all items that are both rendered and visible ...

**Returns:** all items that are both rendered and visible ReturnsArrayAll matching items


### hasConfig

...

**Parameters:** config : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initLayout

A one-time initialization method called just before rendering. ...

A one-time initialization method called just before rendering. Overrides: Ext.layout.Layout.initLayout


### isItemBoxParent

...

**Parameters:** itemContext : Object


### isItemLayoutRoot

...

**Parameters:** item : Object


### isItemShrinkWrap

...

**Parameters:** item : Object


### isRunning

...


### isValidParent

Validates item is in the proper place in the dom. ...

Validates item is in the proper place in the dom.

**Parameters:** item : Object


### moveItem

Moves Component to the provided target instead. ...

Moves Component to the provided target instead.

**Parameters:** item : Object


### notifyOwner

Called for every layout in the layout context after all the layouts have been finally flushed ...

Called for every layout in the layout context after all the layouts have been finally flushed Overrides: Ext.layout.Layout.notifyOwner


### onAdd

...

**Parameters:** item : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onContentChange

This method is called when a child item changes in some way. ...

This method is called when a child item changes in some way. By default this calls Ext.AbstractComponent.updateLayout on this layout's owner.

**Parameters:** child : Ext.ComponentThe child item that has changed.


### onDestroy

...


### onRemove

...


### prune

...

**Parameters:** childEls : Object


### removeChildEls

Removes items in the childEls array based on the return value of a supplied test function. ...

Removes items in the childEls array based on the return value of a supplied test function. The function is called with a entry in childEls and if the test function return true, that entry is removed. If false, that entry is kept.

**Parameters:** testFn : FunctionThe test function.


### renderChildren

...

Overrides: Ext.layout.Layout.renderChildren


### renderItem

Renders the given Component into the target Element. ...

Renders the given Component into the target Element.

**Parameters:** item : Ext.ComponentThe Component to render


### renderItems

Iterates over all passed items, ensuring they are rendered. ...

Iterates over all passed items, ensuring they are rendered. If the items are already rendered, also determines if the items are in the proper place in the dom.

**Parameters:** items : Object


### setConfig

...

**Parameters:** config : Object


### setOwner

Sets the layout owner ...

Sets the layout owner

**Parameters:** owner : Object


### setupRenderTpl

...

**Parameters:** renderTpl : Object


### sortWeightedItems

...

**Parameters:** items : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### transformItemRenderTree

...

**Parameters:** item : Object


### undoLayout

...


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


### animatePolicy

**Type:** Object

An object which contains boolean properties specifying which properties are to be animated upon flush of child Compon...

An object which contains boolean properties specifying which properties are to be animated upon flush of child Component ContextItems. For example, Accordion would have:


### autoSizePolicy

**Type:** Object

...

Defaults to: `{readsWidth: 1, readsHeight: 1, setsWidth: 0, setsHeight: 0}`


### childEls

**Type:** Array

...

Defaults to: `['formTable']` Overrides: Ext.layout.container.Container.childEls


### configMap

**Type:** Object

...

Defaults to: `{}`


### createsInnerCt

**Type:** Boolean

...

Defaults to: `true`


### done

**Type:** Boolean

Used only during a layout run, this value indicates that a layout has finished its calculations. ...

Used only during a layout run, this value indicates that a layout has finished its calculations. This flag is set to true prior to the call to calculate and should be set to false if this layout has more work to do.


### getScrollRangeFlags

**Type:** Object

Returns flags indicating cross-browser handling of scrollHeight/Width. ...

**Returns:** flags indicating cross-browser handling of scrollHeight/Width. In particular, IE has issues with padding-bottom in a scrolling element (it does not include that padding in the scrollHeight). Also, margin-bottom on a child in a scrolling element can be lost. All browsers seem to ignore margin-right on children and padding-right on the parent element (the one with the overflow) This method returns a number with the follow bit positions set based on things not accounted for in scrollHeight and scrollWidth: - 1: Scrolling element's padding-bottom is not included in scrollHeight. - 2: Last child's margin-bottom is not included in scrollHeight. - 4: Scrolling element's padding-right is not included in scrollWidth. - 8: Child's margin-right is not included in scrollWidth. To work around the margin-bottom issue, it is sufficient to create a 0px tall last child that will "hide" the margin. This can also be handled by wrapping the children in an element, again "hiding" the margin. Wrapping the elements is about the only way to preserve their right margins. This is the strategy used by Column layout. To work around the padding-bottom problem, since it is comes from a style on the parent element, about the only simple fix is to create a last child with height equal to padding-bottom. To preserve the right padding, the sizing element needs to have a width that includes the right padding.


### initConfigList

**Type:** Array

...

Defaults to: `[]`


### initConfigMap

**Type:** Object

...

Defaults to: `{}`


### initialized

**Type:** Boolean

...

Defaults to: `false`


### isInstance

**Type:** Boolean

...

Defaults to: `true`


### isLayout

**Type:** Boolean

true in this class to identify an object as an instantiated Layout, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Layout, or subclass thereof. Defaults to: `true`


### lastOverflowAdjust

**Type:** Object

Begin with no previous adjustments ...

Begin with no previous adjustments Defaults to: `{width: 0, height: 0}`


### manageOverflow

**Type:** Boolean

...

Defaults to: `true`


### overflowPadderEl

**Type:** Ext.Element

The element used to correct body padding during overflow.


### padRow

**Type:** String

...

Defaults to: `'<tr><td class="' + Ext.baseCSSPrefix + 'form-item-pad" colspan="3"></td></tr>'`


### renderTpl

**Type:** Array

...

Defaults to: `['<table id="{ownerId}-formTable" class="{tableCls}" style="width:100%" cellpadding="0">', '{%this.renderBody(out,values)%}', '</table>', '{%this.renderPadder(out,values)%}']` Overrides: Ext.layout.container.Container.renderTpl


### running

**Type:** Boolean

...

Defaults to: `false`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### tableCls

**Type:** String

End Definitions ...

End Definitions Defaults to: `Ext.baseCSSPrefix + 'form-layout-table'`


### type

**Type:** String

...

Defaults to: `'form'` Overrides: Ext.layout.container.Container.type


### usesContainerHeight

**Type:** Boolean

...

Defaults to: `true`


### usesContainerWidth

**Type:** Boolean

...

Defaults to: `true`


### usesHeight

**Type:** Boolean

...

Defaults to: `true`


### usesWidth

**Type:** Boolean

...

Defaults to: `true`


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.layout.container.Form

...

**Returns:** Ext.layout.container.Container


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### afterRemove

Removes layout's itemCls and owning Container's itemCls. ...

Removes layout's itemCls and owning Container's itemCls. Clears the managed dimensions flags

**Parameters:** item : Object


### afterRenderItem

...


### applyChildEls

Sets references to elements inside the component. ...

Sets references to elements inside the component.

**Parameters:** el : Object


### beginCollapse

Called by an owning Panel before the Panel begins its collapse process. ...

Called by an owning Panel before the Panel begins its collapse process. Most layouts will not need to override the default Ext.emptyFn implementation.


### beginExpand

Called by an owning Panel before the Panel begins its expand process. ...

Called by an owning Panel before the Panel begins its expand process. Most layouts will not need to override the default Ext.emptyFn implementation.


### beginLayout

In addition to work done by our base classes, containers benefit from some extra cached data. ...

In addition to work done by our base classes, containers benefit from some extra cached data. The following properties are added to the ownerContext: - visibleItems: the result of getVisibleItems - childItems: the ContextItem[] for each visible item - targetContext: the ContextItem for the getTarget element

**Parameters:** ownerContext : Object


### beginLayoutCycle

All of the below methods are old methods moved here from Container layout TODO: remove these methods once Form layout...

All of the below methods are old methods moved here from Container layout TODO: remove these methods once Form layout extends Auto layout Called before any calculation cycles to reset DOM values and prepare for calculation. This is a write phase and DOM reads should be strictly avoided when overridding this method.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### cacheChildItems

...

**Parameters:** ownerContext : Object


### cacheElements

...


### calculate

Called to perform the calculations for this layout. ...

Called to perform the calculations for this layout. This method will be called at least once and may be called repeatedly if the done property is cleared before return to indicate that this layout is not yet done. The done property is always set to `true` before entering this method. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### calculateOverflow

Handles overflow processing for a container. ...

Handles overflow processing for a container. This should be called once the layout has determined contentWidth/Height. In addition to the ownerContext passed to the calculate method, this method also needs the containerSize (the object returned by getContainerSize).

**Parameters:** ownerContext : Ext.layout.ContextItem


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


### completeLayout

This method (if implemented) is called at the end of the cycle in which this layout completes (by not setting done to...

This method (if implemented) is called at the end of the cycle in which this layout completes (by not setting done to `false` in calculate). It is possible for the layout to complete and yet become invalid before the end of the cycle, in which case, this method will not be called. It is also possible for this method to be called and then later the layout becomes invalidated. This will result in calculate being called again, followed by another call to this method. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### configClass

...


### configureItem

Adds layout's itemCls and owning Container's itemCls ...

Adds layout's itemCls and owning Container's itemCls

**Parameters:** item : Object


### destroy

...

Overrides: Ext.util.ElementContainer.destroy


### doRenderBody

...

**Parameters:** out : Object


### doRenderContainer

...

**Parameters:** out : Object


### doRenderItems

...

**Parameters:** out : Object


### doRenderPadder

Creates an element that makes bottom/right body padding consistent across browsers. ...

Creates an element that makes bottom/right body padding consistent across browsers. This element is sized based on the need for scrollbars in calculateOverflow. If the manageOverflow option is false, this element is not created. See getScrollRangeFlags for more details.

**Parameters:** out : Object


### finalizeLayout

This method (if implemented) is called after all layouts have completed. ...

This method (if implemented) is called after all layouts have completed. In most ways this is similar to completeLayout. This call can cause this (or any layout) to be become invalid (see Ext.layout.Context.invalidate), but this is best avoided. This method is intended to be where final reads are made and so it is best to avoid invalidating layouts at this point whenever possible. Even so, this method can be used to perform final checks that may require all other layouts to be complete and then invalidate some results. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### finishRender

...

Overrides: Ext.layout.Layout.finishRender


### finishRenderItems

...

**Parameters:** target : Object


### finishedLayout

This method is called after all layouts are complete and their calculations flushed to the DOM. ...

This method is called after all layouts are complete and their calculations flushed to the DOM. No further layouts will be run and this method is only called once per layout run. The base component layout caches `lastComponentSize`. This is a write phase and DOM reads should be avoided if possible when overridding this method. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### getAnimatePolicy

...


### getChildEls

...


### getClassChildEls

...

**Parameters:** cls : Object


### getConfig

...

**Parameters:** name : Object


### getContainerSize

Returns the container size (that of the target). ...

**Parameters:** ownerContext : Ext.layout.ContextItemThe owner's context item.

**Returns:** the container size (that of the target). Only the fixed-sized dimensions can be returned because the shrinkWrap dimensions are based on the contentWidth/Height as determined by the container layout. If the calculateOverflow method is used and if manageOverflow is true, this may adjust the width/height by the size of scrollbars.


### getContentTarget

...


### getElementTarget

Returns the element into which extra functional DOM elements can be inserted. ...

**Returns:** the element into which extra functional DOM elements can be inserted. Defaults to the owner Component's encapsulating element. May be overridden in Component layout managers which implement a component render target which must only contain child components. ReturnsExt.Element


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getItemSizePolicy

Returns an object describing how this layout manages the size of the given component. ...

**Parameters:** item : Ext.Component

**Returns:** an object describing how this layout manages the size of the given component. This method must be implemented by any layout that manages components.


### getItemsRenderTree

...

**Parameters:** items : Object


### getLayoutItems

Returns an array of child components either for a render phase (Performed in the beforeLayout method of the layout's ...

**Returns:** an array of child components either for a render phase (Performed in the beforeLayout method of the layout's base class), or the layout phase (onLayout). ReturnsExt.Component[]of child components


### getOverflowXStyle

returns the overflow-x style of the render target ...

returns the overflow-x style of the render target

**Parameters:** ownerContext : Ext.layout.ContextItem


### getOverflowYStyle

returns the overflow-y style of the render target ...

returns the overflow-y style of the render target

**Parameters:** ownerContext : Ext.layout.ContextItem


### getPositionOffset

This method is used to offset the DOM position when checking whether the element is a certain child of the target. ...

This method is used to offset the DOM position when checking whether the element is a certain child of the target. This is required in cases where the extra elements prepended to the target before any of the items. An example of this is when using labelAlign: 'top' on a field. The label appears first in the DOM before any child items are created, so when we check the position we need to add an extra offset. Containers that create an innerCt are exempt because this new element preserves the order

**Parameters:** position : Object


### getRenderData

...

Overrides: Ext.layout.container.Container.getRenderData


### getRenderTarget

Returns the element into which rendering must take place. ...

**Returns:** the element into which rendering must take place. Defaults to the owner Container's target element. May be overridden in layout managers which implement an inner element. ReturnsExt.Element


### getRenderTpl

...


### getRenderTree

...

Overrides: Ext.layout.container.Container.getRenderTree


### getRenderedItems

Returns all items that are rendered ...

**Returns:** all items that are rendered ReturnsArrayAll matching items


### getScrollbarsNeeded

...

**Parameters:** width : Object


### getTarget

Returns the owner component's resize element. ...

**Returns:** the owner component's resize element. ReturnsExt.Element


### getVisibleItems

Returns all items that are both rendered and visible ...

**Returns:** all items that are both rendered and visible ReturnsArrayAll matching items


### hasConfig

...

**Parameters:** config : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initLayout

A one-time initialization method called just before rendering. ...

A one-time initialization method called just before rendering. Overrides: Ext.layout.Layout.initLayout


### isItemBoxParent

...

**Parameters:** itemContext : Object


### isItemLayoutRoot

...

**Parameters:** item : Object


### isItemShrinkWrap

...

**Parameters:** item : Object


### isRunning

...


### isValidParent

Validates item is in the proper place in the dom. ...

Validates item is in the proper place in the dom.

**Parameters:** item : Object


### moveItem

Moves Component to the provided target instead. ...

Moves Component to the provided target instead.

**Parameters:** item : Object


### notifyOwner

Called for every layout in the layout context after all the layouts have been finally flushed ...

Called for every layout in the layout context after all the layouts have been finally flushed Overrides: Ext.layout.Layout.notifyOwner


### onAdd

...

**Parameters:** item : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onContentChange

This method is called when a child item changes in some way. ...

This method is called when a child item changes in some way. By default this calls Ext.AbstractComponent.updateLayout on this layout's owner.

**Parameters:** child : Ext.ComponentThe child item that has changed.


### onDestroy

...


### onRemove

...


### prune

...

**Parameters:** childEls : Object


### removeChildEls

Removes items in the childEls array based on the return value of a supplied test function. ...

Removes items in the childEls array based on the return value of a supplied test function. The function is called with a entry in childEls and if the test function return true, that entry is removed. If false, that entry is kept.

**Parameters:** testFn : FunctionThe test function.


### renderChildren

...

Overrides: Ext.layout.Layout.renderChildren


### renderItem

Renders the given Component into the target Element. ...

Renders the given Component into the target Element.

**Parameters:** item : Ext.ComponentThe Component to render


### renderItems

Iterates over all passed items, ensuring they are rendered. ...

Iterates over all passed items, ensuring they are rendered. If the items are already rendered, also determines if the items are in the proper place in the dom.

**Parameters:** items : Object


### setConfig

...

**Parameters:** config : Object


### setOwner

Sets the layout owner ...

Sets the layout owner

**Parameters:** owner : Object


### setupRenderTpl

...

**Parameters:** renderTpl : Object


### sortWeightedItems

...

**Parameters:** items : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### transformItemRenderTree

...

**Parameters:** item : Object


### undoLayout

...


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

### Ext.layout.container.Form

...

**Returns:** Ext.layout.container.Container


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### afterRemove

Removes layout's itemCls and owning Container's itemCls. ...

Removes layout's itemCls and owning Container's itemCls. Clears the managed dimensions flags

**Parameters:** item : Object


### afterRenderItem

...


### applyChildEls

Sets references to elements inside the component. ...

Sets references to elements inside the component.

**Parameters:** el : Object


### beginCollapse

Called by an owning Panel before the Panel begins its collapse process. ...

Called by an owning Panel before the Panel begins its collapse process. Most layouts will not need to override the default Ext.emptyFn implementation.


### beginExpand

Called by an owning Panel before the Panel begins its expand process. ...

Called by an owning Panel before the Panel begins its expand process. Most layouts will not need to override the default Ext.emptyFn implementation.


### beginLayout

In addition to work done by our base classes, containers benefit from some extra cached data. ...

In addition to work done by our base classes, containers benefit from some extra cached data. The following properties are added to the ownerContext: - visibleItems: the result of getVisibleItems - childItems: the ContextItem[] for each visible item - targetContext: the ContextItem for the getTarget element

**Parameters:** ownerContext : Object


### beginLayoutCycle

All of the below methods are old methods moved here from Container layout TODO: remove these methods once Form layout...

All of the below methods are old methods moved here from Container layout TODO: remove these methods once Form layout extends Auto layout Called before any calculation cycles to reset DOM values and prepare for calculation. This is a write phase and DOM reads should be strictly avoided when overridding this method.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### cacheChildItems

...

**Parameters:** ownerContext : Object


### cacheElements

...


### calculate

Called to perform the calculations for this layout. ...

Called to perform the calculations for this layout. This method will be called at least once and may be called repeatedly if the done property is cleared before return to indicate that this layout is not yet done. The done property is always set to `true` before entering this method. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### calculateOverflow

Handles overflow processing for a container. ...

Handles overflow processing for a container. This should be called once the layout has determined contentWidth/Height. In addition to the ownerContext passed to the calculate method, this method also needs the containerSize (the object returned by getContainerSize).

**Parameters:** ownerContext : Ext.layout.ContextItem


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


### completeLayout

This method (if implemented) is called at the end of the cycle in which this layout completes (by not setting done to...

This method (if implemented) is called at the end of the cycle in which this layout completes (by not setting done to `false` in calculate). It is possible for the layout to complete and yet become invalid before the end of the cycle, in which case, this method will not be called. It is also possible for this method to be called and then later the layout becomes invalidated. This will result in calculate being called again, followed by another call to this method. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### configClass

...


### configureItem

Adds layout's itemCls and owning Container's itemCls ...

Adds layout's itemCls and owning Container's itemCls

**Parameters:** item : Object


### destroy

...

Overrides: Ext.util.ElementContainer.destroy


### doRenderBody

...

**Parameters:** out : Object


### doRenderContainer

...

**Parameters:** out : Object


### doRenderItems

...

**Parameters:** out : Object


### doRenderPadder

Creates an element that makes bottom/right body padding consistent across browsers. ...

Creates an element that makes bottom/right body padding consistent across browsers. This element is sized based on the need for scrollbars in calculateOverflow. If the manageOverflow option is false, this element is not created. See getScrollRangeFlags for more details.

**Parameters:** out : Object


### finalizeLayout

This method (if implemented) is called after all layouts have completed. ...

This method (if implemented) is called after all layouts have completed. In most ways this is similar to completeLayout. This call can cause this (or any layout) to be become invalid (see Ext.layout.Context.invalidate), but this is best avoided. This method is intended to be where final reads are made and so it is best to avoid invalidating layouts at this point whenever possible. Even so, this method can be used to perform final checks that may require all other layouts to be complete and then invalidate some results. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### finishRender

...

Overrides: Ext.layout.Layout.finishRender


### finishRenderItems

...

**Parameters:** target : Object


### finishedLayout

This method is called after all layouts are complete and their calculations flushed to the DOM. ...

This method is called after all layouts are complete and their calculations flushed to the DOM. No further layouts will be run and this method is only called once per layout run. The base component layout caches `lastComponentSize`. This is a write phase and DOM reads should be avoided if possible when overridding this method. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### getAnimatePolicy

...


### getChildEls

...


### getClassChildEls

...

**Parameters:** cls : Object


### getConfig

...

**Parameters:** name : Object


### getContainerSize

Returns the container size (that of the target). ...

**Parameters:** ownerContext : Ext.layout.ContextItemThe owner's context item.

**Returns:** the container size (that of the target). Only the fixed-sized dimensions can be returned because the shrinkWrap dimensions are based on the contentWidth/Height as determined by the container layout. If the calculateOverflow method is used and if manageOverflow is true, this may adjust the width/height by the size of scrollbars.


### getContentTarget

...


### getElementTarget

Returns the element into which extra functional DOM elements can be inserted. ...

**Returns:** the element into which extra functional DOM elements can be inserted. Defaults to the owner Component's encapsulating element. May be overridden in Component layout managers which implement a component render target which must only contain child components. ReturnsExt.Element


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getItemSizePolicy

Returns an object describing how this layout manages the size of the given component. ...

**Parameters:** item : Ext.Component

**Returns:** an object describing how this layout manages the size of the given component. This method must be implemented by any layout that manages components.


### getItemsRenderTree

...

**Parameters:** items : Object


### getLayoutItems

Returns an array of child components either for a render phase (Performed in the beforeLayout method of the layout's ...

**Returns:** an array of child components either for a render phase (Performed in the beforeLayout method of the layout's base class), or the layout phase (onLayout). ReturnsExt.Component[]of child components


### getOverflowXStyle

returns the overflow-x style of the render target ...

returns the overflow-x style of the render target

**Parameters:** ownerContext : Ext.layout.ContextItem


### getOverflowYStyle

returns the overflow-y style of the render target ...

returns the overflow-y style of the render target

**Parameters:** ownerContext : Ext.layout.ContextItem


### getPositionOffset

This method is used to offset the DOM position when checking whether the element is a certain child of the target. ...

This method is used to offset the DOM position when checking whether the element is a certain child of the target. This is required in cases where the extra elements prepended to the target before any of the items. An example of this is when using labelAlign: 'top' on a field. The label appears first in the DOM before any child items are created, so when we check the position we need to add an extra offset. Containers that create an innerCt are exempt because this new element preserves the order

**Parameters:** position : Object


### getRenderData

...

Overrides: Ext.layout.container.Container.getRenderData


### getRenderTarget

Returns the element into which rendering must take place. ...

**Returns:** the element into which rendering must take place. Defaults to the owner Container's target element. May be overridden in layout managers which implement an inner element. ReturnsExt.Element


### getRenderTpl

...


### getRenderTree

...

Overrides: Ext.layout.container.Container.getRenderTree


### getRenderedItems

Returns all items that are rendered ...

**Returns:** all items that are rendered ReturnsArrayAll matching items


### getScrollbarsNeeded

...

**Parameters:** width : Object


### getTarget

Returns the owner component's resize element. ...

**Returns:** the owner component's resize element. ReturnsExt.Element


### getVisibleItems

Returns all items that are both rendered and visible ...

**Returns:** all items that are both rendered and visible ReturnsArrayAll matching items


### hasConfig

...

**Parameters:** config : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initLayout

A one-time initialization method called just before rendering. ...

A one-time initialization method called just before rendering. Overrides: Ext.layout.Layout.initLayout


### isItemBoxParent

...

**Parameters:** itemContext : Object


### isItemLayoutRoot

...

**Parameters:** item : Object


### isItemShrinkWrap

...

**Parameters:** item : Object


### isRunning

...


### isValidParent

Validates item is in the proper place in the dom. ...

Validates item is in the proper place in the dom.

**Parameters:** item : Object


### moveItem

Moves Component to the provided target instead. ...

Moves Component to the provided target instead.

**Parameters:** item : Object


### notifyOwner

Called for every layout in the layout context after all the layouts have been finally flushed ...

Called for every layout in the layout context after all the layouts have been finally flushed Overrides: Ext.layout.Layout.notifyOwner


### onAdd

...

**Parameters:** item : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onContentChange

This method is called when a child item changes in some way. ...

This method is called when a child item changes in some way. By default this calls Ext.AbstractComponent.updateLayout on this layout's owner.

**Parameters:** child : Ext.ComponentThe child item that has changed.


### onDestroy

...


### onRemove

...


### prune

...

**Parameters:** childEls : Object


### removeChildEls

Removes items in the childEls array based on the return value of a supplied test function. ...

Removes items in the childEls array based on the return value of a supplied test function. The function is called with a entry in childEls and if the test function return true, that entry is removed. If false, that entry is kept.

**Parameters:** testFn : FunctionThe test function.


### renderChildren

...

Overrides: Ext.layout.Layout.renderChildren


### renderItem

Renders the given Component into the target Element. ...

Renders the given Component into the target Element.

**Parameters:** item : Ext.ComponentThe Component to render


### renderItems

Iterates over all passed items, ensuring they are rendered. ...

Iterates over all passed items, ensuring they are rendered. If the items are already rendered, also determines if the items are in the proper place in the dom.

**Parameters:** items : Object


### setConfig

...

**Parameters:** config : Object


### setOwner

Sets the layout owner ...

Sets the layout owner

**Parameters:** owner : Object


### setupRenderTpl

...

**Parameters:** renderTpl : Object


### sortWeightedItems

...

**Parameters:** items : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### transformItemRenderTree

...

**Parameters:** item : Object


### undoLayout

...


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


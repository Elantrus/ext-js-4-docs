# Ext.layout.container.Absolute

**Extends:** Ext.layout.container.Anchor

**Alternate Names:** Ext.layout.AbsoluteLayout

## Description

This is a layout that inherits the anchoring of Ext.layout.container.Anchor and adds the ability for x/y positioning using the standard x and y component config options.

This class is intended to be extended or created via the layout configuration property. See Ext.container.Container.layout for additional details.

## Examples

### Example 1

```javascript
Ext.create('Ext.form.Panel', { title: 'Absolute Layout', width: 300, height: 275, layout: { type: 'absolute' // layout-specific configs go here //itemCls: 'x-abs-layout-item', }, url:'save-form.php', defaultType: 'textfield', items: [{ x: 10, y: 10, xtype:'label', text: 'Send To:' },{ x: 80, y: 10, name: 'to', anchor:'90%' // anchor width by percentage },{ x: 10, y: 40, xtype:'label', text: 'Subject:' },{ x: 80, y: 40, name: 'subject', anchor: '90%' // anchor width by percentage },{ x:0, y: 80, xtype: 'textareafield', name: 'msg', anchor: '100% 100%' // anchor width and height }], renderTo: Ext.getBody() });
```

## Config options

### anchor

**Type:** String

This configuation option is to be applied to child items of a container managed by this layout (ie. ...

This configuation option is to be applied to **child `items`** of a container managed by this layout (ie. configured with `layout:'anchor'`). This value is what tells the layout how an item should be anchored to the container. `items` added to an AnchorLayout accept an anchoring-specific config property of **anchor** which is a string containing two values: the horizontal anchor value and the vertical anchor value (for example, '100% 50%'). The following types of anchor values are supported: - **Percentage** : Any value between 1 and 100, expressed as a percentage. The first anchor is the percentage width that the item should take up within the container, and the second is the percentage height. For example: - **Offsets** : Any positive or negative integer value. This is a raw adjustment where the first anchor is the offset from the right edge of the container, and the second is the offset from the bottom edge. For example: - **Sides** : Valid values are `right` (or `r`) and `bottom` (or `b`). Either the container must have a fixed size or an anchorSize config value defined at render time in order for these to have any effect. - **Mixed** : Anchor values can also be mixed as needed. For example, to render the width offset from the container right edge by 50 pixels and 75% of the container's height use:


### defaultAnchor

**Type:** String

Default anchor for all child container items applied if no anchor or specific width is set on the child item. ...

Default anchor for all child **container** items applied if no anchor or specific width is set on the child item. Defaults to: `'100%'`


### ignoreOnContentChange

**Type:** Boolean

True indicates that changes to one item in this layout do not effect the layout in general. ...

True indicates that changes to one item in this layout do not effect the layout in general. This may need to be set to false if Ext.Component.autoScroll is enabled for the container. Defaults to: `true`


### itemCls

**Type:** String

An optional extra CSS class that will be added to the container. ...

An optional extra CSS class that will be added to the container. This can be useful for adding customized styles to the container or any of its children using standard CSS rules. See Ext.Component.componentCls also. Defaults to: `Ext.baseCSSPrefix + 'abs-layout-item'` Overrides: Ext.layout.container.Container.itemCls


### reserveScrollbar

**Type:** Boolean

Set to true to leave space for a vertical scrollbar (if the OS shows space-consuming scrollbars) regardless of whethe...

Set to `true` to leave space for a vertical scrollbar (if the OS shows space-consuming scrollbars) regardless of whether a scrollbar is needed. This is useful if content height changes during application usage, but you do not want the calculated width of child items to change when a scrollbar appears or disappears. The scrollbar will appear in the reserved space, and the calculated width of child Components will not change. Defaults to: `false`


### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### anchorFactory

**Type:** Object

private


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

Defaults to: `['outerCt', 'innerCt', 'clearEl']` Overrides: Ext.layout.container.Container.childEls


### configMap

**Type:** Object

...

Defaults to: `{}`


### done

**Type:** Boolean

Used only during a layout run, this value indicates that a layout has finished its calculations. ...

Used only during a layout run, this value indicates that a layout has finished its calculations. This flag is set to true prior to the call to calculate and should be set to false if this layout has more work to do.


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


### isShrinkWrapTpl

**Type:** Boolean

...

Defaults to: `true`


### lastOverflowAdjust

**Type:** Object

Begin with no previous adjustments ...

Begin with no previous adjustments Defaults to: `{width: 0, height: 0}`


### manageOverflow

**Type:** Boolean

true to rerun the layout if scrollbars are needed. ...

true to rerun the layout if scrollbars are needed. Defaults to: `true` Overrides: Ext.layout.container.Auto.manageOverflow


### managePadding

**Type:** Boolean

indicates that this layout will correct cross browser padding differences when the container has overflow. ...

indicates that this layout will correct cross browser padding differences when the container has overflow. In some browsers the right and/or bottom padding of a container is lost when the container has overflow. If managePadding is true the layout will apply the padding to an inner wrapping element instead of the container element that has the overflow so that paddding will be included in the scrollable area. Note: padding will not be managed if it is configured on the container using a style config or css class. In order to be managed, padding must be added to the container using the appropriate contentPaddingProperty. For Panels use Ext.panel.AbstractPanel.bodyPadding, and for Containers, use padding Defaults to: `true`


### overflowPadderEl

**Type:** Ext.Element

The element used to correct body padding during overflow.


### parseAnchorRE

**Type:** RegExp

...

Defaults to: `/^(r|right|b|bottom)$/i`


### renderTpl

**Type:** Object

Auto layout's renderTpl wraps the content in an outerCt which is used to accomplish the following 3 goals: When the...

Auto layout's renderTpl wraps the content in an outerCt which is used to accomplish the following 3 goals: - When the container has a shrink wrapped width and/or height, the outerCt is used to measure the size of the content. - When the container has overflow some browsers lose the container's right and/or bottom padding. To fix this, the padding is rendered to the outerCt instead of the container target element. This ensures that the padding is included in the container's scrollWidth/scrollHeight. In Old IE when a table is used, the padding is rendered to the innerCt td element. - The outerCt contains the margins of its children, that is to say, it prevents them from collapsing. Overrides: Ext.layout.container.Container.renderTpl


### running

**Type:** Boolean

...

Defaults to: `false`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### sizePolicy

**Type:** Object

...

Defaults to: `{$: {readsWidth: 1, readsHeight: 1, setsWidth: 0, setsHeight: 0}, b: {readsWidth: 1, readsHeight: 0, setsWidth: 0, setsHeight: 1}, r: {$: {readsWidth: 0, readsHeight: 1, setsWidth: 1, setsHeight: 0}, b: {readsWidth: 0, readsHeight: 0, setsWidth: 1, setsHeight: 1}}}`


### tableTpl

**Type:** Object

This template is used for dynamically inserting a table outerCt/innerCt when needed. ...

This template is used for dynamically inserting a table outerCt/innerCt when needed. It should be identical to the table template defined in renderTpl except that it does not have renderBody or clearEl. It is an empty shell so that the contents of an already existing innerCt can be moved into it.


### targetCls

**Type:** String

End Definitions ...

End Definitions Defaults to: `Ext.baseCSSPrefix + 'abs-layout-ct'`


### type

**Type:** String

...

Defaults to: `'absolute'` Overrides: Ext.layout.container.Anchor.type


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


### Ext.layout.container.Absolute

...

**Returns:** Ext.layout.container.Container


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### adjustHeightAnchor

private ...

private

**Parameters:** value : Object


### adjustWidthAnchor

private ...

private

**Parameters:** value : Object


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


### beforeLayoutCycle

...

**Parameters:** ownerContext : Object


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

Called before any calculation cycles to reset DOM values and prepare for calculation. ...

Called before any calculation cycles to reset DOM values and prepare for calculation. This is a write phase and DOM reads should be strictly avoided when overridding this method.

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


### calculateContentSize

...

**Parameters:** ownerContext : Object


### calculateItems

...

**Parameters:** ownerContext : Object


### calculateOverflow

Handles overflow processing for a container. ...

Handles overflow processing for a container. In addition to the ownerContext passed to the calculate method, this method also needs the containerSize (the object returned by getContainerSize).

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


### doRenderPadding

...

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

**Returns:** the container size (that of the target). Only the fixed-sized dimensions can be returned because the shrinkWrap dimensions are based on the contentWidth/Height as determined by the container layout. If the calculateOverflow method is used and if manageOverflow is true, this will adjust the width/height by the size of scrollbars.


### getContentTarget

...

Overrides: Ext.layout.container.Container.getContentTarget


### getElementTarget

Overridden method from Ext.layout.container.Container. ...

Overridden method from Ext.layout.container.Container. Used by Container classes to insert special DOM elements which must exist in addition to the child components

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

Returns the overflow-x style of the render target. ...

**Parameters:** ownerContext : Ext.layout.ContextItem

**Returns:** the overflow-x style of the render target. Note: If overflow is configured on a container using style or css class this method will read the dom the first time it is called. It is therefore preferable for performance reasons to use the autoScroll or overflowX config when horizontal overflow is desired.


### getOverflowYStyle

Returns the overflow-y style of the render target. ...

**Parameters:** ownerContext : Ext.layout.ContextItem

**Returns:** the overflow-y style of the render target. Note: If overflow is configured on a container using style or css class this method will read the dom the first time it is called. It is therefore preferable for performance reasons to use the autoScroll or overflowY config when vertical overflow is desired.


### getPositionOffset

This method is used to offset the DOM position when checking whether the element is a certain child of the target. ...

This method is used to offset the DOM position when checking whether the element is a certain child of the target. This is required in cases where the extra elements prepended to the target before any of the items. An example of this is when using labelAlign: 'top' on a field. The label appears first in the DOM before any child items are created, so when we check the position we need to add an extra offset. Containers that create an innerCt are exempt because this new element preserves the order

**Parameters:** position : Object


### getRenderData

...

Overrides: Ext.layout.container.Container.getRenderData


### getRenderTarget

Overridden method from Ext.layout.container.Container. ...

Overridden method from Ext.layout.container.Container. Used in the beforeLayout method to render all items into.

**Returns:** the element into which rendering must take place. Defaults to the owner Container's target element. May be overridden in layout managers which implement an inner element. ReturnsExt.Element


### getRenderTpl

...


### getRenderTree

...


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


### initContextItems

...

**Parameters:** ownerContext : Object


### initLayout

A one-time initialization method called just before rendering. ...

A one-time initialization method called just before rendering. Overrides: Ext.layout.Layout.initLayout


### insertTableCt

In some cases a table-based outerCt/innerCt is required in old IE (see renderTpl). ...

In some cases a table-based outerCt/innerCt is required in old IE (see renderTpl). Most of the time this is determined at render time, however its possible that we made the wrong determination at render time and now that the layout is in progress we need a table. If so, this method should be called to replace the existing outerCt with a new table outerCt, and move the child elements to the new innerCt.

**Parameters:** ownerContext : Object


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


### measureContentHeight

...

**Parameters:** ownerContext : Object


### measureContentWidth

...

**Parameters:** ownerContext : Object


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


### parseAnchor

...

**Parameters:** a : Object


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


### sanityCheck

...

**Parameters:** ownerContext : Object


### setConfig

...

**Parameters:** config : Object


### setCtSizeIfNeeded

This method sets the height and/or width of the outerCt/innerCt to adjust for the following browser-specific issues: ...

This method sets the height and/or width of the outerCt/innerCt to adjust for the following browser-specific issues: - In IE6 and 7 strict if we are using the shrink wrap template, and the outerCt has a 100% width (because the container is not shrink wrapping width currently), and the target element has a vertical scrollbar, the browser disregards the scrollbar when sizing the width of the outerCt. This can result in the target element gaining a horizontal scrollbar. We fix this issue by setting a pixel width on the outerCt - In IE quirks when using the "non shrink wrap" template, a long non-breaking word can cause the outerCt's width to expand beyond the width of its container. This behavior is desired if the container has the potential for horizontal overflow, but can cause text to be hidden if the container's overflow is hidden. To prevent this from happening we give the outerCt a fixed width in IE quirks when the container does not have horizontal overflow. - In some browsers a percentage-height element ignores the horizontal scrollbar of its parent (see Ext.supports.PercentageHeightOverflowBug). If the browser is affected by this bug the outerCt needs a pixel height in order to support percentage-height children when not shrink-wrapping height. If the browser is not affected by this bug, a height of 100% is assigned to the outerCt (see beginLayoutCycle). - In IE6/7 strict when using the "shrink wrap" template, percentage heights on children do not work unless the innerCt td has a height set. We can't use height 100% on the innerCt because conent-box sizing will cause any top/bottom padding to be added to the height. The solution is to set a pixel height on the innerCt. - IE8 strict mode has a bug with percentage height children. if the innerCt has a height of 100%, has padding, and has a child item with a percentage height, that child item will be sized as a percentage of the parent's height plus padding height. In other words, a child with height:50% would have its height caclulated thusly: (parentHeight + parentPaddingHeight) * 0.5 To fix this, we have to give the innerCt a pixel height. - In IE7 strict if we're using the "non shrink wrap" template, and the target element has overflow-y:auto, the outerCt reserves space for the target element's vertical scrollbar even when there is no vertical scrollbar. This is fixed by setting the targetEl's overflow property to "hidden" and then back to "auto".

**Parameters:** ownerContext : Ext.layout.ContextItem


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


### anchorFactory

**Type:** Object

private


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

Defaults to: `['outerCt', 'innerCt', 'clearEl']` Overrides: Ext.layout.container.Container.childEls


### configMap

**Type:** Object

...

Defaults to: `{}`


### done

**Type:** Boolean

Used only during a layout run, this value indicates that a layout has finished its calculations. ...

Used only during a layout run, this value indicates that a layout has finished its calculations. This flag is set to true prior to the call to calculate and should be set to false if this layout has more work to do.


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


### isShrinkWrapTpl

**Type:** Boolean

...

Defaults to: `true`


### lastOverflowAdjust

**Type:** Object

Begin with no previous adjustments ...

Begin with no previous adjustments Defaults to: `{width: 0, height: 0}`


### manageOverflow

**Type:** Boolean

true to rerun the layout if scrollbars are needed. ...

true to rerun the layout if scrollbars are needed. Defaults to: `true` Overrides: Ext.layout.container.Auto.manageOverflow


### managePadding

**Type:** Boolean

indicates that this layout will correct cross browser padding differences when the container has overflow. ...

indicates that this layout will correct cross browser padding differences when the container has overflow. In some browsers the right and/or bottom padding of a container is lost when the container has overflow. If managePadding is true the layout will apply the padding to an inner wrapping element instead of the container element that has the overflow so that paddding will be included in the scrollable area. Note: padding will not be managed if it is configured on the container using a style config or css class. In order to be managed, padding must be added to the container using the appropriate contentPaddingProperty. For Panels use Ext.panel.AbstractPanel.bodyPadding, and for Containers, use padding Defaults to: `true`


### overflowPadderEl

**Type:** Ext.Element

The element used to correct body padding during overflow.


### parseAnchorRE

**Type:** RegExp

...

Defaults to: `/^(r|right|b|bottom)$/i`


### renderTpl

**Type:** Object

Auto layout's renderTpl wraps the content in an outerCt which is used to accomplish the following 3 goals: When the...

Auto layout's renderTpl wraps the content in an outerCt which is used to accomplish the following 3 goals: - When the container has a shrink wrapped width and/or height, the outerCt is used to measure the size of the content. - When the container has overflow some browsers lose the container's right and/or bottom padding. To fix this, the padding is rendered to the outerCt instead of the container target element. This ensures that the padding is included in the container's scrollWidth/scrollHeight. In Old IE when a table is used, the padding is rendered to the innerCt td element. - The outerCt contains the margins of its children, that is to say, it prevents them from collapsing. Overrides: Ext.layout.container.Container.renderTpl


### running

**Type:** Boolean

...

Defaults to: `false`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### sizePolicy

**Type:** Object

...

Defaults to: `{$: {readsWidth: 1, readsHeight: 1, setsWidth: 0, setsHeight: 0}, b: {readsWidth: 1, readsHeight: 0, setsWidth: 0, setsHeight: 1}, r: {$: {readsWidth: 0, readsHeight: 1, setsWidth: 1, setsHeight: 0}, b: {readsWidth: 0, readsHeight: 0, setsWidth: 1, setsHeight: 1}}}`


### tableTpl

**Type:** Object

This template is used for dynamically inserting a table outerCt/innerCt when needed. ...

This template is used for dynamically inserting a table outerCt/innerCt when needed. It should be identical to the table template defined in renderTpl except that it does not have renderBody or clearEl. It is an empty shell so that the contents of an already existing innerCt can be moved into it.


### targetCls

**Type:** String

End Definitions ...

End Definitions Defaults to: `Ext.baseCSSPrefix + 'abs-layout-ct'`


### type

**Type:** String

...

Defaults to: `'absolute'` Overrides: Ext.layout.container.Anchor.type


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


### Ext.layout.container.Absolute

...

**Returns:** Ext.layout.container.Container


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### adjustHeightAnchor

private ...

private

**Parameters:** value : Object


### adjustWidthAnchor

private ...

private

**Parameters:** value : Object


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


### beforeLayoutCycle

...

**Parameters:** ownerContext : Object


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

Called before any calculation cycles to reset DOM values and prepare for calculation. ...

Called before any calculation cycles to reset DOM values and prepare for calculation. This is a write phase and DOM reads should be strictly avoided when overridding this method.

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


### calculateContentSize

...

**Parameters:** ownerContext : Object


### calculateItems

...

**Parameters:** ownerContext : Object


### calculateOverflow

Handles overflow processing for a container. ...

Handles overflow processing for a container. In addition to the ownerContext passed to the calculate method, this method also needs the containerSize (the object returned by getContainerSize).

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


### doRenderPadding

...

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

**Returns:** the container size (that of the target). Only the fixed-sized dimensions can be returned because the shrinkWrap dimensions are based on the contentWidth/Height as determined by the container layout. If the calculateOverflow method is used and if manageOverflow is true, this will adjust the width/height by the size of scrollbars.


### getContentTarget

...

Overrides: Ext.layout.container.Container.getContentTarget


### getElementTarget

Overridden method from Ext.layout.container.Container. ...

Overridden method from Ext.layout.container.Container. Used by Container classes to insert special DOM elements which must exist in addition to the child components

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

Returns the overflow-x style of the render target. ...

**Parameters:** ownerContext : Ext.layout.ContextItem

**Returns:** the overflow-x style of the render target. Note: If overflow is configured on a container using style or css class this method will read the dom the first time it is called. It is therefore preferable for performance reasons to use the autoScroll or overflowX config when horizontal overflow is desired.


### getOverflowYStyle

Returns the overflow-y style of the render target. ...

**Parameters:** ownerContext : Ext.layout.ContextItem

**Returns:** the overflow-y style of the render target. Note: If overflow is configured on a container using style or css class this method will read the dom the first time it is called. It is therefore preferable for performance reasons to use the autoScroll or overflowY config when vertical overflow is desired.


### getPositionOffset

This method is used to offset the DOM position when checking whether the element is a certain child of the target. ...

This method is used to offset the DOM position when checking whether the element is a certain child of the target. This is required in cases where the extra elements prepended to the target before any of the items. An example of this is when using labelAlign: 'top' on a field. The label appears first in the DOM before any child items are created, so when we check the position we need to add an extra offset. Containers that create an innerCt are exempt because this new element preserves the order

**Parameters:** position : Object


### getRenderData

...

Overrides: Ext.layout.container.Container.getRenderData


### getRenderTarget

Overridden method from Ext.layout.container.Container. ...

Overridden method from Ext.layout.container.Container. Used in the beforeLayout method to render all items into.

**Returns:** the element into which rendering must take place. Defaults to the owner Container's target element. May be overridden in layout managers which implement an inner element. ReturnsExt.Element


### getRenderTpl

...


### getRenderTree

...


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


### initContextItems

...

**Parameters:** ownerContext : Object


### initLayout

A one-time initialization method called just before rendering. ...

A one-time initialization method called just before rendering. Overrides: Ext.layout.Layout.initLayout


### insertTableCt

In some cases a table-based outerCt/innerCt is required in old IE (see renderTpl). ...

In some cases a table-based outerCt/innerCt is required in old IE (see renderTpl). Most of the time this is determined at render time, however its possible that we made the wrong determination at render time and now that the layout is in progress we need a table. If so, this method should be called to replace the existing outerCt with a new table outerCt, and move the child elements to the new innerCt.

**Parameters:** ownerContext : Object


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


### measureContentHeight

...

**Parameters:** ownerContext : Object


### measureContentWidth

...

**Parameters:** ownerContext : Object


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


### parseAnchor

...

**Parameters:** a : Object


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


### sanityCheck

...

**Parameters:** ownerContext : Object


### setConfig

...

**Parameters:** config : Object


### setCtSizeIfNeeded

This method sets the height and/or width of the outerCt/innerCt to adjust for the following browser-specific issues: ...

This method sets the height and/or width of the outerCt/innerCt to adjust for the following browser-specific issues: - In IE6 and 7 strict if we are using the shrink wrap template, and the outerCt has a 100% width (because the container is not shrink wrapping width currently), and the target element has a vertical scrollbar, the browser disregards the scrollbar when sizing the width of the outerCt. This can result in the target element gaining a horizontal scrollbar. We fix this issue by setting a pixel width on the outerCt - In IE quirks when using the "non shrink wrap" template, a long non-breaking word can cause the outerCt's width to expand beyond the width of its container. This behavior is desired if the container has the potential for horizontal overflow, but can cause text to be hidden if the container's overflow is hidden. To prevent this from happening we give the outerCt a fixed width in IE quirks when the container does not have horizontal overflow. - In some browsers a percentage-height element ignores the horizontal scrollbar of its parent (see Ext.supports.PercentageHeightOverflowBug). If the browser is affected by this bug the outerCt needs a pixel height in order to support percentage-height children when not shrink-wrapping height. If the browser is not affected by this bug, a height of 100% is assigned to the outerCt (see beginLayoutCycle). - In IE6/7 strict when using the "shrink wrap" template, percentage heights on children do not work unless the innerCt td has a height set. We can't use height 100% on the innerCt because conent-box sizing will cause any top/bottom padding to be added to the height. The solution is to set a pixel height on the innerCt. - IE8 strict mode has a bug with percentage height children. if the innerCt has a height of 100%, has padding, and has a child item with a percentage height, that child item will be sized as a percentage of the parent's height plus padding height. In other words, a child with height:50% would have its height caclulated thusly: (parentHeight + parentPaddingHeight) * 0.5 To fix this, we have to give the innerCt a pixel height. - In IE7 strict if we're using the "non shrink wrap" template, and the target element has overflow-y:auto, the outerCt reserves space for the target element's vertical scrollbar even when there is no vertical scrollbar. This is fixed by setting the targetEl's overflow property to "hidden" and then back to "auto".

**Parameters:** ownerContext : Ext.layout.ContextItem


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

### Ext.layout.container.Absolute

...

**Returns:** Ext.layout.container.Container


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### adjustHeightAnchor

private ...

private

**Parameters:** value : Object


### adjustWidthAnchor

private ...

private

**Parameters:** value : Object


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


### beforeLayoutCycle

...

**Parameters:** ownerContext : Object


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

Called before any calculation cycles to reset DOM values and prepare for calculation. ...

Called before any calculation cycles to reset DOM values and prepare for calculation. This is a write phase and DOM reads should be strictly avoided when overridding this method.

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


### calculateContentSize

...

**Parameters:** ownerContext : Object


### calculateItems

...

**Parameters:** ownerContext : Object


### calculateOverflow

Handles overflow processing for a container. ...

Handles overflow processing for a container. In addition to the ownerContext passed to the calculate method, this method also needs the containerSize (the object returned by getContainerSize).

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


### doRenderPadding

...

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

**Returns:** the container size (that of the target). Only the fixed-sized dimensions can be returned because the shrinkWrap dimensions are based on the contentWidth/Height as determined by the container layout. If the calculateOverflow method is used and if manageOverflow is true, this will adjust the width/height by the size of scrollbars.


### getContentTarget

...

Overrides: Ext.layout.container.Container.getContentTarget


### getElementTarget

Overridden method from Ext.layout.container.Container. ...

Overridden method from Ext.layout.container.Container. Used by Container classes to insert special DOM elements which must exist in addition to the child components

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

Returns the overflow-x style of the render target. ...

**Parameters:** ownerContext : Ext.layout.ContextItem

**Returns:** the overflow-x style of the render target. Note: If overflow is configured on a container using style or css class this method will read the dom the first time it is called. It is therefore preferable for performance reasons to use the autoScroll or overflowX config when horizontal overflow is desired.


### getOverflowYStyle

Returns the overflow-y style of the render target. ...

**Parameters:** ownerContext : Ext.layout.ContextItem

**Returns:** the overflow-y style of the render target. Note: If overflow is configured on a container using style or css class this method will read the dom the first time it is called. It is therefore preferable for performance reasons to use the autoScroll or overflowY config when vertical overflow is desired.


### getPositionOffset

This method is used to offset the DOM position when checking whether the element is a certain child of the target. ...

This method is used to offset the DOM position when checking whether the element is a certain child of the target. This is required in cases where the extra elements prepended to the target before any of the items. An example of this is when using labelAlign: 'top' on a field. The label appears first in the DOM before any child items are created, so when we check the position we need to add an extra offset. Containers that create an innerCt are exempt because this new element preserves the order

**Parameters:** position : Object


### getRenderData

...

Overrides: Ext.layout.container.Container.getRenderData


### getRenderTarget

Overridden method from Ext.layout.container.Container. ...

Overridden method from Ext.layout.container.Container. Used in the beforeLayout method to render all items into.

**Returns:** the element into which rendering must take place. Defaults to the owner Container's target element. May be overridden in layout managers which implement an inner element. ReturnsExt.Element


### getRenderTpl

...


### getRenderTree

...


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


### initContextItems

...

**Parameters:** ownerContext : Object


### initLayout

A one-time initialization method called just before rendering. ...

A one-time initialization method called just before rendering. Overrides: Ext.layout.Layout.initLayout


### insertTableCt

In some cases a table-based outerCt/innerCt is required in old IE (see renderTpl). ...

In some cases a table-based outerCt/innerCt is required in old IE (see renderTpl). Most of the time this is determined at render time, however its possible that we made the wrong determination at render time and now that the layout is in progress we need a table. If so, this method should be called to replace the existing outerCt with a new table outerCt, and move the child elements to the new innerCt.

**Parameters:** ownerContext : Object


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


### measureContentHeight

...

**Parameters:** ownerContext : Object


### measureContentWidth

...

**Parameters:** ownerContext : Object


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


### parseAnchor

...

**Parameters:** a : Object


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


### sanityCheck

...

**Parameters:** ownerContext : Object


### setConfig

...

**Parameters:** config : Object


### setCtSizeIfNeeded

This method sets the height and/or width of the outerCt/innerCt to adjust for the following browser-specific issues: ...

This method sets the height and/or width of the outerCt/innerCt to adjust for the following browser-specific issues: - In IE6 and 7 strict if we are using the shrink wrap template, and the outerCt has a 100% width (because the container is not shrink wrapping width currently), and the target element has a vertical scrollbar, the browser disregards the scrollbar when sizing the width of the outerCt. This can result in the target element gaining a horizontal scrollbar. We fix this issue by setting a pixel width on the outerCt - In IE quirks when using the "non shrink wrap" template, a long non-breaking word can cause the outerCt's width to expand beyond the width of its container. This behavior is desired if the container has the potential for horizontal overflow, but can cause text to be hidden if the container's overflow is hidden. To prevent this from happening we give the outerCt a fixed width in IE quirks when the container does not have horizontal overflow. - In some browsers a percentage-height element ignores the horizontal scrollbar of its parent (see Ext.supports.PercentageHeightOverflowBug). If the browser is affected by this bug the outerCt needs a pixel height in order to support percentage-height children when not shrink-wrapping height. If the browser is not affected by this bug, a height of 100% is assigned to the outerCt (see beginLayoutCycle). - In IE6/7 strict when using the "shrink wrap" template, percentage heights on children do not work unless the innerCt td has a height set. We can't use height 100% on the innerCt because conent-box sizing will cause any top/bottom padding to be added to the height. The solution is to set a pixel height on the innerCt. - IE8 strict mode has a bug with percentage height children. if the innerCt has a height of 100%, has padding, and has a child item with a percentage height, that child item will be sized as a percentage of the parent's height plus padding height. In other words, a child with height:50% would have its height caclulated thusly: (parentHeight + parentPaddingHeight) * 0.5 To fix this, we have to give the innerCt a pixel height. - In IE7 strict if we're using the "non shrink wrap" template, and the target element has overflow-y:auto, the outerCt reserves space for the target element's vertical scrollbar even when there is no vertical scrollbar. This is fixed by setting the targetEl's overflow property to "hidden" and then back to "auto".

**Parameters:** ownerContext : Ext.layout.ContextItem


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


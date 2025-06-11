# Ext.layout.container.Border

**Extends:** Ext.layout.container.Container

**Alternate Names:** Ext.layout.BorderLayout

## Description

This is a multi-pane, application-oriented UI layout style that supports multiple nested panels, automatic bars between regions and built-in expanding and collapsing of regions.

This class is intended to be extended or created via the `layout:'border'` Ext.container.Container.layout config, and should generally not need to be created directly via the new keyword.

Ext.create('Ext.panel.Panel', { width: 500, height: 300, title: 'Border Layout', layout: 'border', items: [{ title: 'South Region is resizable', region: 'south', // position for region xtype: 'panel', height: 100, split: true, // enable resizing margins: '0 5 5 5' },{ // xtype: 'panel' implied by default title: 'West Region is collapsible', region:'west', xtype: 'panel', margins: '5 0 0 5', width: 200, collapsible: true, // make collapsible id: 'west-region-container', layout: 'fit' },{ title: 'Center Region', region: 'center', // center region is required, no width/height specified xtype: 'panel', layout: 'fit', margins: '5 5 0 0' }], renderTo: Ext.getBody() }); Notes When using the split option, the layout will automatically insert a Ext.resizer.Splitter into the appropriate place. This will modify the underlying items collection in the container.

Any Container using the Border layout **must** have a child item with `region:'center'`. The child item in the center region will always be resized to fill the remaining space not used by the other regions in the layout.

Any child items with a region of `west` or `east` may be configured with either an initial `width`, or a Ext.layout.container.Box.flex value, or an initial percentage width **string** (Which is simply divided by 100 and used as a flex value). The 'center' region has a flex value of `1`.

Any child items with a region of `north` or `south` may be configured with either an initial `height`, or a Ext.layout.container.Box.flex value, or an initial percentage height **string** (Which is simply divided by 100 and used as a flex value). The 'center' region has a flex value of `1`.

**There is no BorderLayout.Region class in ExtJS 4.0+**

## Examples

### Example 1

```javascript
Ext.create('Ext.panel.Panel', { width: 500, height: 300, title: 'Border Layout', layout: 'border', items: [{ title: 'South Region is resizable', region: 'south', // position for region xtype: 'panel', height: 100, split: true, // enable resizing margins: '0 5 5 5' },{ // xtype: 'panel' implied by default title: 'West Region is collapsible', region:'west', xtype: 'panel', margins: '5 0 0 5', width: 200, collapsible: true, // make collapsible id: 'west-region-container', layout: 'fit' },{ title: 'Center Region', region: 'center', // center region is required, no width/height specified xtype: 'panel', layout: 'fit', margins: '5 5 0 0' }], renderTo: Ext.getBody() });
```

## Config options

### itemCls

**Type:** String

An optional extra CSS class that will be added to the container. ...

An optional extra CSS class that will be added to the container. This can be useful for adding customized styles to the container or any of its children using standard CSS rules. See Ext.Component.componentCls also. Defaults to: `[Ext.baseCSSPrefix + 'border-item', Ext.baseCSSPrefix + 'box-item']` Overrides: Ext.layout.container.Container.itemCls


### padding

**Type:** Number/String/Object

Sets the padding to be applied to all child items managed by this layout. ...

Sets the padding to be applied to all child items managed by this layout. This property can be specified as a string containing space-separated, numeric padding values. The order of the sides associated with each value matches the way CSS processes padding values: - If there is only one value, it applies to all sides. - If there are two values, the top and bottom borders are set to the first value and the right and left are set to the second. - If there are three values, the top is set to the first value, the left and right are set to the second, and the bottom is set to the third. - If there are four values, they apply to the top, right, bottom, and left, respectively.


### regionWeights

**Type:** Object

The default weights to assign to regions in the border layout. ...

The default weights to assign to regions in the border layout. These values are used when a region does not contain a `weight` property. This object must have properties for all regions ("north", "south", "east" and "west"). **IMPORTANT:** Since this is an object, changing its properties will impact ALL instances of Border layout. If this is not desired, provide a replacement object as a config option instead: The region with the highest weight is assigned space from the border before other regions. Regions of equal weight are assigned space based on their position in the owner's items list (first come, first served).


### split

**Type:** Boolean

This configuration option is to be applied to the child items managed by this layout. ...

This configuration option is to be applied to the **child `items`** managed by this layout. Each region with `split:true` will get a Splitter that allows for manual resizing of the container. Except for the `center` region.


### splitterResize

**Type:** Boolean

This configuration option is to be applied to the child items managed by this layout and is used in conjunction with ...

This configuration option is to be applied to the **child `items`** managed by this layout and is used in conjunction with split. By default, when specifying split, the region can be dragged to be resized. Set this option to false to show the split bar but prevent resizing. Defaults to: `true`


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


### axisProps

**Type:** Object

Reused meta-data objects that describe axis properties. ...

Reused meta-data objects that describe axis properties. Defaults to: `{horz: {borderBegin: 'west', borderEnd: 'east', horizontal: true, posProp: 'x', sizeProp: 'width', sizePropCap: 'Width'}, vert: {borderBegin: 'north', borderEnd: 'south', horizontal: false, posProp: 'y', sizeProp: 'height', sizePropCap: 'Height'}}`


### centerRegion

**Type:** Object


### childEls

**Type:** Array

...

Defaults to: `['overflowPadderEl']` Overrides: Ext.util.ElementContainer.childEls


### configMap

**Type:** Object

...

Defaults to: `{}`


### done

**Type:** Boolean

Used only during a layout run, this value indicates that a layout has finished its calculations. ...

Used only during a layout run, this value indicates that a layout has finished its calculations. This flag is set to true prior to the call to calculate and should be set to false if this layout has more work to do.


### horzMarginProp

**Type:** String

...

Defaults to: `'left'`


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


### isBorderLayout

**Type:** Boolean

...

Defaults to: `true`


### isInstance

**Type:** Boolean

...

Defaults to: `true`


### isLayout

**Type:** Boolean

true in this class to identify an object as an instantiated Layout, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Layout, or subclass thereof. Defaults to: `true`


### manageMargins

**Type:** Boolean

...

Defaults to: `true`


### overflowPadderEl

**Type:** Ext.Element

The element used to correct body padding during overflow.


### padNotOnContainerProp

**Type:** String

...

Defaults to: `'right'`


### padOnContainerProp

**Type:** String

...

Defaults to: `'left'`


### panelCollapseAnimate

**Type:** Boolean

...

Defaults to: `true`


### panelCollapseMode

**Type:** String

...

Defaults to: `'placeholder'`


### percentageRe

**Type:** RegExp

...

Defaults to: `/(\d+)%/`


### regionFlags

**Type:** Object

Flags and configs that get set of regions based on their region property. ...

Flags and configs that get set of regions based on their `region` property. Defaults to: `{center: {isCenter: true, isHorz: false, isVert: false}, north: {isCenter: false, isHorz: false, isVert: true, collapseDirection: 'top'}, south: {isCenter: false, isHorz: false, isVert: true, collapseDirection: 'bottom'}, west: {isCenter: false, isHorz: true, isVert: false, collapseDirection: 'left'}, east: {isCenter: false, isHorz: true, isVert: false, collapseDirection: 'right'}}`


### regionMeta

**Type:** Object

Misc


### renderTpl

**Type:** Array

...

Defaults to: `['{%this.renderBody(out,values)%}']`


### running

**Type:** Boolean

...

Defaults to: `false`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### sizePolicies

**Type:** Object

...

Defaults to: `{vert: {readsWidth: 0, readsHeight: 1, setsWidth: 1, setsHeight: 0}, horz: {readsWidth: 1, readsHeight: 0, setsWidth: 0, setsHeight: 1}, flexAll: {readsWidth: 0, readsHeight: 0, setsWidth: 1, setsHeight: 1}}`


### targetCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'border-layout-ct'`


### touchedRegions

**Type:** Object

Lists the regions that would consider an interior region a neighbor. ...

Lists the regions that would consider an interior region a neighbor. For example, a north region would consider an east or west region its neighbords (as well as an inner north region). Defaults to: `{center: ['north', 'south', 'east', 'west'], north: ['north', 'east', 'west'], south: ['south', 'east', 'west'], east: ['east', 'north', 'south'], west: ['west', 'north', 'south']}`


### type

**Type:** String

...

Defaults to: `'border'` Overrides: Ext.layout.container.Container.type


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


### Ext.layout.container.Border

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


### beginAxis

Creates the axis objects for the layout. ...

Creates the axis objects for the layout. These are only missing size information which is added during calculate.

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


### calculateChildAxis

Performs the calculations for a region on a specified axis. ...

Performs the calculations for a region on a specified axis.

**Parameters:** childContext : Object


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


### finalizeLayout

This method (if implemented) is called after all layouts have completed. ...

This method (if implemented) is called after all layouts have completed. In most ways this is similar to completeLayout. This call can cause this (or any layout) to be become invalid (see Ext.layout.Context.invalidate), but this is best avoided. This method is intended to be where final reads are made and so it is best to avoid invalidating layouts at this point whenever possible. Even so, this method can be used to perform final checks that may require all other layouts to be complete and then invalidate some results. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### finishAxis

Finishes the calculations on an axis. ...

Finishes the calculations on an axis. This basically just assigns the remaining space to the center region.

**Parameters:** ownerContext : Object


### finishPositions

Finishes by setting the positions on the child items. ...

Finishes by setting the positions on the child items.

**Parameters:** childItems : Object


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

**Returns:** the container size (that of the target). Only the fixed-sized dimensions can be returned because the shrinkWrap dimensions are based on the contentWidth/Height as determined by the container layout.


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


### getPlaceholder

...

**Parameters:** comp : Object


### getPositionOffset

This method is used to offset the DOM position when checking whether the element is a certain child of the target. ...

This method is used to offset the DOM position when checking whether the element is a certain child of the target. This is required in cases where the extra elements prepended to the target before any of the items. An example of this is when using labelAlign: 'top' on a field. The label appears first in the DOM before any child items are created, so when we check the position we need to add an extra offset. Containers that create an innerCt are exempt because this new element preserves the order

**Parameters:** position : Object


### getRenderData

...


### getRenderTarget

Returns the element into which rendering must take place. ...

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


### getSplitterTarget

...

**Parameters:** splitter : Object


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

A one-time initialization method called just before rendering.


### insertSplitter

Inserts the splitter for a given region. ...

Inserts the splitter for a given region. A reference to the splitter is also stored on the component as "splitter".

**Parameters:** item : Object


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

Called when a region (actually when any component) is added to the container. ...

Called when a region (actually when any component) is added to the container. The region is decorated with some helpful properties (isCenter, isHorz, isVert) and its splitter is added if its "split" property is true.

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

Overrides: Ext.layout.Layout.onDestroy


### onRemove

...

**Parameters:** item : Object


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


### setupSplitterNeighbors

...

**Parameters:** items : Object


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


### $border-layout-ct-background-color

**Type:** color

The background-color of the Border layout element ...

The background-color of the Border layout element Defaults to: `$neutral-color`


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


### axisProps

**Type:** Object

Reused meta-data objects that describe axis properties. ...

Reused meta-data objects that describe axis properties. Defaults to: `{horz: {borderBegin: 'west', borderEnd: 'east', horizontal: true, posProp: 'x', sizeProp: 'width', sizePropCap: 'Width'}, vert: {borderBegin: 'north', borderEnd: 'south', horizontal: false, posProp: 'y', sizeProp: 'height', sizePropCap: 'Height'}}`


### centerRegion

**Type:** Object


### childEls

**Type:** Array

...

Defaults to: `['overflowPadderEl']` Overrides: Ext.util.ElementContainer.childEls


### configMap

**Type:** Object

...

Defaults to: `{}`


### done

**Type:** Boolean

Used only during a layout run, this value indicates that a layout has finished its calculations. ...

Used only during a layout run, this value indicates that a layout has finished its calculations. This flag is set to true prior to the call to calculate and should be set to false if this layout has more work to do.


### horzMarginProp

**Type:** String

...

Defaults to: `'left'`


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


### isBorderLayout

**Type:** Boolean

...

Defaults to: `true`


### isInstance

**Type:** Boolean

...

Defaults to: `true`


### isLayout

**Type:** Boolean

true in this class to identify an object as an instantiated Layout, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Layout, or subclass thereof. Defaults to: `true`


### manageMargins

**Type:** Boolean

...

Defaults to: `true`


### overflowPadderEl

**Type:** Ext.Element

The element used to correct body padding during overflow.


### padNotOnContainerProp

**Type:** String

...

Defaults to: `'right'`


### padOnContainerProp

**Type:** String

...

Defaults to: `'left'`


### panelCollapseAnimate

**Type:** Boolean

...

Defaults to: `true`


### panelCollapseMode

**Type:** String

...

Defaults to: `'placeholder'`


### percentageRe

**Type:** RegExp

...

Defaults to: `/(\d+)%/`


### regionFlags

**Type:** Object

Flags and configs that get set of regions based on their region property. ...

Flags and configs that get set of regions based on their `region` property. Defaults to: `{center: {isCenter: true, isHorz: false, isVert: false}, north: {isCenter: false, isHorz: false, isVert: true, collapseDirection: 'top'}, south: {isCenter: false, isHorz: false, isVert: true, collapseDirection: 'bottom'}, west: {isCenter: false, isHorz: true, isVert: false, collapseDirection: 'left'}, east: {isCenter: false, isHorz: true, isVert: false, collapseDirection: 'right'}}`


### regionMeta

**Type:** Object

Misc


### renderTpl

**Type:** Array

...

Defaults to: `['{%this.renderBody(out,values)%}']`


### running

**Type:** Boolean

...

Defaults to: `false`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### sizePolicies

**Type:** Object

...

Defaults to: `{vert: {readsWidth: 0, readsHeight: 1, setsWidth: 1, setsHeight: 0}, horz: {readsWidth: 1, readsHeight: 0, setsWidth: 0, setsHeight: 1}, flexAll: {readsWidth: 0, readsHeight: 0, setsWidth: 1, setsHeight: 1}}`


### targetCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'border-layout-ct'`


### touchedRegions

**Type:** Object

Lists the regions that would consider an interior region a neighbor. ...

Lists the regions that would consider an interior region a neighbor. For example, a north region would consider an east or west region its neighbords (as well as an inner north region). Defaults to: `{center: ['north', 'south', 'east', 'west'], north: ['north', 'east', 'west'], south: ['south', 'east', 'west'], east: ['east', 'north', 'south'], west: ['west', 'north', 'south']}`


### type

**Type:** String

...

Defaults to: `'border'` Overrides: Ext.layout.container.Container.type


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


### Ext.layout.container.Border

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


### beginAxis

Creates the axis objects for the layout. ...

Creates the axis objects for the layout. These are only missing size information which is added during calculate.

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


### calculateChildAxis

Performs the calculations for a region on a specified axis. ...

Performs the calculations for a region on a specified axis.

**Parameters:** childContext : Object


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


### finalizeLayout

This method (if implemented) is called after all layouts have completed. ...

This method (if implemented) is called after all layouts have completed. In most ways this is similar to completeLayout. This call can cause this (or any layout) to be become invalid (see Ext.layout.Context.invalidate), but this is best avoided. This method is intended to be where final reads are made and so it is best to avoid invalidating layouts at this point whenever possible. Even so, this method can be used to perform final checks that may require all other layouts to be complete and then invalidate some results. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### finishAxis

Finishes the calculations on an axis. ...

Finishes the calculations on an axis. This basically just assigns the remaining space to the center region.

**Parameters:** ownerContext : Object


### finishPositions

Finishes by setting the positions on the child items. ...

Finishes by setting the positions on the child items.

**Parameters:** childItems : Object


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

**Returns:** the container size (that of the target). Only the fixed-sized dimensions can be returned because the shrinkWrap dimensions are based on the contentWidth/Height as determined by the container layout.


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


### getPlaceholder

...

**Parameters:** comp : Object


### getPositionOffset

This method is used to offset the DOM position when checking whether the element is a certain child of the target. ...

This method is used to offset the DOM position when checking whether the element is a certain child of the target. This is required in cases where the extra elements prepended to the target before any of the items. An example of this is when using labelAlign: 'top' on a field. The label appears first in the DOM before any child items are created, so when we check the position we need to add an extra offset. Containers that create an innerCt are exempt because this new element preserves the order

**Parameters:** position : Object


### getRenderData

...


### getRenderTarget

Returns the element into which rendering must take place. ...

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


### getSplitterTarget

...

**Parameters:** splitter : Object


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

A one-time initialization method called just before rendering.


### insertSplitter

Inserts the splitter for a given region. ...

Inserts the splitter for a given region. A reference to the splitter is also stored on the component as "splitter".

**Parameters:** item : Object


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

Called when a region (actually when any component) is added to the container. ...

Called when a region (actually when any component) is added to the container. The region is decorated with some helpful properties (isCenter, isHorz, isVert) and its splitter is added if its "split" property is true.

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

Overrides: Ext.layout.Layout.onDestroy


### onRemove

...

**Parameters:** item : Object


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


### setupSplitterNeighbors

...

**Parameters:** items : Object


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


### $border-layout-ct-background-color

**Type:** color

The background-color of the Border layout element ...

The background-color of the Border layout element Defaults to: `$neutral-color`


## Methods

### Ext.layout.container.Border

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


### beginAxis

Creates the axis objects for the layout. ...

Creates the axis objects for the layout. These are only missing size information which is added during calculate.

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


### calculateChildAxis

Performs the calculations for a region on a specified axis. ...

Performs the calculations for a region on a specified axis.

**Parameters:** childContext : Object


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


### finalizeLayout

This method (if implemented) is called after all layouts have completed. ...

This method (if implemented) is called after all layouts have completed. In most ways this is similar to completeLayout. This call can cause this (or any layout) to be become invalid (see Ext.layout.Context.invalidate), but this is best avoided. This method is intended to be where final reads are made and so it is best to avoid invalidating layouts at this point whenever possible. Even so, this method can be used to perform final checks that may require all other layouts to be complete and then invalidate some results. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### finishAxis

Finishes the calculations on an axis. ...

Finishes the calculations on an axis. This basically just assigns the remaining space to the center region.

**Parameters:** ownerContext : Object


### finishPositions

Finishes by setting the positions on the child items. ...

Finishes by setting the positions on the child items.

**Parameters:** childItems : Object


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

**Returns:** the container size (that of the target). Only the fixed-sized dimensions can be returned because the shrinkWrap dimensions are based on the contentWidth/Height as determined by the container layout.


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


### getPlaceholder

...

**Parameters:** comp : Object


### getPositionOffset

This method is used to offset the DOM position when checking whether the element is a certain child of the target. ...

This method is used to offset the DOM position when checking whether the element is a certain child of the target. This is required in cases where the extra elements prepended to the target before any of the items. An example of this is when using labelAlign: 'top' on a field. The label appears first in the DOM before any child items are created, so when we check the position we need to add an extra offset. Containers that create an innerCt are exempt because this new element preserves the order

**Parameters:** position : Object


### getRenderData

...


### getRenderTarget

Returns the element into which rendering must take place. ...

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


### getSplitterTarget

...

**Parameters:** splitter : Object


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

A one-time initialization method called just before rendering.


### insertSplitter

Inserts the splitter for a given region. ...

Inserts the splitter for a given region. A reference to the splitter is also stored on the component as "splitter".

**Parameters:** item : Object


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

Called when a region (actually when any component) is added to the container. ...

Called when a region (actually when any component) is added to the container. The region is decorated with some helpful properties (isCenter, isHorz, isVert) and its splitter is added if its "split" property is true.

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

Overrides: Ext.layout.Layout.onDestroy


### onRemove

...

**Parameters:** item : Object


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


### setupSplitterNeighbors

...

**Parameters:** items : Object


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


### $border-layout-ct-background-color

**Type:** color

The background-color of the Border layout element ...

The background-color of the Border layout element Defaults to: `$neutral-color`


## CSS Variables

### $border-layout-ct-background-color

**Type:** color

The background-color of the Border layout element ...

The background-color of the Border layout element Defaults to: `$neutral-color`


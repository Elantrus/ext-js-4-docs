# Ext.layout.container.Accordion

**Extends:** Ext.layout.container.VBox

**Alternate Names:** Ext.layout.AccordionLayout

## Descrição

This is a layout that manages multiple Panels in an expandable accordion style such that by default only
one Panel can be expanded at any given time (set multi config to have more open). Each Panel has
built-in support for expanding and collapsing.

Note: Only Ext Panels and all subclasses of Ext.panel.Panel may be used in an accordion layout Container.

## Exemplos

### Exemplo 1

```javascript
Ext.create('Ext.panel.Panel', {
    title: 'Accordion Layout',
    width: 300,
    height: 300,
    defaults: {
        // applied to each contained panel
        bodyStyle: 'padding:15px'
    },
    layout: {
        // layout-specific configs go here
        type: 'accordion',
        titleCollapse: false,
        animate: true,
        activeOnTop: true
    },
    items: [{
        title: 'Panel 1',
        html: 'Panel content!'
    },{
        title: 'Panel 2',
        html: 'Panel content!'
    },{
        title: 'Panel 3',
        html: 'Panel content!'
    }],
    renderTo: Ext.getBody()
});
```

## Config options

### activeOnTop

**Tipo:** Boolean

Only valid when multi is false and animate is false. ...

Only valid when multi is `false` and animate is `false`.

True to swap the position of each panel as it is expanded so that it becomes the first item in the container,
false to keep the panels in the rendered order.
Defaults to: `false`


### align

**Tipo:** String

Controls how the child items of the container are aligned. ...

Controls how the child items of the container are aligned. Acceptable configuration values for this property are:


**left** : **Default** child items are aligned horizontally at the **left** side of the container.
**center** : child items are aligned horizontally at the **mid-width** of the container.
**right** : child items are aligned horizontally at the **right** of the container.
**stretch** : child items are stretched horizontally to fill the width of the container.
**stretchmax** : child items are stretched horizontally to the size of the largest item.


Defaults to: `'stretch'`Overrides: Ext.layout.container.VBox.align


### alignRoundingMethod

**Tipo:** "round"/"floor"/"ceil"

The Math method to use
for rounding fractional pixels when align:center is used. ...

The Math method to use
for rounding fractional pixels when `align:center` is used.
Defaults to: `'round'`


### animate

**Tipo:** Boolean

True to slide the contained panels open and closed during expand/collapse using animation, false to open and
close di...

True to slide the contained panels open and closed during expand/collapse using animation, false to open and
close directly with no animation. Note: The layout performs animated collapsing
and expanding, *not* the child Panels.
Defaults to: `true`


### autoWidth

**Tipo:** Boolean

Child Panels have their width actively managed to fit within the accordion's width.

Child Panels have their width actively managed to fit within the accordion's width.
        
        This cfg has been **removed** 
        This config is ignored in ExtJS 4


### collapseFirst

**Tipo:** Boolean

True to make sure the collapse/expand toggle button always renders first (to the left of) any other tools
in the cont...

True to make sure the collapse/expand toggle button always renders first (to the left of) any other tools
in the contained Panels' title bars, false to render it last. By default, this will use the
Ext.panel.Panel.collapseFirst setting on the panel. If the config option is specified on the layout,
it will override the panel value.


### constrainAlign

**Tipo:** Boolean

Limits the size of aligned components to the size of the container under certain circumstances. ...

Limits the size of aligned components to the size of the container under certain circumstances.
Firstly, the container width must not be determined by the width of the child components. Secondly, the child
components must have their width shrinkwrapped.
Defaults to: `false`


### defaultMargins

**Tipo:** Object

If the individual contained items do not have a margins property specified or margin specified via CSS, the
default m...

If the individual contained items do not have a margins property specified or margin specified via CSS, the
default margins from this property will be applied to each item.

This property may be specified as an object containing margins to apply in the format:

{
    top: (top margin),
    right: (right margin),
    bottom: (bottom margin),
    left: (left margin)
}


This property may also be specified as a string containing space-separated, numeric margin values. The order of
the sides associated with each value matches the way CSS processes margin values:


If there is only one value, it applies to all sides.
If there are two values, the top and bottom borders are set to the first value and the right and left are
set to the second.
If there are three values, the top is set to the first value, the left and right are set to the second,
and the bottom is set to the third.
If there are four values, they apply to the top, right, bottom, and left, respectively.


Defaults to: `{top: 0, right: 0, bottom: 0, left: 0}`


### fill

**Tipo:** Boolean

True to adjust the active item's height to fill the available space in the container, false to use the
item's current...

True to adjust the active item's height to fill the available space in the container, false to use the
item's current height, or auto height if not explicitly set.
Defaults to: `true`


### flex

**Tipo:** Number

This configuration option is to be applied to child items of the container managed by this layout. ...

This configuration option is to be applied to **child items** of the container managed by this layout. Each child
item with a flex property will be flexed (horizontally in `hbox`, vertically in `vbox`) according to each item's
**relative** flex value compared to the sum of all items with a flex value specified. Any child items that have
either a `flex = 0` or `flex = undefined` will not be 'flexed' (the initial size will not be changed).


### hideCollapseTool

**Tipo:** Boolean

True to hide the contained Panels' collapse/expand toggle buttons, false to display them. ...

True to hide the contained Panels' collapse/expand toggle buttons, false to display them.
When set to true, titleCollapse is automatically set to true.
Defaults to: `false`


### itemCls

**Tipo:** String

An optional extra CSS class that will be added to the container. ...

An optional extra CSS class that will be added to the container. This can be useful for
adding customized styles to the container or any of its children using standard CSS
rules. See Ext.Component.componentCls also.
Defaults to: `[Ext.baseCSSPrefix + 'box-item', Ext.baseCSSPrefix + 'accordion-item']`Overrides: Ext.layout.container.Box.itemCls


### multi

**Tipo:** Boolean

Set to true to enable multiple accordion items to be open at once. ...

Set to true to enable multiple accordion items to be open at once.
Defaults to: `false`


### pack

**Tipo:** String

Controls how the child items of the container are packed together. ...

Controls how the child items of the container are packed together. Acceptable configuration values for this
property are:


**start** - child items are packed together at **left** (HBox) or **top** (VBox) side of container (*default**)
**center** - child items are packed together at **mid-width** (HBox) or **mid-height** (VBox) of container
**end** - child items are packed together at **right** (HBox) or **bottom** (VBox) side of container


Defaults to: `'start'`


### padding

**Tipo:** String

Sets the padding to be applied to all child items managed by this layout. ...

Sets the padding to be applied to all child items managed by this layout.

This property must be specified as a string containing space-separated, numeric padding values. The order of the
sides associated with each value matches the way CSS processes padding values:


If there is only one value, it applies to all sides.
If there are two values, the top and bottom borders are set to the first value and the right and left are
set to the second.
If there are three values, the top is set to the first value, the left and right are set to the second,
and the bottom is set to the third.
If there are four values, they apply to the top, right, bottom, and left, respectively.


Defaults to: `0`


### stretchMaxPartner

**Tipo:** String/Ext.Component

Allows stretchMax calculation to take into account the max perpendicular size (height for HBox layout and width
for V...

Allows stretchMax calculation to take into account the max perpendicular size (height for HBox layout and width
for VBox layout) of another Box layout when calculating its maximum perpendicular child size.

If specified as a string, this may be either a known Container ID, or a ComponentQuery selector which is rooted
at this layout's Container (ie, to find a sibling, use `"^>#siblingItemId`).


### titleCollapse

**Tipo:** Boolean

True to allow expand/collapse of each contained panel by clicking anywhere on the title bar, false to allow
expand/co...

True to allow expand/collapse of each contained panel by clicking anywhere on the title bar, false to allow
expand/collapse only when the toggle tool button is clicked.  When set to false,
hideCollapseTool should be false also. An explicit Ext.panel.Panel.titleCollapse declared
on the panel will override this setting.
Defaults to: `true`


### $className

**Tipo:** String

...

Defaults to: `'Ext.Base'`


### _percentageRe

**Tipo:** RegExp

Matches: <spaces>digits[.digits]<spaces>%<spaces>
Captures: digits[.digits] ...

Matches: `<spaces>digits[.digits]<spaces>%<spaces>`
Captures: `digits[.digits]`
Defaults to: `/^\s*(\d+(?:\.\d*)?)\s*[%]\s*$/`


### alignRoundingMethod

**Tipo:** String

...

Defaults to: `'round'`


### animatePolicy

**Tipo:** Object

An object which contains boolean properties specifying which properties are to be
animated upon flush of child Compon...

An object which contains boolean properties specifying which properties are to be
animated upon flush of child Component ContextItems. For example, Accordion would
have:

 {
     y: true,
     height: true
 }


### autoSizePolicy

**Tipo:** Object

...

Defaults to: `{readsWidth: 1, readsHeight: 1, setsWidth: 0, setsHeight: 0}`


### availableSpaceOffset

**Tipo:** Number

availableSpaceOffset is used to adjust the availableWidth, typically used
to reserve space for a scrollbar ...

availableSpaceOffset is used to adjust the availableWidth, typically used
to reserve space for a scrollbar
Defaults to: `0`


### calculateChildBox

**Tipo:** Object


### calculateChildBoxes

**Tipo:** Object


### childEls

**Tipo:** Array

...

Defaults to: `['innerCt', 'targetEl']`Overrides: Ext.layout.container.Container.childEls


### configMap

**Tipo:** Object

...

Defaults to: `{}`


### createsInnerCt

**Tipo:** Boolean

...

Defaults to: `true`


### defaultAnimatePolicy

**Tipo:** Object

...

Defaults to: `{y: true, height: true}`


### direction

**Tipo:** String

...

Defaults to: `'vertical'`


### done

**Tipo:** Boolean

Used only during a layout run, this value indicates that a
layout has finished its calculations. ...

Used only during a layout run, this value indicates that a
layout has finished its calculations. This flag is set to true prior to the call to
calculate and should be set to false if this layout has more work to do.


### horizontal

**Tipo:** Boolean

...

Defaults to: `false`


### initConfigList

**Tipo:** Array

...

Defaults to: `[]`


### initConfigMap

**Tipo:** Object

...

Defaults to: `{}`


### initialized

**Tipo:** Boolean

...

Defaults to: `false`


### innerCls

**Tipo:** String

...

Defaults to: `Ext.baseCSSPrefix + 'box-inner'`


### isInstance

**Tipo:** Boolean

...

Defaults to: `true`


### isLayout

**Tipo:** Boolean

true in this class to identify an object as an instantiated Layout, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Layout, or subclass thereof.
Defaults to: `true`


### manageMargins

**Tipo:** Boolean

...

Defaults to: `true`


### names

**Tipo:** Object

...

Defaults to: `{beforeX: 'top', beforeScrollX: 'top', beforeScrollerSuffix: '-before-scroller', afterScrollerSuffix: '-after-scroller', leftCap: 'Top', afterX: 'bottom', width: 'height', contentWidth: 'contentHeight', minWidth: 'minHeight', maxWidth: 'maxHeight', widthCap: 'Height', widthModel: 'heightModel', widthIndex: 1, x: 'y', scrollLeft: 'scrollTop', overflowX: 'overflowY', hasOverflowX: 'hasOverflowY', invalidateScrollX: 'invalidateScrollY', parallelMargins: 'tb', center: 'center', beforeY: 'left', afterY: 'right', height: 'width', contentHeight: 'contentWidth', minHeight: 'minWidth', maxHeight: 'maxWidth', heightCap: 'Width', heightModel: 'widthModel', heightIndex: 0, y: 'x', overflowY: 'overflowX', hasOverflowY: 'hasOverflowX', invalidateScrollY: 'invalidateScrollX', perpendicularMargins: 'lr', getWidth: 'getHeight', getHeight: 'getWidth', setWidth: 'setHeight', setHeight: 'setWidth', gotWidth: 'gotHeight', gotHeight: 'gotWidth', setContentWidth: 'setContentHeight', setContentHeight: 'setContentWidth', setWidthInDom: 'setHeightInDom', setHeightInDom: 'setWidthInDom', getScrollLeft: 'getScrollTop', setScrollLeft: 'setScrollTop', scrollTo: 'scrollTo'}`


### overflowPadderEl

**Tipo:** Ext.Element

The element used to correct body padding during overflow.


### renderTpl

**Tipo:** Array

...

Defaults to: `['{%var oc,l=values.$comp.layout,oh=l.overflowHandler;', 'if (oh.getPrefixConfig!==Ext.emptyFn) {', 'if(oc=oh.getPrefixConfig())dh.generateMarkup(oc, out)', '}%}', '<div id="{ownerId}-innerCt" class="{[l.innerCls]} {[oh.getOverflowCls()]}" role="presentation">', '<div id="{ownerId}-targetEl" class="{targetElCls}">', '{%this.renderBody(out, values)%}', '</div>', '</div>', '{%if (oh.getSuffixConfig!==Ext.emptyFn) {', 'if(oc=oh.getSuffixConfig())dh.generateMarkup(oc, out)', '}%}', {disableFormats: true, definitions: 'var dh=Ext.DomHelper;'}]`Overrides: Ext.layout.container.Container.renderTpl


### reserveOffset

**Tipo:** Boolean

whether or not to reserve the availableSpaceOffset in layout calculations ...

whether or not to reserve the availableSpaceOffset in layout calculations
Defaults to: `true`


### running

**Tipo:** Boolean

...

Defaults to: `false`


### scrollOffset

**Tipo:** Number

...

Defaults to: `0`


### self

**Tipo:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics,
`this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics
for a detailed comparison

Ext.define('My.Cat', {
    statics: {
        speciesName: 'Cat' // My.Cat.speciesName = 'Cat'
    },

    constructor: function() {
        alert(this.self.speciesName); // dependent on 'this'
    },

    clone: function() {
        return new this.self();
    }
});


Ext.define('My.SnowLeopard', {
    extend: 'My.Cat',
    statics: {
        speciesName: 'Snow Leopard'         // My.SnowLeopard.speciesName = 'Snow Leopard'
    }
});

var cat = new My.Cat();                     // alerts 'Cat'
var snowLeopard = new My.SnowLeopard();     // alerts 'Snow Leopard'

var clone = snowLeopard.clone();
alert(Ext.getClassName(clone));             // alerts 'My.SnowLeopard'


### sizePolicy

**Tipo:** Object

...

Defaults to: `{flex: {'': {readsWidth: 1, readsHeight: 0, setsWidth: 0, setsHeight: 1}, stretch: {readsWidth: 0, readsHeight: 0, setsWidth: 1, setsHeight: 1}, stretchmax: {readsWidth: 1, readsHeight: 0, setsWidth: 1, setsHeight: 1}}, '': {readsWidth: 1, readsHeight: 1, setsWidth: 0, setsHeight: 0}, stretch: {readsWidth: 0, readsHeight: 1, setsWidth: 1, setsHeight: 0}, stretchmax: {readsWidth: 1, readsHeight: 1, setsWidth: 1, setsHeight: 0}}`


### targetCls

**Tipo:** String

...

Defaults to: `Ext.baseCSSPrefix + 'accordion-layout-ct'`Overrides: Ext.layout.container.Box.targetCls


### targetElCls

**Tipo:** String

...

Defaults to: `Ext.baseCSSPrefix + 'box-target'`


### type

**Tipo:** String

...

Defaults to: `'vbox'`Overrides: Ext.layout.container.Box.type


### updateChildBoxes

**Tipo:** Object


### usesContainerHeight

**Tipo:** Boolean

...

Defaults to: `true`


### usesContainerWidth

**Tipo:** Boolean

...

Defaults to: `true`


### usesHeight

**Tipo:** Boolean

...

Defaults to: `true`


### usesWidth

**Tipo:** Boolean

...

Defaults to: `true`


### $onExtended

**Tipo:** Array

...

Defaults to: `[]`


### Ext.layout.container.Accordion

...

ReturnsExt.layout.container.Accordion


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### afterRemove

Removes layout's itemCls and owning Container's itemCls. ...

Removes layout's itemCls and owning Container's itemCls.
Clears the managed dimensions flags
Parametersitem : Object


### afterRenderItem

...


### applyChildEls

Sets references to elements inside the component. ...

Sets references to elements inside the component.
Parametersel : Object


### beforeRenderItems

...

Parametersitems : Object


### beginCollapse

Called by an owning Panel before the Panel begins its collapse process. ...

Called by an owning Panel before the Panel begins its collapse process.
Most layouts will not need to override the default Ext.emptyFn implementation.
Parameterschild : Object


### beginExpand

Called by an owning Panel before the Panel begins its expand process. ...

Called by an owning Panel before the Panel begins its expand process.
Most layouts will not need to override the default Ext.emptyFn implementation.
Parameterschild : Object


### beginLayout

In addition to work done by our base classes, containers benefit from some extra
cached data. ...

In addition to work done by our base classes, containers benefit from some extra
cached data. The following properties are added to the ownerContext:


visibleItems: the result of getVisibleItems
childItems: the ContextItem[] for each visible item
targetContext: the ContextItem for the getTarget element


ParametersownerContext : Object


### beginLayoutCycle

Called before any calculation cycles to reset DOM values and prepare for calculation. ...

Called before any calculation cycles to reset DOM values and prepare for calculation.

This is a write phase and DOM reads should be strictly avoided when overridding
this method.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### cacheChildItems

...

ParametersownerContext : Object


### cacheElements

...


### cacheFlexes

This method is called to (re)cache our understanding of flexes. ...

This method is called to (re)cache our understanding of flexes. This happens during beginLayout and may need to
be called again if the flexes are changed during the layout (e.g., like ColumnLayout).
ParametersownerContext : Object


### calculate

Called to perform the calculations for this layout. ...

Called to perform the calculations for this layout. This method will be called at
least once and may be called repeatedly if the done property is cleared
before return to indicate that this layout is not yet done. The done property
is always set to `true` before entering this method.

This is a read phase and DOM writes should be strictly avoided in derived classes.
Instead, DOM writes need to be written to Ext.layout.ContextItem objects to
 be flushed at the next opportunity.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### calculateParallel

...

ParametersownerContext : Object


### calculatePerpendicular

...

ParametersownerContext : Object


### calculateStretchMax

...

ParametersownerContext : Object


### callOverridden

Call the original method that was previously overridden with override

Ext.define('My.Cat', {
    constructor: functi...

Call the original method that was previously overridden with override

Ext.define('My.Cat', {
    constructor: function() {
        alert("I'm a cat!");
    }
});

My.Cat.override({
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callOverridden();

        alert("Meeeeoooowwww");
    }
});

var kitty = new My.Cat(); // alerts "I'm going to be a cat!"
                          // alerts "I'm a cat!"
                          // alerts "Meeeeoooowwww"

        
        This method has been **deprecated** 
        as of 4.1. Use callParent instead.


### callParent

Call the "parent" method of the current method. ...

Call the "parent" method of the current method. That is the method previously
overridden by derivation or by an override (see Ext.define).

 Ext.define('My.Base', {
     constructor: function (x) {
         this.x = x;
     },

     statics: {
         method: function (x) {
             return x;
         }
     }
 });

 Ext.define('My.Derived', {
     extend: 'My.Base',

     constructor: function () {
         this.callParent([21]);
     }
 });

 var obj = new My.Derived();

 alert(obj.x);  // alerts 21


This can be used with an override as follows:

 Ext.define('My.DerivedOverride', {
     override: 'My.Derived',

     constructor: function (x) {
         this.callParent([x*2]); // calls original My.Derived constructor
     }
 });

 var obj = new My.Derived();

 alert(obj.x);  // now alerts 42


This also works with static methods.

 Ext.define('My.Derived2', {
     extend: 'My.Base',

     statics: {
         method: function (x) {
             return this.callParent([x*2]); // calls My.Base.method
         }
     }
 });

 alert(My.Base.method(10);     // alerts 10
 alert(My.Derived2.method(10); // alerts 20


Lastly, it also works with overridden static methods.

 Ext.define('My.Derived2Override', {
     override: 'My.Derived2',

     statics: {
         method: function (x) {
             return this.callParent([x*2]); // calls My.Derived2.method
         }
     }
 });

 alert(My.Derived2.method(10); // now alerts 40


To override a method and replace it and also call the superclass method, use
callSuper. This is often done to patch a method to fix a bug.
Parametersargs : Array/ArgumentsThe arguments, either an array or the `arguments` object
from the current method, for example: `this.callParent(arguments)`


### callSuper

This method is used by an override to call the superclass method but bypass any
overridden method. ...

This method is used by an override to call the superclass method but bypass any
overridden method. This is often done to "patch" a method that contains a bug
but for whatever reason cannot be fixed directly.

Consider:

 Ext.define('Ext.some.Class', {
     method: function () {
         console.log('Good');
     }
 });

 Ext.define('Ext.some.DerivedClass', {
     method: function () {
         console.log('Bad');

         // ... logic but with a bug ...

         this.callParent();
     }
 });


To patch the bug in `DerivedClass.method`, the typical solution is to create an
override:

 Ext.define('App.paches.DerivedClass', {
     override: 'Ext.some.DerivedClass',

     method: function () {
         console.log('Fixed');

         // ... logic but with bug fixed ...

         this.callSuper();
     }
 });


The patch method cannot use `callParent` to call the superclass `method` since
that would call the overridden method containing the bug. In other words, the
above patch would only produce "Fixed" then "Good" in the console log, whereas,
using `callParent` would produce "Fixed" then "Bad" then "Good".
Parametersargs : Array/ArgumentsThe arguments, either an array or the `arguments` object
from the current method, for example: `this.callSuper(arguments)`


### completeLayout

This method (if implemented) is called at the end of the cycle in which this layout
completes (by not setting done to...

This method (if implemented) is called at the end of the cycle in which this layout
completes (by not setting done to `false` in calculate). It is
possible for the layout to complete and yet become invalid before the end of the cycle,
in which case, this method will not be called. It is also possible for this method to
be called and then later the layout becomes invalidated. This will result in
calculate being called again, followed by another call to this method.

This is a read phase and DOM writes should be strictly avoided in derived classes.
Instead, DOM writes need to be written to Ext.layout.ContextItem objects to
be flushed at the next opportunity.

This method need not be implemented by derived classes and, in fact, should only be
implemented when needed.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### configClass

...


### configureItem

Adds layout's itemCls and owning Container's itemCls ...

Adds layout's itemCls and owning Container's itemCls
Parametersitem : Object


### destroy

...

Overrides: Ext.layout.container.Container.destroy


### doRenderBody

...

Parametersout : Object


### doRenderContainer

...

Parametersout : Object


### doRenderItems

...

Parametersout : Object


### finalizeLayout

This method (if implemented) is called after all layouts have completed. ...

This method (if implemented) is called after all layouts have completed. In most
ways this is similar to completeLayout. This call can cause this (or any
layout) to be become invalid (see Ext.layout.Context.invalidate), but this
is best avoided. This method is intended to be where final reads are made and so it
is best to avoid invalidating layouts at this point whenever possible. Even so, this
method can be used to perform final checks that may require all other layouts to be
complete and then invalidate some results.

This is a read phase and DOM writes should be strictly avoided in derived classes.
Instead, DOM writes need to be written to Ext.layout.ContextItem objects to
be flushed at the next opportunity.

This method need not be implemented by derived classes and, in fact, should only be
implemented when needed.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### finishRender

...

Overrides: Ext.layout.Layout.finishRender


### finishRenderItems

...

Parameterstarget : Object


### finishedLayout

This method is called after all layouts are complete and their calculations flushed
to the DOM. ...

This method is called after all layouts are complete and their calculations flushed
to the DOM. No further layouts will be run and this method is only called once per
layout run. The base component layout caches `lastComponentSize`.

This is a write phase and DOM reads should be avoided if possible when overridding
this method.

This method need not be implemented by derived classes and, in fact, should only be
implemented when needed.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### flexSort

...

Parametersa : Object


### getAnimatePolicy

...


### getChildEls

...


### getClassChildEls

...

Parameterscls : Object


### getConfig

...

Parametersname : Object


### getContainerSize

Returns the container size (that of the target). ...

Returns the container size (that of the target). Only the fixed-sized dimensions can
be returned because the shrinkWrap dimensions are based on the contentWidth/Height
as determined by the container layout.
ParametersownerContext : Ext.layout.ContextItemThe owner's context item.


### getContentTarget

...


### getElementTarget

Overridden method from Ext.layout.container.Container. ...

Overridden method from Ext.layout.container.Container.
Used by Container classes to insert special DOM elements which must exist in addition to the child components

Returns the element into which extra functional DOM elements can be inserted. Defaults to the owner Component's encapsulating element.

May be overridden in Component layout managers which implement a component render target which must only
contain child components.
ReturnsExt.Element


### getExpanded

...

ParametersexplicitCheck : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### getItemSizePolicy

Returns an object describing how this layout manages the size of the given component. ...

Returns an object describing how this layout manages the size of the given component.
This method must be implemented by any layout that manages components.
Parametersitem : Ext.Component


### getItemsRenderTree

...

Parametersitems : Object


### getLayoutItems

Returns an array of child components either for a render phase (Performed in the beforeLayout
method of the layout's ...

Returns an array of child components either for a render phase (Performed in the beforeLayout
method of the layout's base class), or the layout phase (onLayout).
ReturnsExt.Component[]of child components


### getPositionOffset

This method is used to offset the DOM position when checking
whether the element is a certain child of the target. ...

This method is used to offset the DOM position when checking
whether the element is a certain child of the target. This is
required in cases where the extra elements prepended to the target
before any of the items. An example of this is when using labelAlign: 'top'
on a field. The label appears first in the DOM before any child items are
created, so when we check the position we need to add an extra offset.
Containers that create an innerCt are exempt because this new element
preserves the order
Parametersposition : Object


### getRenderData

...

Overrides: Ext.layout.container.Container.getRenderData


### getRenderTarget

Overridden method from Ext.layout.container.Container. ...

Overridden method from Ext.layout.container.Container.
Used in the beforeLayout method to render all items into.

Returns the element into which rendering must take place. Defaults to the owner Container's
target element.

May be overridden in layout managers which implement an inner element.
ReturnsExt.Element


### getRenderTpl

...


### getRenderTree

...


### getRenderedItems

Returns all items that are rendered ...

Returns all items that are rendered
ReturnsArrayAll matching items


### getScrollbarsNeeded

...

Parameterswidth : Object


### getTarget

Returns the owner component's resize element. ...

Returns the owner component's resize element.
ReturnsExt.Element


### getVisibleItems

Returns all items that are both rendered and visible ...

Returns all items that are both rendered and visible
ReturnsArrayAll matching items


### hasConfig

...

Parametersconfig : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

Ext.define('My.awesome.Class', {
    // The default config
    config: {
        name: 'Awesome',
        isAwesome: true
    },

    constructor: function(config) {
        this.initConfig(config);
    }
});

var awesome = new My.awesome.Class({
    name: 'Super Awesome'
});

alert(awesome.getName()); // 'Super Awesome'

Parametersconfig : Object


### initLayout

A one-time initialization method called just before rendering. ...

A one-time initialization method called just before rendering.


### initOverflowHandler

...


### isItemBoxParent

...

ParametersitemContext : Object


### isItemLayoutRoot

...

Parametersitem : Object


### isItemShrinkWrap

...

Parametersitem : Object


### isRunning

...


### isValidParent

Validates item is in the proper place in the dom. ...

Validates item is in the proper place in the dom.
Parametersitem : Object


### moveItem

Moves Component to the provided target instead. ...

Moves Component to the provided target instead.
Parametersitem : Object


### notifyOwner

Called for every layout in the layout context after all the layouts have been finally flushed ...

Called for every layout in the layout context after all the layouts have been finally flushed
Overrides: Ext.layout.Layout.notifyOwner


### onAdd

...

Parametersitem : Object


### onAfterConstrainInvalidateChild

...

ParameterschildContext : Object


### onAfterStretchMaxInvalidateChild

...

ParameterschildContext : Object


### onBeforeConstrainInvalidateChild

...

ParameterschildContext : Object


### onBeforeStretchMaxInvalidateChild

...

ParameterschildContext : Object


### onComponentCollapse

...

Parameterscomp : Object


### onComponentExpand

When a Component expands, adjust the heights of the other Components to be just enough to accommodate
their headers. ...

When a Component expands, adjust the heights of the other Components to be just enough to accommodate
their headers.
The expanded Component receives the only flex value, and so gets all remaining space.
ParameterstoExpand : Object


### onComponentShow

...

Parameterscomp : Object


### onConfigUpdate

...

Parametersnames : Object


### onContentChange

This method is called when a child item changes in some way. ...

This method is called when a child item changes in some way. By default this calls
Ext.AbstractComponent.updateLayout on this layout's owner.
Parameterschild : Ext.ComponentThe child item that has changed.


### onDestroy

...


### onRemove

...

Parameterscomp : Object


### prune

...

ParameterschildEls : Object


### publishInnerCtSize

...

ParametersownerContext : Object


### removeChildEls

Removes items in the childEls array based on the return value of a supplied test
function. ...

Removes items in the childEls array based on the return value of a supplied test
function. The function is called with a entry in childEls and if the test function
return true, that entry is removed. If false, that entry is kept.
ParameterstestFn : FunctionThe test function.


### renderChildren

...

Overrides: Ext.layout.Layout.renderChildren


### renderItem

Renders the given Component into the target Element. ...

Renders the given Component into the target Element.
Parametersitem : Ext.ComponentThe Component to render


### renderItems

Iterates over all passed items, ensuring they are rendered. ...

Iterates over all passed items, ensuring they are rendered.  If the items are already rendered,
also determines if the items are in the proper place in the dom.
Parametersitems : Object


### roundFlex

...

Parameterswidth : Object


### setConfig

...

Parametersconfig : Object


### setOwner

Sets the layout owner ...

Sets the layout owner
Parametersowner : Object


### setupRenderTpl

...

ParametersrenderTpl : Object


### sortWeightedItems

...

Parametersitems : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self,
`this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what
`this` points to during run-time

Ext.define('My.Cat', {
    statics: {
        totalCreated: 0,
        speciesName: 'Cat' // My.Cat.speciesName = 'Cat'
    },

    constructor: function() {
        var statics = this.statics();

        alert(statics.speciesName);     // always equals to 'Cat' no matter what 'this' refers to
                                        // equivalent to: My.Cat.speciesName

        alert(this.self.speciesName);   // dependent on 'this'

        statics.totalCreated++;
    },

    clone: function() {
        var cloned = new this.self;                      // dependent on 'this'

        cloned.groupName = this.statics().speciesName;   // equivalent to: My.Cat.speciesName

        return cloned;
    }
});


Ext.define('My.SnowLeopard', {
    extend: 'My.Cat',

    statics: {
        speciesName: 'Snow Leopard'     // My.SnowLeopard.speciesName = 'Snow Leopard'
    },

    constructor: function() {
        this.callParent();
    }
});

var cat = new My.Cat();                 // alerts 'Cat', then alerts 'Cat'

var snowLeopard = new My.SnowLeopard(); // alerts 'Cat', then alerts 'Snow Leopard'

var clone = snowLeopard.clone();
alert(Ext.getClassName(clone));         // alerts 'My.SnowLeopard'
alert(clone.groupName);                 // alerts 'Cat'

alert(My.Cat.totalCreated);             // alerts 3

ReturnsExt.Class


### undoLayout

...


### updatePanelClasses

...

ParametersownerContext : Object


### addConfig

...

Parametersconfig : Object


### addInheritableStatics

...

Parametersmembers : Object


### addMember

...

Parametersname : Object


### addMembers

Add methods / properties to the prototype of this class. ...

Add methods / properties to the prototype of this class.

Ext.define('My.awesome.Cat', {
    constructor: function() {
        ...
    }
});

 My.awesome.Cat.addMembers({
     meow: function() {
        alert('Meowww...');
     }
 });

 var kitty = new My.awesome.Cat;
 kitty.meow();

Parametersmembers : Object


### addStatics

Add / override static properties of this class. ...

Add / override static properties of this class.

Ext.define('My.cool.Class', {
    ...
});

My.cool.Class.addStatics({
    someProperty: 'someValue',      // My.cool.Class.someProperty = 'someValue'
    method1: function() { ... },    // My.cool.Class.method1 = function() { ... };
    method2: function() { ... }     // My.cool.Class.method2 = function() { ... };
});

Parametersmembers : Object


### addXtype

...

Parametersxtype : Object


### borrow

Borrow another class' members to the prototype of this class. ...

Borrow another class' members to the prototype of this class.

Ext.define('Bank', {
    money: '$$$',
    printMoney: function() {
        alert('$$$$$$$');
    }
});

Ext.define('Thief', {
    ...
});

Thief.borrow(Bank, ['money', 'printMoney']);

var steve = new Thief();

alert(steve.money); // alerts '$$$'
steve.printMoney(); // alerts '$$$$$$$'

ParametersfromClass : Ext.BaseThe class to borrow members from


### create

Create a new instance of this Class. ...

Create a new instance of this Class.

Ext.define('My.cool.Class', {
    ...
});

My.cool.Class.create({
    someConfig: true
});


All parameters are passed to the constructor of the class.
ReturnsObjectthe created instance.


### createAlias

Create aliases for existing prototype methods. ...

Create aliases for existing prototype methods. Example:

Ext.define('My.cool.Class', {
    method1: function() { ... },
    method2: function() { ... }
});

var test = new My.cool.Class();

My.cool.Class.createAlias({
    method3: 'method1',
    method4: 'method2'
});

test.method3(); // test.method1()

My.cool.Class.createAlias('method5', 'method3');

test.method5(); // test.method3() -> test.method1()

Parametersalias : String/ObjectThe new method name, or an object to set multiple aliases. See
flexSetter


### extend

...

Parametersconfig : Object


### getName

Get the current class' name in string format. ...

Get the current class' name in string format.

Ext.define('My.cool.Class', {
    constructor: function() {
        alert(this.self.getName()); // alerts 'My.cool.Class'
    }
});

My.cool.Class.getName(); // 'My.cool.Class'

ReturnsStringclassName


### implement

Adds members to class. ...

Adds members to class.
        
        This method has been **deprecated** since 4.1
        Use addMembers instead.


### mixin

Used internally by the mixins pre-processor ...

Used internally by the mixins pre-processor
Parametersname : Object


### onExtended

...

Parametersfn : Object


### override

Override members of this class. ...

Override members of this class. Overridden methods can be invoked via
callParent.

Ext.define('My.Cat', {
    constructor: function() {
        alert("I'm a cat!");
    }
});

My.Cat.override({
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callParent(arguments);

        alert("Meeeeoooowwww");
    }
});

var kitty = new My.Cat(); // alerts "I'm going to be a cat!"
                          // alerts "I'm a cat!"
                          // alerts "Meeeeoooowwww"


As of 4.1, direct use of this method is deprecated. Use Ext.define
instead:

Ext.define('My.CatOverride', {
    override: 'My.Cat',
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callParent(arguments);

        alert("Meeeeoooowwww");
    }
});


The above accomplishes the same result but can be managed by the Ext.Loader
which can properly order the override and its target class and the build process
can determine whether the override is needed based on the required state of the
target class (My.Cat).
        
        This method has been **deprecated** since 4.1.0
        Use Ext.define instead


### triggerExtended

...


### $accordion-background-color

**Tipo:** color

The background-color of the Accordion layout element ...

The background-color of the Accordion layout element
Defaults to: `#fff`


### $accordion-body-border-width

**Tipo:** string

The text-transform property of Accordion headers ...

The text-transform property of Accordion headers
Defaults to: `0`


### $accordion-header-background-color

**Tipo:** color

The background-color of Accordion headers ...

The background-color of Accordion headers
Defaults to: `$base-color`


### $accordion-header-border-width

**Tipo:** number/list

The border-width of Accordion headers ...

The border-width of Accordion headers
Defaults to: `1px 0`


### $accordion-header-color

**Tipo:** color

The text color of Accordion headers ...

The text color of Accordion headers
Defaults to: `#000`


### $accordion-header-font-family

**Tipo:** string

The font-family of Accordion headers ...

The font-family of Accordion headers
Defaults to: `$font-family`


### $accordion-header-font-weight

**Tipo:** string

The font-weight of Accordion headers ...

The font-weight of Accordion headers
Defaults to: `normal`


### $accordion-header-padding

**Tipo:** number/list

The padding of Accordion headers ...

The padding of Accordion headers
Defaults to: `4px 5px`


### $accordion-header-text-transform

**Tipo:** string

The text-transform property of Accordion headers ...

The text-transform property of Accordion headers
Defaults to: `none`


### $accordion-header-tool-size

**Tipo:** number

The size of Tools in Accordion headers ...

The size of Tools in Accordion headers
Defaults to: `$tool-size`


### $accordion-item-margin

**Tipo:** number/list

The padding of the Accordion layout element ...

The padding of the Accordion layout element
Defaults to: `0`


### $accordion-padding

**Tipo:** color

The background-color of the Accordion layout element ...

The background-color of the Accordion layout element
Defaults to: `0`


### $accordion-tool-background-image

**Tipo:** string

The sprite image to use for Tools in Accordion headers ...

The sprite image to use for Tools in Accordion headers
Defaults to: `'tools/tool-sprites'`


## Properties

### $className

**Tipo:** String

...

Defaults to: `'Ext.Base'`


### _percentageRe

**Tipo:** RegExp

Matches: <spaces>digits[.digits]<spaces>%<spaces>
Captures: digits[.digits] ...

Matches: `<spaces>digits[.digits]<spaces>%<spaces>`
Captures: `digits[.digits]`
Defaults to: `/^\s*(\d+(?:\.\d*)?)\s*[%]\s*$/`


### alignRoundingMethod

**Tipo:** String

...

Defaults to: `'round'`


### animatePolicy

**Tipo:** Object

An object which contains boolean properties specifying which properties are to be
animated upon flush of child Compon...

An object which contains boolean properties specifying which properties are to be
animated upon flush of child Component ContextItems. For example, Accordion would
have:

 {
     y: true,
     height: true
 }


### autoSizePolicy

**Tipo:** Object

...

Defaults to: `{readsWidth: 1, readsHeight: 1, setsWidth: 0, setsHeight: 0}`


### availableSpaceOffset

**Tipo:** Number

availableSpaceOffset is used to adjust the availableWidth, typically used
to reserve space for a scrollbar ...

availableSpaceOffset is used to adjust the availableWidth, typically used
to reserve space for a scrollbar
Defaults to: `0`


### calculateChildBox

**Tipo:** Object


### calculateChildBoxes

**Tipo:** Object


### childEls

**Tipo:** Array

...

Defaults to: `['innerCt', 'targetEl']`Overrides: Ext.layout.container.Container.childEls


### configMap

**Tipo:** Object

...

Defaults to: `{}`


### createsInnerCt

**Tipo:** Boolean

...

Defaults to: `true`


### defaultAnimatePolicy

**Tipo:** Object

...

Defaults to: `{y: true, height: true}`


### direction

**Tipo:** String

...

Defaults to: `'vertical'`


### done

**Tipo:** Boolean

Used only during a layout run, this value indicates that a
layout has finished its calculations. ...

Used only during a layout run, this value indicates that a
layout has finished its calculations. This flag is set to true prior to the call to
calculate and should be set to false if this layout has more work to do.


### horizontal

**Tipo:** Boolean

...

Defaults to: `false`


### initConfigList

**Tipo:** Array

...

Defaults to: `[]`


### initConfigMap

**Tipo:** Object

...

Defaults to: `{}`


### initialized

**Tipo:** Boolean

...

Defaults to: `false`


### innerCls

**Tipo:** String

...

Defaults to: `Ext.baseCSSPrefix + 'box-inner'`


### isInstance

**Tipo:** Boolean

...

Defaults to: `true`


### isLayout

**Tipo:** Boolean

true in this class to identify an object as an instantiated Layout, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Layout, or subclass thereof.
Defaults to: `true`


### manageMargins

**Tipo:** Boolean

...

Defaults to: `true`


### names

**Tipo:** Object

...

Defaults to: `{beforeX: 'top', beforeScrollX: 'top', beforeScrollerSuffix: '-before-scroller', afterScrollerSuffix: '-after-scroller', leftCap: 'Top', afterX: 'bottom', width: 'height', contentWidth: 'contentHeight', minWidth: 'minHeight', maxWidth: 'maxHeight', widthCap: 'Height', widthModel: 'heightModel', widthIndex: 1, x: 'y', scrollLeft: 'scrollTop', overflowX: 'overflowY', hasOverflowX: 'hasOverflowY', invalidateScrollX: 'invalidateScrollY', parallelMargins: 'tb', center: 'center', beforeY: 'left', afterY: 'right', height: 'width', contentHeight: 'contentWidth', minHeight: 'minWidth', maxHeight: 'maxWidth', heightCap: 'Width', heightModel: 'widthModel', heightIndex: 0, y: 'x', overflowY: 'overflowX', hasOverflowY: 'hasOverflowX', invalidateScrollY: 'invalidateScrollX', perpendicularMargins: 'lr', getWidth: 'getHeight', getHeight: 'getWidth', setWidth: 'setHeight', setHeight: 'setWidth', gotWidth: 'gotHeight', gotHeight: 'gotWidth', setContentWidth: 'setContentHeight', setContentHeight: 'setContentWidth', setWidthInDom: 'setHeightInDom', setHeightInDom: 'setWidthInDom', getScrollLeft: 'getScrollTop', setScrollLeft: 'setScrollTop', scrollTo: 'scrollTo'}`


### overflowPadderEl

**Tipo:** Ext.Element

The element used to correct body padding during overflow.


### renderTpl

**Tipo:** Array

...

Defaults to: `['{%var oc,l=values.$comp.layout,oh=l.overflowHandler;', 'if (oh.getPrefixConfig!==Ext.emptyFn) {', 'if(oc=oh.getPrefixConfig())dh.generateMarkup(oc, out)', '}%}', '<div id="{ownerId}-innerCt" class="{[l.innerCls]} {[oh.getOverflowCls()]}" role="presentation">', '<div id="{ownerId}-targetEl" class="{targetElCls}">', '{%this.renderBody(out, values)%}', '</div>', '</div>', '{%if (oh.getSuffixConfig!==Ext.emptyFn) {', 'if(oc=oh.getSuffixConfig())dh.generateMarkup(oc, out)', '}%}', {disableFormats: true, definitions: 'var dh=Ext.DomHelper;'}]`Overrides: Ext.layout.container.Container.renderTpl


### reserveOffset

**Tipo:** Boolean

whether or not to reserve the availableSpaceOffset in layout calculations ...

whether or not to reserve the availableSpaceOffset in layout calculations
Defaults to: `true`


### running

**Tipo:** Boolean

...

Defaults to: `false`


### scrollOffset

**Tipo:** Number

...

Defaults to: `0`


### self

**Tipo:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics,
`this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics
for a detailed comparison

Ext.define('My.Cat', {
    statics: {
        speciesName: 'Cat' // My.Cat.speciesName = 'Cat'
    },

    constructor: function() {
        alert(this.self.speciesName); // dependent on 'this'
    },

    clone: function() {
        return new this.self();
    }
});


Ext.define('My.SnowLeopard', {
    extend: 'My.Cat',
    statics: {
        speciesName: 'Snow Leopard'         // My.SnowLeopard.speciesName = 'Snow Leopard'
    }
});

var cat = new My.Cat();                     // alerts 'Cat'
var snowLeopard = new My.SnowLeopard();     // alerts 'Snow Leopard'

var clone = snowLeopard.clone();
alert(Ext.getClassName(clone));             // alerts 'My.SnowLeopard'


### sizePolicy

**Tipo:** Object

...

Defaults to: `{flex: {'': {readsWidth: 1, readsHeight: 0, setsWidth: 0, setsHeight: 1}, stretch: {readsWidth: 0, readsHeight: 0, setsWidth: 1, setsHeight: 1}, stretchmax: {readsWidth: 1, readsHeight: 0, setsWidth: 1, setsHeight: 1}}, '': {readsWidth: 1, readsHeight: 1, setsWidth: 0, setsHeight: 0}, stretch: {readsWidth: 0, readsHeight: 1, setsWidth: 1, setsHeight: 0}, stretchmax: {readsWidth: 1, readsHeight: 1, setsWidth: 1, setsHeight: 0}}`


### targetCls

**Tipo:** String

...

Defaults to: `Ext.baseCSSPrefix + 'accordion-layout-ct'`Overrides: Ext.layout.container.Box.targetCls


### targetElCls

**Tipo:** String

...

Defaults to: `Ext.baseCSSPrefix + 'box-target'`


### type

**Tipo:** String

...

Defaults to: `'vbox'`Overrides: Ext.layout.container.Box.type


### updateChildBoxes

**Tipo:** Object


### usesContainerHeight

**Tipo:** Boolean

...

Defaults to: `true`


### usesContainerWidth

**Tipo:** Boolean

...

Defaults to: `true`


### usesHeight

**Tipo:** Boolean

...

Defaults to: `true`


### usesWidth

**Tipo:** Boolean

...

Defaults to: `true`


### $onExtended

**Tipo:** Array

...

Defaults to: `[]`


### Ext.layout.container.Accordion

...

ReturnsExt.layout.container.Accordion


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### afterRemove

Removes layout's itemCls and owning Container's itemCls. ...

Removes layout's itemCls and owning Container's itemCls.
Clears the managed dimensions flags
Parametersitem : Object


### afterRenderItem

...


### applyChildEls

Sets references to elements inside the component. ...

Sets references to elements inside the component.
Parametersel : Object


### beforeRenderItems

...

Parametersitems : Object


### beginCollapse

Called by an owning Panel before the Panel begins its collapse process. ...

Called by an owning Panel before the Panel begins its collapse process.
Most layouts will not need to override the default Ext.emptyFn implementation.
Parameterschild : Object


### beginExpand

Called by an owning Panel before the Panel begins its expand process. ...

Called by an owning Panel before the Panel begins its expand process.
Most layouts will not need to override the default Ext.emptyFn implementation.
Parameterschild : Object


### beginLayout

In addition to work done by our base classes, containers benefit from some extra
cached data. ...

In addition to work done by our base classes, containers benefit from some extra
cached data. The following properties are added to the ownerContext:


visibleItems: the result of getVisibleItems
childItems: the ContextItem[] for each visible item
targetContext: the ContextItem for the getTarget element


ParametersownerContext : Object


### beginLayoutCycle

Called before any calculation cycles to reset DOM values and prepare for calculation. ...

Called before any calculation cycles to reset DOM values and prepare for calculation.

This is a write phase and DOM reads should be strictly avoided when overridding
this method.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### cacheChildItems

...

ParametersownerContext : Object


### cacheElements

...


### cacheFlexes

This method is called to (re)cache our understanding of flexes. ...

This method is called to (re)cache our understanding of flexes. This happens during beginLayout and may need to
be called again if the flexes are changed during the layout (e.g., like ColumnLayout).
ParametersownerContext : Object


### calculate

Called to perform the calculations for this layout. ...

Called to perform the calculations for this layout. This method will be called at
least once and may be called repeatedly if the done property is cleared
before return to indicate that this layout is not yet done. The done property
is always set to `true` before entering this method.

This is a read phase and DOM writes should be strictly avoided in derived classes.
Instead, DOM writes need to be written to Ext.layout.ContextItem objects to
 be flushed at the next opportunity.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### calculateParallel

...

ParametersownerContext : Object


### calculatePerpendicular

...

ParametersownerContext : Object


### calculateStretchMax

...

ParametersownerContext : Object


### callOverridden

Call the original method that was previously overridden with override

Ext.define('My.Cat', {
    constructor: functi...

Call the original method that was previously overridden with override

Ext.define('My.Cat', {
    constructor: function() {
        alert("I'm a cat!");
    }
});

My.Cat.override({
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callOverridden();

        alert("Meeeeoooowwww");
    }
});

var kitty = new My.Cat(); // alerts "I'm going to be a cat!"
                          // alerts "I'm a cat!"
                          // alerts "Meeeeoooowwww"

        
        This method has been **deprecated** 
        as of 4.1. Use callParent instead.


### callParent

Call the "parent" method of the current method. ...

Call the "parent" method of the current method. That is the method previously
overridden by derivation or by an override (see Ext.define).

 Ext.define('My.Base', {
     constructor: function (x) {
         this.x = x;
     },

     statics: {
         method: function (x) {
             return x;
         }
     }
 });

 Ext.define('My.Derived', {
     extend: 'My.Base',

     constructor: function () {
         this.callParent([21]);
     }
 });

 var obj = new My.Derived();

 alert(obj.x);  // alerts 21


This can be used with an override as follows:

 Ext.define('My.DerivedOverride', {
     override: 'My.Derived',

     constructor: function (x) {
         this.callParent([x*2]); // calls original My.Derived constructor
     }
 });

 var obj = new My.Derived();

 alert(obj.x);  // now alerts 42


This also works with static methods.

 Ext.define('My.Derived2', {
     extend: 'My.Base',

     statics: {
         method: function (x) {
             return this.callParent([x*2]); // calls My.Base.method
         }
     }
 });

 alert(My.Base.method(10);     // alerts 10
 alert(My.Derived2.method(10); // alerts 20


Lastly, it also works with overridden static methods.

 Ext.define('My.Derived2Override', {
     override: 'My.Derived2',

     statics: {
         method: function (x) {
             return this.callParent([x*2]); // calls My.Derived2.method
         }
     }
 });

 alert(My.Derived2.method(10); // now alerts 40


To override a method and replace it and also call the superclass method, use
callSuper. This is often done to patch a method to fix a bug.
Parametersargs : Array/ArgumentsThe arguments, either an array or the `arguments` object
from the current method, for example: `this.callParent(arguments)`


### callSuper

This method is used by an override to call the superclass method but bypass any
overridden method. ...

This method is used by an override to call the superclass method but bypass any
overridden method. This is often done to "patch" a method that contains a bug
but for whatever reason cannot be fixed directly.

Consider:

 Ext.define('Ext.some.Class', {
     method: function () {
         console.log('Good');
     }
 });

 Ext.define('Ext.some.DerivedClass', {
     method: function () {
         console.log('Bad');

         // ... logic but with a bug ...

         this.callParent();
     }
 });


To patch the bug in `DerivedClass.method`, the typical solution is to create an
override:

 Ext.define('App.paches.DerivedClass', {
     override: 'Ext.some.DerivedClass',

     method: function () {
         console.log('Fixed');

         // ... logic but with bug fixed ...

         this.callSuper();
     }
 });


The patch method cannot use `callParent` to call the superclass `method` since
that would call the overridden method containing the bug. In other words, the
above patch would only produce "Fixed" then "Good" in the console log, whereas,
using `callParent` would produce "Fixed" then "Bad" then "Good".
Parametersargs : Array/ArgumentsThe arguments, either an array or the `arguments` object
from the current method, for example: `this.callSuper(arguments)`


### completeLayout

This method (if implemented) is called at the end of the cycle in which this layout
completes (by not setting done to...

This method (if implemented) is called at the end of the cycle in which this layout
completes (by not setting done to `false` in calculate). It is
possible for the layout to complete and yet become invalid before the end of the cycle,
in which case, this method will not be called. It is also possible for this method to
be called and then later the layout becomes invalidated. This will result in
calculate being called again, followed by another call to this method.

This is a read phase and DOM writes should be strictly avoided in derived classes.
Instead, DOM writes need to be written to Ext.layout.ContextItem objects to
be flushed at the next opportunity.

This method need not be implemented by derived classes and, in fact, should only be
implemented when needed.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### configClass

...


### configureItem

Adds layout's itemCls and owning Container's itemCls ...

Adds layout's itemCls and owning Container's itemCls
Parametersitem : Object


### destroy

...

Overrides: Ext.layout.container.Container.destroy


### doRenderBody

...

Parametersout : Object


### doRenderContainer

...

Parametersout : Object


### doRenderItems

...

Parametersout : Object


### finalizeLayout

This method (if implemented) is called after all layouts have completed. ...

This method (if implemented) is called after all layouts have completed. In most
ways this is similar to completeLayout. This call can cause this (or any
layout) to be become invalid (see Ext.layout.Context.invalidate), but this
is best avoided. This method is intended to be where final reads are made and so it
is best to avoid invalidating layouts at this point whenever possible. Even so, this
method can be used to perform final checks that may require all other layouts to be
complete and then invalidate some results.

This is a read phase and DOM writes should be strictly avoided in derived classes.
Instead, DOM writes need to be written to Ext.layout.ContextItem objects to
be flushed at the next opportunity.

This method need not be implemented by derived classes and, in fact, should only be
implemented when needed.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### finishRender

...

Overrides: Ext.layout.Layout.finishRender


### finishRenderItems

...

Parameterstarget : Object


### finishedLayout

This method is called after all layouts are complete and their calculations flushed
to the DOM. ...

This method is called after all layouts are complete and their calculations flushed
to the DOM. No further layouts will be run and this method is only called once per
layout run. The base component layout caches `lastComponentSize`.

This is a write phase and DOM reads should be avoided if possible when overridding
this method.

This method need not be implemented by derived classes and, in fact, should only be
implemented when needed.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### flexSort

...

Parametersa : Object


### getAnimatePolicy

...


### getChildEls

...


### getClassChildEls

...

Parameterscls : Object


### getConfig

...

Parametersname : Object


### getContainerSize

Returns the container size (that of the target). ...

Returns the container size (that of the target). Only the fixed-sized dimensions can
be returned because the shrinkWrap dimensions are based on the contentWidth/Height
as determined by the container layout.
ParametersownerContext : Ext.layout.ContextItemThe owner's context item.


### getContentTarget

...


### getElementTarget

Overridden method from Ext.layout.container.Container. ...

Overridden method from Ext.layout.container.Container.
Used by Container classes to insert special DOM elements which must exist in addition to the child components

Returns the element into which extra functional DOM elements can be inserted. Defaults to the owner Component's encapsulating element.

May be overridden in Component layout managers which implement a component render target which must only
contain child components.
ReturnsExt.Element


### getExpanded

...

ParametersexplicitCheck : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### getItemSizePolicy

Returns an object describing how this layout manages the size of the given component. ...

Returns an object describing how this layout manages the size of the given component.
This method must be implemented by any layout that manages components.
Parametersitem : Ext.Component


### getItemsRenderTree

...

Parametersitems : Object


### getLayoutItems

Returns an array of child components either for a render phase (Performed in the beforeLayout
method of the layout's ...

Returns an array of child components either for a render phase (Performed in the beforeLayout
method of the layout's base class), or the layout phase (onLayout).
ReturnsExt.Component[]of child components


### getPositionOffset

This method is used to offset the DOM position when checking
whether the element is a certain child of the target. ...

This method is used to offset the DOM position when checking
whether the element is a certain child of the target. This is
required in cases where the extra elements prepended to the target
before any of the items. An example of this is when using labelAlign: 'top'
on a field. The label appears first in the DOM before any child items are
created, so when we check the position we need to add an extra offset.
Containers that create an innerCt are exempt because this new element
preserves the order
Parametersposition : Object


### getRenderData

...

Overrides: Ext.layout.container.Container.getRenderData


### getRenderTarget

Overridden method from Ext.layout.container.Container. ...

Overridden method from Ext.layout.container.Container.
Used in the beforeLayout method to render all items into.

Returns the element into which rendering must take place. Defaults to the owner Container's
target element.

May be overridden in layout managers which implement an inner element.
ReturnsExt.Element


### getRenderTpl

...


### getRenderTree

...


### getRenderedItems

Returns all items that are rendered ...

Returns all items that are rendered
ReturnsArrayAll matching items


### getScrollbarsNeeded

...

Parameterswidth : Object


### getTarget

Returns the owner component's resize element. ...

Returns the owner component's resize element.
ReturnsExt.Element


### getVisibleItems

Returns all items that are both rendered and visible ...

Returns all items that are both rendered and visible
ReturnsArrayAll matching items


### hasConfig

...

Parametersconfig : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

Ext.define('My.awesome.Class', {
    // The default config
    config: {
        name: 'Awesome',
        isAwesome: true
    },

    constructor: function(config) {
        this.initConfig(config);
    }
});

var awesome = new My.awesome.Class({
    name: 'Super Awesome'
});

alert(awesome.getName()); // 'Super Awesome'

Parametersconfig : Object


### initLayout

A one-time initialization method called just before rendering. ...

A one-time initialization method called just before rendering.


### initOverflowHandler

...


### isItemBoxParent

...

ParametersitemContext : Object


### isItemLayoutRoot

...

Parametersitem : Object


### isItemShrinkWrap

...

Parametersitem : Object


### isRunning

...


### isValidParent

Validates item is in the proper place in the dom. ...

Validates item is in the proper place in the dom.
Parametersitem : Object


### moveItem

Moves Component to the provided target instead. ...

Moves Component to the provided target instead.
Parametersitem : Object


### notifyOwner

Called for every layout in the layout context after all the layouts have been finally flushed ...

Called for every layout in the layout context after all the layouts have been finally flushed
Overrides: Ext.layout.Layout.notifyOwner


### onAdd

...

Parametersitem : Object


### onAfterConstrainInvalidateChild

...

ParameterschildContext : Object


### onAfterStretchMaxInvalidateChild

...

ParameterschildContext : Object


### onBeforeConstrainInvalidateChild

...

ParameterschildContext : Object


### onBeforeStretchMaxInvalidateChild

...

ParameterschildContext : Object


### onComponentCollapse

...

Parameterscomp : Object


### onComponentExpand

When a Component expands, adjust the heights of the other Components to be just enough to accommodate
their headers. ...

When a Component expands, adjust the heights of the other Components to be just enough to accommodate
their headers.
The expanded Component receives the only flex value, and so gets all remaining space.
ParameterstoExpand : Object


### onComponentShow

...

Parameterscomp : Object


### onConfigUpdate

...

Parametersnames : Object


### onContentChange

This method is called when a child item changes in some way. ...

This method is called when a child item changes in some way. By default this calls
Ext.AbstractComponent.updateLayout on this layout's owner.
Parameterschild : Ext.ComponentThe child item that has changed.


### onDestroy

...


### onRemove

...

Parameterscomp : Object


### prune

...

ParameterschildEls : Object


### publishInnerCtSize

...

ParametersownerContext : Object


### removeChildEls

Removes items in the childEls array based on the return value of a supplied test
function. ...

Removes items in the childEls array based on the return value of a supplied test
function. The function is called with a entry in childEls and if the test function
return true, that entry is removed. If false, that entry is kept.
ParameterstestFn : FunctionThe test function.


### renderChildren

...

Overrides: Ext.layout.Layout.renderChildren


### renderItem

Renders the given Component into the target Element. ...

Renders the given Component into the target Element.
Parametersitem : Ext.ComponentThe Component to render


### renderItems

Iterates over all passed items, ensuring they are rendered. ...

Iterates over all passed items, ensuring they are rendered.  If the items are already rendered,
also determines if the items are in the proper place in the dom.
Parametersitems : Object


### roundFlex

...

Parameterswidth : Object


### setConfig

...

Parametersconfig : Object


### setOwner

Sets the layout owner ...

Sets the layout owner
Parametersowner : Object


### setupRenderTpl

...

ParametersrenderTpl : Object


### sortWeightedItems

...

Parametersitems : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self,
`this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what
`this` points to during run-time

Ext.define('My.Cat', {
    statics: {
        totalCreated: 0,
        speciesName: 'Cat' // My.Cat.speciesName = 'Cat'
    },

    constructor: function() {
        var statics = this.statics();

        alert(statics.speciesName);     // always equals to 'Cat' no matter what 'this' refers to
                                        // equivalent to: My.Cat.speciesName

        alert(this.self.speciesName);   // dependent on 'this'

        statics.totalCreated++;
    },

    clone: function() {
        var cloned = new this.self;                      // dependent on 'this'

        cloned.groupName = this.statics().speciesName;   // equivalent to: My.Cat.speciesName

        return cloned;
    }
});


Ext.define('My.SnowLeopard', {
    extend: 'My.Cat',

    statics: {
        speciesName: 'Snow Leopard'     // My.SnowLeopard.speciesName = 'Snow Leopard'
    },

    constructor: function() {
        this.callParent();
    }
});

var cat = new My.Cat();                 // alerts 'Cat', then alerts 'Cat'

var snowLeopard = new My.SnowLeopard(); // alerts 'Cat', then alerts 'Snow Leopard'

var clone = snowLeopard.clone();
alert(Ext.getClassName(clone));         // alerts 'My.SnowLeopard'
alert(clone.groupName);                 // alerts 'Cat'

alert(My.Cat.totalCreated);             // alerts 3

ReturnsExt.Class


### undoLayout

...


### updatePanelClasses

...

ParametersownerContext : Object


### addConfig

...

Parametersconfig : Object


### addInheritableStatics

...

Parametersmembers : Object


### addMember

...

Parametersname : Object


### addMembers

Add methods / properties to the prototype of this class. ...

Add methods / properties to the prototype of this class.

Ext.define('My.awesome.Cat', {
    constructor: function() {
        ...
    }
});

 My.awesome.Cat.addMembers({
     meow: function() {
        alert('Meowww...');
     }
 });

 var kitty = new My.awesome.Cat;
 kitty.meow();

Parametersmembers : Object


### addStatics

Add / override static properties of this class. ...

Add / override static properties of this class.

Ext.define('My.cool.Class', {
    ...
});

My.cool.Class.addStatics({
    someProperty: 'someValue',      // My.cool.Class.someProperty = 'someValue'
    method1: function() { ... },    // My.cool.Class.method1 = function() { ... };
    method2: function() { ... }     // My.cool.Class.method2 = function() { ... };
});

Parametersmembers : Object


### addXtype

...

Parametersxtype : Object


### borrow

Borrow another class' members to the prototype of this class. ...

Borrow another class' members to the prototype of this class.

Ext.define('Bank', {
    money: '$$$',
    printMoney: function() {
        alert('$$$$$$$');
    }
});

Ext.define('Thief', {
    ...
});

Thief.borrow(Bank, ['money', 'printMoney']);

var steve = new Thief();

alert(steve.money); // alerts '$$$'
steve.printMoney(); // alerts '$$$$$$$'

ParametersfromClass : Ext.BaseThe class to borrow members from


### create

Create a new instance of this Class. ...

Create a new instance of this Class.

Ext.define('My.cool.Class', {
    ...
});

My.cool.Class.create({
    someConfig: true
});


All parameters are passed to the constructor of the class.
ReturnsObjectthe created instance.


### createAlias

Create aliases for existing prototype methods. ...

Create aliases for existing prototype methods. Example:

Ext.define('My.cool.Class', {
    method1: function() { ... },
    method2: function() { ... }
});

var test = new My.cool.Class();

My.cool.Class.createAlias({
    method3: 'method1',
    method4: 'method2'
});

test.method3(); // test.method1()

My.cool.Class.createAlias('method5', 'method3');

test.method5(); // test.method3() -> test.method1()

Parametersalias : String/ObjectThe new method name, or an object to set multiple aliases. See
flexSetter


### extend

...

Parametersconfig : Object


### getName

Get the current class' name in string format. ...

Get the current class' name in string format.

Ext.define('My.cool.Class', {
    constructor: function() {
        alert(this.self.getName()); // alerts 'My.cool.Class'
    }
});

My.cool.Class.getName(); // 'My.cool.Class'

ReturnsStringclassName


### implement

Adds members to class. ...

Adds members to class.
        
        This method has been **deprecated** since 4.1
        Use addMembers instead.


### mixin

Used internally by the mixins pre-processor ...

Used internally by the mixins pre-processor
Parametersname : Object


### onExtended

...

Parametersfn : Object


### override

Override members of this class. ...

Override members of this class. Overridden methods can be invoked via
callParent.

Ext.define('My.Cat', {
    constructor: function() {
        alert("I'm a cat!");
    }
});

My.Cat.override({
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callParent(arguments);

        alert("Meeeeoooowwww");
    }
});

var kitty = new My.Cat(); // alerts "I'm going to be a cat!"
                          // alerts "I'm a cat!"
                          // alerts "Meeeeoooowwww"


As of 4.1, direct use of this method is deprecated. Use Ext.define
instead:

Ext.define('My.CatOverride', {
    override: 'My.Cat',
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callParent(arguments);

        alert("Meeeeoooowwww");
    }
});


The above accomplishes the same result but can be managed by the Ext.Loader
which can properly order the override and its target class and the build process
can determine whether the override is needed based on the required state of the
target class (My.Cat).
        
        This method has been **deprecated** since 4.1.0
        Use Ext.define instead


### triggerExtended

...


### $accordion-background-color

**Tipo:** color

The background-color of the Accordion layout element ...

The background-color of the Accordion layout element
Defaults to: `#fff`


### $accordion-body-border-width

**Tipo:** string

The text-transform property of Accordion headers ...

The text-transform property of Accordion headers
Defaults to: `0`


### $accordion-header-background-color

**Tipo:** color

The background-color of Accordion headers ...

The background-color of Accordion headers
Defaults to: `$base-color`


### $accordion-header-border-width

**Tipo:** number/list

The border-width of Accordion headers ...

The border-width of Accordion headers
Defaults to: `1px 0`


### $accordion-header-color

**Tipo:** color

The text color of Accordion headers ...

The text color of Accordion headers
Defaults to: `#000`


### $accordion-header-font-family

**Tipo:** string

The font-family of Accordion headers ...

The font-family of Accordion headers
Defaults to: `$font-family`


### $accordion-header-font-weight

**Tipo:** string

The font-weight of Accordion headers ...

The font-weight of Accordion headers
Defaults to: `normal`


### $accordion-header-padding

**Tipo:** number/list

The padding of Accordion headers ...

The padding of Accordion headers
Defaults to: `4px 5px`


### $accordion-header-text-transform

**Tipo:** string

The text-transform property of Accordion headers ...

The text-transform property of Accordion headers
Defaults to: `none`


### $accordion-header-tool-size

**Tipo:** number

The size of Tools in Accordion headers ...

The size of Tools in Accordion headers
Defaults to: `$tool-size`


### $accordion-item-margin

**Tipo:** number/list

The padding of the Accordion layout element ...

The padding of the Accordion layout element
Defaults to: `0`


### $accordion-padding

**Tipo:** color

The background-color of the Accordion layout element ...

The background-color of the Accordion layout element
Defaults to: `0`


### $accordion-tool-background-image

**Tipo:** string

The sprite image to use for Tools in Accordion headers ...

The sprite image to use for Tools in Accordion headers
Defaults to: `'tools/tool-sprites'`


## Methods

### Ext.layout.container.Accordion

...

ReturnsExt.layout.container.Accordion


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### afterRemove

Removes layout's itemCls and owning Container's itemCls. ...

Removes layout's itemCls and owning Container's itemCls.
Clears the managed dimensions flags
Parametersitem : Object


### afterRenderItem

...


### applyChildEls

Sets references to elements inside the component. ...

Sets references to elements inside the component.
Parametersel : Object


### beforeRenderItems

...

Parametersitems : Object


### beginCollapse

Called by an owning Panel before the Panel begins its collapse process. ...

Called by an owning Panel before the Panel begins its collapse process.
Most layouts will not need to override the default Ext.emptyFn implementation.
Parameterschild : Object


### beginExpand

Called by an owning Panel before the Panel begins its expand process. ...

Called by an owning Panel before the Panel begins its expand process.
Most layouts will not need to override the default Ext.emptyFn implementation.
Parameterschild : Object


### beginLayout

In addition to work done by our base classes, containers benefit from some extra
cached data. ...

In addition to work done by our base classes, containers benefit from some extra
cached data. The following properties are added to the ownerContext:


visibleItems: the result of getVisibleItems
childItems: the ContextItem[] for each visible item
targetContext: the ContextItem for the getTarget element


ParametersownerContext : Object


### beginLayoutCycle

Called before any calculation cycles to reset DOM values and prepare for calculation. ...

Called before any calculation cycles to reset DOM values and prepare for calculation.

This is a write phase and DOM reads should be strictly avoided when overridding
this method.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### cacheChildItems

...

ParametersownerContext : Object


### cacheElements

...


### cacheFlexes

This method is called to (re)cache our understanding of flexes. ...

This method is called to (re)cache our understanding of flexes. This happens during beginLayout and may need to
be called again if the flexes are changed during the layout (e.g., like ColumnLayout).
ParametersownerContext : Object


### calculate

Called to perform the calculations for this layout. ...

Called to perform the calculations for this layout. This method will be called at
least once and may be called repeatedly if the done property is cleared
before return to indicate that this layout is not yet done. The done property
is always set to `true` before entering this method.

This is a read phase and DOM writes should be strictly avoided in derived classes.
Instead, DOM writes need to be written to Ext.layout.ContextItem objects to
 be flushed at the next opportunity.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### calculateParallel

...

ParametersownerContext : Object


### calculatePerpendicular

...

ParametersownerContext : Object


### calculateStretchMax

...

ParametersownerContext : Object


### callOverridden

Call the original method that was previously overridden with override

Ext.define('My.Cat', {
    constructor: functi...

Call the original method that was previously overridden with override

Ext.define('My.Cat', {
    constructor: function() {
        alert("I'm a cat!");
    }
});

My.Cat.override({
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callOverridden();

        alert("Meeeeoooowwww");
    }
});

var kitty = new My.Cat(); // alerts "I'm going to be a cat!"
                          // alerts "I'm a cat!"
                          // alerts "Meeeeoooowwww"

        
        This method has been **deprecated** 
        as of 4.1. Use callParent instead.


### callParent

Call the "parent" method of the current method. ...

Call the "parent" method of the current method. That is the method previously
overridden by derivation or by an override (see Ext.define).

 Ext.define('My.Base', {
     constructor: function (x) {
         this.x = x;
     },

     statics: {
         method: function (x) {
             return x;
         }
     }
 });

 Ext.define('My.Derived', {
     extend: 'My.Base',

     constructor: function () {
         this.callParent([21]);
     }
 });

 var obj = new My.Derived();

 alert(obj.x);  // alerts 21


This can be used with an override as follows:

 Ext.define('My.DerivedOverride', {
     override: 'My.Derived',

     constructor: function (x) {
         this.callParent([x*2]); // calls original My.Derived constructor
     }
 });

 var obj = new My.Derived();

 alert(obj.x);  // now alerts 42


This also works with static methods.

 Ext.define('My.Derived2', {
     extend: 'My.Base',

     statics: {
         method: function (x) {
             return this.callParent([x*2]); // calls My.Base.method
         }
     }
 });

 alert(My.Base.method(10);     // alerts 10
 alert(My.Derived2.method(10); // alerts 20


Lastly, it also works with overridden static methods.

 Ext.define('My.Derived2Override', {
     override: 'My.Derived2',

     statics: {
         method: function (x) {
             return this.callParent([x*2]); // calls My.Derived2.method
         }
     }
 });

 alert(My.Derived2.method(10); // now alerts 40


To override a method and replace it and also call the superclass method, use
callSuper. This is often done to patch a method to fix a bug.
Parametersargs : Array/ArgumentsThe arguments, either an array or the `arguments` object
from the current method, for example: `this.callParent(arguments)`


### callSuper

This method is used by an override to call the superclass method but bypass any
overridden method. ...

This method is used by an override to call the superclass method but bypass any
overridden method. This is often done to "patch" a method that contains a bug
but for whatever reason cannot be fixed directly.

Consider:

 Ext.define('Ext.some.Class', {
     method: function () {
         console.log('Good');
     }
 });

 Ext.define('Ext.some.DerivedClass', {
     method: function () {
         console.log('Bad');

         // ... logic but with a bug ...

         this.callParent();
     }
 });


To patch the bug in `DerivedClass.method`, the typical solution is to create an
override:

 Ext.define('App.paches.DerivedClass', {
     override: 'Ext.some.DerivedClass',

     method: function () {
         console.log('Fixed');

         // ... logic but with bug fixed ...

         this.callSuper();
     }
 });


The patch method cannot use `callParent` to call the superclass `method` since
that would call the overridden method containing the bug. In other words, the
above patch would only produce "Fixed" then "Good" in the console log, whereas,
using `callParent` would produce "Fixed" then "Bad" then "Good".
Parametersargs : Array/ArgumentsThe arguments, either an array or the `arguments` object
from the current method, for example: `this.callSuper(arguments)`


### completeLayout

This method (if implemented) is called at the end of the cycle in which this layout
completes (by not setting done to...

This method (if implemented) is called at the end of the cycle in which this layout
completes (by not setting done to `false` in calculate). It is
possible for the layout to complete and yet become invalid before the end of the cycle,
in which case, this method will not be called. It is also possible for this method to
be called and then later the layout becomes invalidated. This will result in
calculate being called again, followed by another call to this method.

This is a read phase and DOM writes should be strictly avoided in derived classes.
Instead, DOM writes need to be written to Ext.layout.ContextItem objects to
be flushed at the next opportunity.

This method need not be implemented by derived classes and, in fact, should only be
implemented when needed.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### configClass

...


### configureItem

Adds layout's itemCls and owning Container's itemCls ...

Adds layout's itemCls and owning Container's itemCls
Parametersitem : Object


### destroy

...

Overrides: Ext.layout.container.Container.destroy


### doRenderBody

...

Parametersout : Object


### doRenderContainer

...

Parametersout : Object


### doRenderItems

...

Parametersout : Object


### finalizeLayout

This method (if implemented) is called after all layouts have completed. ...

This method (if implemented) is called after all layouts have completed. In most
ways this is similar to completeLayout. This call can cause this (or any
layout) to be become invalid (see Ext.layout.Context.invalidate), but this
is best avoided. This method is intended to be where final reads are made and so it
is best to avoid invalidating layouts at this point whenever possible. Even so, this
method can be used to perform final checks that may require all other layouts to be
complete and then invalidate some results.

This is a read phase and DOM writes should be strictly avoided in derived classes.
Instead, DOM writes need to be written to Ext.layout.ContextItem objects to
be flushed at the next opportunity.

This method need not be implemented by derived classes and, in fact, should only be
implemented when needed.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### finishRender

...

Overrides: Ext.layout.Layout.finishRender


### finishRenderItems

...

Parameterstarget : Object


### finishedLayout

This method is called after all layouts are complete and their calculations flushed
to the DOM. ...

This method is called after all layouts are complete and their calculations flushed
to the DOM. No further layouts will be run and this method is only called once per
layout run. The base component layout caches `lastComponentSize`.

This is a write phase and DOM reads should be avoided if possible when overridding
this method.

This method need not be implemented by derived classes and, in fact, should only be
implemented when needed.
ParametersownerContext : Ext.layout.ContextItemThe context item for the layout's owner
component.


### flexSort

...

Parametersa : Object


### getAnimatePolicy

...


### getChildEls

...


### getClassChildEls

...

Parameterscls : Object


### getConfig

...

Parametersname : Object


### getContainerSize

Returns the container size (that of the target). ...

Returns the container size (that of the target). Only the fixed-sized dimensions can
be returned because the shrinkWrap dimensions are based on the contentWidth/Height
as determined by the container layout.
ParametersownerContext : Ext.layout.ContextItemThe owner's context item.


### getContentTarget

...


### getElementTarget

Overridden method from Ext.layout.container.Container. ...

Overridden method from Ext.layout.container.Container.
Used by Container classes to insert special DOM elements which must exist in addition to the child components

Returns the element into which extra functional DOM elements can be inserted. Defaults to the owner Component's encapsulating element.

May be overridden in Component layout managers which implement a component render target which must only
contain child components.
ReturnsExt.Element


### getExpanded

...

ParametersexplicitCheck : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### getItemSizePolicy

Returns an object describing how this layout manages the size of the given component. ...

Returns an object describing how this layout manages the size of the given component.
This method must be implemented by any layout that manages components.
Parametersitem : Ext.Component


### getItemsRenderTree

...

Parametersitems : Object


### getLayoutItems

Returns an array of child components either for a render phase (Performed in the beforeLayout
method of the layout's ...

Returns an array of child components either for a render phase (Performed in the beforeLayout
method of the layout's base class), or the layout phase (onLayout).
ReturnsExt.Component[]of child components


### getPositionOffset

This method is used to offset the DOM position when checking
whether the element is a certain child of the target. ...

This method is used to offset the DOM position when checking
whether the element is a certain child of the target. This is
required in cases where the extra elements prepended to the target
before any of the items. An example of this is when using labelAlign: 'top'
on a field. The label appears first in the DOM before any child items are
created, so when we check the position we need to add an extra offset.
Containers that create an innerCt are exempt because this new element
preserves the order
Parametersposition : Object


### getRenderData

...

Overrides: Ext.layout.container.Container.getRenderData


### getRenderTarget

Overridden method from Ext.layout.container.Container. ...

Overridden method from Ext.layout.container.Container.
Used in the beforeLayout method to render all items into.

Returns the element into which rendering must take place. Defaults to the owner Container's
target element.

May be overridden in layout managers which implement an inner element.
ReturnsExt.Element


### getRenderTpl

...


### getRenderTree

...


### getRenderedItems

Returns all items that are rendered ...

Returns all items that are rendered
ReturnsArrayAll matching items


### getScrollbarsNeeded

...

Parameterswidth : Object


### getTarget

Returns the owner component's resize element. ...

Returns the owner component's resize element.
ReturnsExt.Element


### getVisibleItems

Returns all items that are both rendered and visible ...

Returns all items that are both rendered and visible
ReturnsArrayAll matching items


### hasConfig

...

Parametersconfig : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

Ext.define('My.awesome.Class', {
    // The default config
    config: {
        name: 'Awesome',
        isAwesome: true
    },

    constructor: function(config) {
        this.initConfig(config);
    }
});

var awesome = new My.awesome.Class({
    name: 'Super Awesome'
});

alert(awesome.getName()); // 'Super Awesome'

Parametersconfig : Object


### initLayout

A one-time initialization method called just before rendering. ...

A one-time initialization method called just before rendering.


### initOverflowHandler

...


### isItemBoxParent

...

ParametersitemContext : Object


### isItemLayoutRoot

...

Parametersitem : Object


### isItemShrinkWrap

...

Parametersitem : Object


### isRunning

...


### isValidParent

Validates item is in the proper place in the dom. ...

Validates item is in the proper place in the dom.
Parametersitem : Object


### moveItem

Moves Component to the provided target instead. ...

Moves Component to the provided target instead.
Parametersitem : Object


### notifyOwner

Called for every layout in the layout context after all the layouts have been finally flushed ...

Called for every layout in the layout context after all the layouts have been finally flushed
Overrides: Ext.layout.Layout.notifyOwner


### onAdd

...

Parametersitem : Object


### onAfterConstrainInvalidateChild

...

ParameterschildContext : Object


### onAfterStretchMaxInvalidateChild

...

ParameterschildContext : Object


### onBeforeConstrainInvalidateChild

...

ParameterschildContext : Object


### onBeforeStretchMaxInvalidateChild

...

ParameterschildContext : Object


### onComponentCollapse

...

Parameterscomp : Object


### onComponentExpand

When a Component expands, adjust the heights of the other Components to be just enough to accommodate
their headers. ...

When a Component expands, adjust the heights of the other Components to be just enough to accommodate
their headers.
The expanded Component receives the only flex value, and so gets all remaining space.
ParameterstoExpand : Object


### onComponentShow

...

Parameterscomp : Object


### onConfigUpdate

...

Parametersnames : Object


### onContentChange

This method is called when a child item changes in some way. ...

This method is called when a child item changes in some way. By default this calls
Ext.AbstractComponent.updateLayout on this layout's owner.
Parameterschild : Ext.ComponentThe child item that has changed.


### onDestroy

...


### onRemove

...

Parameterscomp : Object


### prune

...

ParameterschildEls : Object


### publishInnerCtSize

...

ParametersownerContext : Object


### removeChildEls

Removes items in the childEls array based on the return value of a supplied test
function. ...

Removes items in the childEls array based on the return value of a supplied test
function. The function is called with a entry in childEls and if the test function
return true, that entry is removed. If false, that entry is kept.
ParameterstestFn : FunctionThe test function.


### renderChildren

...

Overrides: Ext.layout.Layout.renderChildren


### renderItem

Renders the given Component into the target Element. ...

Renders the given Component into the target Element.
Parametersitem : Ext.ComponentThe Component to render


### renderItems

Iterates over all passed items, ensuring they are rendered. ...

Iterates over all passed items, ensuring they are rendered.  If the items are already rendered,
also determines if the items are in the proper place in the dom.
Parametersitems : Object


### roundFlex

...

Parameterswidth : Object


### setConfig

...

Parametersconfig : Object


### setOwner

Sets the layout owner ...

Sets the layout owner
Parametersowner : Object


### setupRenderTpl

...

ParametersrenderTpl : Object


### sortWeightedItems

...

Parametersitems : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self,
`this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what
`this` points to during run-time

Ext.define('My.Cat', {
    statics: {
        totalCreated: 0,
        speciesName: 'Cat' // My.Cat.speciesName = 'Cat'
    },

    constructor: function() {
        var statics = this.statics();

        alert(statics.speciesName);     // always equals to 'Cat' no matter what 'this' refers to
                                        // equivalent to: My.Cat.speciesName

        alert(this.self.speciesName);   // dependent on 'this'

        statics.totalCreated++;
    },

    clone: function() {
        var cloned = new this.self;                      // dependent on 'this'

        cloned.groupName = this.statics().speciesName;   // equivalent to: My.Cat.speciesName

        return cloned;
    }
});


Ext.define('My.SnowLeopard', {
    extend: 'My.Cat',

    statics: {
        speciesName: 'Snow Leopard'     // My.SnowLeopard.speciesName = 'Snow Leopard'
    },

    constructor: function() {
        this.callParent();
    }
});

var cat = new My.Cat();                 // alerts 'Cat', then alerts 'Cat'

var snowLeopard = new My.SnowLeopard(); // alerts 'Cat', then alerts 'Snow Leopard'

var clone = snowLeopard.clone();
alert(Ext.getClassName(clone));         // alerts 'My.SnowLeopard'
alert(clone.groupName);                 // alerts 'Cat'

alert(My.Cat.totalCreated);             // alerts 3

ReturnsExt.Class


### undoLayout

...


### updatePanelClasses

...

ParametersownerContext : Object


### addConfig

...

Parametersconfig : Object


### addInheritableStatics

...

Parametersmembers : Object


### addMember

...

Parametersname : Object


### addMembers

Add methods / properties to the prototype of this class. ...

Add methods / properties to the prototype of this class.

Ext.define('My.awesome.Cat', {
    constructor: function() {
        ...
    }
});

 My.awesome.Cat.addMembers({
     meow: function() {
        alert('Meowww...');
     }
 });

 var kitty = new My.awesome.Cat;
 kitty.meow();

Parametersmembers : Object


### addStatics

Add / override static properties of this class. ...

Add / override static properties of this class.

Ext.define('My.cool.Class', {
    ...
});

My.cool.Class.addStatics({
    someProperty: 'someValue',      // My.cool.Class.someProperty = 'someValue'
    method1: function() { ... },    // My.cool.Class.method1 = function() { ... };
    method2: function() { ... }     // My.cool.Class.method2 = function() { ... };
});

Parametersmembers : Object


### addXtype

...

Parametersxtype : Object


### borrow

Borrow another class' members to the prototype of this class. ...

Borrow another class' members to the prototype of this class.

Ext.define('Bank', {
    money: '$$$',
    printMoney: function() {
        alert('$$$$$$$');
    }
});

Ext.define('Thief', {
    ...
});

Thief.borrow(Bank, ['money', 'printMoney']);

var steve = new Thief();

alert(steve.money); // alerts '$$$'
steve.printMoney(); // alerts '$$$$$$$'

ParametersfromClass : Ext.BaseThe class to borrow members from


### create

Create a new instance of this Class. ...

Create a new instance of this Class.

Ext.define('My.cool.Class', {
    ...
});

My.cool.Class.create({
    someConfig: true
});


All parameters are passed to the constructor of the class.
ReturnsObjectthe created instance.


### createAlias

Create aliases for existing prototype methods. ...

Create aliases for existing prototype methods. Example:

Ext.define('My.cool.Class', {
    method1: function() { ... },
    method2: function() { ... }
});

var test = new My.cool.Class();

My.cool.Class.createAlias({
    method3: 'method1',
    method4: 'method2'
});

test.method3(); // test.method1()

My.cool.Class.createAlias('method5', 'method3');

test.method5(); // test.method3() -> test.method1()

Parametersalias : String/ObjectThe new method name, or an object to set multiple aliases. See
flexSetter


### extend

...

Parametersconfig : Object


### getName

Get the current class' name in string format. ...

Get the current class' name in string format.

Ext.define('My.cool.Class', {
    constructor: function() {
        alert(this.self.getName()); // alerts 'My.cool.Class'
    }
});

My.cool.Class.getName(); // 'My.cool.Class'

ReturnsStringclassName


### implement

Adds members to class. ...

Adds members to class.
        
        This method has been **deprecated** since 4.1
        Use addMembers instead.


### mixin

Used internally by the mixins pre-processor ...

Used internally by the mixins pre-processor
Parametersname : Object


### onExtended

...

Parametersfn : Object


### override

Override members of this class. ...

Override members of this class. Overridden methods can be invoked via
callParent.

Ext.define('My.Cat', {
    constructor: function() {
        alert("I'm a cat!");
    }
});

My.Cat.override({
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callParent(arguments);

        alert("Meeeeoooowwww");
    }
});

var kitty = new My.Cat(); // alerts "I'm going to be a cat!"
                          // alerts "I'm a cat!"
                          // alerts "Meeeeoooowwww"


As of 4.1, direct use of this method is deprecated. Use Ext.define
instead:

Ext.define('My.CatOverride', {
    override: 'My.Cat',
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callParent(arguments);

        alert("Meeeeoooowwww");
    }
});


The above accomplishes the same result but can be managed by the Ext.Loader
which can properly order the override and its target class and the build process
can determine whether the override is needed based on the required state of the
target class (My.Cat).
        
        This method has been **deprecated** since 4.1.0
        Use Ext.define instead


### triggerExtended

...


### $accordion-background-color

**Tipo:** color

The background-color of the Accordion layout element ...

The background-color of the Accordion layout element
Defaults to: `#fff`


### $accordion-body-border-width

**Tipo:** string

The text-transform property of Accordion headers ...

The text-transform property of Accordion headers
Defaults to: `0`


### $accordion-header-background-color

**Tipo:** color

The background-color of Accordion headers ...

The background-color of Accordion headers
Defaults to: `$base-color`


### $accordion-header-border-width

**Tipo:** number/list

The border-width of Accordion headers ...

The border-width of Accordion headers
Defaults to: `1px 0`


### $accordion-header-color

**Tipo:** color

The text color of Accordion headers ...

The text color of Accordion headers
Defaults to: `#000`


### $accordion-header-font-family

**Tipo:** string

The font-family of Accordion headers ...

The font-family of Accordion headers
Defaults to: `$font-family`


### $accordion-header-font-weight

**Tipo:** string

The font-weight of Accordion headers ...

The font-weight of Accordion headers
Defaults to: `normal`


### $accordion-header-padding

**Tipo:** number/list

The padding of Accordion headers ...

The padding of Accordion headers
Defaults to: `4px 5px`


### $accordion-header-text-transform

**Tipo:** string

The text-transform property of Accordion headers ...

The text-transform property of Accordion headers
Defaults to: `none`


### $accordion-header-tool-size

**Tipo:** number

The size of Tools in Accordion headers ...

The size of Tools in Accordion headers
Defaults to: `$tool-size`


### $accordion-item-margin

**Tipo:** number/list

The padding of the Accordion layout element ...

The padding of the Accordion layout element
Defaults to: `0`


### $accordion-padding

**Tipo:** color

The background-color of the Accordion layout element ...

The background-color of the Accordion layout element
Defaults to: `0`


### $accordion-tool-background-image

**Tipo:** string

The sprite image to use for Tools in Accordion headers ...

The sprite image to use for Tools in Accordion headers
Defaults to: `'tools/tool-sprites'`


## CSS Variables

### $accordion-background-color

**Tipo:** color

The background-color of the Accordion layout element ...

The background-color of the Accordion layout element
Defaults to: `#fff`


### $accordion-body-border-width

**Tipo:** string

The text-transform property of Accordion headers ...

The text-transform property of Accordion headers
Defaults to: `0`


### $accordion-header-background-color

**Tipo:** color

The background-color of Accordion headers ...

The background-color of Accordion headers
Defaults to: `$base-color`


### $accordion-header-border-width

**Tipo:** number/list

The border-width of Accordion headers ...

The border-width of Accordion headers
Defaults to: `1px 0`


### $accordion-header-color

**Tipo:** color

The text color of Accordion headers ...

The text color of Accordion headers
Defaults to: `#000`


### $accordion-header-font-family

**Tipo:** string

The font-family of Accordion headers ...

The font-family of Accordion headers
Defaults to: `$font-family`


### $accordion-header-font-weight

**Tipo:** string

The font-weight of Accordion headers ...

The font-weight of Accordion headers
Defaults to: `normal`


### $accordion-header-padding

**Tipo:** number/list

The padding of Accordion headers ...

The padding of Accordion headers
Defaults to: `4px 5px`


### $accordion-header-text-transform

**Tipo:** string

The text-transform property of Accordion headers ...

The text-transform property of Accordion headers
Defaults to: `none`


### $accordion-header-tool-size

**Tipo:** number

The size of Tools in Accordion headers ...

The size of Tools in Accordion headers
Defaults to: `$tool-size`


### $accordion-item-margin

**Tipo:** number/list

The padding of the Accordion layout element ...

The padding of the Accordion layout element
Defaults to: `0`


### $accordion-padding

**Tipo:** color

The background-color of the Accordion layout element ...

The background-color of the Accordion layout element
Defaults to: `0`


### $accordion-tool-background-image

**Tipo:** string

The sprite image to use for Tools in Accordion headers ...

The sprite image to use for Tools in Accordion headers
Defaults to: `'tools/tool-sprites'`


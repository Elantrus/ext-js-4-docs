# Ext.dom.Element

**Extends:** Ext.dom.AbstractElement

**Alternate Names:** Ext.Element, Ext.core.Element

## Description

Encapsulates a DOM element, adding simple DOM manipulation facilities, normalizing for browser differences.

All instances of this class inherit the methods of Ext.fx.Anim making visual effects easily available to all DOM elements.

Note that the events documented in this class are not Ext events, they encapsulate browser events. Some older browsers may not support the full range of events. Which events are supported is beyond the control of Ext JS.

Usage:

// by id var el = Ext.get("my-div"); // by DOM element reference var el = Ext.get(myDivElement); Animations When an element is manipulated, by default there is no animation.

var el = Ext.get("my-div"); // no animation el.setWidth(100); Many of the functions for manipulating an element have an optional "animate" parameter. This parameter can be specified as boolean (true) for default animation effects.

// default animation el.setWidth(100, true); To configure the effects, an object literal with animation options to use as the Element animation configuration object can also be specified. Note that the supported Element animation configuration options are a subset of the Ext.fx.Anim animation options specific to Fx effects. The supported Element animation configuration options are:

Option Default Description --------- -------- --------------------------------------------- duration 350 The duration of the animation in milliseconds easing easeOut The easing method callback none A function to execute when the anim completes scope this The scope (this) of the callback function Usage:

// Element animation options object var opt = { duration: 1000, easing: 'elasticIn', callback: this.foo, scope: this }; // animation with some options set el.setWidth(100, opt); The Element animation object being used for the animation will be set on the options object as "anim", which allows you to stop or manipulate the animation. Here is an example:

// using the "anim" property to get the Anim object if(opt.anim.isAnimated()){ opt.anim.stop(); } Composite (Collections of) Elements For working with collections of Elements, see Ext.CompositeElement

**From override Ext.rtl.dom.Element_position:** This override adds RTL positioning methods to Ext.dom.Element.

## Properties

### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### _positionTopRight

**Type:** Array

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.** Defaults to: `['position', 'top', 'right']`


### autoBoxAdjust

**Type:** Boolean

True to automatically adjust width and height settings for box-model issues. ...

True to automatically adjust width and height settings for box-model issues. Defaults to: `true`


### configMap

**Type:** Object

...

Defaults to: `{}`


### defaultUnit

**Type:** String

The default unit to append to CSS values where a unit isn't provided. ...

The default unit to append to CSS values where a unit isn't provided. **Overridden in Ext.dom.AbstractElement_static.** Defaults to: `"px"`


### dom

**Type:** HTMLElement

The DOM element


### getTrueXY

**Type:** Object

Returns the X,Y position of the passed element in browser document space without regard to any RTL direction settings. ...

**Returns:** the `X,Y` position of the passed element in browser document space without regard to any RTL direction settings. **Defined in override Ext.dom.Element_position.**


### id

**Type:** String

The DOM element ID


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


### originalDisplay

**Type:** String

The element's default display mode. ...

The element's default display mode. **Defined in override Ext.dom.Element_fx.** Defaults to: `""`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### styleHooks

**Type:** Object

This shared object is keyed by style name (e.g., 'margin-left' or 'marginLeft'). ...

This shared object is keyed by style name (e.g., 'margin-left' or 'marginLeft'). The values are objects with the following properties: - `name` (String) : The actual name to be presented to the DOM. This is typically the value returned by normalize. - `get` (Function) : A hook function that will perform the get on this style. These functions receive "(dom, el)" arguments. The `dom` parameter is the DOM Element from which to get ths tyle. The `el` argument (may be null) is the Ext.Element. - `set` (Function) : A hook function that will perform the set on this style. These functions receive "(dom, value, el)" arguments. The `dom` parameter is the DOM Element from which to get ths tyle. The `value` parameter is the new value for the style. The `el` argument (may be null) is the Ext.Element. The `this` pointer is the object that contains `get` or `set`, which means that `this.name` can be accessed if needed. The hook functions are both optional. **Defined in override Ext.dom.AbstractElement_style.** Defaults to: `{}`


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### ASCLASS

**Type:** Number

Visibility mode constant for use with Ext.dom.Element.setVisibilityMode. ...

Visibility mode constant for use with Ext.dom.Element.setVisibilityMode. Add or remove the Ext.Layer.visibilityCls class to hide the element. Defaults to: `4`


### DISPLAY

**Type:** Number

Visibility mode constant for use with Ext.dom.Element.setVisibilityMode. ...

Visibility mode constant for use with Ext.dom.Element.setVisibilityMode. Use the CSS 'display' property to hide the element. Defaults to: `2`


### OFFSETS

**Type:** Number

Visibility mode constant for use with Ext.dom.Element.setVisibilityMode. ...

Visibility mode constant for use with Ext.dom.Element.setVisibilityMode. Use CSS absolute positioning and top/left offsets to hide the element. Defaults to: `3`


### VISIBILITY

**Type:** Number

Visibility mode constant for use with Ext.dom.Element.setVisibilityMode. ...

Visibility mode constant for use with Ext.dom.Element.setVisibilityMode. Use the CSS 'visibility' property to hide the element. Note that in this mode, isVisible may return true for an element even though it actually has a parent element that is hidden. For this reason, and in most cases, using the OFFSETS mode is a better choice. Defaults to: `1`


### borders

**Type:** Object

Defined in override Ext.dom.AbstractElement_static. ...

**Defined in override Ext.dom.AbstractElement_static.** Defaults to: `{l: 'border-left-width', r: 'border-right-width', t: 'border-top-width', b: 'border-bottom-width'}`


### camelRe

**Type:** RegExp

Defined in override Ext.dom.AbstractElement_static. ...

**Defined in override Ext.dom.AbstractElement_static.** Defaults to: `/(-[a-z])/gi`


### cssRe

**Type:** RegExp

Defined in override Ext.dom.AbstractElement_static. ...

**Defined in override Ext.dom.AbstractElement_static.** Defaults to: `/([a-z0-9\-]+)\s*:\s*([^;\s]+(?:\s*[^;\s]+)*)?;?/gi`


### margins

**Type:** Object

Defined in override Ext.dom.AbstractElement_static. ...

**Defined in override Ext.dom.AbstractElement_static.** Defaults to: `{l: 'margin-left', r: 'margin-right', t: 'margin-top', b: 'margin-bottom'}`


### msRe

**Type:** RegExp

Defined in override Ext.dom.AbstractElement_static. ...

**Defined in override Ext.dom.AbstractElement_static.** Defaults to: `/^-ms-/`


### opacityRe

**Type:** RegExp

Defined in override Ext.dom.AbstractElement_static. ...

**Defined in override Ext.dom.AbstractElement_static.** Defaults to: `/alpha\(opacity=(.*)\)/i`


### paddings

**Type:** Object

Defined in override Ext.dom.AbstractElement_static. ...

**Defined in override Ext.dom.AbstractElement_static.** Defaults to: `{l: 'padding-left', r: 'padding-right', t: 'padding-top', b: 'padding-bottom'}`


### propertyCache

**Type:** Object

Defined in override Ext.dom.AbstractElement_static. ...

**Defined in override Ext.dom.AbstractElement_static.** Defaults to: `{}`


### trimRe

**Type:** RegExp

...

Defaults to: `/^\s+|\s+$/g`


### unitRe

**Type:** RegExp

Defined in override Ext.dom.AbstractElement_static. ...

**Defined in override Ext.dom.AbstractElement_static.** Defaults to: `/\d+(px|em|%|en|ex|pt|in|cm|mm|pc)$/i`


### whitespaceRe

**Type:** RegExp

...

Defaults to: `/\s/`


### Ext.dom.Element

Creates new Element directly. ...

Creates new Element directly.

**Parameters:** element : String/HTMLElement


### addCls

Adds one or more CSS classes to the element. ...

Adds one or more CSS classes to the element. Duplicate classes are automatically filtered out. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** className : String/String[]The CSS classes to add separated by space, or an array of classes


### addClsOnClick

Sets up event handlers to add and remove a css class when the mouse is down and then up on this element (a click effe...

Sets up event handlers to add and remove a css class when the mouse is down and then up on this element (a click effect) **Defined in override Ext.dom.Element_style.**

**Parameters:** className : StringThe class to add


### addClsOnFocus

Sets up event handlers to add and remove a css class when this element has the focus Defined in override Ext.dom.Ele...

Sets up event handlers to add and remove a css class when this element has the focus **Defined in override Ext.dom.Element_style.**

**Parameters:** className : StringThe class to add


### addClsOnOver

Sets up event handlers to add and remove a css class when the mouse is over this element Defined in override Ext.dom...

Sets up event handlers to add and remove a css class when the mouse is over this element **Defined in override Ext.dom.Element_style.**

**Parameters:** className : StringThe class to add


### addKeyListener

Convenience method for constructing a KeyMap ...

Convenience method for constructing a KeyMap

**Parameters:** key : String/Number/Number[]/ObjectEither a string with the keys to listen for, the numeric key code, array of key codes or an object with the following options: key : Number/Array


### addKeyMap

Creates a KeyMap for this element ...

Creates a KeyMap for this element

**Parameters:** config : ObjectThe KeyMap config. See Ext.util.KeyMap for more details


### addListener

Shorthand for on. ...

Shorthand for on. Appends an event handler to this element.

**Parameters:** eventName : StringThe name of event to handle.


### adjustDirect2DDimension

Returns 1 if the browser returns the subpixel dimension rounded to the lowest pixel. ...

**Parameters:** dimension : Object

**Returns:** 1 if the browser returns the subpixel dimension rounded to the lowest pixel. **Defined in override Ext.dom.Element_style.**


### anchorAnimX

Defined in override Ext.dom.Element_anim. ...

**Defined in override Ext.dom.Element_anim.**

**Parameters:** anchor : Object


### anim

process the passed fx configuration. ...

- process the passed fx configuration. **Defined in override Ext.dom.Element_anim.**

**Parameters:** config : Object


### animate

Performs custom animation on this Element. ...

Performs custom animation on this Element. The following properties may be specified in `from`, `to`, and `keyframe` objects: - `x` - The page X position in pixels. - `y` - The page Y position in pixels - `left` - The element's CSS `left` value. Units must be supplied. - `top` - The element's CSS `top` value. Units must be supplied. - `width` - The element's CSS `width` value. Units must be supplied. - `height` - The element's CSS `height` value. Units must be supplied. - `scrollLeft` - The element's `scrollLeft` value. - `scrollTop` - The element's `scrollTop` value. - `opacity` - The element's `opacity` value. This must be a value between `0` and `1`. **Be aware** that animating an Element which is being used by an Ext Component without in some way informing the Component about the changed element state will result in incorrect Component behaviour. This is because the Component will be using the old state of the element. To avoid this problem, it is now possible to directly animate certain properties of Components. **Defined in override Ext.dom.Element_anim.**

**Parameters:** config : ObjectConfiguration for Ext.fx.Anim. Note that the to config is required.


### appendChild

Appends the passed element(s) to this element Defined in override Ext.dom.AbstractElement_insertion. ...

Appends the passed element(s) to this element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElement/ObjectThe id or element to insert or a DomHelper config The id of the node, a DOM Node or an existing Element.


### appendTo

Appends this element to the passed element Defined in override Ext.dom.AbstractElement_insertion. ...

Appends this element to the passed element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElementThe new parent element. The id of the node, a DOM Node or an existing Element.


### applyStyles

More flexible version of setStyle for setting style properties. ...

More flexible version of setStyle for setting style properties. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** styles : String/Object/FunctionA style specification string, e.g. "width:100px", or object in the form {width:"100px"}, or a function which returns such a specification.


### blur

Tries to blur the element. ...

Tries to blur the element. Any exceptions are caught and ignored.

**Returns:** Ext.dom.Elementthis


### boxWrap

Wraps the specified element with a special 9 element markup/CSS block that renders by default as a gray container wit...

Wraps the specified element with a special 9 element markup/CSS block that renders by default as a gray container with a gradient background, rounded corners and a 4-way shadow. This special markup is used throughout Ext when box wrapping elements (Ext.button.Button, Ext.panel.Panel when frame=true, Ext.window.Window). The markup is of this form: Example usage: **Defined in override Ext.dom.Element_style.**

**Parameters:** class : String (optional)A base CSS class to apply to the containing wrapper element. Note that there are a number of CSS rules that are dependent on this name to make the overall effect work, so if you supply an alternate base class, make sure you also supply all of the necessary rules. Defaults to: `'x-box'`


### cacheScrollValues

When an element is moved around in the DOM, or is hidden using display:none, it loses layout, and therefore all scrol...

When an element is moved around in the DOM, or is hidden using `display:none`, it loses layout, and therefore all scroll positions of all descendant elements are lost. This function caches them, and returns a function, which when run will restore the cached positions. In the following example, the Panel is moved from one Container to another which will cause it to lose all scroll positions:

**Returns:** FunctionA function which will restore all descentant elements of this Element to their scroll positions recorded when this function was executed. Be aware that the returned function is a closure which has captured the scope of `cacheScrollValues`, so take care to derefence it as soon as not needed - if is it is a `var` it will drop out of scope, and the reference will be freed.


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


### center

Centers the Element in either the viewport, or another Element. ...

Centers the Element in either the viewport, or another Element. **Defined in override Ext.dom.Element_position.**

**Parameters:** centerIn : String/HTMLElement/Ext.dom.Elementelement in which to center the element.


### child

Selects a single direct child based on the passed CSS selector (the selector should not contain an id). ...

Selects a single *direct* child based on the passed CSS selector (the selector should not contain an id). **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : StringThe CSS selector


### clean

Removes Empty, or whitespace filled text nodes. ...

Removes Empty, or whitespace filled text nodes. Combines adjacent text nodes.

**Parameters:** forceReclean : Boolean (optional)By default the element keeps track if it has been cleaned already so you can call this over and over. However, if you update the element and need to force a reclean, you can pass true. Defaults to: `false`


### clearListeners

Alias for removeAllListeners. ...

Alias for removeAllListeners. Removes all previous added listeners from this element

**Returns:** Ext.dom.Elementthis


### clearOpacity

Clears any opacity settings from this element. ...

Clears any opacity settings from this element. Required in some cases for IE. **Defined in override Ext.dom.Element_style.**

**Returns:** Ext.dom.Elementthis


### clearPositioning

Clears positioning back to the default when the document was loaded. ...

Clears positioning back to the default when the document was loaded. **Defined in override Ext.dom.Element_position.**

**Parameters:** value : String (optional)The value to use for the left, right, top, bottom. You could use 'auto'. Defaults to: `''`


### clip

Store the current overflow setting and clip overflow on the element - use unclip to remove Defined in override Ext.d...

Store the current overflow setting and clip overflow on the element - use unclip to remove **Defined in override Ext.dom.Element_style.**

**Returns:** Ext.dom.Elementthis


### configClass

...


### constrainScrollLeft

Defined in override Ext.dom.Element_scroll. ...

**Defined in override Ext.dom.Element_scroll.**

**Parameters:** left : Object


### constrainScrollTop

Defined in override Ext.dom.Element_scroll. ...

**Defined in override Ext.dom.Element_scroll.**

**Parameters:** top : Object


### contains

Returns true if this element is an ancestor of the passed element ...

**Parameters:** el : HTMLElement/StringThe element to check

**Returns:** true if this element is an ancestor of the passed element


### createChild

Creates the passed DomHelper config and appends it to this element or optionally inserts it before the passed child e...

Creates the passed DomHelper config and appends it to this element or optionally inserts it before the passed child element. **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** config : ObjectDomHelper element config object. If no tag is specified (e.g., {tag:'input'}) then a div will be automatically generated with the specified attributes.


### createProxy

Creates a proxy element of this element ...

Creates a proxy element of this element

**Parameters:** config : String/ObjectThe class name of the proxy element or a DomHelper config object


### createShim

Creates an iframe shim for this element to keep selects and other windowed objects from showing through. ...

Creates an iframe shim for this element to keep selects and other windowed objects from showing through.

**Returns:** Ext.dom.ElementThe new shim element


### destroy

Alias to remove. ...

Alias to remove. Removes this element's dom reference. Note that event and cache removal is handled at Ext.removeNode Overrides: Ext.Base.destroy


### down

Selects a single child at any depth below this element based on the passed CSS selector (the selector should not cont...

Selects a single child at any depth below this element based on the passed CSS selector (the selector should not contain an id). **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : StringThe CSS selector


### enableDisplayMode

Convenience method for setVisibilityMode(Element.DISPLAY) ...

Convenience method for setVisibilityMode(Element.DISPLAY)

**Parameters:** display : String (optional)What to set display to when visible


### fadeIn

Fade an element in (from transparent to opaque). ...

Fade an element in (from transparent to opaque). The ending opacity can be specified using the `opacity` config option. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** options : Object (optional)Object literal with any of the Ext.fx.Anim config options


### fadeOut

Fade an element out (from opaque to transparent). ...

Fade an element out (from opaque to transparent). The ending opacity can be specified using the `opacity` config option. Note that IE may require `useDisplay:true` in order to redisplay correctly. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** options : Object (optional)Object literal with any of the Ext.fx.Anim config options


### findParent

Looks at this node and then at parent nodes for a match of the passed simple selector (e.g. ...

Looks at this node and then at parent nodes for a match of the passed simple selector (e.g. div.some-class or span:first-child) **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : StringThe simple selector to test


### findParentNode

Looks at parent nodes for a match of the passed simple selector (e.g. ...

Looks at parent nodes for a match of the passed simple selector (e.g. div.some-class or span:first-child) **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : StringThe simple selector to test


### first

Gets the first child, skipping text nodes Defined in override Ext.dom.AbstractElement_traversal. ...

Gets the first child, skipping text nodes **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : String (optional)Find the next sibling that matches the passed simple selector


### focus

Tries to focus the element. ...

Tries to focus the element. Any exceptions are caught and ignored.

**Parameters:** defer : Number (optional)Milliseconds to defer the focus


### focusable

Alias for isFocusable. ...

Alias for isFocusable. Checks whether this element can be focused.

**Parameters:** asFocusEl : Object


### frame

Shows a ripple of exploding, attenuating borders to draw attention to an Element. ...

Shows a ripple of exploding, attenuating borders to draw attention to an Element. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** color : String (optional)The hex color value for the border. Defaults to: `'#C3DAF9'`


### getActiveElement

Returns the active element in the DOM. ...

**Returns:** the active element in the DOM. If the browser supports activeElement on the document, this is returned. If not, the focus is tracked and the active element is maintained internally. **Defined in override Ext.dom.AbstractElement_static.** ReturnsHTMLElementThe active (focused) element in the document.


### getAttribute

Returns the value of an attribute from the element's underlying DOM node. ...

**Parameters:** name : StringThe attribute name

**Returns:** the value of an attribute from the element's underlying DOM node.


### getAttributeNS

Returns the value of a namespaced attribute from the element's underlying DOM node. ...

**Parameters:** namespace : StringThe namespace in which to look for the attribute

**Returns:** the value of a namespaced attribute from the element's underlying DOM node.


### getBorderWidth

Gets the width of the border(s) for the specified side(s) Defined in override Ext.dom.AbstractElement_style. ...

Gets the width of the border(s) for the specified side(s) **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** side : StringCan be t, l, r, b or any combination of those to add multiple values. For example, passing `'lr'` would get the border **l**eft width + the border **r**ight width.


### getBottom

Gets the bottom Y coordinate of the element (element Y position + element height) Defined in override Ext.dom.Elemen...

Gets the bottom Y coordinate of the element (element Y position + element height) **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### getById

Returns a child element of this element given its id. ...

**Parameters:** id : StringThe id of the desired child element.

**Returns:** a child element of this element given its `id`.


### getCache

...


### getCenterXY

Calculates the x, y to center this element on the screen Defined in override Ext.dom.Element_position. ...

Calculates the x, y to center this element on the screen **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### getColor

Return the CSS color for the specified CSS attribute. ...

Return the CSS color for the specified CSS attribute. rgb, 3 digit (like `#fff`) and valid values are convert to standard 6 digit hex color. **Defined in override Ext.dom.Element_style.**

**Parameters:** attr : StringThe css attribute


### getComputedHeight

Returns either the offsetHeight or the height of this element based on CSS height adjusted by padding or borders when...

**Returns:** either the offsetHeight or the height of this element based on CSS height adjusted by padding or borders when needed to simulate offsetHeight when offsets aren't available. This may not work on display:none elements if a height has not been set using CSS. **Defined in override Ext.dom.Element_style.** ReturnsNumber


### getComputedWidth

Returns either the offsetWidth or the width of this element based on CSS width adjusted by padding or borders when ne...

**Returns:** either the offsetWidth or the width of this element based on CSS width adjusted by padding or borders when needed to simulate offsetWidth when offsets aren't available. This may not work on display:none elements if a width has not been set using CSS. **Defined in override Ext.dom.Element_style.** ReturnsNumber


### getConfig

...

**Parameters:** name : Object


### getFrameWidth

Returns the sum width of the padding and borders for the passed "sides". ...

**Parameters:** sides : String

**Returns:** the sum width of the padding and borders for the passed "sides". See getBorderWidth() for more information about the sides. **Defined in override Ext.dom.Element_style.**


### getHTML

Returns the innerHTML of an Element or an empty string if the element's dom no longer exists. ...

**Returns:** the innerHTML of an Element or an empty string if the element's dom no longer exists.


### getHeight

Returns the offset height of the element Defined in override Ext.dom.AbstractElement_style. ...

**Parameters:** contentHeight : Boolean (optional)true to get the height minus borders and padding

**Returns:** the offset height of the element **Defined in override Ext.dom.AbstractElement_style.**


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getLeft

Gets the left X coordinate Defined in override Ext.dom.Element_position. ...

Gets the left X coordinate **Defined in override Ext.dom.Element_position.** This method has been **deprecated** Use getX or getLocalX


### getLoader

Gets this element's ElementLoader ...

Gets this element's ElementLoader

**Returns:** Ext.ElementLoaderThe loader


### getLocalX

Gets the local CSS X position for the element Defined in override Ext.dom.Element_position. ...

Gets the local CSS X position for the element **Defined in override Ext.dom.Element_position.**

**Returns:** Number


### getLocalXY

Gets the local CSS X and Y position for the element Defined in override Ext.dom.Element_position. ...

Gets the local CSS X and Y position for the element **Defined in override Ext.dom.Element_position.**

**Returns:** Array[x, y]


### getLocalY

Gets the local CSS Y position for the element Defined in override Ext.dom.Element_position. ...

Gets the local CSS Y position for the element **Defined in override Ext.dom.Element_position.**

**Returns:** Number


### getMargin

Returns an object with properties top, left, right and bottom representing the margins of this element unless sides i...

**Parameters:** sides : String (optional)Any combination of l, r, t, b to get the sum of those sides

**Returns:** an object with properties top, left, right and bottom representing the margins of this element unless sides is passed, then it returns the calculated width of the sides (see getPadding) **Defined in override Ext.dom.AbstractElement_style.**


### getPadding

Gets the width of the padding(s) for the specified side(s) Defined in override Ext.dom.AbstractElement_style. ...

Gets the width of the padding(s) for the specified side(s) **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** side : StringCan be t, l, r, b or any combination of those to add multiple values. For example, passing `'lr'` would get the padding **l**eft + the padding **r**ight.


### getPageBox

Returns an object defining the area of this Element which can be passed to Ext.util.Positionable.setBox to set anothe...

**Returns:** an object defining the area of this Element which can be passed to Ext.util.Positionable.setBox to set another Element's size/location to match this element. **Defined in override Ext.dom.Element_position.** This method has been **deprecated** use Ext.util.Positionable.getBox to get a box object, and Ext.util.Positionable.getRegion to get a Region.


### getPositioning

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.** **From override Ext.dom.Element_position:** Gets an object with all CSS positioning properties. Useful along with setPostioning to get snapshot before performing an update and then restoring the element.

**Parameters:** autoPx : Object


### getRight

Gets the right X coordinate of the element (element X position + element width) Defined in override Ext.dom.Element_...

Gets the right X coordinate of the element (element X position + element width) **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### getRightMarginFixCleaner

Creates a function to call to clean up problems with the work-around for the WebKit RightMargin bug. ...

Creates a function to call to clean up problems with the work-around for the WebKit RightMargin bug. The work-around is to add "display: 'inline-block'" to the element before calling getComputedStyle and then to restore its original display value. The problem with this is that it corrupts the selection of an INPUT or TEXTAREA element (as in the "I-beam" goes away but ths focus remains). To cleanup after this, we need to capture the selection of any such element and then restore it after we have restored the display style. **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** target : Ext.dom.ElementThe top-most element being adjusted.


### getScroll

Returns the current scroll position of the element. ...

**Returns:** the current scroll position of the element. **Defined in override Ext.dom.Element_scroll.** ReturnsObjectAn object containing the scroll position in the format `{left: (scrollLeft), top: (scrollTop)}`


### getScrollLeft

Gets the left scroll position Defined in override Ext.dom.Element_scroll. ...

Gets the left scroll position **Defined in override Ext.dom.Element_scroll.**

**Returns:** NumberThe left scroll position


### getScrollTop

Gets the top scroll position Defined in override Ext.dom.Element_scroll. ...

Gets the top scroll position **Defined in override Ext.dom.Element_scroll.**

**Returns:** NumberThe top scroll position


### getSize

Returns the size of the element. ...

**Parameters:** contentSize : Boolean (optional)true to get the width/size minus borders and padding

**Returns:** the size of the element. **Defined in override Ext.dom.AbstractElement_style.**


### getStyle

Returns a named style property based on computed/currentStyle (primary) and inline-style if primary is not available. ...

**Parameters:** property : String/String[]The style property (or multiple property names in an array) whose value is returned.

**Returns:** a named style property based on computed/currentStyle (primary) and inline-style if primary is not available. **Defined in override Ext.dom.AbstractElement_style.**


### getStyleSize

Returns the dimensions of the element available to lay content out in. ...

**Returns:** the dimensions of the element available to lay content out in. getStyleSize utilizes prefers style sizing if present, otherwise it chooses the larger of offsetHeight/clientHeight and offsetWidth/clientWidth. To obtain the size excluding scrollbars, use getViewSize. Sizing of the document body is handled at the adapter level which handles special cases for IE and strict modes, etc. **Defined in override Ext.dom.Element_style.** ReturnsObjectObject describing width and height. width : Number


### getTextWidth

Returns the width in pixels of the passed text, or the width of the text in this Element. ...

**Parameters:** text : StringThe text to measure. Defaults to the innerHTML of the element.

**Returns:** the width in pixels of the passed text, or the width of the text in this Element.


### getTop

Gets the top Y coordinate Defined in override Ext.dom.Element_position. ...

Gets the top Y coordinate **Defined in override Ext.dom.Element_position.** This method has been **deprecated** Use getY or getLocalY


### getValue

Returns the value of the "value" attribute ...

**Parameters:** asNumber : Booleantrue to parse the value as a number

**Returns:** the value of the "value" attribute


### getViewSize

Returns the dimensions of the element available to lay content out in. ...

**Returns:** the dimensions of the element available to lay content out in. If the element (or any ancestor element) has CSS style `display: none`, the dimensions will be zero. Example: getViewSize utilizes clientHeight/clientWidth which excludes sizing of scrollbars. To obtain the size including scrollbars, use getStyleSize Sizing of the document body is handled at the adapter level which handles special cases for IE and strict modes, etc. **Defined in override Ext.dom.AbstractElement_style.** ReturnsObjectObject describing width and height. width : Number


### getVisibilityMode

...


### getWidth

Returns the offset width of the element Defined in override Ext.dom.AbstractElement_style. ...

**Parameters:** contentWidth : Boolean (optional)true to get the width minus borders and padding

**Returns:** the offset width of the element **Defined in override Ext.dom.AbstractElement_style.**


### getX

Gets element X position in page coordinates Defined in override Ext.dom.Element_position. ...

Gets element X position in page coordinates **Defined in override Ext.dom.Element_position.**

**Returns:** Number


### getY

Gets element Y position in page coordinates Defined in override Ext.dom.Element_position. ...

Gets element Y position in page coordinates **Defined in override Ext.dom.Element_position.**

**Returns:** Number


### ghost

Slides the element while fading it out of view. ...

Slides the element while fading it out of view. An anchor point can be optionally passed to set the ending point of the effect. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** anchor : String (optional)One of the valid Ext.fx.Anim anchor positions (defaults to bottom: 'b')


### hasCls

Checks if the specified CSS class exists on this element's DOM node. ...

Checks if the specified CSS class exists on this element's DOM node. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** className : StringThe CSS class to check for


### hasConfig

...

**Parameters:** config : Object


### hasMetrics

Determine if the Element has a relevant height and width available based upon current logical visibility state Defin...

Determine if the Element has a relevant height and width available based upon current logical visibility state **Defined in override Ext.dom.Element_fx.**


### hide

Hide this element - Uses display mode to determine whether to use "display" or "visibility". ...

Hide this element - Uses display mode to determine whether to use "display" or "visibility". See setVisible. **Defined in override Ext.dom.Element_fx.**

**Parameters:** animate : Boolean/Object (optional)true for the default animation or a standard Element animation config object


### highlight

Highlights the Element by setting a color (applies to the background-color by default, but can be changed using the "...

Highlights the Element by setting a color (applies to the background-color by default, but can be changed using the "attr" config option) and then fading back to the original color. If no original color is available, you should provide the "endColor" config option which will be cleared after the animation. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** color : String (optional)The highlight color. Should be a 6 char hex color without the leading # (defaults to yellow: 'ffff9c')


### hover

Sets up event handlers to call the passed functions when the mouse is moved into and out of the Element. ...

Sets up event handlers to call the passed functions when the mouse is moved into and out of the Element.

**Parameters:** overFn : FunctionThe function to call when the mouse enters the Element.


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initDD

Initializes a Ext.dd.DD drag drop object for this element. ...

Initializes a Ext.dd.DD drag drop object for this element. **Defined in override Ext.dom.Element_dd.**

**Parameters:** group : StringThe group the DD object is member of


### initDDProxy

Initializes a Ext.dd.DDProxy object for this element. ...

Initializes a Ext.dd.DDProxy object for this element. **Defined in override Ext.dom.Element_dd.**

**Parameters:** group : StringThe group the DDProxy object is member of


### initDDTarget

Initializes a Ext.dd.DDTarget object for this element. ...

Initializes a Ext.dd.DDTarget object for this element. **Defined in override Ext.dom.Element_dd.**

**Parameters:** group : StringThe group the DDTarget object is member of


### insertAfter

Inserts this element after the passed element in the DOM Defined in override Ext.dom.AbstractElement_insertion. ...

Inserts this element after the passed element in the DOM **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElementThe element to insert after. The id of the node, a DOM Node or an existing Element.


### insertBefore

Inserts this element before the passed element in the DOM Defined in override Ext.dom.AbstractElement_insertion. ...

Inserts this element before the passed element in the DOM **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElementThe element before which this element will be inserted. The id of the node, a DOM Node or an existing Element.


### insertFirst

Inserts (or creates) an element (or DomHelper config) as the first child of this element Defined in override Ext.dom...

Inserts (or creates) an element (or DomHelper config) as the first child of this element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElement/ObjectThe id or element to insert or a DomHelper config to create and insert


### insertHtml

Inserts an html fragment into this element Defined in override Ext.dom.AbstractElement_insertion. ...

Inserts an html fragment into this element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** where : StringWhere to insert the html in relation to this element - beforeBegin, afterBegin, beforeEnd, afterEnd. See Ext.dom.Helper.insertHtml for details.


### insertSibling

Inserts (or creates) the passed element (or DomHelper config) as a sibling of this element Defined in override Ext.d...

Inserts (or creates) the passed element (or DomHelper config) as a sibling of this element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElement/Object/ArrayThe id, element to insert or a DomHelper config to create and insert *or* an array of any of those.


### is

Returns true if this element matches the passed simple selector (e.g. ...

**Parameters:** selector : StringThe simple selector to test

**Returns:** true if this element matches the passed simple selector (e.g. div.some-class or span:first-child)


### isAncestor

Defined in override Ext.dom.AbstractElement_traversal. ...

**Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** element : Object


### isBorderBox

Tests various css rules/browsers to determine if this element uses a border box ...

Tests various css rules/browsers to determine if this element uses a border box

**Returns:** Boolean


### isDisplayed

Returns true if display is not "none" ...

**Returns:** true if display is not "none" ReturnsBoolean


### isFocusable

Checks whether this element can be focused. ...

Checks whether this element can be focused.

**Parameters:** asFocusEl : Object


### isMasked

Returns true if this element is masked. ...

**Returns:** true if this element is masked. Also re-centers any displayed message within the mask. ReturnsBoolean


### isScrollable

Returns true if this element is scrollable. ...

**Returns:** true if this element is scrollable. **Defined in override Ext.dom.Element_scroll.** ReturnsBoolean


### isStyle

Checks if the current value of a style is equal to a given value. ...

Checks if the current value of a style is equal to a given value. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** style : Stringproperty whose value is returned.


### isTransparent

Returns true if the value of the given property is visually transparent. ...

**Parameters:** prop : StringThe style property whose value is to be tested.

**Returns:** true if the value of the given property is visually transparent. This may be due to a 'transparent' style value or an rgba value with 0 in the alpha component. **Defined in override Ext.dom.AbstractElement_style.**


### isVisible

Checks whether the element is currently visible using both visibility and display properties. ...

Checks whether the element is currently visible using both visibility and display properties.

**Parameters:** deep : Boolean (optional)True to walk the dom and see if parent elements are hidden. If false, the function only checks the visibility of the element itself and it may return `true` even though a parent is not visible. Defaults to: `false`


### last

Gets the last child, skipping text nodes Defined in override Ext.dom.AbstractElement_traversal. ...

Gets the last child, skipping text nodes **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : String (optional)Find the previous sibling that matches the passed simple selector


### load

Direct access to the Ext.ElementLoader Ext.ElementLoader.load method. ...

Direct access to the Ext.ElementLoader Ext.ElementLoader.load method. The method takes the same object parameter as Ext.ElementLoader.load

**Parameters:** options : Object


### mask

Puts a mask over this element to disable user interaction. ...

Puts a mask over this element to disable user interaction. Requires core.css. This method can only be applied to elements which accept child nodes.

**Parameters:** msg : String (optional)A message to display in the mask


### matchNode

Defined in override Ext.dom.AbstractElement_traversal. ...

**Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** dir : Object


### monitorMouseLeave

Monitors this Element for the mouse leaving. ...

Monitors this Element for the mouse leaving. Calls the function after the specified delay only if the mouse was not moved back into the Element within the delay. If the mouse *was* moved back in, the function is not called.

**Parameters:** delay : NumberThe delay **in milliseconds** to wait for possible mouse re-entry before calling the handler function.


### moveTo

Sets the position of the element in page coordinates. ...

Sets the position of the element in page coordinates. **Defined in override Ext.dom.Element_position.** This method has been **deprecated** Use setXY instead.


### needsTabIndex

Returns true if this element needs an explicit tabIndex to make it focusable. ...

**Returns:** true if this element needs an explicit tabIndex to make it focusable. Input fields, text areas, buttons anchors elements **with an href** etc do not need a tabIndex, but structural elements do.


### next

Gets the next sibling, skipping text nodes Defined in override Ext.dom.AbstractElement_traversal. ...

Gets the next sibling, skipping text nodes **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : String (optional)Find the next sibling that matches the passed simple selector


### on

Appends an event handler to this element. ...

Appends an event handler to this element.

**Parameters:** eventName : StringThe name of event to handle.


### onConfigUpdate

...

**Parameters:** names : Object


### parent

Gets the parent node for this element, optionally chaining up trying to match a selector Defined in override Ext.dom...

Gets the parent node for this element, optionally chaining up trying to match a selector **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : String (optional)Find a parent node that matches the passed simple selector


### pause

Creates a pause before any subsequent queued effects begin. ...

Creates a pause before any subsequent queued effects begin. If there are no effects queued after the pause it will have no effect. Usage: **Defined in override Ext.dom.Element_anim.** This method has been **deprecated** since 4.0 Use the `delay` config to animate instead.


### position

Initializes positioning on this element. ...

Initializes positioning on this element. If a desired position is not passed, it will make the the element positioned relative IF it is not already positioned. **Defined in override Ext.dom.Element_position.**

**Parameters:** pos : String (optional)Positioning to use "relative", "absolute" or "fixed"


### prev

Gets the previous sibling, skipping text nodes Defined in override Ext.dom.AbstractElement_traversal. ...

Gets the previous sibling, skipping text nodes **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : String (optional)Find the previous sibling that matches the passed simple selector


### puff

Fades the element out while slowly expanding it in all directions. ...

Fades the element out while slowly expanding it in all directions. When the effect is completed, the element will be hidden (visibility = 'hidden') but block elements will still take up space in the document. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** options : Object (optional)Object literal with any of the Ext.fx.Anim config options


### purgeAllListeners

Recursively removes all previous added listeners from this element and its children ...

Recursively removes all previous added listeners from this element and its children

**Returns:** Ext.dom.Elementthis


### query

Selects child nodes based on the passed CSS selector (the selector should not contain an id). ...

Selects child nodes based on the passed CSS selector (the selector should not contain an id). **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : StringThe CSS selector


### radioCls

Adds one or more CSS classes to this element and removes the same class(es) from all siblings. ...

Adds one or more CSS classes to this element and removes the same class(es) from all siblings. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** className : String/String[]The CSS class to add, or an array of classes


### relayEvent

Create an event handler on this element such that when the event fires and is handled by this element, it will be rel...

Create an event handler on this element such that when the event fires and is handled by this element, it will be relayed to another object (i.e., fired again as if it originated from that object instead).

**Parameters:** eventName : StringThe type of event to relay


### remove

Removes this element's dom reference. ...

Removes this element's dom reference. Note that event and cache removal is handled at Ext.removeNode


### removeAllListeners

Removes all previous added listeners from this element ...

Removes all previous added listeners from this element

**Returns:** Ext.dom.Elementthis


### removeCls

Removes one or more CSS classes from the element. ...

Removes one or more CSS classes from the element. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** className : String/String[]The CSS classes to remove separated by space, or an array of classes


### removeListener

Shorthand for un. ...

Shorthand for un. Removes an event handler from this element. **Note**: if a *scope* was explicitly specified when adding the listener, the same scope must be specified here. Example:

**Parameters:** eventName : StringThe name of the event from which to remove the handler.


### repaint

Forces the browser to repaint this element Defined in override Ext.dom.AbstractElement_style. ...

Forces the browser to repaint this element **Defined in override Ext.dom.AbstractElement_style.**

**Returns:** Ext.dom.Elementthis


### replace

Replaces the passed element with this element Defined in override Ext.dom.AbstractElement_insertion. ...

Replaces the passed element with this element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElementThe element to replace. The id of the node, a DOM Node or an existing Element.


### replaceCls

Replaces a CSS class on the element with another. ...

Replaces a CSS class on the element with another. If the old name does not exist, the new name will simply be added. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** oldClassName : StringThe CSS class to replace


### replaceWith

Replaces this element with the passed element Defined in override Ext.dom.AbstractElement_insertion. ...

Replaces this element with the passed element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElement/ObjectThe new element (id of the node, a DOM Node or an existing Element) or a DomHelper config of an element to create


### rtlGetLocalX

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**


### rtlGetLocalXY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**


### rtlSetLocalX

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### rtlSetLocalXY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### rtlSetX

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### rtlSetXY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** xy : Object


### rtlSetY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** y : Object


### rtlTranslatePoints

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### rtlTranslateXY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### scale

Animates the transition of an element's dimensions from a starting height/width to an ending height/width. ...

Animates the transition of an element's dimensions from a starting height/width to an ending height/width. This method is a convenience implementation of shift. Usage: **Defined in override Ext.dom.Element_anim.** This method has been **deprecated** since 4.0 Just use animate instead.


### scroll

Scrolls this element the specified direction. ...

Scrolls this element the specified direction. Does bounds checking to make sure the scroll is within this element's scrollable range. **Defined in override Ext.dom.Element_scroll.**

**Parameters:** - direction : StringPossible values are: `"l"` (or `"left"`) - `"r"` (or `"right"`) - `"t"` (or `"top"`, or `"up"`) - `"b"` (or `"bottom"`, or `"down"`)


### scrollBy

Scrolls this element by the passed delta values, optionally animating. ...

Scrolls this element by the passed delta values, optionally animating. All of the following are equivalent: **Defined in override Ext.dom.Element_scroll.**

**Parameters:** deltaX : Number/Number[]/ObjectEither the x delta, an Array specifying x and y deltas or an object with "x" and "y" properties.


### scrollChildIntoView

Defined in override Ext.dom.Element_scroll. ...

**Defined in override Ext.dom.Element_scroll.**

**Parameters:** child : Object


### scrollIntoView

Scrolls this element into view within the passed container. ...

Scrolls this element into view within the passed container. **Defined in override Ext.dom.Element_scroll.**

**Parameters:** container : String/HTMLElement/Ext.Element (optional)The container element to scroll. Should be a string (id), dom node, or Ext.Element. Defaults to: `document.body`


### scrollTo

Scrolls this element the specified scroll point. ...

Scrolls this element the specified scroll point. It does NOT do bounds checking so if you scroll to a weird value it will try to do it. For auto bounds checking, use scroll. **Defined in override Ext.dom.Element_scroll.**

**Parameters:** side : StringEither "left" for scrollLeft values or "top" for scrollTop values.


### select

Creates a Ext.CompositeElement for child nodes based on the passed CSS selector (the selector should not contain an id). ...

Creates a Ext.CompositeElement for child nodes based on the passed CSS selector (the selector should not contain an id). **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : StringThe CSS selector


### selectable

Enable text selection for this element (normalized across browsers) Defined in override Ext.dom.Element_style. ...

Enable text selection for this element (normalized across browsers) **Defined in override Ext.dom.Element_style.**

**Returns:** Ext.Elementthis


### serializeForm

Serializes a DOM form into a url encoded string Defined in override Ext.dom.AbstractElement_static. ...

Serializes a DOM form into a url encoded string **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** form : ObjectThe form


### set

Sets the passed attributes as attributes of this element (a style attribute can be a string, object or function) ...

Sets the passed attributes as attributes of this element (a style attribute can be a string, object or function)

**Parameters:** o : ObjectThe object with the attributes


### setBottom

Sets the element's CSS bottom style. ...

Sets the element's CSS bottom style. **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### setBounds

Sets the element's position and size in one shot. ...

Sets the element's position and size in one shot. If animation is true then width, height, x and y will be animated concurrently. **Defined in override Ext.dom.Element_position.** This method has been **deprecated** Use Ext.util.Positionable.setBox instead.


### setConfig

...

**Parameters:** config : Object


### setDisplayed

Sets the CSS display property. ...

Sets the CSS display property. Uses originalDisplay if the specified value is a boolean true. **Defined in override Ext.dom.Element_fx.**

**Parameters:** value : Boolean/StringBoolean value to display the element using its default display, or a string to set the display directly.


### setHTML

Set the innerHTML of this element ...

Set the innerHTML of this element

**Parameters:** html : StringThe new HTML


### setHeight

Set the height of this Element. ...

Set the height of this Element. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** - height : Number/StringThe new height. This may be one of: A Number specifying the new height in this Element's defaultUnits (by default, pixels.) - A String used to set the CSS height style. Animation may **not** be used.


### setHorizontal

Removes "vertical" state from this element (reverses everything done by setVertical). ...

Removes "vertical" state from this element (reverses everything done by setVertical). **Defined in override Ext.dom.Element_style.**


### setLeft

Sets the element's left position directly using CSS style (instead of setX). ...

Sets the element's left position directly using CSS style (instead of setX). **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### setLeftTop

Sets the element's left and top positions directly using CSS style Defined in override Ext.dom.Element_position. ...

Sets the element's left and top positions directly using CSS style **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### setLocation

Sets the position of the element in page coordinates. ...

Sets the position of the element in page coordinates. **Defined in override Ext.dom.Element_position.** This method has been **deprecated** Use setXY instead.


### setOpacity

Set the opacity of the element Defined in override Ext.dom.Element_style. ...

Set the opacity of the element **Defined in override Ext.dom.Element_style.**

**Parameters:** opacity : NumberThe new opacity. 0 = transparent, .5 = 50% visibile, 1 = fully visible, etc


### setPositioning

Set positioning with an object returned by getPositioning. ...

Set positioning with an object returned by getPositioning. **Defined in override Ext.dom.Element_position.**

**Parameters:** posCfg : Object


### setRight

Sets the element's CSS right style. ...

Sets the element's CSS right style. **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### setScrollLeft

Sets the left scroll position Defined in override Ext.dom.Element_scroll. ...

Sets the left scroll position **Defined in override Ext.dom.Element_scroll.**

**Parameters:** left : NumberThe left scroll position


### setScrollTop

Sets the top scroll position Defined in override Ext.dom.Element_scroll. ...

Sets the top scroll position **Defined in override Ext.dom.Element_scroll.**

**Parameters:** top : NumberThe top scroll position


### setSize

Set the size of this Element. ...

Set the size of this Element. If animation is true, both width and height will be animated concurrently. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** - width : Number/StringThe new width. This may be one of: A Number specifying the new width in this Element's defaultUnits (by default, pixels). - A String used to set the CSS width style. Animation may **not** be used. - A size object in the format `{width: widthValue, height: heightValue}`.


### setStyle

Wrapper for setting style properties, also takes single object parameter of multiple styles. ...

Wrapper for setting style properties, also takes single object parameter of multiple styles. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** property : String/ObjectThe style property to be set, or an object of multiple styles.


### setTop

Sets the element's top position directly using CSS style (instead of setY). ...

Sets the element's top position directly using CSS style (instead of setY). **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### setVertical

Changes this Element's state to "vertical" (rotated 90 or 270 degrees). ...

Changes this Element's state to "vertical" (rotated 90 or 270 degrees). This involves inverting the getters and setters for height and width, and applying hooks for rotating getters and setters for border/margin/padding. (getWidth becomes getHeight and vice versa), setStyle and getStyle will also return the inverse when height or width are being operated on. **Defined in override Ext.dom.Element_style.**

**Parameters:** angle : Numberthe angle of rotation - either 90 or 270


### setVisibilityMode

Use this to change the visibility mode between VISIBILITY, DISPLAY, OFFSETS or ASCLASS. ...

Use this to change the visibility mode between VISIBILITY, DISPLAY, OFFSETS or ASCLASS.

**Parameters:** mode : Object


### setVisible

Sets the visibility of the element (see details). ...

Sets the visibility of the element (see details). If the visibilityMode is set to Element.DISPLAY, it will use the display property to hide the element, otherwise it uses visibility. The default is to hide and show using the visibility property. **Defined in override Ext.dom.Element_fx.**

**Parameters:** visible : BooleanWhether the element is visible


### setWidth

Set the width of this Element. ...

Set the width of this Element. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** - width : Number/StringThe new width. This may be one of: A Number specifying the new width in this Element's defaultUnits (by default, pixels). - A String used to set the CSS width style. Animation may **not** be used.


### setX

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### setXY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** xy : Object


### setY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** y : Object


### shift

Animates the transition of any combination of an element's dimensions, xy position and/or opacity. ...

Animates the transition of any combination of an element's dimensions, xy position and/or opacity. Any of these properties not specified in the config object will not be changed. This effect requires that at least one new dimension, position or opacity setting must be passed in on the config object in order for the function to have any effect. Usage: **Defined in override Ext.dom.Element_anim.** This method has been **deprecated** since 4.0 Just use animate instead.


### show

Show this element - Uses display mode to determine whether to use "display" or "visibility". ...

Show this element - Uses display mode to determine whether to use "display" or "visibility". See setVisible. **Defined in override Ext.dom.Element_fx.**

**Parameters:** animate : Boolean/Object (optional)true for the default animation or a standard Element animation config object


### slideIn

Slides the element into view. ...

Slides the element into view. An anchor point can be optionally passed to set the point of origin for the slide effect. This function automatically handles wrapping the element with a fixed-size container if needed. See the Ext.fx.Anim class overview for valid anchor point options. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** anchor : String (optional)One of the valid Ext.fx.Anim anchor positions (defaults to top: 't')


### slideOut

Slides the element out of view. ...

Slides the element out of view. An anchor point can be optionally passed to set the end point for the slide effect. When the effect is completed, the element will be hidden (visibility = 'hidden') but block elements will still take up space in the document. The element must be removed from the DOM using the 'remove' config option if desired. This function automatically handles wrapping the element with a fixed-size container if needed. See the Ext.fx.Anim class overview for valid anchor point options. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** anchor : String (optional)One of the valid Ext.fx.Anim anchor positions (defaults to top: 't')


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### swallowEvent

Stops the specified event(s) from bubbling and optionally prevents the default action ...

Stops the specified event(s) from bubbling and optionally prevents the default action

**Parameters:** eventName : String/String[]an event / array of events to stop from bubbling


### switchOff

Blinks the element as if it was clicked and then collapses on its center (similar to switching off a television). ...

Blinks the element as if it was clicked and then collapses on its center (similar to switching off a television). When the effect is completed, the element will be hidden (visibility = 'hidden') but block elements will still take up space in the document. The element must be removed from the DOM using the 'remove' config option if desired. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** options : Object (optional)Object literal with any of the Ext.fx.Anim config options


### syncContent

. Currently used for updating grid cells without modifying DOM structure Synchronizes content of this Element with t...

. Currently used for updating grid cells without modifying DOM structure Synchronizes content of this Element with the content of the passed element. Style and CSS class are copied from source into this Element, and contents are synched recursively. If a child node is a text node, the textual data is copied.

**Parameters:** source : Object


### toggle

Toggles the element's visibility or display, depending on visibility mode. ...

Toggles the element's visibility or display, depending on visibility mode. **Defined in override Ext.dom.Element_fx.**

**Parameters:** animate : Boolean/Object (optional)True for the default animation, or a standard Element animation config object


### toggleCls

Toggles the specified CSS class on this element (removes it if it already exists, otherwise adds it). ...

Toggles the specified CSS class on this element (removes it if it already exists, otherwise adds it). **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** className : StringThe CSS class to toggle


### translatePoints

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### translateXY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### un

Removes an event handler from this element. ...

Removes an event handler from this element. **Note**: if a *scope* was explicitly specified when adding the listener, the same scope must be specified here. Example:

**Parameters:** eventName : StringThe name of the event from which to remove the handler.


### unclip

Return clipping (overflow) to original clipping before clip was called Defined in override Ext.dom.Element_style. ...

Return clipping (overflow) to original clipping before clip was called **Defined in override Ext.dom.Element_style.**

**Returns:** Ext.dom.Elementthis


### unmask

Hides a previously applied mask. ...

Hides a previously applied mask. Overrides: Ext.dom.AbstractElement.unmask


### unselectable

Disables text selection for this element (normalized across browsers) Defined in override Ext.dom.Element_style. ...

Disables text selection for this element (normalized across browsers) **Defined in override Ext.dom.Element_style.**

**Returns:** Ext.dom.Elementthis


### up

Walks up the DOM looking for a parent node that matches the passed simple selector (e.g. ...

Walks up the DOM looking for a parent node that matches the passed simple selector (e.g. div.some-class or span:first-child). This is a shortcut for findParentNode() that always returns an Ext.dom.Element. **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : StringThe simple selector to test


### update

Updates the innerHTML of this element, optionally searching for and processing scripts. ...

Updates the innerHTML of this element, optionally searching for and processing scripts.

**Parameters:** html : StringThe new HTML


### wrap

Creates and wraps this element with another element Defined in override Ext.dom.AbstractElement_insertion. ...

Creates and wraps this element with another element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** config : Object (optional)DomHelper element config object for the wrapper element or null for an empty div


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


### addMethods

...


### addStatics

Add / override static properties of this class. ...

Add / override static properties of this class.

**Parameters:** members : Object


### addToCache

...

**Parameters:** el : Object


### addUnits

Test if size has a unit, otherwise appends the passed unit string, or the default for this Element. ...

Test if size has a unit, otherwise appends the passed unit string, or the default for this Element. **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** size : Object{Object} The size to set


### addXtype

...

**Parameters:** xtype : Object


### borrow

Borrow another class' members to the prototype of this class. ...

Borrow another class' members to the prototype of this class.

**Parameters:** fromClass : Ext.BaseThe class to borrow members from


### camelReplaceFn

private Defined in override Ext.dom.AbstractElement_static. ...

private **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** m : Object


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


### fromPoint

Returns the top Element that is located at the passed coordinates Defined in override Ext.dom.AbstractElement_static. ...

**Parameters:** x : NumberThe x coordinate

**Returns:** the top Element that is located at the passed coordinates **Defined in override Ext.dom.AbstractElement_static.**


### get

Retrieves Ext.dom.Element objects. ...

Retrieves Ext.dom.Element objects. Ext.get is alias for Ext.dom.Element.get. **This method does not retrieve Components.** This method retrieves Ext.dom.Element objects which encapsulate DOM elements. To retrieve a Component by its ID, use Ext.ComponentManager.get. When passing an id, it should not include the `#` character that is used for a css selector. Uses simple caching to consistently return the same object. Automatically fixes if an object was recreated with the same id via AJAX or DOM.

**Parameters:** el : String/HTMLElement/Ext.ElementThe id of the node, a DOM Node or an existing Element.


### getDocumentHeight

Retrieves the document height Defined in override Ext.dom.AbstractElement_static. ...

Retrieves the document height **Defined in override Ext.dom.AbstractElement_static.**

**Returns:** NumberdocumentHeight


### getDocumentWidth

Retrieves the document width Defined in override Ext.dom.AbstractElement_static. ...

Retrieves the document width **Defined in override Ext.dom.AbstractElement_static.**

**Returns:** NumberdocumentWidth


### getName

Get the current class' name in string format. ...

Get the current class' name in string format.

**Returns:** StringclassName


### getOrientation

Retrieves the current orientation of the window. ...

Retrieves the current orientation of the window. This is calculated by determing if the height is greater than the width. **Defined in override Ext.dom.AbstractElement_static.**

**Returns:** StringOrientation of window: 'portrait' or 'landscape'


### getViewSize

Retrieves the viewport size of the window. ...

Retrieves the viewport size of the window. **Defined in override Ext.dom.AbstractElement_static.**

**Returns:** Objectobject containing width and height properties


### getViewportHeight

Retrieves the viewport height of the window. ...

Retrieves the viewport height of the window. **Defined in override Ext.dom.AbstractElement_static.**

**Returns:** NumberviewportHeight


### getViewportWidth

Retrieves the viewport width of the window. ...

Retrieves the viewport width of the window. **Defined in override Ext.dom.AbstractElement_static.**

**Returns:** NumberviewportWidth


### getXY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.** **From override Ext.dom.Element_position:** Gets element X and Y positions in page coordinates

**Parameters:** el : Object


### implement

Adds members to class. ...

Adds members to class. This method has been **deprecated** since 4.1 Use addMembers instead.


### isAncestor

Defined in override Ext.dom.AbstractElement_static. ...

**Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** p : Object


### mergeClsList

Returns an array of unique class names based upon the input strings, or string arrays. ...

**Parameters:** clsList1 : MixedA string of class names, or an array of class names.

**Returns:** an array of unique class names based upon the input strings, or string arrays. The number of parameters is unlimited. Example


### mixin

Used internally by the mixins pre-processor ...

Used internally by the mixins pre-processor

**Parameters:** name : Object


### normalize

Normalizes CSS property keys from dash delimited to camel case JavaScript Syntax. ...

Normalizes CSS property keys from dash delimited to camel case JavaScript Syntax. For example: - border-width -> borderWidth - padding-top -> paddingTop **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** prop : StringThe property to normalize


### onExtended

...

**Parameters:** fn : Object


### override

Override members of this class. ...

Override members of this class. Overridden methods can be invoked via callParent. As of 4.1, direct use of this method is deprecated. Use Ext.define instead: The above accomplishes the same result but can be managed by the Ext.Loader which can properly order the override and its target class and the build process can determine whether the override is needed based on the required state of the target class (My.Cat). This method has been **deprecated** since 4.1.0 Use Ext.define instead


### parseBox

Parses a number or string representing margin sizes into an object. ...

Parses a number or string representing margin sizes into an object. Supports CSS-style margin declarations (e.g. 10, "10", "10 10", "10 10 10" and "10 10 10 10" are all valid options and would return the same result) **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** box : Number/StringThe encoded margins


### parseStyles

Converts a CSS string into an object with a property for each style. ...

Converts a CSS string into an object with a property for each style. The sample code below would return an object with 2 properties, one for background-color and one for color. **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** styles : StringA CSS string


### removeCls

Returns an array of unique class names deom the first parameter with all class names from the second parameter removed. ...

**Parameters:** existingClsList : MixedA string of class names, or an array of class names.

**Returns:** an array of unique class names deom the first parameter with all class names from the second parameter removed. Example


### select

Selects elements based on the passed CSS selector to enable Element methods to be applied to many related elements in...

Selects elements based on the passed CSS selector to enable Element methods to be applied to many related elements in one statement through the returned CompositeElement or CompositeElementLite object.

**Parameters:** selector : String/HTMLElement[]The CSS selector or an array of elements


### triggerExtended

...


### unitizeBox

Parses a number or string representing margin sizes into an object. ...

Parses a number or string representing margin sizes into an object. Supports CSS-style margin declarations (e.g. 10, "10", "10 10", "10 10 10" and "10 10 10 10" are all valid options and would return the same result) **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** box : Number/String/ObjectThe encoded margins, or an object with top, right, bottom, and left properties


### DOMActivate

Where supported. ...

Where supported. Fires when an element is activated, for instance, through a mouse click or a keypress.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMAttrModified

Where supported. ...

Where supported. Fires when an attribute has been modified.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMCharacterDataModified

Where supported. ...

Where supported. Fires when the character data has been modified.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMFocusIn

Where supported. ...

Where supported. Similar to HTML focus event, but can be applied to any focusable element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMFocusOut

Where supported. ...

Where supported. Similar to HTML blur event, but can be applied to any focusable element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMNodeInserted

Where supported. ...

Where supported. Fires when a node has been added as a child of another node.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMNodeInsertedIntoDocument

Where supported. ...

Where supported. Fires when a node is being inserted into a document.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMNodeRemoved

Where supported. ...

Where supported. Fires when a descendant node of the element is removed.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMNodeRemovedFromDocument

Where supported. ...

Where supported. Fires when a node is being removed from a document.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMSubtreeModified

Where supported. ...

Where supported. Fires when the subtree is modified.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### abort

Fires when an object/image is stopped from loading before completely loaded. ...

Fires when an object/image is stopped from loading before completely loaded.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### blur

Fires when an element loses focus either via the pointing device or by tabbing navigation. ...

Fires when an element loses focus either via the pointing device or by tabbing navigation.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### change

Fires when a control loses the input focus and its value has been modified since gaining focus. ...

Fires when a control loses the input focus and its value has been modified since gaining focus.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### click

Fires when a mouse click is detected within the element. ...

Fires when a mouse click is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### contextmenu

Fires when a right click is detected within the element. ...

Fires when a right click is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### dblclick

Fires when a mouse double click is detected within the element. ...

Fires when a mouse double click is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### error

Fires when an object/image/frame cannot be loaded properly. ...

Fires when an object/image/frame cannot be loaded properly.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### focus

Fires when an element receives focus either via the pointing device or by tab navigation. ...

Fires when an element receives focus either via the pointing device or by tab navigation.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### keydown

Fires when a keydown is detected within the element. ...

Fires when a keydown is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### keypress

Fires when a keypress is detected within the element. ...

Fires when a keypress is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### keyup

Fires when a keyup is detected within the element. ...

Fires when a keyup is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### load

Fires when the user agent finishes loading all content within the element. ...

Fires when the user agent finishes loading all content within the element. Only supported by window, frames, objects and images.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mousedown

Fires when a mousedown is detected within the element. ...

Fires when a mousedown is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseenter

Fires when the mouse enters the element. ...

Fires when the mouse enters the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseleave

Fires when the mouse leaves the element. ...

Fires when the mouse leaves the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mousemove

Fires when a mousemove is detected with the element. ...

Fires when a mousemove is detected with the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseout

Fires when a mouseout is detected with the element. ...

Fires when a mouseout is detected with the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseover

Fires when a mouseover is detected within the element. ...

Fires when a mouseover is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseup

Fires when a mouseup is detected within the element. ...

Fires when a mouseup is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### reset

Fires when a form is reset. ...

Fires when a form is reset.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### resize

Fires when a document view is resized. ...

Fires when a document view is resized.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### scroll

Fires when a document view is scrolled. ...

Fires when a document view is scrolled.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### select

Fires when a user selects some text in a text field, including input and textarea. ...

Fires when a user selects some text in a text field, including input and textarea.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### submit

Fires when a form is submitted. ...

Fires when a form is submitted.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### unload

Fires when the user agent removes all content from a window or frame. ...

Fires when the user agent removes all content from a window or frame. For elements, it fires when the target element or any of its content has been removed.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


## Methods

### Ext.dom.Element

Creates new Element directly. ...

Creates new Element directly.

**Parameters:** element : String/HTMLElement


### addCls

Adds one or more CSS classes to the element. ...

Adds one or more CSS classes to the element. Duplicate classes are automatically filtered out. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** className : String/String[]The CSS classes to add separated by space, or an array of classes


### addClsOnClick

Sets up event handlers to add and remove a css class when the mouse is down and then up on this element (a click effe...

Sets up event handlers to add and remove a css class when the mouse is down and then up on this element (a click effect) **Defined in override Ext.dom.Element_style.**

**Parameters:** className : StringThe class to add


### addClsOnFocus

Sets up event handlers to add and remove a css class when this element has the focus Defined in override Ext.dom.Ele...

Sets up event handlers to add and remove a css class when this element has the focus **Defined in override Ext.dom.Element_style.**

**Parameters:** className : StringThe class to add


### addClsOnOver

Sets up event handlers to add and remove a css class when the mouse is over this element Defined in override Ext.dom...

Sets up event handlers to add and remove a css class when the mouse is over this element **Defined in override Ext.dom.Element_style.**

**Parameters:** className : StringThe class to add


### addKeyListener

Convenience method for constructing a KeyMap ...

Convenience method for constructing a KeyMap

**Parameters:** key : String/Number/Number[]/ObjectEither a string with the keys to listen for, the numeric key code, array of key codes or an object with the following options: key : Number/Array


### addKeyMap

Creates a KeyMap for this element ...

Creates a KeyMap for this element

**Parameters:** config : ObjectThe KeyMap config. See Ext.util.KeyMap for more details


### addListener

Shorthand for on. ...

Shorthand for on. Appends an event handler to this element.

**Parameters:** eventName : StringThe name of event to handle.


### adjustDirect2DDimension

Returns 1 if the browser returns the subpixel dimension rounded to the lowest pixel. ...

**Parameters:** dimension : Object

**Returns:** 1 if the browser returns the subpixel dimension rounded to the lowest pixel. **Defined in override Ext.dom.Element_style.**


### anchorAnimX

Defined in override Ext.dom.Element_anim. ...

**Defined in override Ext.dom.Element_anim.**

**Parameters:** anchor : Object


### anim

process the passed fx configuration. ...

- process the passed fx configuration. **Defined in override Ext.dom.Element_anim.**

**Parameters:** config : Object


### animate

Performs custom animation on this Element. ...

Performs custom animation on this Element. The following properties may be specified in `from`, `to`, and `keyframe` objects: - `x` - The page X position in pixels. - `y` - The page Y position in pixels - `left` - The element's CSS `left` value. Units must be supplied. - `top` - The element's CSS `top` value. Units must be supplied. - `width` - The element's CSS `width` value. Units must be supplied. - `height` - The element's CSS `height` value. Units must be supplied. - `scrollLeft` - The element's `scrollLeft` value. - `scrollTop` - The element's `scrollTop` value. - `opacity` - The element's `opacity` value. This must be a value between `0` and `1`. **Be aware** that animating an Element which is being used by an Ext Component without in some way informing the Component about the changed element state will result in incorrect Component behaviour. This is because the Component will be using the old state of the element. To avoid this problem, it is now possible to directly animate certain properties of Components. **Defined in override Ext.dom.Element_anim.**

**Parameters:** config : ObjectConfiguration for Ext.fx.Anim. Note that the to config is required.


### appendChild

Appends the passed element(s) to this element Defined in override Ext.dom.AbstractElement_insertion. ...

Appends the passed element(s) to this element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElement/ObjectThe id or element to insert or a DomHelper config The id of the node, a DOM Node or an existing Element.


### appendTo

Appends this element to the passed element Defined in override Ext.dom.AbstractElement_insertion. ...

Appends this element to the passed element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElementThe new parent element. The id of the node, a DOM Node or an existing Element.


### applyStyles

More flexible version of setStyle for setting style properties. ...

More flexible version of setStyle for setting style properties. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** styles : String/Object/FunctionA style specification string, e.g. "width:100px", or object in the form {width:"100px"}, or a function which returns such a specification.


### blur

Tries to blur the element. ...

Tries to blur the element. Any exceptions are caught and ignored.

**Returns:** Ext.dom.Elementthis


### boxWrap

Wraps the specified element with a special 9 element markup/CSS block that renders by default as a gray container wit...

Wraps the specified element with a special 9 element markup/CSS block that renders by default as a gray container with a gradient background, rounded corners and a 4-way shadow. This special markup is used throughout Ext when box wrapping elements (Ext.button.Button, Ext.panel.Panel when frame=true, Ext.window.Window). The markup is of this form: Example usage: **Defined in override Ext.dom.Element_style.**

**Parameters:** class : String (optional)A base CSS class to apply to the containing wrapper element. Note that there are a number of CSS rules that are dependent on this name to make the overall effect work, so if you supply an alternate base class, make sure you also supply all of the necessary rules. Defaults to: `'x-box'`


### cacheScrollValues

When an element is moved around in the DOM, or is hidden using display:none, it loses layout, and therefore all scrol...

When an element is moved around in the DOM, or is hidden using `display:none`, it loses layout, and therefore all scroll positions of all descendant elements are lost. This function caches them, and returns a function, which when run will restore the cached positions. In the following example, the Panel is moved from one Container to another which will cause it to lose all scroll positions:

**Returns:** FunctionA function which will restore all descentant elements of this Element to their scroll positions recorded when this function was executed. Be aware that the returned function is a closure which has captured the scope of `cacheScrollValues`, so take care to derefence it as soon as not needed - if is it is a `var` it will drop out of scope, and the reference will be freed.


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


### center

Centers the Element in either the viewport, or another Element. ...

Centers the Element in either the viewport, or another Element. **Defined in override Ext.dom.Element_position.**

**Parameters:** centerIn : String/HTMLElement/Ext.dom.Elementelement in which to center the element.


### child

Selects a single direct child based on the passed CSS selector (the selector should not contain an id). ...

Selects a single *direct* child based on the passed CSS selector (the selector should not contain an id). **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : StringThe CSS selector


### clean

Removes Empty, or whitespace filled text nodes. ...

Removes Empty, or whitespace filled text nodes. Combines adjacent text nodes.

**Parameters:** forceReclean : Boolean (optional)By default the element keeps track if it has been cleaned already so you can call this over and over. However, if you update the element and need to force a reclean, you can pass true. Defaults to: `false`


### clearListeners

Alias for removeAllListeners. ...

Alias for removeAllListeners. Removes all previous added listeners from this element

**Returns:** Ext.dom.Elementthis


### clearOpacity

Clears any opacity settings from this element. ...

Clears any opacity settings from this element. Required in some cases for IE. **Defined in override Ext.dom.Element_style.**

**Returns:** Ext.dom.Elementthis


### clearPositioning

Clears positioning back to the default when the document was loaded. ...

Clears positioning back to the default when the document was loaded. **Defined in override Ext.dom.Element_position.**

**Parameters:** value : String (optional)The value to use for the left, right, top, bottom. You could use 'auto'. Defaults to: `''`


### clip

Store the current overflow setting and clip overflow on the element - use unclip to remove Defined in override Ext.d...

Store the current overflow setting and clip overflow on the element - use unclip to remove **Defined in override Ext.dom.Element_style.**

**Returns:** Ext.dom.Elementthis


### configClass

...


### constrainScrollLeft

Defined in override Ext.dom.Element_scroll. ...

**Defined in override Ext.dom.Element_scroll.**

**Parameters:** left : Object


### constrainScrollTop

Defined in override Ext.dom.Element_scroll. ...

**Defined in override Ext.dom.Element_scroll.**

**Parameters:** top : Object


### contains

Returns true if this element is an ancestor of the passed element ...

**Parameters:** el : HTMLElement/StringThe element to check

**Returns:** true if this element is an ancestor of the passed element


### createChild

Creates the passed DomHelper config and appends it to this element or optionally inserts it before the passed child e...

Creates the passed DomHelper config and appends it to this element or optionally inserts it before the passed child element. **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** config : ObjectDomHelper element config object. If no tag is specified (e.g., {tag:'input'}) then a div will be automatically generated with the specified attributes.


### createProxy

Creates a proxy element of this element ...

Creates a proxy element of this element

**Parameters:** config : String/ObjectThe class name of the proxy element or a DomHelper config object


### createShim

Creates an iframe shim for this element to keep selects and other windowed objects from showing through. ...

Creates an iframe shim for this element to keep selects and other windowed objects from showing through.

**Returns:** Ext.dom.ElementThe new shim element


### destroy

Alias to remove. ...

Alias to remove. Removes this element's dom reference. Note that event and cache removal is handled at Ext.removeNode Overrides: Ext.Base.destroy


### down

Selects a single child at any depth below this element based on the passed CSS selector (the selector should not cont...

Selects a single child at any depth below this element based on the passed CSS selector (the selector should not contain an id). **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : StringThe CSS selector


### enableDisplayMode

Convenience method for setVisibilityMode(Element.DISPLAY) ...

Convenience method for setVisibilityMode(Element.DISPLAY)

**Parameters:** display : String (optional)What to set display to when visible


### fadeIn

Fade an element in (from transparent to opaque). ...

Fade an element in (from transparent to opaque). The ending opacity can be specified using the `opacity` config option. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** options : Object (optional)Object literal with any of the Ext.fx.Anim config options


### fadeOut

Fade an element out (from opaque to transparent). ...

Fade an element out (from opaque to transparent). The ending opacity can be specified using the `opacity` config option. Note that IE may require `useDisplay:true` in order to redisplay correctly. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** options : Object (optional)Object literal with any of the Ext.fx.Anim config options


### findParent

Looks at this node and then at parent nodes for a match of the passed simple selector (e.g. ...

Looks at this node and then at parent nodes for a match of the passed simple selector (e.g. div.some-class or span:first-child) **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : StringThe simple selector to test


### findParentNode

Looks at parent nodes for a match of the passed simple selector (e.g. ...

Looks at parent nodes for a match of the passed simple selector (e.g. div.some-class or span:first-child) **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : StringThe simple selector to test


### first

Gets the first child, skipping text nodes Defined in override Ext.dom.AbstractElement_traversal. ...

Gets the first child, skipping text nodes **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : String (optional)Find the next sibling that matches the passed simple selector


### focus

Tries to focus the element. ...

Tries to focus the element. Any exceptions are caught and ignored.

**Parameters:** defer : Number (optional)Milliseconds to defer the focus


### focusable

Alias for isFocusable. ...

Alias for isFocusable. Checks whether this element can be focused.

**Parameters:** asFocusEl : Object


### frame

Shows a ripple of exploding, attenuating borders to draw attention to an Element. ...

Shows a ripple of exploding, attenuating borders to draw attention to an Element. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** color : String (optional)The hex color value for the border. Defaults to: `'#C3DAF9'`


### getActiveElement

Returns the active element in the DOM. ...

**Returns:** the active element in the DOM. If the browser supports activeElement on the document, this is returned. If not, the focus is tracked and the active element is maintained internally. **Defined in override Ext.dom.AbstractElement_static.** ReturnsHTMLElementThe active (focused) element in the document.


### getAttribute

Returns the value of an attribute from the element's underlying DOM node. ...

**Parameters:** name : StringThe attribute name

**Returns:** the value of an attribute from the element's underlying DOM node.


### getAttributeNS

Returns the value of a namespaced attribute from the element's underlying DOM node. ...

**Parameters:** namespace : StringThe namespace in which to look for the attribute

**Returns:** the value of a namespaced attribute from the element's underlying DOM node.


### getBorderWidth

Gets the width of the border(s) for the specified side(s) Defined in override Ext.dom.AbstractElement_style. ...

Gets the width of the border(s) for the specified side(s) **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** side : StringCan be t, l, r, b or any combination of those to add multiple values. For example, passing `'lr'` would get the border **l**eft width + the border **r**ight width.


### getBottom

Gets the bottom Y coordinate of the element (element Y position + element height) Defined in override Ext.dom.Elemen...

Gets the bottom Y coordinate of the element (element Y position + element height) **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### getById

Returns a child element of this element given its id. ...

**Parameters:** id : StringThe id of the desired child element.

**Returns:** a child element of this element given its `id`.


### getCache

...


### getCenterXY

Calculates the x, y to center this element on the screen Defined in override Ext.dom.Element_position. ...

Calculates the x, y to center this element on the screen **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### getColor

Return the CSS color for the specified CSS attribute. ...

Return the CSS color for the specified CSS attribute. rgb, 3 digit (like `#fff`) and valid values are convert to standard 6 digit hex color. **Defined in override Ext.dom.Element_style.**

**Parameters:** attr : StringThe css attribute


### getComputedHeight

Returns either the offsetHeight or the height of this element based on CSS height adjusted by padding or borders when...

**Returns:** either the offsetHeight or the height of this element based on CSS height adjusted by padding or borders when needed to simulate offsetHeight when offsets aren't available. This may not work on display:none elements if a height has not been set using CSS. **Defined in override Ext.dom.Element_style.** ReturnsNumber


### getComputedWidth

Returns either the offsetWidth or the width of this element based on CSS width adjusted by padding or borders when ne...

**Returns:** either the offsetWidth or the width of this element based on CSS width adjusted by padding or borders when needed to simulate offsetWidth when offsets aren't available. This may not work on display:none elements if a width has not been set using CSS. **Defined in override Ext.dom.Element_style.** ReturnsNumber


### getConfig

...

**Parameters:** name : Object


### getFrameWidth

Returns the sum width of the padding and borders for the passed "sides". ...

**Parameters:** sides : String

**Returns:** the sum width of the padding and borders for the passed "sides". See getBorderWidth() for more information about the sides. **Defined in override Ext.dom.Element_style.**


### getHTML

Returns the innerHTML of an Element or an empty string if the element's dom no longer exists. ...

**Returns:** the innerHTML of an Element or an empty string if the element's dom no longer exists.


### getHeight

Returns the offset height of the element Defined in override Ext.dom.AbstractElement_style. ...

**Parameters:** contentHeight : Boolean (optional)true to get the height minus borders and padding

**Returns:** the offset height of the element **Defined in override Ext.dom.AbstractElement_style.**


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getLeft

Gets the left X coordinate Defined in override Ext.dom.Element_position. ...

Gets the left X coordinate **Defined in override Ext.dom.Element_position.** This method has been **deprecated** Use getX or getLocalX


### getLoader

Gets this element's ElementLoader ...

Gets this element's ElementLoader

**Returns:** Ext.ElementLoaderThe loader


### getLocalX

Gets the local CSS X position for the element Defined in override Ext.dom.Element_position. ...

Gets the local CSS X position for the element **Defined in override Ext.dom.Element_position.**

**Returns:** Number


### getLocalXY

Gets the local CSS X and Y position for the element Defined in override Ext.dom.Element_position. ...

Gets the local CSS X and Y position for the element **Defined in override Ext.dom.Element_position.**

**Returns:** Array[x, y]


### getLocalY

Gets the local CSS Y position for the element Defined in override Ext.dom.Element_position. ...

Gets the local CSS Y position for the element **Defined in override Ext.dom.Element_position.**

**Returns:** Number


### getMargin

Returns an object with properties top, left, right and bottom representing the margins of this element unless sides i...

**Parameters:** sides : String (optional)Any combination of l, r, t, b to get the sum of those sides

**Returns:** an object with properties top, left, right and bottom representing the margins of this element unless sides is passed, then it returns the calculated width of the sides (see getPadding) **Defined in override Ext.dom.AbstractElement_style.**


### getPadding

Gets the width of the padding(s) for the specified side(s) Defined in override Ext.dom.AbstractElement_style. ...

Gets the width of the padding(s) for the specified side(s) **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** side : StringCan be t, l, r, b or any combination of those to add multiple values. For example, passing `'lr'` would get the padding **l**eft + the padding **r**ight.


### getPageBox

Returns an object defining the area of this Element which can be passed to Ext.util.Positionable.setBox to set anothe...

**Returns:** an object defining the area of this Element which can be passed to Ext.util.Positionable.setBox to set another Element's size/location to match this element. **Defined in override Ext.dom.Element_position.** This method has been **deprecated** use Ext.util.Positionable.getBox to get a box object, and Ext.util.Positionable.getRegion to get a Region.


### getPositioning

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.** **From override Ext.dom.Element_position:** Gets an object with all CSS positioning properties. Useful along with setPostioning to get snapshot before performing an update and then restoring the element.

**Parameters:** autoPx : Object


### getRight

Gets the right X coordinate of the element (element X position + element width) Defined in override Ext.dom.Element_...

Gets the right X coordinate of the element (element X position + element width) **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### getRightMarginFixCleaner

Creates a function to call to clean up problems with the work-around for the WebKit RightMargin bug. ...

Creates a function to call to clean up problems with the work-around for the WebKit RightMargin bug. The work-around is to add "display: 'inline-block'" to the element before calling getComputedStyle and then to restore its original display value. The problem with this is that it corrupts the selection of an INPUT or TEXTAREA element (as in the "I-beam" goes away but ths focus remains). To cleanup after this, we need to capture the selection of any such element and then restore it after we have restored the display style. **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** target : Ext.dom.ElementThe top-most element being adjusted.


### getScroll

Returns the current scroll position of the element. ...

**Returns:** the current scroll position of the element. **Defined in override Ext.dom.Element_scroll.** ReturnsObjectAn object containing the scroll position in the format `{left: (scrollLeft), top: (scrollTop)}`


### getScrollLeft

Gets the left scroll position Defined in override Ext.dom.Element_scroll. ...

Gets the left scroll position **Defined in override Ext.dom.Element_scroll.**

**Returns:** NumberThe left scroll position


### getScrollTop

Gets the top scroll position Defined in override Ext.dom.Element_scroll. ...

Gets the top scroll position **Defined in override Ext.dom.Element_scroll.**

**Returns:** NumberThe top scroll position


### getSize

Returns the size of the element. ...

**Parameters:** contentSize : Boolean (optional)true to get the width/size minus borders and padding

**Returns:** the size of the element. **Defined in override Ext.dom.AbstractElement_style.**


### getStyle

Returns a named style property based on computed/currentStyle (primary) and inline-style if primary is not available. ...

**Parameters:** property : String/String[]The style property (or multiple property names in an array) whose value is returned.

**Returns:** a named style property based on computed/currentStyle (primary) and inline-style if primary is not available. **Defined in override Ext.dom.AbstractElement_style.**


### getStyleSize

Returns the dimensions of the element available to lay content out in. ...

**Returns:** the dimensions of the element available to lay content out in. getStyleSize utilizes prefers style sizing if present, otherwise it chooses the larger of offsetHeight/clientHeight and offsetWidth/clientWidth. To obtain the size excluding scrollbars, use getViewSize. Sizing of the document body is handled at the adapter level which handles special cases for IE and strict modes, etc. **Defined in override Ext.dom.Element_style.** ReturnsObjectObject describing width and height. width : Number


### getTextWidth

Returns the width in pixels of the passed text, or the width of the text in this Element. ...

**Parameters:** text : StringThe text to measure. Defaults to the innerHTML of the element.

**Returns:** the width in pixels of the passed text, or the width of the text in this Element.


### getTop

Gets the top Y coordinate Defined in override Ext.dom.Element_position. ...

Gets the top Y coordinate **Defined in override Ext.dom.Element_position.** This method has been **deprecated** Use getY or getLocalY


### getValue

Returns the value of the "value" attribute ...

**Parameters:** asNumber : Booleantrue to parse the value as a number

**Returns:** the value of the "value" attribute


### getViewSize

Returns the dimensions of the element available to lay content out in. ...

**Returns:** the dimensions of the element available to lay content out in. If the element (or any ancestor element) has CSS style `display: none`, the dimensions will be zero. Example: getViewSize utilizes clientHeight/clientWidth which excludes sizing of scrollbars. To obtain the size including scrollbars, use getStyleSize Sizing of the document body is handled at the adapter level which handles special cases for IE and strict modes, etc. **Defined in override Ext.dom.AbstractElement_style.** ReturnsObjectObject describing width and height. width : Number


### getVisibilityMode

...


### getWidth

Returns the offset width of the element Defined in override Ext.dom.AbstractElement_style. ...

**Parameters:** contentWidth : Boolean (optional)true to get the width minus borders and padding

**Returns:** the offset width of the element **Defined in override Ext.dom.AbstractElement_style.**


### getX

Gets element X position in page coordinates Defined in override Ext.dom.Element_position. ...

Gets element X position in page coordinates **Defined in override Ext.dom.Element_position.**

**Returns:** Number


### getY

Gets element Y position in page coordinates Defined in override Ext.dom.Element_position. ...

Gets element Y position in page coordinates **Defined in override Ext.dom.Element_position.**

**Returns:** Number


### ghost

Slides the element while fading it out of view. ...

Slides the element while fading it out of view. An anchor point can be optionally passed to set the ending point of the effect. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** anchor : String (optional)One of the valid Ext.fx.Anim anchor positions (defaults to bottom: 'b')


### hasCls

Checks if the specified CSS class exists on this element's DOM node. ...

Checks if the specified CSS class exists on this element's DOM node. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** className : StringThe CSS class to check for


### hasConfig

...

**Parameters:** config : Object


### hasMetrics

Determine if the Element has a relevant height and width available based upon current logical visibility state Defin...

Determine if the Element has a relevant height and width available based upon current logical visibility state **Defined in override Ext.dom.Element_fx.**


### hide

Hide this element - Uses display mode to determine whether to use "display" or "visibility". ...

Hide this element - Uses display mode to determine whether to use "display" or "visibility". See setVisible. **Defined in override Ext.dom.Element_fx.**

**Parameters:** animate : Boolean/Object (optional)true for the default animation or a standard Element animation config object


### highlight

Highlights the Element by setting a color (applies to the background-color by default, but can be changed using the "...

Highlights the Element by setting a color (applies to the background-color by default, but can be changed using the "attr" config option) and then fading back to the original color. If no original color is available, you should provide the "endColor" config option which will be cleared after the animation. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** color : String (optional)The highlight color. Should be a 6 char hex color without the leading # (defaults to yellow: 'ffff9c')


### hover

Sets up event handlers to call the passed functions when the mouse is moved into and out of the Element. ...

Sets up event handlers to call the passed functions when the mouse is moved into and out of the Element.

**Parameters:** overFn : FunctionThe function to call when the mouse enters the Element.


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initDD

Initializes a Ext.dd.DD drag drop object for this element. ...

Initializes a Ext.dd.DD drag drop object for this element. **Defined in override Ext.dom.Element_dd.**

**Parameters:** group : StringThe group the DD object is member of


### initDDProxy

Initializes a Ext.dd.DDProxy object for this element. ...

Initializes a Ext.dd.DDProxy object for this element. **Defined in override Ext.dom.Element_dd.**

**Parameters:** group : StringThe group the DDProxy object is member of


### initDDTarget

Initializes a Ext.dd.DDTarget object for this element. ...

Initializes a Ext.dd.DDTarget object for this element. **Defined in override Ext.dom.Element_dd.**

**Parameters:** group : StringThe group the DDTarget object is member of


### insertAfter

Inserts this element after the passed element in the DOM Defined in override Ext.dom.AbstractElement_insertion. ...

Inserts this element after the passed element in the DOM **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElementThe element to insert after. The id of the node, a DOM Node or an existing Element.


### insertBefore

Inserts this element before the passed element in the DOM Defined in override Ext.dom.AbstractElement_insertion. ...

Inserts this element before the passed element in the DOM **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElementThe element before which this element will be inserted. The id of the node, a DOM Node or an existing Element.


### insertFirst

Inserts (or creates) an element (or DomHelper config) as the first child of this element Defined in override Ext.dom...

Inserts (or creates) an element (or DomHelper config) as the first child of this element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElement/ObjectThe id or element to insert or a DomHelper config to create and insert


### insertHtml

Inserts an html fragment into this element Defined in override Ext.dom.AbstractElement_insertion. ...

Inserts an html fragment into this element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** where : StringWhere to insert the html in relation to this element - beforeBegin, afterBegin, beforeEnd, afterEnd. See Ext.dom.Helper.insertHtml for details.


### insertSibling

Inserts (or creates) the passed element (or DomHelper config) as a sibling of this element Defined in override Ext.d...

Inserts (or creates) the passed element (or DomHelper config) as a sibling of this element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElement/Object/ArrayThe id, element to insert or a DomHelper config to create and insert *or* an array of any of those.


### is

Returns true if this element matches the passed simple selector (e.g. ...

**Parameters:** selector : StringThe simple selector to test

**Returns:** true if this element matches the passed simple selector (e.g. div.some-class or span:first-child)


### isAncestor

Defined in override Ext.dom.AbstractElement_traversal. ...

**Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** element : Object


### isBorderBox

Tests various css rules/browsers to determine if this element uses a border box ...

Tests various css rules/browsers to determine if this element uses a border box

**Returns:** Boolean


### isDisplayed

Returns true if display is not "none" ...

**Returns:** true if display is not "none" ReturnsBoolean


### isFocusable

Checks whether this element can be focused. ...

Checks whether this element can be focused.

**Parameters:** asFocusEl : Object


### isMasked

Returns true if this element is masked. ...

**Returns:** true if this element is masked. Also re-centers any displayed message within the mask. ReturnsBoolean


### isScrollable

Returns true if this element is scrollable. ...

**Returns:** true if this element is scrollable. **Defined in override Ext.dom.Element_scroll.** ReturnsBoolean


### isStyle

Checks if the current value of a style is equal to a given value. ...

Checks if the current value of a style is equal to a given value. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** style : Stringproperty whose value is returned.


### isTransparent

Returns true if the value of the given property is visually transparent. ...

**Parameters:** prop : StringThe style property whose value is to be tested.

**Returns:** true if the value of the given property is visually transparent. This may be due to a 'transparent' style value or an rgba value with 0 in the alpha component. **Defined in override Ext.dom.AbstractElement_style.**


### isVisible

Checks whether the element is currently visible using both visibility and display properties. ...

Checks whether the element is currently visible using both visibility and display properties.

**Parameters:** deep : Boolean (optional)True to walk the dom and see if parent elements are hidden. If false, the function only checks the visibility of the element itself and it may return `true` even though a parent is not visible. Defaults to: `false`


### last

Gets the last child, skipping text nodes Defined in override Ext.dom.AbstractElement_traversal. ...

Gets the last child, skipping text nodes **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : String (optional)Find the previous sibling that matches the passed simple selector


### load

Direct access to the Ext.ElementLoader Ext.ElementLoader.load method. ...

Direct access to the Ext.ElementLoader Ext.ElementLoader.load method. The method takes the same object parameter as Ext.ElementLoader.load

**Parameters:** options : Object


### mask

Puts a mask over this element to disable user interaction. ...

Puts a mask over this element to disable user interaction. Requires core.css. This method can only be applied to elements which accept child nodes.

**Parameters:** msg : String (optional)A message to display in the mask


### matchNode

Defined in override Ext.dom.AbstractElement_traversal. ...

**Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** dir : Object


### monitorMouseLeave

Monitors this Element for the mouse leaving. ...

Monitors this Element for the mouse leaving. Calls the function after the specified delay only if the mouse was not moved back into the Element within the delay. If the mouse *was* moved back in, the function is not called.

**Parameters:** delay : NumberThe delay **in milliseconds** to wait for possible mouse re-entry before calling the handler function.


### moveTo

Sets the position of the element in page coordinates. ...

Sets the position of the element in page coordinates. **Defined in override Ext.dom.Element_position.** This method has been **deprecated** Use setXY instead.


### needsTabIndex

Returns true if this element needs an explicit tabIndex to make it focusable. ...

**Returns:** true if this element needs an explicit tabIndex to make it focusable. Input fields, text areas, buttons anchors elements **with an href** etc do not need a tabIndex, but structural elements do.


### next

Gets the next sibling, skipping text nodes Defined in override Ext.dom.AbstractElement_traversal. ...

Gets the next sibling, skipping text nodes **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : String (optional)Find the next sibling that matches the passed simple selector


### on

Appends an event handler to this element. ...

Appends an event handler to this element.

**Parameters:** eventName : StringThe name of event to handle.


### onConfigUpdate

...

**Parameters:** names : Object


### parent

Gets the parent node for this element, optionally chaining up trying to match a selector Defined in override Ext.dom...

Gets the parent node for this element, optionally chaining up trying to match a selector **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : String (optional)Find a parent node that matches the passed simple selector


### pause

Creates a pause before any subsequent queued effects begin. ...

Creates a pause before any subsequent queued effects begin. If there are no effects queued after the pause it will have no effect. Usage: **Defined in override Ext.dom.Element_anim.** This method has been **deprecated** since 4.0 Use the `delay` config to animate instead.


### position

Initializes positioning on this element. ...

Initializes positioning on this element. If a desired position is not passed, it will make the the element positioned relative IF it is not already positioned. **Defined in override Ext.dom.Element_position.**

**Parameters:** pos : String (optional)Positioning to use "relative", "absolute" or "fixed"


### prev

Gets the previous sibling, skipping text nodes Defined in override Ext.dom.AbstractElement_traversal. ...

Gets the previous sibling, skipping text nodes **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : String (optional)Find the previous sibling that matches the passed simple selector


### puff

Fades the element out while slowly expanding it in all directions. ...

Fades the element out while slowly expanding it in all directions. When the effect is completed, the element will be hidden (visibility = 'hidden') but block elements will still take up space in the document. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** options : Object (optional)Object literal with any of the Ext.fx.Anim config options


### purgeAllListeners

Recursively removes all previous added listeners from this element and its children ...

Recursively removes all previous added listeners from this element and its children

**Returns:** Ext.dom.Elementthis


### query

Selects child nodes based on the passed CSS selector (the selector should not contain an id). ...

Selects child nodes based on the passed CSS selector (the selector should not contain an id). **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : StringThe CSS selector


### radioCls

Adds one or more CSS classes to this element and removes the same class(es) from all siblings. ...

Adds one or more CSS classes to this element and removes the same class(es) from all siblings. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** className : String/String[]The CSS class to add, or an array of classes


### relayEvent

Create an event handler on this element such that when the event fires and is handled by this element, it will be rel...

Create an event handler on this element such that when the event fires and is handled by this element, it will be relayed to another object (i.e., fired again as if it originated from that object instead).

**Parameters:** eventName : StringThe type of event to relay


### remove

Removes this element's dom reference. ...

Removes this element's dom reference. Note that event and cache removal is handled at Ext.removeNode


### removeAllListeners

Removes all previous added listeners from this element ...

Removes all previous added listeners from this element

**Returns:** Ext.dom.Elementthis


### removeCls

Removes one or more CSS classes from the element. ...

Removes one or more CSS classes from the element. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** className : String/String[]The CSS classes to remove separated by space, or an array of classes


### removeListener

Shorthand for un. ...

Shorthand for un. Removes an event handler from this element. **Note**: if a *scope* was explicitly specified when adding the listener, the same scope must be specified here. Example:

**Parameters:** eventName : StringThe name of the event from which to remove the handler.


### repaint

Forces the browser to repaint this element Defined in override Ext.dom.AbstractElement_style. ...

Forces the browser to repaint this element **Defined in override Ext.dom.AbstractElement_style.**

**Returns:** Ext.dom.Elementthis


### replace

Replaces the passed element with this element Defined in override Ext.dom.AbstractElement_insertion. ...

Replaces the passed element with this element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElementThe element to replace. The id of the node, a DOM Node or an existing Element.


### replaceCls

Replaces a CSS class on the element with another. ...

Replaces a CSS class on the element with another. If the old name does not exist, the new name will simply be added. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** oldClassName : StringThe CSS class to replace


### replaceWith

Replaces this element with the passed element Defined in override Ext.dom.AbstractElement_insertion. ...

Replaces this element with the passed element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** el : String/HTMLElement/Ext.dom.AbstractElement/ObjectThe new element (id of the node, a DOM Node or an existing Element) or a DomHelper config of an element to create


### rtlGetLocalX

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**


### rtlGetLocalXY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**


### rtlSetLocalX

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### rtlSetLocalXY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### rtlSetX

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### rtlSetXY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** xy : Object


### rtlSetY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** y : Object


### rtlTranslatePoints

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### rtlTranslateXY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### scale

Animates the transition of an element's dimensions from a starting height/width to an ending height/width. ...

Animates the transition of an element's dimensions from a starting height/width to an ending height/width. This method is a convenience implementation of shift. Usage: **Defined in override Ext.dom.Element_anim.** This method has been **deprecated** since 4.0 Just use animate instead.


### scroll

Scrolls this element the specified direction. ...

Scrolls this element the specified direction. Does bounds checking to make sure the scroll is within this element's scrollable range. **Defined in override Ext.dom.Element_scroll.**

**Parameters:** - direction : StringPossible values are: `"l"` (or `"left"`) - `"r"` (or `"right"`) - `"t"` (or `"top"`, or `"up"`) - `"b"` (or `"bottom"`, or `"down"`)


### scrollBy

Scrolls this element by the passed delta values, optionally animating. ...

Scrolls this element by the passed delta values, optionally animating. All of the following are equivalent: **Defined in override Ext.dom.Element_scroll.**

**Parameters:** deltaX : Number/Number[]/ObjectEither the x delta, an Array specifying x and y deltas or an object with "x" and "y" properties.


### scrollChildIntoView

Defined in override Ext.dom.Element_scroll. ...

**Defined in override Ext.dom.Element_scroll.**

**Parameters:** child : Object


### scrollIntoView

Scrolls this element into view within the passed container. ...

Scrolls this element into view within the passed container. **Defined in override Ext.dom.Element_scroll.**

**Parameters:** container : String/HTMLElement/Ext.Element (optional)The container element to scroll. Should be a string (id), dom node, or Ext.Element. Defaults to: `document.body`


### scrollTo

Scrolls this element the specified scroll point. ...

Scrolls this element the specified scroll point. It does NOT do bounds checking so if you scroll to a weird value it will try to do it. For auto bounds checking, use scroll. **Defined in override Ext.dom.Element_scroll.**

**Parameters:** side : StringEither "left" for scrollLeft values or "top" for scrollTop values.


### select

Creates a Ext.CompositeElement for child nodes based on the passed CSS selector (the selector should not contain an id). ...

Creates a Ext.CompositeElement for child nodes based on the passed CSS selector (the selector should not contain an id). **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : StringThe CSS selector


### selectable

Enable text selection for this element (normalized across browsers) Defined in override Ext.dom.Element_style. ...

Enable text selection for this element (normalized across browsers) **Defined in override Ext.dom.Element_style.**

**Returns:** Ext.Elementthis


### serializeForm

Serializes a DOM form into a url encoded string Defined in override Ext.dom.AbstractElement_static. ...

Serializes a DOM form into a url encoded string **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** form : ObjectThe form


### set

Sets the passed attributes as attributes of this element (a style attribute can be a string, object or function) ...

Sets the passed attributes as attributes of this element (a style attribute can be a string, object or function)

**Parameters:** o : ObjectThe object with the attributes


### setBottom

Sets the element's CSS bottom style. ...

Sets the element's CSS bottom style. **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### setBounds

Sets the element's position and size in one shot. ...

Sets the element's position and size in one shot. If animation is true then width, height, x and y will be animated concurrently. **Defined in override Ext.dom.Element_position.** This method has been **deprecated** Use Ext.util.Positionable.setBox instead.


### setConfig

...

**Parameters:** config : Object


### setDisplayed

Sets the CSS display property. ...

Sets the CSS display property. Uses originalDisplay if the specified value is a boolean true. **Defined in override Ext.dom.Element_fx.**

**Parameters:** value : Boolean/StringBoolean value to display the element using its default display, or a string to set the display directly.


### setHTML

Set the innerHTML of this element ...

Set the innerHTML of this element

**Parameters:** html : StringThe new HTML


### setHeight

Set the height of this Element. ...

Set the height of this Element. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** - height : Number/StringThe new height. This may be one of: A Number specifying the new height in this Element's defaultUnits (by default, pixels.) - A String used to set the CSS height style. Animation may **not** be used.


### setHorizontal

Removes "vertical" state from this element (reverses everything done by setVertical). ...

Removes "vertical" state from this element (reverses everything done by setVertical). **Defined in override Ext.dom.Element_style.**


### setLeft

Sets the element's left position directly using CSS style (instead of setX). ...

Sets the element's left position directly using CSS style (instead of setX). **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### setLeftTop

Sets the element's left and top positions directly using CSS style Defined in override Ext.dom.Element_position. ...

Sets the element's left and top positions directly using CSS style **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### setLocation

Sets the position of the element in page coordinates. ...

Sets the position of the element in page coordinates. **Defined in override Ext.dom.Element_position.** This method has been **deprecated** Use setXY instead.


### setOpacity

Set the opacity of the element Defined in override Ext.dom.Element_style. ...

Set the opacity of the element **Defined in override Ext.dom.Element_style.**

**Parameters:** opacity : NumberThe new opacity. 0 = transparent, .5 = 50% visibile, 1 = fully visible, etc


### setPositioning

Set positioning with an object returned by getPositioning. ...

Set positioning with an object returned by getPositioning. **Defined in override Ext.dom.Element_position.**

**Parameters:** posCfg : Object


### setRight

Sets the element's CSS right style. ...

Sets the element's CSS right style. **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### setScrollLeft

Sets the left scroll position Defined in override Ext.dom.Element_scroll. ...

Sets the left scroll position **Defined in override Ext.dom.Element_scroll.**

**Parameters:** left : NumberThe left scroll position


### setScrollTop

Sets the top scroll position Defined in override Ext.dom.Element_scroll. ...

Sets the top scroll position **Defined in override Ext.dom.Element_scroll.**

**Parameters:** top : NumberThe top scroll position


### setSize

Set the size of this Element. ...

Set the size of this Element. If animation is true, both width and height will be animated concurrently. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** - width : Number/StringThe new width. This may be one of: A Number specifying the new width in this Element's defaultUnits (by default, pixels). - A String used to set the CSS width style. Animation may **not** be used. - A size object in the format `{width: widthValue, height: heightValue}`.


### setStyle

Wrapper for setting style properties, also takes single object parameter of multiple styles. ...

Wrapper for setting style properties, also takes single object parameter of multiple styles. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** property : String/ObjectThe style property to be set, or an object of multiple styles.


### setTop

Sets the element's top position directly using CSS style (instead of setY). ...

Sets the element's top position directly using CSS style (instead of setY). **Defined in override Ext.dom.Element_position.** This method has been **deprecated**


### setVertical

Changes this Element's state to "vertical" (rotated 90 or 270 degrees). ...

Changes this Element's state to "vertical" (rotated 90 or 270 degrees). This involves inverting the getters and setters for height and width, and applying hooks for rotating getters and setters for border/margin/padding. (getWidth becomes getHeight and vice versa), setStyle and getStyle will also return the inverse when height or width are being operated on. **Defined in override Ext.dom.Element_style.**

**Parameters:** angle : Numberthe angle of rotation - either 90 or 270


### setVisibilityMode

Use this to change the visibility mode between VISIBILITY, DISPLAY, OFFSETS or ASCLASS. ...

Use this to change the visibility mode between VISIBILITY, DISPLAY, OFFSETS or ASCLASS.

**Parameters:** mode : Object


### setVisible

Sets the visibility of the element (see details). ...

Sets the visibility of the element (see details). If the visibilityMode is set to Element.DISPLAY, it will use the display property to hide the element, otherwise it uses visibility. The default is to hide and show using the visibility property. **Defined in override Ext.dom.Element_fx.**

**Parameters:** visible : BooleanWhether the element is visible


### setWidth

Set the width of this Element. ...

Set the width of this Element. **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** - width : Number/StringThe new width. This may be one of: A Number specifying the new width in this Element's defaultUnits (by default, pixels). - A String used to set the CSS width style. Animation may **not** be used.


### setX

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### setXY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** xy : Object


### setY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** y : Object


### shift

Animates the transition of any combination of an element's dimensions, xy position and/or opacity. ...

Animates the transition of any combination of an element's dimensions, xy position and/or opacity. Any of these properties not specified in the config object will not be changed. This effect requires that at least one new dimension, position or opacity setting must be passed in on the config object in order for the function to have any effect. Usage: **Defined in override Ext.dom.Element_anim.** This method has been **deprecated** since 4.0 Just use animate instead.


### show

Show this element - Uses display mode to determine whether to use "display" or "visibility". ...

Show this element - Uses display mode to determine whether to use "display" or "visibility". See setVisible. **Defined in override Ext.dom.Element_fx.**

**Parameters:** animate : Boolean/Object (optional)true for the default animation or a standard Element animation config object


### slideIn

Slides the element into view. ...

Slides the element into view. An anchor point can be optionally passed to set the point of origin for the slide effect. This function automatically handles wrapping the element with a fixed-size container if needed. See the Ext.fx.Anim class overview for valid anchor point options. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** anchor : String (optional)One of the valid Ext.fx.Anim anchor positions (defaults to top: 't')


### slideOut

Slides the element out of view. ...

Slides the element out of view. An anchor point can be optionally passed to set the end point for the slide effect. When the effect is completed, the element will be hidden (visibility = 'hidden') but block elements will still take up space in the document. The element must be removed from the DOM using the 'remove' config option if desired. This function automatically handles wrapping the element with a fixed-size container if needed. See the Ext.fx.Anim class overview for valid anchor point options. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** anchor : String (optional)One of the valid Ext.fx.Anim anchor positions (defaults to top: 't')


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### swallowEvent

Stops the specified event(s) from bubbling and optionally prevents the default action ...

Stops the specified event(s) from bubbling and optionally prevents the default action

**Parameters:** eventName : String/String[]an event / array of events to stop from bubbling


### switchOff

Blinks the element as if it was clicked and then collapses on its center (similar to switching off a television). ...

Blinks the element as if it was clicked and then collapses on its center (similar to switching off a television). When the effect is completed, the element will be hidden (visibility = 'hidden') but block elements will still take up space in the document. The element must be removed from the DOM using the 'remove' config option if desired. Usage: **Defined in override Ext.dom.Element_anim.**

**Parameters:** options : Object (optional)Object literal with any of the Ext.fx.Anim config options


### syncContent

. Currently used for updating grid cells without modifying DOM structure Synchronizes content of this Element with t...

. Currently used for updating grid cells without modifying DOM structure Synchronizes content of this Element with the content of the passed element. Style and CSS class are copied from source into this Element, and contents are synched recursively. If a child node is a text node, the textual data is copied.

**Parameters:** source : Object


### toggle

Toggles the element's visibility or display, depending on visibility mode. ...

Toggles the element's visibility or display, depending on visibility mode. **Defined in override Ext.dom.Element_fx.**

**Parameters:** animate : Boolean/Object (optional)True for the default animation, or a standard Element animation config object


### toggleCls

Toggles the specified CSS class on this element (removes it if it already exists, otherwise adds it). ...

Toggles the specified CSS class on this element (removes it if it already exists, otherwise adds it). **Defined in override Ext.dom.AbstractElement_style.**

**Parameters:** className : StringThe CSS class to toggle


### translatePoints

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### translateXY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.**

**Parameters:** x : Object


### un

Removes an event handler from this element. ...

Removes an event handler from this element. **Note**: if a *scope* was explicitly specified when adding the listener, the same scope must be specified here. Example:

**Parameters:** eventName : StringThe name of the event from which to remove the handler.


### unclip

Return clipping (overflow) to original clipping before clip was called Defined in override Ext.dom.Element_style. ...

Return clipping (overflow) to original clipping before clip was called **Defined in override Ext.dom.Element_style.**

**Returns:** Ext.dom.Elementthis


### unmask

Hides a previously applied mask. ...

Hides a previously applied mask. Overrides: Ext.dom.AbstractElement.unmask


### unselectable

Disables text selection for this element (normalized across browsers) Defined in override Ext.dom.Element_style. ...

Disables text selection for this element (normalized across browsers) **Defined in override Ext.dom.Element_style.**

**Returns:** Ext.dom.Elementthis


### up

Walks up the DOM looking for a parent node that matches the passed simple selector (e.g. ...

Walks up the DOM looking for a parent node that matches the passed simple selector (e.g. div.some-class or span:first-child). This is a shortcut for findParentNode() that always returns an Ext.dom.Element. **Defined in override Ext.dom.AbstractElement_traversal.**

**Parameters:** selector : StringThe simple selector to test


### update

Updates the innerHTML of this element, optionally searching for and processing scripts. ...

Updates the innerHTML of this element, optionally searching for and processing scripts.

**Parameters:** html : StringThe new HTML


### wrap

Creates and wraps this element with another element Defined in override Ext.dom.AbstractElement_insertion. ...

Creates and wraps this element with another element **Defined in override Ext.dom.AbstractElement_insertion.**

**Parameters:** config : Object (optional)DomHelper element config object for the wrapper element or null for an empty div


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


### addMethods

...


### addStatics

Add / override static properties of this class. ...

Add / override static properties of this class.

**Parameters:** members : Object


### addToCache

...

**Parameters:** el : Object


### addUnits

Test if size has a unit, otherwise appends the passed unit string, or the default for this Element. ...

Test if size has a unit, otherwise appends the passed unit string, or the default for this Element. **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** size : Object{Object} The size to set


### addXtype

...

**Parameters:** xtype : Object


### borrow

Borrow another class' members to the prototype of this class. ...

Borrow another class' members to the prototype of this class.

**Parameters:** fromClass : Ext.BaseThe class to borrow members from


### camelReplaceFn

private Defined in override Ext.dom.AbstractElement_static. ...

private **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** m : Object


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


### fromPoint

Returns the top Element that is located at the passed coordinates Defined in override Ext.dom.AbstractElement_static. ...

**Parameters:** x : NumberThe x coordinate

**Returns:** the top Element that is located at the passed coordinates **Defined in override Ext.dom.AbstractElement_static.**


### get

Retrieves Ext.dom.Element objects. ...

Retrieves Ext.dom.Element objects. Ext.get is alias for Ext.dom.Element.get. **This method does not retrieve Components.** This method retrieves Ext.dom.Element objects which encapsulate DOM elements. To retrieve a Component by its ID, use Ext.ComponentManager.get. When passing an id, it should not include the `#` character that is used for a css selector. Uses simple caching to consistently return the same object. Automatically fixes if an object was recreated with the same id via AJAX or DOM.

**Parameters:** el : String/HTMLElement/Ext.ElementThe id of the node, a DOM Node or an existing Element.


### getDocumentHeight

Retrieves the document height Defined in override Ext.dom.AbstractElement_static. ...

Retrieves the document height **Defined in override Ext.dom.AbstractElement_static.**

**Returns:** NumberdocumentHeight


### getDocumentWidth

Retrieves the document width Defined in override Ext.dom.AbstractElement_static. ...

Retrieves the document width **Defined in override Ext.dom.AbstractElement_static.**

**Returns:** NumberdocumentWidth


### getName

Get the current class' name in string format. ...

Get the current class' name in string format.

**Returns:** StringclassName


### getOrientation

Retrieves the current orientation of the window. ...

Retrieves the current orientation of the window. This is calculated by determing if the height is greater than the width. **Defined in override Ext.dom.AbstractElement_static.**

**Returns:** StringOrientation of window: 'portrait' or 'landscape'


### getViewSize

Retrieves the viewport size of the window. ...

Retrieves the viewport size of the window. **Defined in override Ext.dom.AbstractElement_static.**

**Returns:** Objectobject containing width and height properties


### getViewportHeight

Retrieves the viewport height of the window. ...

Retrieves the viewport height of the window. **Defined in override Ext.dom.AbstractElement_static.**

**Returns:** NumberviewportHeight


### getViewportWidth

Retrieves the viewport width of the window. ...

Retrieves the viewport width of the window. **Defined in override Ext.dom.AbstractElement_static.**

**Returns:** NumberviewportWidth


### getXY

Defined in override Ext.rtl.dom.Element_position. ...

**Defined in override Ext.rtl.dom.Element_position.** **From override Ext.dom.Element_position:** Gets element X and Y positions in page coordinates

**Parameters:** el : Object


### implement

Adds members to class. ...

Adds members to class. This method has been **deprecated** since 4.1 Use addMembers instead.


### isAncestor

Defined in override Ext.dom.AbstractElement_static. ...

**Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** p : Object


### mergeClsList

Returns an array of unique class names based upon the input strings, or string arrays. ...

**Parameters:** clsList1 : MixedA string of class names, or an array of class names.

**Returns:** an array of unique class names based upon the input strings, or string arrays. The number of parameters is unlimited. Example


### mixin

Used internally by the mixins pre-processor ...

Used internally by the mixins pre-processor

**Parameters:** name : Object


### normalize

Normalizes CSS property keys from dash delimited to camel case JavaScript Syntax. ...

Normalizes CSS property keys from dash delimited to camel case JavaScript Syntax. For example: - border-width -> borderWidth - padding-top -> paddingTop **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** prop : StringThe property to normalize


### onExtended

...

**Parameters:** fn : Object


### override

Override members of this class. ...

Override members of this class. Overridden methods can be invoked via callParent. As of 4.1, direct use of this method is deprecated. Use Ext.define instead: The above accomplishes the same result but can be managed by the Ext.Loader which can properly order the override and its target class and the build process can determine whether the override is needed based on the required state of the target class (My.Cat). This method has been **deprecated** since 4.1.0 Use Ext.define instead


### parseBox

Parses a number or string representing margin sizes into an object. ...

Parses a number or string representing margin sizes into an object. Supports CSS-style margin declarations (e.g. 10, "10", "10 10", "10 10 10" and "10 10 10 10" are all valid options and would return the same result) **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** box : Number/StringThe encoded margins


### parseStyles

Converts a CSS string into an object with a property for each style. ...

Converts a CSS string into an object with a property for each style. The sample code below would return an object with 2 properties, one for background-color and one for color. **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** styles : StringA CSS string


### removeCls

Returns an array of unique class names deom the first parameter with all class names from the second parameter removed. ...

**Parameters:** existingClsList : MixedA string of class names, or an array of class names.

**Returns:** an array of unique class names deom the first parameter with all class names from the second parameter removed. Example


### select

Selects elements based on the passed CSS selector to enable Element methods to be applied to many related elements in...

Selects elements based on the passed CSS selector to enable Element methods to be applied to many related elements in one statement through the returned CompositeElement or CompositeElementLite object.

**Parameters:** selector : String/HTMLElement[]The CSS selector or an array of elements


### triggerExtended

...


### unitizeBox

Parses a number or string representing margin sizes into an object. ...

Parses a number or string representing margin sizes into an object. Supports CSS-style margin declarations (e.g. 10, "10", "10 10", "10 10 10" and "10 10 10 10" are all valid options and would return the same result) **Defined in override Ext.dom.AbstractElement_static.**

**Parameters:** box : Number/String/ObjectThe encoded margins, or an object with top, right, bottom, and left properties


### DOMActivate

Where supported. ...

Where supported. Fires when an element is activated, for instance, through a mouse click or a keypress.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMAttrModified

Where supported. ...

Where supported. Fires when an attribute has been modified.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMCharacterDataModified

Where supported. ...

Where supported. Fires when the character data has been modified.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMFocusIn

Where supported. ...

Where supported. Similar to HTML focus event, but can be applied to any focusable element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMFocusOut

Where supported. ...

Where supported. Similar to HTML blur event, but can be applied to any focusable element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMNodeInserted

Where supported. ...

Where supported. Fires when a node has been added as a child of another node.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMNodeInsertedIntoDocument

Where supported. ...

Where supported. Fires when a node is being inserted into a document.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMNodeRemoved

Where supported. ...

Where supported. Fires when a descendant node of the element is removed.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMNodeRemovedFromDocument

Where supported. ...

Where supported. Fires when a node is being removed from a document.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMSubtreeModified

Where supported. ...

Where supported. Fires when the subtree is modified.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### abort

Fires when an object/image is stopped from loading before completely loaded. ...

Fires when an object/image is stopped from loading before completely loaded.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### blur

Fires when an element loses focus either via the pointing device or by tabbing navigation. ...

Fires when an element loses focus either via the pointing device or by tabbing navigation.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### change

Fires when a control loses the input focus and its value has been modified since gaining focus. ...

Fires when a control loses the input focus and its value has been modified since gaining focus.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### click

Fires when a mouse click is detected within the element. ...

Fires when a mouse click is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### contextmenu

Fires when a right click is detected within the element. ...

Fires when a right click is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### dblclick

Fires when a mouse double click is detected within the element. ...

Fires when a mouse double click is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### error

Fires when an object/image/frame cannot be loaded properly. ...

Fires when an object/image/frame cannot be loaded properly.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### focus

Fires when an element receives focus either via the pointing device or by tab navigation. ...

Fires when an element receives focus either via the pointing device or by tab navigation.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### keydown

Fires when a keydown is detected within the element. ...

Fires when a keydown is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### keypress

Fires when a keypress is detected within the element. ...

Fires when a keypress is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### keyup

Fires when a keyup is detected within the element. ...

Fires when a keyup is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### load

Fires when the user agent finishes loading all content within the element. ...

Fires when the user agent finishes loading all content within the element. Only supported by window, frames, objects and images.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mousedown

Fires when a mousedown is detected within the element. ...

Fires when a mousedown is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseenter

Fires when the mouse enters the element. ...

Fires when the mouse enters the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseleave

Fires when the mouse leaves the element. ...

Fires when the mouse leaves the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mousemove

Fires when a mousemove is detected with the element. ...

Fires when a mousemove is detected with the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseout

Fires when a mouseout is detected with the element. ...

Fires when a mouseout is detected with the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseover

Fires when a mouseover is detected within the element. ...

Fires when a mouseover is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseup

Fires when a mouseup is detected within the element. ...

Fires when a mouseup is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### reset

Fires when a form is reset. ...

Fires when a form is reset.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### resize

Fires when a document view is resized. ...

Fires when a document view is resized.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### scroll

Fires when a document view is scrolled. ...

Fires when a document view is scrolled.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### select

Fires when a user selects some text in a text field, including input and textarea. ...

Fires when a user selects some text in a text field, including input and textarea.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### submit

Fires when a form is submitted. ...

Fires when a form is submitted.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### unload

Fires when the user agent removes all content from a window or frame. ...

Fires when the user agent removes all content from a window or frame. For elements, it fires when the target element or any of its content has been removed.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


## Events

### DOMActivate

Where supported. ...

Where supported. Fires when an element is activated, for instance, through a mouse click or a keypress.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMAttrModified

Where supported. ...

Where supported. Fires when an attribute has been modified.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMCharacterDataModified

Where supported. ...

Where supported. Fires when the character data has been modified.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMFocusIn

Where supported. ...

Where supported. Similar to HTML focus event, but can be applied to any focusable element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMFocusOut

Where supported. ...

Where supported. Similar to HTML blur event, but can be applied to any focusable element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMNodeInserted

Where supported. ...

Where supported. Fires when a node has been added as a child of another node.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMNodeInsertedIntoDocument

Where supported. ...

Where supported. Fires when a node is being inserted into a document.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMNodeRemoved

Where supported. ...

Where supported. Fires when a descendant node of the element is removed.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMNodeRemovedFromDocument

Where supported. ...

Where supported. Fires when a node is being removed from a document.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### DOMSubtreeModified

Where supported. ...

Where supported. Fires when the subtree is modified.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### abort

Fires when an object/image is stopped from loading before completely loaded. ...

Fires when an object/image is stopped from loading before completely loaded.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### blur

Fires when an element loses focus either via the pointing device or by tabbing navigation. ...

Fires when an element loses focus either via the pointing device or by tabbing navigation.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### change

Fires when a control loses the input focus and its value has been modified since gaining focus. ...

Fires when a control loses the input focus and its value has been modified since gaining focus.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### click

Fires when a mouse click is detected within the element. ...

Fires when a mouse click is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### contextmenu

Fires when a right click is detected within the element. ...

Fires when a right click is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### dblclick

Fires when a mouse double click is detected within the element. ...

Fires when a mouse double click is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### error

Fires when an object/image/frame cannot be loaded properly. ...

Fires when an object/image/frame cannot be loaded properly.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### focus

Fires when an element receives focus either via the pointing device or by tab navigation. ...

Fires when an element receives focus either via the pointing device or by tab navigation.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### keydown

Fires when a keydown is detected within the element. ...

Fires when a keydown is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### keypress

Fires when a keypress is detected within the element. ...

Fires when a keypress is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### keyup

Fires when a keyup is detected within the element. ...

Fires when a keyup is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### load

Fires when the user agent finishes loading all content within the element. ...

Fires when the user agent finishes loading all content within the element. Only supported by window, frames, objects and images.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mousedown

Fires when a mousedown is detected within the element. ...

Fires when a mousedown is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseenter

Fires when the mouse enters the element. ...

Fires when the mouse enters the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseleave

Fires when the mouse leaves the element. ...

Fires when the mouse leaves the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mousemove

Fires when a mousemove is detected with the element. ...

Fires when a mousemove is detected with the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseout

Fires when a mouseout is detected with the element. ...

Fires when a mouseout is detected with the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseover

Fires when a mouseover is detected within the element. ...

Fires when a mouseover is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### mouseup

Fires when a mouseup is detected within the element. ...

Fires when a mouseup is detected within the element.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### reset

Fires when a form is reset. ...

Fires when a form is reset.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### resize

Fires when a document view is resized. ...

Fires when a document view is resized.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### scroll

Fires when a document view is scrolled. ...

Fires when a document view is scrolled.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### select

Fires when a user selects some text in a text field, including input and textarea. ...

Fires when a user selects some text in a text field, including input and textarea.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### submit

Fires when a form is submitted. ...

Fires when a form is submitted.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


### unload

Fires when the user agent removes all content from a window or frame. ...

Fires when the user agent removes all content from a window or frame. For elements, it fires when the target element or any of its content has been removed.

**Parameters:** e : Ext.EventObjectThe Ext.EventObject encapsulating the DOM event.


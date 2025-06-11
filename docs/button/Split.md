# Ext.button.Split

**Extends:** Ext.button.Button

**Widget Alias:** splitbutton

**Alternate Names:** Ext.SplitButton

## Descrição

A split button that provides a built-in dropdown arrow that can fire an event separately from the default click event
of the button. Typically this would be used to display a dropdown menu that provides additional options to the
primary button action, but any custom handler can provide the arrowclick implementation.  Example usage:

// display a dropdown menu:
Ext.create('Ext.button.Split', {
    renderTo: Ext.getBody(),
    text: 'Options',
    // handle a click on the button itself
    handler: function() {
        alert("The button was clicked");
    },
    menu: new Ext.menu.Menu({
        items: [
            // these will render as dropdown menu items when the arrow is clicked:
            {text: 'Item 1', handler: function(){ alert("Item 1 clicked"); }},
            {text: 'Item 2', handler: function(){ alert("Item 2 clicked"); }}
        ]
    })
});


Instead of showing a menu, you can provide any type of custom functionality you want when the dropdown
arrow is clicked:

## Exemplos

### Exemplo 1

```javascript
// display a dropdown menu:
Ext.create('Ext.button.Split', {
    renderTo: Ext.getBody(),
    text: 'Options',
    // handle a click on the button itself
    handler: function() {
        alert("The button was clicked");
    },
    menu: new Ext.menu.Menu({
        items: [
            // these will render as dropdown menu items when the arrow is clicked:
            {text: 'Item 1', handler: function(){ alert("Item 1 clicked"); }},
            {text: 'Item 2', handler: function(){ alert("Item 2 clicked"); }}
        ]
    })
});
```

## Config options

### allowDepress

**Tipo:** Boolean

False to not allow a pressed Button to be depressed. ...

False to not allow a pressed Button to be depressed. Only valid when enableToggle is true.
Defaults to: `true`


### arrowAlign

**Tipo:** String

The side of the Button box to render the arrow if the button has an associated menu. ...

The side of the Button box to render the arrow if the button has an associated menu. Two
values are allowed:


'right'
'bottom'


Defaults to: `'right'`


### arrowCls

**Tipo:** String

The className used for the inner arrow element if the button has a menu. ...

The className used for the inner arrow element if the button has a menu.
Defaults to: `'split'`Overrides: Ext.button.Button.arrowCls


### arrowHandler

**Tipo:** Function

A function called when the arrow button is clicked (can be used instead of click event) ...

A function called when the arrow button is clicked (can be used instead of click event)
Parametersthis : Ext.button.Split


### arrowTooltip

**Tipo:** String

The title attribute of the arrow.


### autoEl

**Tipo:** String/Object

A tag name or DomHelper spec used to create the Element which will
encapsulate this Component. ...

A tag name or DomHelper spec used to create the Element which will
encapsulate this Component.

You do not normally need to specify this. For the base classes Ext.Component and
Ext.container.Container, this defaults to **'div'**. The more complex Sencha classes use a more
complex DOM structure specified by their own renderTpls.

This is intended to allow the developer to create application-specific utility Components encapsulated by
different DOM elements. Example usage:

{
    xtype: 'component',
    autoEl: {
        tag: 'img',
        src: 'http://www.example.com/example.jpg'
    }
}, {
    xtype: 'component',
    autoEl: {
        tag: 'blockquote',
        html: 'autoEl is cool!'
    }
}, {
    xtype: 'container',
    autoEl: 'ul',
    cls: 'ux-unordered-list',
    items: {
        xtype: 'component',
        autoEl: 'li',
        html: 'First list item'
    }
}

        Available since: 2.3.0


### autoLoad

**Tipo:** Ext.ComponentLoader/Object/String/Boolean

An alias for loader config which also allows to specify just a string which will be
used as the url that's automatica...

An alias for loader config which also allows to specify just a string which will be
used as the url that's automatically loaded:

Ext.create('Ext.Component', {
    autoLoad: 'content.html',
    renderTo: Ext.getBody()
});


The above is the same as:

Ext.create('Ext.Component', {
    loader: {
        url: 'content.html',
        autoLoad: true
    },
    renderTo: Ext.getBody()
});


Don't use it together with loader config.
        
        This cfg has been **deprecated** since 4.1.1
        Use loader config instead.


### autoRender

**Tipo:** Boolean/String/HTMLElement/Ext.Element

This config is intended mainly for non-floating Components which may or may not be shown. ...

This config is intended mainly for non-floating Components which may or may not be shown. Instead of using
renderTo in the configuration, and rendering upon construction, this allows a Component to render itself
upon first *show*. If floating is `true`, the value of this config is omitted as if it is `true`.

Specify as `true` to have this Component render to the document body upon first show.

Specify as an element, or the ID of an element to have this Component render to a specific element upon first
show.
Defaults to: `false`


### autoScroll

**Tipo:** Boolean

true to use overflow:'auto' on the components layout element and show scroll bars automatically when necessary,
false...

`true` to use overflow:'auto' on the components layout element and show scroll bars automatically when necessary,
`false` to clip any overflowing content.
This should not be combined with overflowX or  overflowY.
Defaults to: `false`


### autoShow

**Tipo:** Boolean

true to automatically show the component upon creation. ...

`true` to automatically show the component upon creation. This config option may only be used for
floating components or components that use autoRender.
Defaults to: `false`        Available since: 2.3.0


### baseCls

**Tipo:** String

The base CSS class to add to all buttons. ...

The base CSS class to add to all buttons.
Defaults to: `'x-btn'`Overrides: Ext.AbstractComponent.baseCls


### baseParams

**Tipo:** Object

An object literal of parameters to pass to the url when the href property is specified.


### border

**Tipo:** Number/String/Boolean

Specifies the border size for this component. ...

Specifies the border size for this component. The border can be a single numeric value to apply to all sides or it can
be a CSS style specification for each style, for example: '10 5 3 10' (top, right, bottom, left).

For components that have no border by default, setting this won't make the border appear by itself.
You also need to specify border color and style:

border: 5,
style: {
    borderColor: 'red',
    borderStyle: 'solid'
}


To turn off the border, use `border: false`.


### childEls

**Tipo:** Object[]

An array describing the child elements of the Component. ...

An array describing the child elements of the Component. Each member of the array
is an object with these properties:


`name` - The property name on the Component for the child element.
`itemId` - The id to combine with the Component's id that is the id of the child element.
`id` - The id of the child element.



If the array member is a string, it is equivalent to `{ name: m, itemId: m }`.

For example, a Component which renders a title and body text:

Ext.create('Ext.Component', {
    renderTo: Ext.getBody(),
    renderTpl: [
        '<h1 id="{id}-title">{title}</h1>',
        '<p>{msg}</p>',
    ],
    renderData: {
        title: "Error",
        msg: "Something went wrong"
    },
    childEls: ["title"],
    listeners: {
        afterrender: function(cmp){
            // After rendering the component will have a title property
            cmp.title.setStyle({color: "red"});
        }
    }
});


A more flexible, but somewhat slower, approach is renderSelectors.


### clickEvent

**Tipo:** String

The DOM event that will fire the handler of the button. ...

The DOM event that will fire the handler of the button. This can be any valid event name (dblclick, contextmenu).
Defaults to: `'click'`


### cls

**Tipo:** String

A CSS class string to apply to the button's main element.

A CSS class string to apply to the button's main element.
Overrides: Ext.AbstractComponent.cls


### columnWidth

**Tipo:** Number/String

Defines the column width inside column layout. ...

Defines the column width inside column layout.

Can be specified as a number or as a percentage.


### componentCls

**Tipo:** String

CSS Class to be added to a components root level element to give distinction to it via styling.


### componentLayout

**Tipo:** String/Object

The sizing and positioning of a Component's internal Elements is the responsibility of the Component's layout
manager...

The sizing and positioning of a Component's internal Elements is the responsibility of the Component's layout
manager which sizes a Component's internal structure in response to the Component being sized.

Generally, developers will not use this configuration as all provided Components which need their internal
elements sizing (Such as input fields) come with their own componentLayout managers.

The default layout manager will be used on instances of the base Ext.Component
class which simply sizes the Component's encapsulating element to the height and width specified in the
setSize method.
Defaults to: `'button'`Overrides: Ext.AbstractComponent.componentLayout


### constrain

**Tipo:** Boolean

True to constrain this Components within its containing element, false to allow it to fall outside of its containing
...

True to constrain this Components within its containing element, false to allow it to fall outside of its containing
element. By default this Component will be rendered to `document.body`. To render and constrain this Component within
another element specify renderTo.
Defaults to: `false`


### constrainTo

**Tipo:** Ext.util.Region/Ext.Element

A Region (or an element from which a Region measurement will be read) which is used
to constrain the component. ...

A Region (or an element from which a Region measurement will be read) which is used
to constrain the component. Only applies when the component is floating.


### constraintInsets

**Tipo:** Object/String

An object or a string (in TRBL order) specifying insets from the configured constrain region
within which this compon...

An object or a string (in TRBL order) specifying insets from the configured constrain region
within which this component must be constrained when positioning or sizing.
example:

   constraintInsets: '10 10 10 10' // Constrain with 10px insets from parent


### contentEl

**Tipo:** String

Specify an existing HTML element, or the id of an existing HTML element to use as the content for this component. ...

Specify an existing HTML element, or the `id` of an existing HTML element to use as the content for this component.

This config option is used to take an existing HTML element and place it in the layout element of a new component
(it simply moves the specified DOM element *after the Component is rendered* to use as the content.

**Notes:**

The specified HTML element is appended to the layout element of the component after any configured
HTML has been inserted, and so the document will not contain this element at the time
the render event is fired.

The specified HTML element used will not participate in any **`layout`**
scheme that the Component may use. It is just HTML. Layouts operate on child
**`items`**.

Add either the `x-hidden` or the `x-hide-display` CSS class to prevent a brief flicker of the content before it
is rendered to the panel.
        Available since: 3.4.0


### data

**Tipo:** Object

The initial set of data to apply to the `tpl` to update the content area of the Component.

The initial set of data to apply to the `tpl` to update the content area of the Component.
        Available since: 3.4.0


### defaultAlign

**Tipo:** String

The default Ext.Element#getAlignToXY anchor position value for this menu
relative to its element of origin. ...

The default Ext.Element#getAlignToXY anchor position value for this menu
relative to its element of origin. Used in conjunction with showBy.
Defaults to: `"tl-bl?"`


### destroyMenu

**Tipo:** Boolean

Whether or not to destroy any associated menu when this button is destroyed. ...

Whether or not to destroy any associated menu when this button is destroyed. The menu
will be destroyed unless this is explicitly set to false.


### disabled

**Tipo:** Boolean

True to start disabled. ...

True to start disabled.
Defaults to: `false`Overrides: Ext.AbstractComponent.disabled


### disabledCls

**Tipo:** String

CSS class to add when the Component is disabled. ...

CSS class to add when the Component is disabled.
Defaults to: `'x-item-disabled'`


### draggable

**Tipo:** Boolean/Object

Specify as true to make a floating Component draggable using the Component's encapsulating element as
the drag handle. ...

Specify as true to make a floating Component draggable using the Component's encapsulating element as
the drag handle.

This may also be specified as a config object for the ComponentDragger which is
instantiated to perform dragging.

For example to create a Component which may only be dragged around using a certain internal element as the drag
handle, use the delegate option:

new Ext.Component({
    constrain: true,
    floating: true,
    style: {
        backgroundColor: '#fff',
        border: '1px solid black'
    },
    html: '<h1 style="cursor:move">The title</h1><p>The content</p>',
    draggable: {
        delegate: 'h1'
    }
}).show();

Defaults to: `false`Overrides: Ext.AbstractComponent.draggable


### enableToggle

**Tipo:** Boolean

True to enable pressed/not pressed toggling. ...

True to enable pressed/not pressed toggling. If a toggleGroup is specified, this
option will be set to true.
Defaults to: `false`


### fixed

**Tipo:** Boolean

Configure as true to have this Component fixed at its X, Y coordinates in the browser viewport, immune
to scrolling t...

Configure as `true` to have this Component fixed at its `X, Y` coordinates in the browser viewport, immune
to scrolling the document.

*Only in browsers that support `position:fixed`*

*IE6 and IE7, 8 and 9 quirks do not support `position: fixed`*
Defaults to: `false`


### floating

**Tipo:** Boolean

Specify as true to float the Component outside of the document flow using CSS absolute positioning. ...

Specify as true to float the Component outside of the document flow using CSS absolute positioning.

Components such as Windows and Menus are floating by default.

Floating Components that are programatically rendered will register
themselves with the global ZIndexManager

Floating Components as child items of a Container

A floating Component may be used as a child item of a Container. This just allows the floating Component to seek
a ZIndexManager by examining the ownerCt chain.

When configured as floating, Components acquire, at render time, a ZIndexManager which
manages a stack of related floating Components. The ZIndexManager brings a single floating Component to the top
of its stack when the Component's toFront method is called.

The ZIndexManager is found by traversing up the ownerCt chain to find an ancestor which itself is
floating. This is so that descendant floating Components of floating *Containers* (Such as a ComboBox dropdown
within a Window) can have its zIndex managed relative to any siblings, but always **above** that floating
ancestor Container.

If no floating ancestor is found, a floating Component registers itself with the default ZIndexManager.

Floating components *do not participate in the Container's layout*. Because of this, they are not rendered until
you explicitly show them.

After rendering, the ownerCt reference is deleted, and the floatParent property is set to the found
floating ancestor Container. If no floating ancestor Container was found the floatParent property will
not be set.
Defaults to: `false`Overrides: Ext.AbstractComponent.floating


### focusCls

**Tipo:** String

The CSS class to add to a button when it is in the focussed state. ...

The CSS class to add to a button when it is in the focussed state.
Defaults to: `'focus'`


### focusOnToFront

**Tipo:** Boolean

Specifies whether the floated component should be automatically focused when
it is brought to the front. ...

Specifies whether the floated component should be automatically focused when
it is brought to the front.
Defaults to: `true`


### formBind

**Tipo:** Boolean

When inside FormPanel, any component configured with formBind: true will
be enabled/disabled depending on the validit...

When inside FormPanel, any component configured with `formBind: true` will
be enabled/disabled depending on the validity state of the form.
See Ext.form.Panel for more information and example.
Defaults to: `false`


### frame

**Tipo:** Boolean

Specify as true to have the Component inject framing elements within the Component at render time to provide a
graphi...

Specify as `true` to have the Component inject framing elements within the Component at render time to provide a
graphical rounded frame around the Component content.

This is only necessary when running on outdated, or non standard-compliant browsers such as Microsoft's Internet
Explorer prior to version 9 which do not support rounded corners natively.

The extra space taken up by this framing is available from the read only property frameSize.
Defaults to: `true`Overrides: Ext.AbstractComponent.frame


### glyph

**Tipo:** Number/String

A numeric unicode character code to use as the icon for this button. ...

A numeric unicode character code to use as the icon for this button. The default
font-family for glyphs can be set globally using
Ext.setGlyphFontFamily(). Alternatively, this
config option accepts a string with the charCode and font-family separated by the
`@` symbol. For example '65@My Font Family'.


### handleMouseEvents

**Tipo:** Boolean

False to disable visual cues on mouseover, mouseout and mousedown. ...

False to disable visual cues on mouseover, mouseout and mousedown.
Defaults to: `true`


### handler

**Tipo:** Function

A function called when the button is clicked (can be used instead of click event). ...

A function called when the button is clicked (can be used instead of click event).
Parametersbutton : Ext.button.ButtonThis button.


### height

**Tipo:** Number

The height of this component in pixels.


### hidden

**Tipo:** Boolean

True to start hidden. ...

True to start hidden.
Defaults to: `false`Overrides: Ext.AbstractComponent.hidden


### hideMode

**Tipo:** String

A String which specifies how this Component's encapsulating DOM element will be hidden. ...

A String which specifies how this Component's encapsulating DOM element will be hidden. Values may be:


`'display'` : The Component will be hidden using the `display: none` style.
`'visibility'` : The Component will be hidden using the `visibility: hidden` style.
`'offsets'` : The Component will be hidden by absolutely positioning it out of the visible area of the document.
This is useful when a hidden Component must maintain measurable dimensions. Hiding using `display` results in a
Component having zero dimensions.


Defaults to: `'display'`        Available since: 1.1.0


### href

**Tipo:** String

The URL to open when the button is clicked. ...

The URL to open when the button is clicked. Specifying this config causes the Button to be
rendered with the specified URL as the `href` attribute of its `<a>` Element.

This is better than specifying a click handler of

function() { window.location = "http://www.sencha.com" }


because the UI will provide meaningful hints to the user as to what to expect upon clicking
the button, and will also allow the user to open in a new tab or window, bookmark or drag the URL, or directly save
the URL stream to disk.

See also the hrefTarget config.


### hrefTarget

**Tipo:** String

The target attribute to use for the underlying anchor. ...

The target attribute to use for the underlying anchor. Only used if the href
property is specified.
Defaults to: `"_blank"`


### html

**Tipo:** String/Object

An HTML fragment, or a DomHelper specification to use as the layout element content. ...

An HTML fragment, or a DomHelper specification to use as the layout element content.
The HTML content is added after the component is rendered, so the document will not contain this HTML at the time
the render event is fired. This content is inserted into the body *before* any configured contentEl
is appended.
Defaults to: `''`        Available since: 3.4.0


### icon

**Tipo:** String

The path to an image to display in the button.


### iconAlign

**Tipo:** String

The side of the Button box to render the icon. ...

The side of the Button box to render the icon. Four values are allowed:


'top'
'right'
'bottom'
'left'


Defaults to: `'left'`


### iconCls

**Tipo:** String

A css class which sets a background image to be used as the icon for this button.


### id

**Tipo:** String

The unique id of this component instance. ...

The **unique id of this component instance.**

It should not be necessary to use this configuration except for singleton objects in your application. Components
created with an `id` may be accessed globally using Ext.getCmp.

Instead of using assigned ids, use the itemId config, and ComponentQuery
which provides selector-based searching for Sencha Components analogous to DOM querying. The Container class contains shortcut methods to query
its descendant Components by selector.

Note that this `id` will also be used as the element id for the containing HTML element that is rendered to the
page for this component. This allows you to write id-based CSS rules to style the specific instance of this
component uniquely, and also to select sub-elements using this component's `id` as the parent.

**Note:** To avoid complications imposed by a unique `id` also see `itemId`.

**Note:** To access the container of a Component see `ownerCt`.

Defaults to an auto-assigned id.
        Available since: 1.1.0


### itemId

**Tipo:** String

An itemId can be used as an alternative way to get a reference to a component when no object reference is
available. ...

An `itemId` can be used as an alternative way to get a reference to a component when no object reference is
available. Instead of using an `id` with Ext.getCmp, use `itemId` with
Ext.container.Container.getComponent which will retrieve
`itemId`'s or id's. Since `itemId`'s are an index to the container's internal MixedCollection, the
`itemId` is scoped locally to the container -- avoiding potential conflicts with Ext.ComponentManager
which requires a **unique** `id`.

var c = new Ext.panel.Panel({ //
    height: 300,
    renderTo: document.body,
    layout: 'auto',
    items: [
        {
            itemId: 'p1',
            title: 'Panel 1',
            height: 150
        },
        {
            itemId: 'p2',
            title: 'Panel 2',
            height: 150
        }
    ]
})
p1 = c.getComponent('p1'); // not the same as Ext.getCmp()
p2 = p1.ownerCt.getComponent('p2'); // reference via a sibling


Also see id, `Ext.container.Container.query`, `Ext.container.Container.down` and
`Ext.container.Container.child`.

**Note**: to access the container of an item see ownerCt.
        Available since: 3.4.0


### listeners

**Tipo:** Object

A config object containing one or more event handlers to be added to this object during initialization. ...

A config object containing one or more event handlers to be added to this object during initialization. This
should be a valid listeners config object as specified in the addListener example for attaching multiple
handlers at once.

**DOM events from Ext JS Components**

While *some* Ext JS Component classes export selected DOM events (e.g. "click", "mouseover" etc), this is usually
only done when extra value can be added. For example the DataView's **`itemclick`** event passing the node clicked on. To access DOM events directly from a
child element of a Component, we need to specify the `element` option to identify the Component property to add a
DOM listener to:

new Ext.panel.Panel({
    width: 400,
    height: 200,
    dockedItems: [{
        xtype: 'toolbar'
    }],
    listeners: {
        click: {
            element: 'el', //bind to the underlying el property on the panel
            fn: function(){ console.log('click el'); }
        },
        dblclick: {
            element: 'body', //bind to the underlying body property on the panel
            fn: function(){ console.log('dblclick body'); }
        }
    }
});


### loader

**Tipo:** Ext.ComponentLoader/Object

A configuration object or an instance of a Ext.ComponentLoader to load remote content
for this Component. ...

A configuration object or an instance of a Ext.ComponentLoader to load remote content
for this Component.

Ext.create('Ext.Component', {
    loader: {
        url: 'content.html',
        autoLoad: true
    },
    renderTo: Ext.getBody()
});


### margin

**Tipo:** Number/String

Specifies the margin for this component. ...

Specifies the margin for this component. The margin can be a single numeric value to apply to all sides or it can
be a CSS style specification for each style, for example: '10 5 3 10' (top, right, bottom, left).


### maxHeight

**Tipo:** Number

The maximum value in pixels which this Component will set its height to. ...

The maximum value in pixels which this Component will set its height to.

**Warning:** This will override any size management applied by layout managers.


### maxWidth

**Tipo:** Number

The maximum value in pixels which this Component will set its width to. ...

The maximum value in pixels which this Component will set its width to.

**Warning:** This will override any size management applied by layout managers.


### menu

**Tipo:** Ext.menu.Menu/String/Object

Standard menu attribute consisting of a reference to a menu object, a menu id or a menu config blob.


### menuActiveCls

**Tipo:** String

The CSS class to add to a button when it's menu is active. ...

The CSS class to add to a button when it's menu is active.
Defaults to: `'menu-active'`


### menuAlign

**Tipo:** String

The position to align the menu to (see Ext.util.Positionable.alignTo for more details). ...

The position to align the menu to (see Ext.util.Positionable.alignTo for more details).
Defaults to: `'tl-bl?'`


### minHeight

**Tipo:** Number

The minimum value in pixels which this Component will set its height to. ...

The minimum value in pixels which this Component will set its height to.

**Warning:** This will override any size management applied by layout managers.


### minWidth

**Tipo:** Number

The minimum width for this button (used to give a set of buttons a common width). ...

The minimum width for this button (used to give a set of buttons a common width).
See also Ext.panel.Panel.minButtonWidth.
Overrides: Ext.AbstractComponent.minWidth


### overCls

**Tipo:** String

The CSS class to add to a button when it is in the over (hovered) state. ...

The CSS class to add to a button when it is in the over (hovered) state.
Defaults to: `'over'`Overrides: Ext.AbstractComponent.overCls


### overflowText

**Tipo:** String

If used in a Toolbar, the text to be used if this item is shown in the overflow menu. ...

If used in a Toolbar, the text to be used if this item is shown in the overflow menu.
See also Ext.toolbar.Item.`overflowText`.


### overflowX

**Tipo:** String

Possible values are:
 * 'auto' to enable automatic horizontal scrollbar (overflow-x: 'auto'). ...

Possible values are:
 * `'auto'` to enable automatic horizontal scrollbar (overflow-x: 'auto').
 * `'scroll'` to always enable horizontal scrollbar (overflow-x: 'scroll').
The default is overflow-x: 'hidden'. This should not be combined with autoScroll.


### overflowY

**Tipo:** String

Possible values are:
 * 'auto' to enable automatic vertical scrollbar (overflow-y: 'auto'). ...

Possible values are:
 * `'auto'` to enable automatic vertical scrollbar (overflow-y: 'auto').
 * `'scroll'` to always enable vertical scrollbar (overflow-y: 'scroll').
The default is overflow-y: 'hidden'. This should not be combined with autoScroll.


### padding

**Tipo:** Number/String

Specifies the padding for this component. ...

Specifies the padding for this component. The padding can be a single numeric value to apply to all sides or it
can be a CSS style specification for each style, for example: '10 5 3 10' (top, right, bottom, left).


### params

**Tipo:** Object

An object literal of parameters to pass to the url when the href property is specified. ...

An object literal of parameters to pass to the url when the href property is specified. Any params
override baseParams. New params can be set using the setParams method.


### plugins

**Tipo:** Ext.AbstractPlugin[]/Ext.AbstractPlugin/Object[]/Object/Ext.enums.Plugin[]/Ext.enums.Plugin

An array of plugins to be added to this component. ...

An array of plugins to be added to this component. Can also be just a single plugin instead of array.

Plugins provide custom functionality for a component. The only requirement for
a valid plugin is that it contain an `init` method that accepts a reference of type Ext.Component. When a component
is created, if any plugins are available, the component will call the init method on each plugin, passing a
reference to itself. Each plugin can then call methods or respond to events on the component as needed to provide
its functionality.

Plugins can be added to component by either directly referencing the plugin instance:

plugins: [Ext.create('Ext.grid.plugin.CellEditing', {clicksToEdit: 1})],


By using config object with ptype:

plugins: [{ptype: 'cellediting', clicksToEdit: 1}],


Or with just a ptype:

plugins: ['cellediting', 'gridviewdragdrop'],


See Ext.enums.Plugin for list of all ptypes.
        Available since: 2.3.0


### pressed

**Tipo:** Boolean

True to start pressed (only if enableToggle = true) ...

True to start pressed (only if enableToggle = true)
Defaults to: `false`


### pressedCls

**Tipo:** String

The CSS class to add to a button when it is in the pressed state. ...

The CSS class to add to a button when it is in the pressed state.
Defaults to: `'pressed'`


### preventDefault

**Tipo:** Boolean

True to prevent the default action when the clickEvent is processed. ...

True to prevent the default action when the clickEvent is processed.
Defaults to: `true`


### region

**Tipo:** "north"/"south"/"east"/"west"/"center"

Defines the region inside border layout. ...

Defines the region inside border layout.

Possible values:


north - Positions component at top.
south - Positions component at bottom.
east - Positions component at right.
west - Positions component at left.
center - Positions component at the remaining space.
There **must** be a component with `region: "center"` in every border layout.


### renderData

**Tipo:** Object

The data used by renderTpl in addition to the following property values of the component:


id
ui
uiCls
baseCls
compo...

The data used by renderTpl in addition to the following property values of the component:


id
ui
uiCls
baseCls
componentCls
frame



See renderSelectors and childEls for usage examples.


### renderSelectors

**Tipo:** Object

An object containing properties specifying DomQuery selectors which identify child elements
created by the render pro...

An object containing properties specifying DomQuery selectors which identify child elements
created by the render process.

After the Component's internal structure is rendered according to the renderTpl, this object is iterated through,
and the found Elements are added as properties to the Component using the `renderSelector` property name.

For example, a Component which renders a title and description into its element:

Ext.create('Ext.Component', {
    renderTo: Ext.getBody(),
    renderTpl: [
        '<h1 class="title">{title}</h1>',
        '<p>{desc}</p>'
    ],
    renderData: {
        title: "Error",
        desc: "Something went wrong"
    },
    renderSelectors: {
        titleEl: 'h1.title',
        descEl: 'p'
    },
    listeners: {
        afterrender: function(cmp){
            // After rendering the component will have a titleEl and descEl properties
            cmp.titleEl.setStyle({color: "red"});
        }
    }
});


For a faster, but less flexible, alternative that achieves the same end result (properties for child elements on the
Component after render), see childEls and addChildEls.


### renderTo

**Tipo:** String/HTMLElement/Ext.Element

Specify the id of the element, a DOM element or an existing Element that this component will be rendered into. ...

Specify the `id` of the element, a DOM element or an existing Element that this component will be rendered into.

**Notes:**

Do *not* use this option if the Component is to be a child item of a Container.
It is the responsibility of the Container's
layout manager to render and manage its child items.

When using this config, a call to `render()` is not required.

See also: render.
        Available since: 2.3.0


### renderTpl

**Tipo:** Ext.XTemplate/String/String[]

We have to keep "unselectable" attribute on all elements because it's not inheritable. ...

We have to keep "unselectable" attribute on all elements because it's not inheritable.
Without it, clicking anywhere on a button disrupts current selection and cursor position
in HtmlEditor.

An XTemplate used to create the internal structure inside this Component's encapsulating
Element.

You do not normally need to specify this. For the base classes Ext.Component and
Ext.container.Container, this defaults to **`null`** which means that they will be initially rendered
with no internal structure; they render their Element empty. The more specialized Ext JS and Sencha Touch
classes which use a more complex DOM structure, provide their own template definitions.

This is intended to allow the developer to create application-specific utility Components with customized
internal structure.

Upon rendering, any created child elements may be automatically imported into object properties using the
renderSelectors and childEls options.
Defaults to: `['<span id="{id}-btnWrap" class="{baseCls}-wrap', '<tpl if="splitCls"> {splitCls}</tpl>', '{childElCls}" unselectable="on">', '<span id="{id}-btnEl" class="{baseCls}-button">', '<span id="{id}-btnInnerEl" class="{baseCls}-inner {innerCls}', '{childElCls}" unselectable="on">', '{text}', '</span>', '<span role="img" id="{id}-btnIconEl" class="{baseCls}-icon-el {iconCls}', '{childElCls} {glyphCls}" unselectable="on" style="', '<tpl if="iconUrl">background-image:url({iconUrl});</tpl>', '<tpl if="glyph && glyphFontFamily">font-family:{glyphFontFamily};</tpl>">', '<tpl if="glyph">&#{glyph};</tpl><tpl if="iconCls || iconUrl">&#160;</tpl>', '</span>', '</span>', '</span>', '<tpl if="closable">', '<span id="{id}-closeEl" class="{baseCls}-close-btn" title="{closeText}" tabIndex="0"></span>', '</tpl>']`Overrides: Ext.AbstractComponent.renderTpl


### repeat

**Tipo:** Boolean/Object

True to repeat fire the click event while the mouse is down. ...

True to repeat fire the click event while the mouse is down. This can also be a
ClickRepeater config object.
Defaults to: `false`


### resizable

**Tipo:** Boolean/Object

Specify as true to apply a Resizer to this Component after rendering. ...

Specify as `true` to apply a Resizer to this Component after rendering.

May also be specified as a config object to be passed to the constructor of Resizer
to override any defaults. By default the Component passes its minimum and maximum size, and uses
`Ext.resizer.Resizer.dynamic: false`


### resizeHandles

**Tipo:** String

A valid Ext.resizer.Resizer handles config string. ...

A valid Ext.resizer.Resizer handles config string. Only applies when resizable = true.
Defaults to: `'all'`


### rtl

**Tipo:** Boolean

True to layout this component and its descendants in "rtl" (right-to-left) mode. ...

True to layout this component and its descendants in "rtl" (right-to-left) mode.
Can be explicitly set to false to override a true value inherited from an ancestor.

**Defined in override Ext.rtl.AbstractComponent.**


### saveDelay

**Tipo:** Number

A buffer to be applied if many state events are fired within a short period. ...

A buffer to be applied if many state events are fired within a short period.
Defaults to: `100`


### scale

**Tipo:** "small"/"medium"/"large"

The size of the Button. ...

The size of the Button. Three values are allowed:


'small' - Results in the button element being 16px high.
'medium' - Results in the button element being 24px high.
'large' - Results in the button element being 32px high.


Defaults to: `'small'`


### scope

**Tipo:** Object

The scope (this reference) in which the handler and toggleHandler is executed. ...

The scope (**this** reference) in which the `handler` and `toggleHandler` is executed.
Defaults to this Button.


### shadow

**Tipo:** String/Boolean

Specifies whether the floating component should be given a shadow. ...

Specifies whether the floating component should be given a shadow. Set to true to automatically create an
Ext.Shadow, or a string indicating the shadow's display Ext.Shadow.mode. Set to false to
disable the shadow.
Defaults to: `'sides'`


### shadowOffset

**Tipo:** Number

Number of pixels to offset the shadow.


### showEmptyMenu

**Tipo:** Boolean

True to force an attached menu with no items to be shown when clicking
this button. ...

True to force an attached menu with no items to be shown when clicking
this button. By default, the menu will not show if it is empty.
Defaults to: `false`


### shrinkWrap

**Tipo:** Boolean/Number

If this property is a number, it is interpreted as follows:


0: Neither width nor height depend on content. ...

If this property is a number, it is interpreted as follows:


0: Neither width nor height depend on content. This is equivalent to `false`.
1: Width depends on content (shrink wraps), but height does not.
2: Height depends on content (shrink wraps), but width does not. The default.
3: Both width and height depend on content (shrink wrap). This is equivalent to `true`.



In CSS terms, shrink-wrap width is analogous to an inline-block element as opposed
to a block-level element. Some container layouts always shrink-wrap their children,
effectively ignoring this property (e.g., Ext.layout.container.HBox,
Ext.layout.container.VBox, Ext.layout.component.Dock).
Defaults to: `3`Overrides: Ext.AbstractComponent.shrinkWrap


### stateEvents

**Tipo:** String[]

An array of events that, when fired, should trigger this object to
save its state. ...

An array of events that, when fired, should trigger this object to
save its state. Defaults to none. `stateEvents` may be any type
of event supported by this object, including browser or custom events
(e.g., ['click', 'customerchange']).


See `stateful` for an explanation of saving and
restoring object state.


### stateId

**Tipo:** String

The unique id for this object to use for state management purposes. ...

The unique id for this object to use for state management purposes.

See stateful for an explanation of saving and restoring state.


### stateful

**Tipo:** Boolean

A flag which causes the object to attempt to restore the state of
internal properties from a saved state on startup. ...

A flag which causes the object to attempt to restore the state of
internal properties from a saved state on startup. The object must have
a stateId for state to be managed.

Auto-generated ids are not guaranteed to be stable across page loads and
cannot be relied upon to save and restore the same state for a object.

For state saving to work, the state manager's provider must have been
set to an implementation of Ext.state.Provider which overrides the
set and get
methods to save and recall name/value pairs. A built-in implementation,
Ext.state.CookieProvider is available.

To set the state provider for the current page:

   Ext.state.Manager.setProvider(new Ext.state.CookieProvider({

   expires: new Date(new Date().getTime()+(1000*60*60*24*7)), //7 days from now


   }));

A stateful object attempts to save state when one of the events
listed in the stateEvents configuration fires.

To save state, a stateful object first serializes its state by
calling *getState*.

The Component base class implements getState to save its width and height within the state
only if they were initially configured, and have changed from the configured value.

The Panel class saves its collapsed state in addition to that.

The Grid class saves its column state in addition to its superclass state.

If there is more application state to be save, the developer must provide an implementation which
first calls the superclass method to inherit the above behaviour, and then injects new properties
into the returned object.

The value yielded by getState is passed to Ext.state.Manager.set
which uses the configured Ext.state.Provider to save the object
keyed by the stateId.

During construction, a stateful object attempts to *restore* its state by calling
Ext.state.Manager.get passing the stateId

The resulting object is passed to applyState*. The default implementation of
applyState simply copies properties into the object, but a developer may
override this to support restoration of more complex application state.

You can perform extra processing on state save and restore by attaching
handlers to the beforestaterestore, staterestore,
beforestatesave and statesave events.
Defaults to: `false`


### style

**Tipo:** String/Object

A custom style specification to be applied to this component's Element. ...

A custom style specification to be applied to this component's Element. Should be a valid argument to
Ext.Element.applyStyles.

new Ext.panel.Panel({
    title: 'Some Title',
    renderTo: Ext.getBody(),
    width: 400, height: 300,
    layout: 'form',
    items: [{
        xtype: 'textarea',
        style: {
            width: '95%',
            marginBottom: '10px'
        }
    },
    new Ext.button.Button({
        text: 'Send',
        minWidth: '100',
        style: {
            marginBottom: '10px'
        }
    })
    ]
});

        Available since: 1.1.0


### tabIndex

**Tipo:** Number

Set a DOM tabIndex for this button. ...

Set a DOM tabIndex for this button.
Defaults to: `0`


### text

**Tipo:** String

The button text to be used as innerHTML (html tags are accepted).


### textAlign

**Tipo:** String

The text alignment for this button (center, left, right). ...

The text alignment for this button (center, left, right).
Defaults to: `'center'`


### toFrontOnShow

**Tipo:** Boolean

True to automatically call toFront when the show method is called on an already visible,
floating component. ...

True to automatically call toFront when the show method is called on an already visible,
floating component.
Defaults to: `true`


### toggleGroup

**Tipo:** String

The group this toggle button is a member of (only 1 per group can be pressed). ...

The group this toggle button is a member of (only 1 per group can be pressed). If a toggleGroup
is specified, the enableToggle configuration will automatically be set to true.


### toggleHandler

**Tipo:** Function

Function called when a Button with enableToggle set to true is clicked. ...

Function called when a Button with enableToggle set to true is clicked.
Parametersbutton : Ext.button.ButtonThis button.


### tooltip

**Tipo:** String/Object

The tooltip for the button - can be a string to be used as innerHTML (html tags are accepted) or
QuickTips config obj...

The tooltip for the button - can be a string to be used as innerHTML (html tags are accepted) or
QuickTips config object.


### tooltipType

**Tipo:** String

The type of tooltip to use. ...

The type of tooltip to use. Either 'qtip' for QuickTips or 'title' for title attribute.
Defaults to: `'qtip'`


### tpl

**Tipo:** Ext.XTemplate/Ext.Template/String/String[]

An Ext.Template, Ext.XTemplate or an array of strings to form an Ext.XTemplate. ...

An Ext.Template, Ext.XTemplate or an array of strings to form an Ext.XTemplate. Used in
conjunction with the `data` and `tplWriteMode` configurations.
        Available since: 3.4.0


### tplWriteMode

**Tipo:** String

The Ext.(X)Template method to use when updating the content area of the Component. ...

The Ext.(X)Template method to use when updating the content area of the Component.
See `Ext.XTemplate.overwrite` for information on default mode.
Defaults to: `'overwrite'`        Available since: 3.4.0


### ui

**Tipo:** String

A UI style for a component. ...

A UI style for a component.
Defaults to: `'default'`


### uiCls

**Tipo:** String[]

An array of of classNames which are currently applied to this component. ...

An array of of `classNames` which are currently applied to this component.
Defaults to: `[]`


### width

**Tipo:** Number

The width of this component in pixels.


### xtype

**Tipo:** Ext.enums.Widget

This property provides a shorter alternative to creating objects than using a full
class name. ...

This property provides a shorter alternative to creating objects than using a full
class name. Using `xtype` is the most common way to define component instances,
especially in a container. For example, the items in a form containing text fields
could be created explicitly like so:

 items: [
     Ext.create('Ext.form.field.Text', {
         fieldLabel: 'Foo'
     }),
     Ext.create('Ext.form.field.Text', {
         fieldLabel: 'Bar'
     }),
     Ext.create('Ext.form.field.Number', {
         fieldLabel: 'Num'
     })
 ]


But by using `xtype`, the above becomes:

 items: [
     {
         xtype: 'textfield',
         fieldLabel: 'Foo'
     },
     {
         xtype: 'textfield',
         fieldLabel: 'Bar'
     },
     {
         xtype: 'numberfield',
         fieldLabel: 'Num'
     }
 ]


When the `xtype` is common to many items, Ext.container.AbstractContainer.defaultType
is another way to specify the `xtype` for all items that don't have an explicit `xtype`:

 defaultType: 'textfield',
 items: [
     { fieldLabel: 'Foo' },
     { fieldLabel: 'Bar' },
     { fieldLabel: 'Num', xtype: 'numberfield' }
 ]


Each member of the `items` array is now just a "configuration object". These objects
are used to create and configure component instances. A configuration object can be
manually used to instantiate a component using Ext.widget:

 var text1 = Ext.create('Ext.form.field.Text', {
     fieldLabel: 'Foo'
 });

 // or alternatively:

 var text1 = Ext.widget({
     xtype: 'textfield',
     fieldLabel: 'Foo'
 });


This conversion of configuration objects into instantiated components is done when
a container is created as part of its {Ext.container.AbstractContainer.initComponent}
process. As part of the same process, the `items` array is converted from its raw
array form into a Ext.util.MixedCollection instance.

You can define your own `xtype` on a custom component by specifying
the `xtype` property in Ext.define. For example:

Ext.define('MyApp.PressMeButton', {
    extend: 'Ext.button.Button',
    xtype: 'pressmebutton',
    text: 'Press Me'
});


Care should be taken when naming an `xtype` in a custom component because there is
a single, shared scope for all xtypes. Third part components should consider using
a prefix to avoid collisions.

Ext.define('Foo.form.CoolButton', {
    extend: 'Ext.button.Button',
    xtype: 'ux-coolbutton',
    text: 'Cool!'
});


See Ext.enums.Widget for list of all available xtypes.
        Available since: 2.3.0


### $className

**Tipo:** String

...

Defaults to: `'Ext.Base'`


### _alignRe

**Tipo:** RegExp

...

Defaults to: `/^([a-z]+)-([a-z]+)(\?)?$/`


### _isLayoutRoot

**Tipo:** Boolean

Setting this property to true causes the isLayoutRoot method to return
true and stop the search for the top-most comp...

Setting this property to `true` causes the isLayoutRoot method to return
`true` and stop the search for the top-most component for a layout.
Defaults to: `false`


### _positionTopLeft

**Tipo:** Array

...

Defaults to: `['position', 'top', 'left']`


### _triggerRegion

**Tipo:** Object

A reusable object used by getTriggerRegion to avoid excessive object creation. ...

A reusable object used by getTriggerRegion to avoid excessive object creation.
Defaults to: `{}`


### allowDomMove

**Tipo:** Boolean

...

Defaults to: `true`


### allowedScales

**Tipo:** Array

An array of allowed scales. ...

An array of allowed scales.
Defaults to: `['small', 'medium', 'large']`


### autoGenId

**Tipo:** Boolean

true indicates an id was auto-generated rather than provided by configuration. ...

`true` indicates an `id` was auto-generated rather than provided by configuration.
Defaults to: `false`


### borderBoxCls

**Tipo:** String

private ...

private
Defaults to: `Ext.baseCSSPrefix + 'border-box'`


### bubbleEvents

**Tipo:** Array

...

Defaults to: `[]`


### childEls

**Tipo:** Array

...

Defaults to: `[]`


### componentLayoutCounter

**Tipo:** Number

The number of component layout calls made on this object. ...

The number of component layout calls made on this object.
Defaults to: `0`


### configMap

**Tipo:** Object

...

Defaults to: `{}`


### contentPaddingProperty

**Tipo:** String

The name of the padding property that is used by the layout to manage
padding. ...

The name of the padding property that is used by the layout to manage
padding.  See managePadding
Defaults to: `'padding'`


### convertPositionSpec

**Tipo:** Object

By default this method does nothing but return the position spec passed to it. ...

By default this method does nothing but return the position spec passed to it. In
rtl mode it is overridden to convert "l" to "r" and vice versa when required.


### defaultComponentLayoutType

**Tipo:** String

...

Defaults to: `'autocomponent'`


### deferLayouts

**Tipo:** Boolean

...

Defaults to: `false`


### disabled

**Tipo:** Boolean

True if this button is disabled. ...

True if this button is disabled.
Defaults to: `false`


### draggable

**Tipo:** Boolean

Indicates whether or not the component can be dragged. ...

Indicates whether or not the component can be dragged.
Defaults to: `false`


### eventsSuspended

**Tipo:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called.
Defaults to: `0`


### floatParent

**Tipo:** Ext.Container

Only present for floating Components which were inserted as child items of Containers. ...

**Only present for floating Components which were inserted as child items of Containers.**

There are other similar relationships such as the button which activates a menu, or the
menu item which activated a submenu, or the
column header which activated the column menu.

These differences are abstracted away by the up method.

Floating Components that are programatically rendered will not have a `floatParent`
property.

See floating and zIndexManager


### frameCls

**Tipo:** String

...

Defaults to: `Ext.baseCSSPrefix + 'frame'`


### frameElNames

**Tipo:** Array

...

Defaults to: `['TL', 'TC', 'TR', 'ML', 'MC', 'MR', 'BL', 'BC', 'BR']`


### frameElementsArray

**Tipo:** Array

...

Defaults to: `['tl', 'tc', 'tr', 'ml', 'mc', 'mr', 'bl', 'bc', 'br']`


### frameIdRegex

**Tipo:** RegExp

...

Defaults to: `/[\-]frame\d+[TMB][LCR]$/`


### frameInfoCache

**Tipo:** Object

Cache the frame information object so as not to cause style recalculations ...

Cache the frame information object so as not to cause style recalculations
Defaults to: `{}`


### frameSize

**Tipo:** Object

Indicates the width of any framing elements which were added within the encapsulating
element to provide graphical, r...

Indicates the width of any framing elements which were added within the encapsulating
element to provide graphical, rounded borders. See the frame config. This
property is `null` if the component is not framed.

This is an object containing the frame width in pixels for all four sides of the
Component containing the following properties:
top : Number (optional)The width of the top framing element in pixels.
Defaults to: `0`


### frameTableTpl

**Tipo:** Object


### frameTpl

**Tipo:** Array

...

Defaults to: `['{%this.renderDockedItems(out,values,0);%}', '<tpl if="top">', '<tpl if="left"><div id="{fgid}TL" class="{frameCls}-tl {baseCls}-tl {baseCls}-{ui}-tl<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-tl</tpl>{frameElCls}" role="presentation"></tpl>', '<tpl if="right"><div id="{fgid}TR" class="{frameCls}-tr {baseCls}-tr {baseCls}-{ui}-tr<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-tr</tpl>{frameElCls}" role="presentation"></tpl>', '<div id="{fgid}TC" class="{frameCls}-tc {baseCls}-tc {baseCls}-{ui}-tc<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-tc</tpl>{frameElCls}" role="presentation"></div>', '<tpl if="right"></div></tpl>', '<tpl if="left"></div></tpl>', '</tpl>', '<tpl if="left"><div id="{fgid}ML" class="{frameCls}-ml {baseCls}-ml {baseCls}-{ui}-ml<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-ml</tpl>{frameElCls}" role="presentation"></tpl>', '<tpl if="right"><div id="{fgid}MR" class="{frameCls}-mr {baseCls}-mr {baseCls}-{ui}-mr<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-mr</tpl>{frameElCls}" role="presentation"></tpl>', '<div id="{fgid}MC" class="{frameCls}-mc {baseCls}-mc {baseCls}-{ui}-mc<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-mc</tpl>{frameElCls}" role="presentation">', '{%this.applyRenderTpl(out, values)%}', '</div>', '<tpl if="right"></div></tpl>', '<tpl if="left"></div></tpl>', '<tpl if="bottom">', '<tpl if="left"><div id="{fgid}BL" class="{frameCls}-bl {baseCls}-bl {baseCls}-{ui}-bl<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-bl</tpl>{frameElCls}" role="presentation"></tpl>', '<tpl if="right"><div id="{fgid}BR" class="{frameCls}-br {baseCls}-br {baseCls}-{ui}-br<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-br</tpl>{frameElCls}" role="presentation"></tpl>', '<div id="{fgid}BC" class="{frameCls}-bc {baseCls}-bc {baseCls}-{ui}-bc<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-bc</tpl>{frameElCls}" role="presentation"></div>', '<tpl if="right"></div></tpl>', '<tpl if="left"></div></tpl>', '</tpl>', '{%this.renderDockedItems(out,values,1);%}']`


### hasListeners

**Tipo:** Object

This object holds a key for any event that has a listener. ...

This object holds a key for any event that has a listener. The listener may be set
directly on the instance, or on its class or a super class (via observe) or
on the MVC EventBus. The values of this object are truthy
(a non-zero number) and falsy (0 or undefined). They do not represent an exact count
of listeners. The value for an event is truthy if the event must be fired and is
falsy if there is no need to fire the event.

The intended use of this property is to avoid the expense of fireEvent calls when
there are no listeners. This can be particularly helpful when one would otherwise
have to call fireEvent hundreds or thousands of times. It is used like this:

 if (this.hasListeners.foo) {
     this.fireEvent('foo', this, arg1);
 }


### hidden

**Tipo:** Boolean

True if this button is hidden. ...

True if this button is hidden.
Defaults to: `false`


### horizontalPosProp

**Tipo:** String

...

Defaults to: `'left'`


### initConfigList

**Tipo:** Array

...

Defaults to: `[]`


### initConfigMap

**Tipo:** Object

...

Defaults to: `{}`


### isAction

**Tipo:** Boolean

`true` in this class to identify an object as an instantiated Button, or subclass thereof.


### isAnimate

**Tipo:** Boolean

...

Defaults to: `true`


### isComponent

**Tipo:** Boolean

true in this class to identify an object as an instantiated Component, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Component, or subclass thereof.
Defaults to: `true`


### isInstance

**Tipo:** Boolean

...

Defaults to: `true`


### isObservable

**Tipo:** Boolean

true in this class to identify an object as an instantiated Observable, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Observable, or subclass thereof.
Defaults to: `true`


### isQueryable

**Tipo:** Boolean

...

Defaults to: `true`


### layoutSuspendCount

**Tipo:** Number

...

Defaults to: `0`


### maskOnDisable

**Tipo:** Boolean

This is an internal flag that you use when creating custom components. ...

This is an internal flag that you use when creating custom components. By default this is set to `true` which means
that every component gets a mask when it's disabled. Components like FieldContainer, FieldSet, Field, Button, Tab
override this property to `false` since they want to implement custom disable logic.
Defaults to: `true`


### menu

**Tipo:** Ext.menu.Menu

The Menu object associated with this Button when configured with the menu config
option.


### offsetsCls

**Tipo:** String

...

Defaults to: `Ext.baseCSSPrefix + 'hide-offsets'`


### ownerCt

**Tipo:** Ext.Container

This Component's owner Container (is set automatically
when this Component is added to a Container). ...

This Component's owner Container (is set automatically
when this Component is added to a Container).

*Important.* This is not a universal upwards navigation pointer. It indicates the Container which owns and manages
this Component if any. There are other similar relationships such as the button which activates a menu, or the
menu item which activated a submenu, or the
column header which activated the column menu.

These differences are abstracted away by the up method.

**Note**: to access items within the Container see itemId.
        Available since: 2.3.0


### pressed

**Tipo:** Boolean

True if this button is pressed (only if enableToggle = true). ...

True if this button is pressed (only if enableToggle = true).
Defaults to: `false`


### rendered

**Tipo:** Boolean

Indicates whether or not the component has been rendered. ...

Indicates whether or not the component has been rendered.
Defaults to: `false`        Available since: 1.1.0


### scrollFlags

**Tipo:** Object

An object property which provides unified information as to which dimensions are scrollable based upon
the autoScroll...

An object property which provides unified information as to which dimensions are scrollable based upon
the autoScroll, overflowX and overflowY settings (And for *views* of trees and grids, the owning panel's scroll setting).

Note that if you set overflow styles using the style config or bodyStyle config, this object does not include that information;
it is best to use autoScroll, overflowX and overflowY if you need to access these flags.

This object has the following properties:
x : Boolean`true` if this Component is scrollable horizontally - style setting may be `'auto'` or `'scroll'`.


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


### split

**Tipo:** Boolean

...

Defaults to: `true`


### template

**Tipo:** Ext.Template

A Template used to create the Button's DOM structure. ...

A Template used to create the Button's DOM structure.

Instances, or subclasses which need a different DOM structure may provide a different template layout in
conjunction with an implementation of getTemplateArgs.


### weight

**Tipo:** Number

...

Defaults to: `0`


### zIndexManager

**Tipo:** Ext.ZIndexManager

Only present for floating Components after they have been rendered. ...

Only present for floating Components after they have been rendered.

A reference to the ZIndexManager which is managing this Component's z-index.

The ZIndexManager maintains a stack of floating Component z-indices, and also provides
a single modal mask which is insert just beneath the topmost visible modal floating Component.

Floating Components may be brought to the front or sent to the back of the
z-index stack.

This defaults to the global ZIndexManager for floating Components that are
programatically rendered.

For floating Components which are added to a Container, the ZIndexManager is acquired from the first
ancestor Container found which is floating. If no floating ancestor is found, the global ZIndexManager is
used.

See floating and zIndexParent


### zIndexParent

**Tipo:** Ext.Container

Only present for floating Components which were inserted as child items of Containers, and which have a floating
Cont...

Only present for floating Components which were inserted as child items of Containers, and which have a floating
Container in their containment ancestry.

For floating Components which are child items of a Container, the zIndexParent will be a floating
ancestor Container which is responsible for the base z-index value of all its floating descendants. It provides
a ZIndexManager which provides z-indexing services for all its descendant floating
Components.

Floating Components that are programatically rendered will not have a `zIndexParent`
property.

For example, the dropdown BoundList of a ComboBox which is in a Window will have the
Window as its `zIndexParent`, and will always show above that Window, wherever the Window is placed in the z-index stack.

See floating and zIndexManager


### $onExtended

**Tipo:** Array

...

Defaults to: `[]`


### Ext.button.Split

Creates new Component. ...

Creates new Component.
Parametersconfig : Ext.Element/String/ObjectThe configuration options may be specified as either:





**an element** : it is set as the internal element and its id used as the component id
**a string** : it is assumed to be the id of an existing element and is used as the component id
**anything else** : it is assumed to be a standard config object and is applied to the component


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### addClass

Adds a CSS class to the top level element representing this component. ...

Adds a CSS class to the top level element representing this component.
        
        This method has been **deprecated** since 4.1
        Use addCls instead.


### addCls

Adds a CSS class to the top level element representing this component. ...

Adds a CSS class to the top level element representing this component.
Parameterscls : String/String[]The CSS class name to add.


### addClsWithUI

Adds a cls to the uiCls array, which will also call addUIClsToElement and adds to all elements of this
component. ...

Adds a `cls` to the `uiCls` array, which will also call addUIClsToElement and adds to all elements of this
component.
Parametersclasses : String/String[]A string or an array of strings to add to the `uiCls`.


### addEvents

Adds the specified events to the list of events which this Observable may fire. ...

Adds the specified events to the list of events which this Observable may fire.
ParameterseventNames : Object/String...Either an object with event names as properties with
a value of `true`. For example:

this.addEvents({
    storeloaded: true,
    storecleared: true
});


Or any number of event names as separate parameters. For example:

this.addEvents('storeloaded', 'storecleared');


### addFocusListener

Sets up the focus listener on this Component's focusEl if it has one. ...

Sets up the focus listener on this Component's focusEl if it has one.

Form Components which must implicitly participate in tabbing order usually have a naturally focusable
element as their focusEl, and it is the DOM event of that receiving focus which drives
the Component's `onFocus` handling, and the DOM event of it being blurred which drives the `onBlur` handling.

If the focusEl is **not** naturally focusable, then the listeners are only added
if the FocusManager is enabled.


### addListener

Appends an event handler to this object. ...

Appends an event handler to this object.  For example:

myGridPanel.on("mouseover", this.onMouseOver, this);


The method also allows for a single argument to be passed which is a config object
containing properties which specify multiple events. For example:

myGridPanel.on({
    cellClick: this.onCellClick,
    mouseover: this.onMouseOver,
    mouseout: this.onMouseOut,
    scope: this // Important. Ensure "this" is correct during handler execution
});


One can also specify options for each event handler separately:

myGridPanel.on({
    cellClick: {fn: this.onCellClick, scope: this, single: true},
    mouseover: {fn: panel.onMouseOver, scope: panel}
});


*Names* of methods in a specified scope may also be used. Note that
`scope` MUST be specified to use this option:

myGridPanel.on({
    cellClick: {fn: 'onCellClick', scope: this, single: true},
    mouseover: {fn: 'onMouseOver', scope: panel}
});

ParameterseventName : String/ObjectThe name of the event to listen for.
May also be an object who's property names are event names.


### addManagedListener

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destr...

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destroyed.
Parametersitem : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### addOverCls

...

Overrides: Ext.AbstractComponent.addOverCls


### addPlugin

Adds a plugin. ...

Adds a plugin. May be called at any time in the component's lifecycle.
Parametersplugin : Object


### addPropertyToState

Save a property to the given state object if it is not its default or configured
value. ...

Save a property to the given state object if it is not its default or configured
value.
Parametersstate : ObjectThe state object.


### addStateEvents

Add events that will trigger the state to be saved. ...

Add events that will trigger the state to be saved. If the first argument is an
array, each element of that array is the name of a state event. Otherwise, each
argument passed to this method is the name of a state event.
Parametersevents : String/String[]The event name or an array of event names.


### addUIClsToElement

Method which adds a specified UI + uiCls to the components element. ...

Method which adds a specified UI + `uiCls` to the components element. Can be overridden to remove the UI from more
than just the components element.
Parametersui : StringThe UI to remove from the element.


### addUIToElement

Method which adds a specified UI to the components element. ...

Method which adds a specified UI to the components element.


### adjustForConstraints

private ==>  used outside of core
TODO: currently only used by ToolTip. ...

private ==>  used outside of core
TODO: currently only used by ToolTip. does this method belong here?
Parametersxy : Object


### adjustPosition

...

Parametersx : Object


### afterComponentLayout

Called by the layout system after the Component has been laid out. ...

Called by the layout system after the Component has been laid out.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### afterFirstLayout

...

Parameterswidth : Object


### afterHide

Invoked after the Component has been hidden. ...

Invoked after the Component has been hidden.

Gets passed the same `callback` and `scope` parameters that onHide received.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### afterRender

Allows addition of behavior after rendering is complete. ...

Allows addition of behavior after rendering is complete. At this stage the Component’s Element
will have been styled according to the configuration, will have had any configured CSS class
names added, and will be in the configured visibility and the configured enable state.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### afterSetPosition

Template method called after a Component has been positioned. ...

Template method called after a Component has been positioned.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### afterShow

Invoked after the Component is shown (after onShow is called). ...

Invoked after the Component is shown (after onShow is called).

Gets passed the same parameters as show.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### alignTo

Aligns the element with another element relative to the specified anchor points. ...

Aligns the element with another element relative to the specified anchor points. If
the other element is the document it aligns it to the viewport. The position
parameter is optional, and can be specified in any one of the following formats:


**Blank**: Defaults to aligning the element's top-left corner to the target's
bottom-left corner ("tl-bl").
**One anchor (deprecated)**: The passed anchor position is used as the target
element's anchor point.  The element being aligned will position its top-left
corner (tl) to that point. This method has been deprecated in favor of the newer
two anchor syntax below.
**Two anchors**: If two values from the table below are passed separated by a dash,
the first value is used as the element's anchor point, and the second value is
used as the target's anchor point.



In addition to the anchor points, the position parameter also supports the "?"
character. If "?" is passed at the end of the position string, the element will
attempt to align as specified, but the position will be adjusted to constrain to
the viewport if necessary. Note that the element being aligned might be swapped to
align to a different position than that specified in order to enforce the viewport
constraints. Following are all of the supported anchor positions:

Value  Description
-----  -----------------------------
tl     The top left corner (default)
t      The center of the top edge
tr     The top right corner
l      The center of the left edge
c      In the center of the element
r      The center of the right edge
bl     The bottom left corner
b      The center of the bottom edge
br     The bottom right corner



Example Usage:

// align el to other-el using the default positioning
// ("tl-bl", non-constrained)
el.alignTo("other-el");

// align the top left corner of el with the top right corner of other-el
// (constrained to viewport)
el.alignTo("other-el", "tr?");

// align the bottom right corner of el with the center left edge of other-el
el.alignTo("other-el", "br-l?");

// align the center of el with the bottom left corner of other-el and
// adjust the x position by -6 pixels (and the y position by 0)
el.alignTo("other-el", "c-bl", [-6, 0]);

Parameterselement : Ext.util.Positionable/HTMLElement/StringThe Positionable,
HTMLElement, or id of the element to align to.


### anchorTo

Anchors an element to another element and realigns it when the window is resized. ...

Anchors an element to another element and realigns it when the window is resized.
Parameterselement : Ext.util.Positionable/HTMLElement/StringThe Positionable,
HTMLElement, or id of the element to align to.


### anim

process the passed fx configuration. ...

process the passed fx configuration.


Parametersconfig : Object


### animate

Performs custom animation on this object. ...

Performs custom animation on this object.

This method is applicable to both the Component class and the Sprite
class. It performs animated transitions of certain properties of this object over a specified timeline.

Animating a Component

When animating a Component, the following properties may be specified in `from`, `to`, and `keyframe` objects:


`x` - The Component's page X position in pixels.
`y` - The Component's page Y position in pixels
`left` - The Component's `left` value in pixels.
`top` - The Component's `top` value in pixels.
`width` - The Component's `width` value in pixels.
`height` - The Component's `height` value in pixels.
`dynamic` - Specify as true to update the Component's layout (if it is a Container) at every frame of the animation.
*Use sparingly as laying out on every intermediate size change is an expensive operation.*



For example, to animate a Window to a new size, ensuring that its internal layout and any shadow is correct:

myWindow = Ext.create('Ext.window.Window', {
    title: 'Test Component animation',
    width: 500,
    height: 300,
    layout: {
        type: 'hbox',
        align: 'stretch'
    },
    items: [{
        title: 'Left: 33%',
        margins: '5 0 5 5',
        flex: 1
    }, {
        title: 'Left: 66%',
        margins: '5 5 5 5',
        flex: 2
    }]
});
myWindow.show();
myWindow.header.el.on('click', function() {
    myWindow.animate({
        to: {
            width: (myWindow.getWidth() == 500) ? 700 : 500,
            height: (myWindow.getHeight() == 300) ? 400 : 300
        }
    });
});


For performance reasons, by default, the internal layout is only updated when the Window reaches its final `"to"`
size. If dynamic updating of the Window's child Components is required, then configure the animation with
`dynamic: true` and the two child items will maintain their proportions during the animation.
Parametersconfig : ObjectConfiguration for Ext.fx.Anim.
Note that the to config is required.


### applyChildEls

Sets references to elements inside the component. ...

Sets references to elements inside the component.
Parametersel : Object


### applyRenderSelectors

Sets references to elements inside the component. ...

Sets references to elements inside the component. This applies renderSelectors
as well as childEls.


### applyState

Applies the state to the object. ...

Applies the state to the object. This should be overridden in subclasses to do
more complex state operations. By default it applies the state properties onto
the current object.
Parametersstate : ObjectThe state


### beforeBlur

Template method to do any pre-blur processing. ...

Template method to do any pre-blur processing.
Parameterse : Ext.EventObjectThe event object


### beforeComponentLayout

Occurs before componentLayout is run. ...

Occurs before `componentLayout` is run. Returning `false` from this method will prevent the `componentLayout` from
being executed.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### beforeDestroy

Invoked before the Component is destroyed. ...

Invoked before the Component is destroyed.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### beforeFocus

Template method to do any pre-focus processing. ...

Template method to do any pre-focus processing.
Parameterse : Ext.EventObjectThe event object


### beforeLayout

Occurs before componentLayout is run. ...

Occurs before componentLayout is run. In previous releases, this method could
return `false` to prevent its layout but that is not supported in Ext JS 4.1 or
higher. This method is simply a notification of the impending layout to give the
component a chance to adjust the DOM. Ideally, DOM reads should be avoided at this
time to reduce expensive document reflows.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### beforeRender

...

Overrides: Ext.Component.beforeRender


### beforeSetPosition

Template method called before a Component is positioned. ...

Template method called before a Component is positioned.

Ensures that the position is adjusted so that the Component is constrained if so configured.
Parametersx : Object


### beforeShow

Invoked before the Component is shown. ...

Invoked before the Component is shown.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### blur

...

ReturnsExt.Componentthis


### bubble

Bubbles up the component/container heirarchy, calling the specified function with each component. ...

Bubbles up the component/container heirarchy, calling the specified function with each component. The scope
(*this*) of function call will be the scope provided or the current component. The arguments to the function will
be the args provided or the current component. If the function returns false at any point, the bubble is stopped.
Parametersfn : FunctionThe function to call


### calculateAnchorXY

Calculates x,y coordinates specified by the anchor position on the element, adding
extraX and extraY values. ...

Calculates x,y coordinates specified by the anchor position on the element, adding
extraX and extraY values.
Parametersanchor : String (optional)The specified anchor position.
See alignTo for details on supported anchor positions.
Defaults to: `'tl'`


### calculateConstrainedPosition

Calculates the new [x,y] position to move this Positionable into a constrain region. ...

Calculates the new [x,y] position to move this Positionable into a constrain region.

By default, this Positionable is constrained to be within the container it was added to, or the element it was
rendered to.

Priority is given to constraining the top and left within the constraint.

An alternative constraint may be passed.
ParametersconstrainTo : String/HTMLElement/Ext.Element/Ext.util.Region (optional)The Element or Region
into which this Component is to be constrained. Defaults to the element into which this Positionable
was rendered, or this Component's {@link Ext.Component.constrainTo.


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


### cancelFocus

Cancel any deferred focus on this component ...

Cancel any deferred focus on this component


### captureArgs

...

Parameterso : Object


### center

Center this Component in its container. ...

Center this Component in its container.
ReturnsExt.Componentthis


### child

Retrieves the first direct child of this container which matches the passed selector or component. ...

Retrieves the first direct child of this container which matches the passed selector or component.
The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.
Parametersselector : String/Ext.Component (optional)An Ext.ComponentQuery selector. If no selector is
specified, the first child will be returned.


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### clearTip

...


### cloneConfig

Clone the current component using the original config values passed into this instance by default. ...

Clone the current component using the original config values passed into this instance by default.
Parametersoverrides : ObjectA new config containing any properties to override in the cloned version.
An id property can be passed on this object, otherwise one will be generated to avoid duplicates.


### configClass

...


### constructPlugin

...

Parametersptype : String/Objectstring or config object containing a ptype property.

Constructs a plugin according to the passed config object/ptype string.

Ensures that the constructed plugin always has a `cmp` reference back to this component.
The setting up of this is done in PluginManager. The PluginManager ensures that a reference to this
component is passed to the constructor. It also ensures that the plugin's `setCmp` method (if any) is called.


### constructPlugins

Returns an array of fully constructed plugin instances. ...

Returns an array of fully constructed plugin instances. This converts any configs into their
appropriate instances.

It does not mutate the plugins array. It creates a new array.


### continueFireEvent

Continue to fire event. ...

Continue to fire event.
ParameterseventName : String


### convertPositionSpec

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**
ParametersposSpec : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.
ParametersnewName : StringThe name under which to refire the passed parameters.


### deleteMembers

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### didIconStateChange

Checks if the icon/iconCls changed from being empty to having a value, or having a value to being empty. ...

Checks if the icon/iconCls changed from being empty to having a value, or having a value to being empty.
Parametersold : StringThe old icon/iconCls


### disable

inherit docs

Disable the component. ...

inherit docs

Disable the component.
        Available since: 1.1.0
Parameterssilent : Boolean (optional)Passing `true` will suppress the `disable` event from being fired.
Defaults to: `false`


### doApplyRenderTpl

Called from the selected frame generation template to insert this Component's inner structure inside the framing stru...

Called from the selected frame generation template to insert this Component's inner structure inside the framing structure.

When framing is used, a selected frame generation template is used as the primary template of the getElConfig instead
of the configured renderTpl. The renderTpl is invoked by this method which is injected into the framing template.
Parametersout : Object


### doAutoRender

Handles autoRender. ...

Handles autoRender.
Floating Components may have an ownerCt. If they are asking to be constrained, constrain them within that
ownerCt, and have their z-index managed locally. Floating Components are always rendered to document.body


### doComponentLayout

This method needs to be called whenever you change something on this component that requires the Component's
layout t...

This method needs to be called whenever you change something on this component that requires the Component's
layout to be recalculated.
ReturnsExt.container.Containerthis


### doConstrain

Moves this floating Component into a constrain region. ...

Moves this floating Component into a constrain region.

By default, this Component is constrained to be within the container it was added to, or the element it was
rendered to.

An alternative constraint may be passed.
ParametersconstrainTo : String/HTMLElement/Ext.Element/Ext.util.Region (optional)The Element or Region
into which this Component is to be constrained. Defaults to the element into which this floating Component
was rendered.


### doRenderContent

...

Parametersout : Object


### doRenderFramingDockedItems

...

Parametersout : Object


### doToggle

...


### down

Retrieves the first descendant of this container which matches the passed selector. ...

Retrieves the first descendant of this container which matches the passed selector.
The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.
Parametersselector : String/Ext.Component (optional)An Ext.ComponentQuery selector or Ext.Component. If no selector is
specified, the first child will be returned.


### enable

inherit docs

Enable the component ...

inherit docs

Enable the component
        Available since: 1.1.0
Parameterssilent : Boolean (optional)Passing `true` will suppress the `enable` event from being fired.
Defaults to: `false`


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if
present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if
present. There is no implementation in the Observable base class.

This is commonly used by Ext.Components to bubble events to owner Containers.
See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the
Component's immediate owner. But if a known target is required, this can be overridden to access the
required target more quickly.

Example:

Ext.define('Ext.overrides.form.field.Base', {
    override: 'Ext.form.field.Base',

    //  Add functionality to Field's initComponent to enable the change event to bubble
    initComponent: function () {
        this.callParent();
        this.enableBubble('change');
    }
});

var myForm = Ext.create('Ext.form.Panel', {
    title: 'User Details',
    items: [{
        ...
    }],
    listeners: {
        change: function() {
            // Title goes red if form has been modified.
            myForm.header.setStyle('color', 'red');
        }
    }
});

ParameterseventNames : String/String[]The event name to bubble, or an Array of event names.


### ensureAttachedToBody

Ensures that this component is attached to document.body. ...

Ensures that this component is attached to `document.body`. If the component was
rendered to Ext.getDetachedBody, then it will be appended to `document.body`.
Any configured position is also restored.
ParametersrunLayout : Boolean (optional)True to run the component's layout.
Defaults to: `false`


### findParentBy

Find a container above this component at any level by a custom function. ...

Find a container above this component at any level by a custom function. If the passed function returns true, the
container will be returned.

See also the up method.
Parametersfn : FunctionThe custom function to call with the arguments (container, this component).


### findParentByType

Find a container above this component at any level by xtype or class

See also the up method. ...

Find a container above this component at any level by xtype or class

See also the up method.
Parametersxtype : String/Ext.ClassThe xtype string for a component, or the class of the component directly


### findPlugin

Retrieves plugin from this component's collection by its ptype. ...

Retrieves plugin from this component's collection by its `ptype`.
Parametersptype : StringThe Plugin's ptype as specified by the class's `alias` configuration.


### finishRender

This method visits the rendered component tree in a "top-down" order. ...

This method visits the rendered component tree in a "top-down" order. That is, this
code runs on a parent component before running on a child. This method calls the
onRender method of each component.
ParameterscontainerIdx : NumberThe index into the Container items of this Component.


### finishRenderChildren

...


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed
to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed
to addListener).

An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by
calling enableBubble.
ParameterseventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list.

An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by
calling enableBubble.
ParameterseventName : StringThe name of the event to fire.


### fireHandler

...

Parameterse : Object


### fireHierarchyEvent

For more information on the hierarchy events, see the note for the
hierarchyEventSource observer defined in the onCla...

For more information on the hierarchy events, see the note for the
hierarchyEventSource observer defined in the onClassCreated callback.

This functionality is contained in Component (as opposed to Container)
because a Component can be the ownerCt for a floating component (loadmask),
and the loadmask needs to know when its owner is shown/hidden via the
hierarchyEventSource so that its hidden state can be synchronized.

TODO: merge this functionality with Ext.globalEvents
Parametersename : Object


### fitContainer

...

Parametersanimate : Object


### focus

Try to focus this component. ...

Try to focus this component.
ParametersselectText : Boolean (optional)If applicable, true to also select the text in this component


### forceComponentLayout

Forces this component to redo its componentLayout. ...

Forces this component to redo its componentLayout.
        
        This method has been **deprecated** since 4.1.0
        Use updateLayout instead.


### getActionEl

inherit docs ...

inherit docs
Overrides: Ext.Component.getActionEl


### getActiveAnimation

Returns the current animation if this object has any effects actively running or queued, else returns false. ...

Returns the current animation if this object has any effects actively running or queued, else returns false.
ReturnsExt.fx.Anim/BooleanAnim if element has active effects, else false


### getAlignToXY

Gets the x,y coordinates to align this element with another element. ...

Gets the x,y coordinates to align this element with another element. See
alignTo for more info on the supported position values.
Parameterselement : Ext.util.Positionable/HTMLElement/StringThe Positionable,
HTMLElement, or id of the element to align to.


### getAnchor

private ...

private


### getAnchorToXY

Begin Positionable methods



Overridden in Ext.rtl.AbstractComponent. ...

Begin Positionable methods



**Overridden in Ext.rtl.AbstractComponent.**

Gets the x,y coordinates of an element specified by the anchor position on the
element.
Parametersel : Ext.dom.ElementThe element


### getAnchorXY

Gets the x,y coordinates specified by the anchor position on the element. ...

Gets the x,y coordinates specified by the anchor position on the element.
Parametersanchor : String (optional)The specified anchor position.
See alignTo for details on supported anchor positions.
Defaults to: `'tl'`


### getAnimateTarget

...

Parameterstarget : Object


### getAutoId

...


### getBorderPadding

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Returns the size of the element's borders and padding.
ReturnsObjectan object with the following numeric properties
- beforeX
- afterX
- beforeY
- afterY


### getBox

Return an object defining the area of this Element which can be passed to
setBox to set another Element's size/locati...

Return an object defining the area of this Element which can be passed to
setBox to set another Element's size/location to match this element.
ParameterscontentBox : Boolean (optional)If true a box for the content of the element is
returned.


### getBtnWrapFrameWidth

...

Parametersside : Object


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable
ReturnsExt.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getBubbleTarget

Implements an upward event bubbling policy. ...

Implements an upward event bubbling policy. By default a Component bubbles events up to its reference owner.

Component subclasses may implement a different bubbling strategy by overriding this method.
Overrides: Ext.AbstractComponent.getBubbleTarget


### getChildEls

...


### getClassChildEls

...

Parameterscls : Object


### getComponentCls

...


### getComponentLayout

...


### getConfig

...

Parametersname : Object


### getConstrainVector

Returns the [X, Y] vector by which this Positionable's element must be translated to make a best
attempt to constrain...

Returns the `[X, Y]` vector by which this Positionable's element must be translated to make a best
attempt to constrain within the passed constraint. Returns `false` if the element
does not need to be moved.

Priority is given to constraining the top and left within the constraint.

The constraint may either be an existing element into which the element is to be
constrained, or a Region into which this element is to be
constrained.

By default, any extra shadow around the element is **not** included in the constrain calculations - the edges
of the element are used as the element bounds. To constrain the shadow within the constrain region, set the
`constrainShadow` property on this element to `true`.
ParametersconstrainTo : Ext.util.Positionable/HTMLElement/String/Ext.util.Region (optional)The
Positionable, HTMLElement, element id, or Region into which the element is to be
constrained.


### getContentTarget

...


### getDragEl

...


### getEl

Retrieves the top level element representing this component. ...

Retrieves the top level element representing this component.
        Available since: 1.1.0
ReturnsExt.dom.Element


### getElConfig

...


### getFocusEl

inherit docs

Returns the focus holder element associated with this Component. ...

inherit docs

Returns the focus holder element associated with this Component. At the Component base class level, this function returns `undefined`.

Subclasses which use embedded focusable elements (such as Window, Field and Button) should override this
for use by the focus method.

Containers which need to participate in the FocusManager's navigation and Container focusing scheme also
need to return a `focusEl`, although focus is only listened for in this case if the FocusManager is enabled.
Overrides: Ext.AbstractComponent.getFocusEl


### getFrameInfo

On render, reads an encoded style attribute, "filter" from the style of this Component's element. ...

On render, reads an encoded style attribute, "filter" from the style of this Component's element.
This information is memoized based upon the CSS class name of this Component's element.
Because child Components are rendered as textual HTML as part of the topmost Container, a dummy div is inserted
into the document to receive the document element's CSS class name, and therefore style attributes.


### getFrameRenderData

...


### getFrameTpl

...

Parameterstable : Object


### getFramingInfoCls

...


### getHeight

Gets the current height of the component's underlying element. ...

Gets the current height of the component's underlying element.
ReturnsNumber


### getHierarchyState

A component's hierarchyState is used to keep track of aspects of a component's
state that affect its descendants hier...

A component's hierarchyState is used to keep track of aspects of a component's
state that affect its descendants hierarchically like "collapsed" and "hidden".
For example, if this.hierarchyState.hidden == true, it means that either this
component, or one of its ancestors is hidden.

Hierarchical state management is implemented by chaining each component's
hierarchyState property to its parent container's hierarchyState property via the
prototype. The result is such that if a component's hierarchyState does not have
it's own property, it inherits the property from the nearest ancestor that does.

To set a hierarchical "hidden" value:

this.getHierarchyState().hidden = true;


It is important to remember when unsetting hierarchyState properties to delete
them instead of just setting them to a falsy value.  This ensures that the
hierarchyState returns to a state of inheriting the value instead of overriding it
To unset the hierarchical "hidden" value:

delete this.getHierarchyState().hidden;


IMPORTANT! ALWAYS access hierarchyState using this method, not by accessing
this.hierarchyState directly.  The hierarchyState property does not exist until
the first time getHierarchyState() is called.  At that point getHierarchyState()
walks up the component tree to establish the hierarchyState prototype chain.
Additionally the hierarchyState property should NOT be relied upon even after
the initial call to getHierarchyState() because  it is possible for the
hierarchyState to be invalidated. Invalidation typically happens when a component
is moved to a new container. In such a case the hierarchy state remains invalid
until the next time getHierarchyState() is called on the component or one of its
descendants.
Parametersinner : Object


### getHref

If there is a configured href for this Button, returns the href with parameters appended. ...

If there is a configured href for this Button, returns the href with parameters appended.
ReturnsString/BooleanThe href string with parameters appended.


### getId

Retrieves the id of this component. ...

Retrieves the `id` of this component. Will auto-generate an `id` if one has not already been set.
ReturnsString


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### getInnerCls

...


### getInsertPosition

This function takes the position argument passed to onRender and returns a
DOM element that you can use in the insert...

This function takes the position argument passed to onRender and returns a
DOM element that you can use in the insertBefore.
Parametersposition : String/Number/Ext.dom.Element/HTMLElementIndex, element id or element you want
to put this component before.


### getItemId

Returns the value of itemId assigned to this component, or when that
is not set, returns the value of id. ...

Returns the value of itemId assigned to this component, or when that
is not set, returns the value of id.
ReturnsString


### getLoader

Gets the Ext.ComponentLoader for this Component. ...

Gets the Ext.ComponentLoader for this Component.
ReturnsExt.ComponentLoaderThe loader instance, null if it doesn't exist.


### getLocalX

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Returns the x coordinate of this element reletive to its `offsetParent`.
ReturnsNumberThe local x coordinate


### getLocalXY

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Returns the x and y coordinates of this element relative to its `offsetParent`.
ReturnsNumber[]The local XY position of the element


### getLocalY

Returns the y coordinate of this element reletive to its offsetParent. ...

Returns the y coordinate of this element reletive to its `offsetParent`.
ReturnsNumberThe local y coordinate


### getMaskTarget

...


### getOffsetsTo

Returns the offsets of this element from the passed element. ...

Returns the offsets of this element from the passed element. The element must both
be part of the DOM tree and not have display:none to have page coordinates.
ParametersoffsetsTo : Ext.util.Positionable/HTMLElement/StringThe Positionable,
HTMLElement, or element id to get get the offsets from.


### getOuterSize

Include margins ...

Include margins


### getOverflowEl

Get an el for overflowing, defaults to the target el ...

Get an el for overflowing, defaults to the target el


### getOverflowStyle

Returns the CSS style object which will set the Component's scroll styles. ...

Returns the CSS style object which will set the Component's scroll styles. This must be applied
to the target element.


### getOwningBorderContainer

Returns the owning container if that container uses border layout. ...

Returns the owning container if that container uses `border` layout. Otherwise
this method returns `null`.

**Defined in override Ext.layout.container.border.Region.**
ReturnsExt.container.ContainerThe owning border container or `null`.


### getOwningBorderLayout

Returns the owning border (Ext.layout.container.Border) instance if there is
one. ...

Returns the owning `border` (`Ext.layout.container.Border`) instance if there is
one. Otherwise this method returns `null`.

**Defined in override Ext.layout.container.border.Region.**
ReturnsExt.layout.container.BorderThe owning border layout or `null`.


### getPlugin

Retrieves a plugin from this component's collection by its pluginId. ...

Retrieves a plugin from this component's collection by its `pluginId`.
ParameterspluginId : String


### getPosition

Gets the current XY position of the component's underlying element. ...

Gets the current XY position of the component's underlying element.
Parameterslocal : Boolean (optional)If true the element's left and top are returned instead of page XY.
Defaults to: `false`


### getPositionEl

Deprecate 5.0 ...

Deprecate 5.0


### getProxy

...


### getRefItems

...

Parametersdeep : Object


### getRefOwner

Used by ComponentQuery, and the up method to find the
owning Component in the linkage hierarchy. ...

Used by ComponentQuery, and the up method to find the
owning Component in the linkage hierarchy.

By default this returns the Container which contains this Component.

This may be overriden by Component authors who implement ownership hierarchies which are not
based upon ownerCt, such as BoundLists being owned by Fields or Menus being owned by Buttons.


### getRegion

Returns a region object that defines the area of this element. ...

Returns a region object that defines the area of this element.
ReturnsExt.util.RegionA Region containing "top, left, bottom, right" properties.


### getRenderTree

...


### getResizeEl

Deprecate 5.0 ...

Deprecate 5.0


### getSize

Gets the current size of the component's underlying element. ...

Gets the current size of the component's underlying element.
ReturnsObjectAn object containing the element's size `{width: (element width), height: (element height)}`


### getSizeModel

Returns an object that describes how this component's width and height are managed. ...

Returns an object that describes how this component's width and height are managed.
All of these objects are shared and should not be modified.
ParametersownerCtSizeModel : Object


### getSplitCls

...


### getState

The supplied default state gathering method for the AbstractComponent class. ...

The supplied default state gathering method for the AbstractComponent class.

This method returns dimension settings such as `flex`, `anchor`, `width` and `height` along with `collapsed`
state.

Subclasses which implement more complex state should call the superclass's implementation, and apply their state
to the result if this basic state is to be saved.

Note that Component state will only be saved if the Component has a stateId and there as a StateProvider
configured for the document.
ReturnsObject


### getStateId

Gets the state id for this object. ...

Gets the state id for this object.
ReturnsStringThe 'stateId' or the implicit 'id' specified by component configuration.


### getStyleProxy

Returns an offscreen div with the same class name as the element this is being rendered. ...

Returns an offscreen div with the same class name as the element this is being rendered.
This is because child item rendering takes place in a detached div which, being not
part of the document, has no styling.
Parameterscls : Object


### getTargetEl

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. ...

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component.


### getTemplateArgs

This method returns an object which provides substitution parameters for the XTemplate used to
create this Button's D...

This method returns an object which provides substitution parameters for the XTemplate used to
create this Button's DOM structure.

Instances or subclasses which use a different Template to create a different DOM structure may need to provide
their own implementation of this method.
ReturnsObjectSubstitution data for a Template. The default implementation which provides data for the default
template returns an Object containing the following properties:
innerCls : StringA CSS class to apply to the button's text element.


### getText

Gets the text for this Button ...

Gets the text for this Button
ReturnsStringThe button text


### getTipAttr

...


### getTpl

...

Parametersname : Object


### getTriggerRegion

Returns an object containing begin and end properties that indicate the
left/right bounds of a right trigger or the t...

Returns an object containing `begin` and `end` properties that indicate the
left/right bounds of a right trigger or the top/bottom bounds of a bottom trigger.
ReturnsObject


### getTriggerSize

Measures the size of the trigger area for menu and split buttons. ...

Measures the size of the trigger area for menu and split buttons. Will be a width for
a right-aligned trigger and a height for a bottom-aligned trigger. Cached after first measurement.


### getViewRegion

Returns the content region of this element. ...

Returns the **content** region of this element. That is the region within the borders
and padding.
ReturnsExt.util.RegionA Region containing "top, left, bottom, right" member data.


### getVisibilityEl

Deprecate 5.0 ...

Deprecate 5.0


### getWidth

Gets the current width of the component's underlying element. ...

Gets the current width of the component's underlying element.
ReturnsNumber


### getX

Gets the current X position of the DOM element based on page coordinates. ...

Gets the current X position of the DOM element based on page coordinates.
ReturnsNumberThe X position of the element


### getXType

Gets the xtype for this component as registered with Ext.ComponentManager. ...

Gets the xtype for this component as registered with Ext.ComponentManager. For a list of all available
xtypes, see the Ext.Component header. Example usage:

var t = new Ext.form.field.Text();
alert(t.getXType());  // alerts 'textfield'

ReturnsStringThe xtype


### getXTypes

Returns this Component's xtype hierarchy as a slash-delimited string. ...

Returns this Component's xtype hierarchy as a slash-delimited string. For a list of all available xtypes, see the
Ext.Component header.

If using your own subclasses, be aware that a Component must register its own xtype to participate in
determination of inherited xtypes.

Example usage:

var t = new Ext.form.field.Text();
alert(t.getXTypes());  // alerts 'component/field/textfield'

        Available since: 2.3.0
ReturnsStringThe xtype hierarchy string


### getXY

Gets the current position of the DOM element based on page coordinates. ...

Gets the current position of the DOM element based on page coordinates.
ReturnsNumber[]The XY position of the element


### getY

Gets the current Y position of the DOM element based on page coordinates. ...

Gets the current Y position of the DOM element based on page coordinates.
ReturnsNumberThe Y position of the element


### hasActiveFx

Returns the current animation if this object has any effects actively running or queued, else returns false. ...

Returns the current animation if this object has any effects actively running or queued, else returns false.
        
        This method has been **deprecated** since 4.0
        Replaced by getActiveAnimation


### hasCls

Checks if the specified CSS class exists on this element's DOM node. ...

Checks if the specified CSS class exists on this element's DOM node.
ParametersclassName : StringThe CSS class to check for.


### hasConfig

...

Parametersconfig : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer
indicates whether the event needs firing or not.
ParameterseventName : StringThe name of the event to check for


### hasUICls

Checks if there is currently a specified uiCls. ...

Checks if there is currently a specified `uiCls`.
Parameterscls : StringThe `cls` to check.


### hasVisibleMenu

Returns true if the button has a menu and it is visible ...

Returns true if the button has a menu and it is visible
ReturnsBoolean


### hide

Hides this Component, setting it to invisible using the configured hideMode. ...

Hides this Component, setting it to invisible using the configured hideMode.
ParametersanimateTarget : String/Ext.Element/Ext.Component (optional)only valid for floating Components
such as Windows or ToolTips, or regular Components which have
been configured with `floating: true`.. The target to which the Component should animate while hiding.
Defaults to: `null`


### hideMenu

Hides this button's menu (if it has one) ...

Hides this button's menu (if it has one)
ReturnsExt.button.Buttonthis


### initBorderRegion

This method is called by the Ext.layout.container.Border class when instances are
added as regions to the layout. ...

This method is called by the `Ext.layout.container.Border` class when instances are
added as regions to the layout. Since it is valid to add any component to a border
layout as a region, this method must be added to `Ext.Component` but is only ever
called when that component is owned by a `border` layout.

**Defined in override Ext.layout.container.border.Region.**


### initCls

...


### initComponent

The initComponent template method is an important initialization step for a Component. ...

The initComponent template method is an important initialization step for a Component. It is intended to be
implemented by each subclass of Ext.Component to provide any needed constructor logic. The
initComponent method of the class being created is called first, with each initComponent method
up the hierarchy to Ext.Component being called thereafter. This makes it easy to implement and,
if needed, override the constructor logic of the Component at any step in the hierarchy.

The initComponent method **must** contain a call to callParent in order
to ensure that the parent class' initComponent method is also called.

All config options passed to the constructor are applied to `this` before initComponent is called,
so you can simply access them with `this.someOption`.

The following example demonstrates using a dynamic string for the text of a button at the time of
instantiation of the class.

Ext.define('DynamicButtonText', {
    extend: 'Ext.button.Button',

    initComponent: function() {
        this.text = new Date();
        this.renderTo = Ext.getBody();
        this.callParent();
    }
});

Ext.onReady(function() {
    Ext.create('DynamicButtonText');
});

        Available since: 1.1.0
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


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


### initContainer

...

Parameterscontainer : Object


### initDraggable

...


### initEvents

Initialize any events on this component ...

Initialize any events on this component


### initFrame

...


### initFramingTpl

Poke in a reference to applyRenderTpl(frameInfo, out) ...

Poke in a reference to applyRenderTpl(frameInfo, out)
Parameterstable : Object


### initHierarchyEvents

...


### initHierarchyState

Called by getHierarchyState to initialize the hierarchyState the first
time it is requested. ...

Called by getHierarchyState to initialize the hierarchyState the first
time it is requested.

**Overridden in Ext.rtl.AbstractComponent.**
ParametershierarchyState : Object


### initPadding

Initializes padding by applying it to the target element, or if the layout manages
padding ensures that the padding o...

Initializes padding by applying it to the target element, or if the layout manages
padding ensures that the padding on the target element is "0".
ParameterstargetEl : Object


### initPlugin

...

Parametersplugin : Object


### initRenderData

Initialized the renderData to be used when rendering the renderTpl. ...

Initialized the renderData to be used when rendering the renderTpl.
ReturnsObjectObject with keys and values that are going to be applied to the renderTpl


### initRenderTpl

Initializes the renderTpl. ...

Initializes the renderTpl.
ReturnsExt.XTemplateThe renderTpl XTemplate instance.


### initResizable

...

Parametersresizable : Object


### initState

Initializes the state of the object upon construction. ...

Initializes the state of the object upon construction.


### initStyles

Applies padding, margin, border, top, left, height, and width configs to the
appropriate elements. ...

Applies padding, margin, border, top, left, height, and width configs to the
appropriate elements.
ParameterstargetEl : Object


### is

Tests whether this Component matches the selector string. ...

Tests whether this Component matches the selector string.
Parametersselector : StringThe selector string to test against.


### isContainedFloater

Utility method to determine if a Component is floating, and has an owning Container whose coordinate system
it must b...

Utility method to determine if a Component is floating, and has an owning Container whose coordinate system
it must be positioned in when using setPosition.


### isDescendant

...

Parametersancestor : Object


### isDescendantOf

Determines whether this component is the descendant of a particular container. ...

Determines whether this component is the descendant of a particular container.
Parameterscontainer : Ext.Container


### isDisabled

Method to determine whether this Component is currently disabled. ...

Method to determine whether this Component is currently disabled.
ReturnsBooleanthe disabled state of this Component.


### isDraggable

Method to determine whether this Component is draggable. ...

Method to determine whether this Component is draggable.
ReturnsBooleanthe draggable state of this component.


### isDroppable

Method to determine whether this Component is droppable. ...

Method to determine whether this Component is droppable.
ReturnsBooleanthe droppable state of this component.


### isFloating

Method to determine whether this Component is floating. ...

Method to determine whether this Component is floating.
ReturnsBooleanthe floating state of this component.


### isFocusable

...


### isHidden

Method to determine whether this Component is currently set to hidden. ...

Method to determine whether this Component is currently set to hidden.
ReturnsBooleanthe hidden state of this Component.


### isHierarchicallyHidden

...


### isLayoutRoot

Determines whether this Component is the root of a layout. ...

Determines whether this Component is the root of a layout. This returns `true` if
this component can run its layout without assistance from or impact on its owner.
If this component cannot run its layout given these restrictions, `false` is returned
and its owner will be considered as the next candidate for the layout root.

Setting the _isLayoutRoot property to `true` causes this method to always
return `true`. This may be useful when updating a layout of a Container which shrink
wraps content, and you know that it will not change size, and so can safely be the
topmost participant in the layout run.


### isLayoutSuspended

Returns true if layout is suspended for this component. ...

Returns `true` if layout is suspended for this component. This can come from direct
suspension of this component's layout activity (Ext.Container.suspendLayout) or if one
of this component's containers is suspended.
ReturnsBoolean`true` layout of this component is suspended.


### isLocalRtl

Returns true if this component's local coordinate system is rtl. ...

Returns true if this component's local coordinate system is rtl. For normal
components this equates to the value of isParentRtl().  Floaters are a bit different
because a floater's element can be a childNode of something other than its
parent component's element.  For floaters we have to read the dom to see if the
component's element's parentNode has a css direction value of "rtl".

**Defined in override Ext.rtl.AbstractComponent.**
ReturnsBoolean


### isOppositeRootDirection

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**


### isParentRtl

Returns true if this component's parent container is rtl. ...

Returns true if this component's parent container is rtl. Used by rtl positioning
methods to determine if the component should be positioned using a right-to-left
coordinate system.

**Defined in override Ext.rtl.AbstractComponent.**
ReturnsBoolean


### isVisible

Returns true if this component is visible. ...

Returns `true` if this component is visible.
        Available since: 1.1.0
Parametersdeep : Boolean (optional)Pass `true` to interrogate the visibility status of all parent Containers to
determine whether this Component is truly visible to the user.

Generally, to determine whether a Component is hidden, the no argument form is needed. For example when creating
dynamically laid out UIs in a hidden Container before showing them.
Defaults to: `false`


### isXType

Tests whether or not this Component is of a specific xtype. ...

Tests whether or not this Component is of a specific xtype. This can test whether this Component is descended
from the xtype (default) or whether it is directly of the xtype specified (`shallow = true`).

If using your own subclasses, be aware that a Component must register its own xtype to participate in
determination of inherited xtypes.

For a list of all available xtypes, see the Ext.Component header.

Example usage:

var t = new Ext.form.field.Text();
var isText = t.isXType('textfield');        // true
var isBoxSubclass = t.isXType('field');       // true, descended from Ext.form.field.Base
var isBoxInstance = t.isXType('field', true); // false, not a direct Ext.form.field.Base instance

        Available since: 2.3.0
Parametersxtype : StringThe xtype to check for this Component


### makeFloating

...

Parametersdom : Object


### mask

...


### maybeShowMenu

...


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener.

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destroyed.
Parametersitem : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### move

Move the element relative to its current position. ...

Move the element relative to its current position.
Parametersdirection : StringPossible values are:


`"l"` (or `"left"`)
`"r"` (or `"right"`)
`"t"` (or `"top"`, or `"up"`)
`"b"` (or `"bottom"`, or `"down"`)


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener.

Removes listeners that were added by the mon method.
Parametersitem : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### nextNode

Returns the next node in the Component tree in tree traversal order. ...

Returns the next node in the Component tree in tree traversal order.

Note that this is not limited to siblings, and if invoked upon a node with no matching siblings, will walk the
tree to attempt to find a match. Contrast with nextSibling.
Parametersselector : String (optional)A ComponentQuery selector to filter the following nodes.


### nextSibling

Returns the next sibling of this Component. ...

Returns the next sibling of this Component.

Optionally selects the next sibling which matches the passed ComponentQuery selector.

May also be referred to as **`next()`**

Note that this is limited to siblings, and if no siblings of the item match, `null` is returned. Contrast with
nextNode
Parametersselector : String (optional)A ComponentQuery selector to filter the following items.


### on

Shorthand for addListener. ...

Shorthand for addListener.

Appends an event handler to this object.  For example:

myGridPanel.on("mouseover", this.onMouseOver, this);


The method also allows for a single argument to be passed which is a config object
containing properties which specify multiple events. For example:

myGridPanel.on({
    cellClick: this.onCellClick,
    mouseover: this.onMouseOver,
    mouseout: this.onMouseOut,
    scope: this // Important. Ensure "this" is correct during handler execution
});


One can also specify options for each event handler separately:

myGridPanel.on({
    cellClick: {fn: this.onCellClick, scope: this, single: true},
    mouseover: {fn: panel.onMouseOver, scope: panel}
});


*Names* of methods in a specified scope may also be used. Note that
`scope` MUST be specified to use this option:

myGridPanel.on({
    cellClick: {fn: 'onCellClick', scope: this, single: true},
    mouseover: {fn: 'onMouseOver', scope: panel}
});

ParameterseventName : String/ObjectThe name of the event to listen for.
May also be an object who's property names are event names.


### onAdded

Method to manage awareness of when components are added to their
respective Container, firing an added event. ...

Method to manage awareness of when components are added to their
respective Container, firing an added event. References are
established at add time rather than at render time.

Allows addition of behavior when a Component is added to a
Container. At this stage, the Component is in the parent
Container's collection of child items. After calling the
superclass's `onAdded`, the `ownerCt` reference will be present,
and if configured with a ref, the `refOwner` will be set.
        Available since: 3.4.0
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onAfterFloatLayout

...


### onBeforeFloatLayout

...


### onBlur

private ...

private
Parameterse : Object


### onBoxReady

...

Parameterswidth : Object


### onClick

...

Parameterse : Object


### onConfigUpdate

...

Parametersnames : Object


### onDestroy

Allows addition of behavior to the destroy operation. ...

Allows addition of behavior to the destroy operation.
After calling the superclass's onDestroy, the Component will be destroyed.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onDisable

See comments in onFocus

Allows addition of behavior to the disable operation. ...

See comments in onFocus

Allows addition of behavior to the disable operation.
After calling the superclass's `onDisable`, the Component will be disabled.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onDownKey

...

Parametersk : Object


### onEnable

Allows addition of behavior to the enable operation. ...

Allows addition of behavior to the enable operation.
After calling the superclass's `onEnable`, the Component will be enabled.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onFloatShow

...


### onFocus

private ...

private
Parameterse : Object


### onHide

Possibly animates down to a target element. ...

Possibly animates down to a target element.

Allows addition of behavior to the hide operation. After
calling the superclass’s onHide, the Component will be hidden.

Gets passed the same parameters as hide.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onKeyDown

Listen for TAB events and wrap round if tabbing of either end of the Floater ...

Listen for TAB events and wrap round if tabbing of either end of the Floater
Parameterse : Object


### onMenuHide

...

Parameterse : Object


### onMenuShow

...

Parameterse : Object


### onMenuTriggerOut

virtual mouseleave handler called when it is detected that the mouseout event
signified the mouse leaving the arrow a...

virtual mouseleave handler called when it is detected that the mouseout event
signified the mouse leaving the arrow area of the button - the `<em>`.
Parameterse : Object


### onMenuTriggerOver

virtual mouseenter handler called when it is detected that the mouseover event
signified the mouse entering the arrow...

virtual mouseenter handler called when it is detected that the mouseover event
signified the mouse entering the arrow area of the button - the `<em>`.
Parameterse : Object


### onMouseDown

...

Parameterse : Object


### onMouseEnter

virtual mouseenter handler called when it is detected that the mouseout event
signified the mouse entering the encaps...

virtual mouseenter handler called when it is detected that the mouseout event
signified the mouse entering the encapsulating element.
Parameterse : Object


### onMouseLeave

virtual mouseleave handler called when it is detected that the mouseover event
signified the mouse entering the encap...

virtual mouseleave handler called when it is detected that the mouseover event
signified the mouse entering the encapsulating element.
Parameterse : Object


### onMouseMove

mousemove handler called when the mouse moves anywhere within the encapsulating element. ...

mousemove handler called when the mouse moves anywhere within the encapsulating element.
The position is checked to determine if the mouse is entering or leaving the trigger area. Using
mousemove to check this is more resource intensive than we'd like, but it is necessary because
the trigger area does not line up exactly with sub-elements so we don't always get mouseover/out
events when needed. In the future we should consider making the trigger a separate element that
is absolutely positioned and sized over the trigger area.
Parameterse : Object


### onMouseOut

mouseout handler called when a mouseout event occurs anywhere within the encapsulating element -
or the mouse leaves ...

mouseout handler called when a mouseout event occurs anywhere within the encapsulating element -
or the mouse leaves the encapsulating element.
The targets are interrogated to see what is being exited to where.
Parameterse : Object


### onMouseOver

mouseover handler called when a mouseover event occurs anywhere within the encapsulating element. ...

mouseover handler called when a mouseover event occurs anywhere within the encapsulating element.
The targets are interrogated to see what is being entered from where.
Parameterse : Object


### onMouseUp

...

Parameterse : Object


### onPosition

Called after the component is moved, this method is empty by default but can be implemented by any
subclass that need...

Called after the component is moved, this method is empty by default but can be implemented by any
subclass that needs to perform custom logic after a move occurs.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onRemoved

Method to manage awareness of when components are removed from their
respective Container, firing a removed event. ...

Method to manage awareness of when components are removed from their
respective Container, firing a removed event. References are properly
cleaned up after removing a component from its owning container.

Allows addition of behavior when a Component is removed from
its parent Container. At this stage, the Component has been
removed from its parent Container's collection of child items,
but has not been destroyed (It will be destroyed if the parent
Container's `autoDestroy` is `true`, or if the remove call was
passed a truthy second parameter). After calling the
superclass's `onRemoved`, the `ownerCt` and the `refOwner` will not
be present.
        Available since: 3.4.0
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onRender

Template method called when this Component's DOM structure is created. ...

Template method called when this Component's DOM structure is created.

At this point, this Component's (and all descendants') DOM structure *exists* but it has not
been layed out (positioned and sized).

Subclasses which override this to gain access to the structure at render time should
call the parent class's method before attempting to access any child elements of the Component.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onRepeatClick

...

Parametersrepeat : Object


### onResize

Allows addition of behavior to the resize operation. ...

Allows addition of behavior to the resize operation.

Called when Ext.resizer.Resizer#drag event is fired.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onShow

Allows addition of behavior to the show operation. ...

Allows addition of behavior to the show operation. After
calling the superclass's onShow, the Component will be visible.

Override in subclasses where more complex behaviour is needed.

Gets passed the same parameters as show.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onShowComplete

Invoked after the afterShow method is complete. ...

Invoked after the afterShow method is complete.

Gets passed the same `callback` and `scope` parameters that afterShow received.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onShowVeto

...


### onStateChange

This method is called when any of the stateEvents are fired. ...

This method is called when any of the stateEvents are fired.


### parseBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**
Parametersbox : Object


### postBlur

Template method to do any post-blur processing. ...

Template method to do any post-blur processing.
Parameterse : Ext.EventObjectThe event object


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a
class derives from this class or uses this class as a mixin.
ParametersT : FunctionThe class constructor to prepare.


### previousNode

Returns the previous node in the Component tree in tree traversal order. ...

Returns the previous node in the Component tree in tree traversal order.

Note that this is not limited to siblings, and if invoked upon a node with no matching siblings, will walk the
tree in reverse order to attempt to find a match. Contrast with previousSibling.
Parametersselector : String (optional)A ComponentQuery selector to filter the preceding nodes.


### previousSibling

Returns the previous sibling of this Component. ...

Returns the previous sibling of this Component.

Optionally selects the previous sibling which matches the passed ComponentQuery
selector.

May also be referred to as **`prev()`**

Note that this is limited to siblings, and if no siblings of the item match, `null` is returned. Contrast with
previousNode
Parametersselector : String (optional)A ComponentQuery selector to filter the preceding items.


### prune

...

ParameterschildEls : Object


### query

Retrieves all descendant components which match the passed selector. ...

Retrieves all descendant components which match the passed selector.
Executes an Ext.ComponentQuery.query using this container as its root.
Parametersselector : String (optional)Selector complying to an Ext.ComponentQuery selector.
If no selector is specified all items will be returned.


### queryBy

Retrieves all descendant components which match the passed function. ...

Retrieves all descendant components which match the passed function.
The function should return false for components that are to be
excluded from the selection.
Parametersfn : FunctionThe matcher function. It will be called with a single argument,
the component being tested.


### queryById

Finds a component at any level under this container matching the id/itemId. ...

Finds a component at any level under this container matching the id/itemId.
This is a shorthand for calling ct.down('#' + id);
Parametersid : StringThe id to find


### registerFloatingItem

Called by Component#doAutoRender

Register a Container configured floating: true with this Component's ZIndexManager. ...

Called by Component#doAutoRender

Register a Container configured `floating: true` with this Component's ZIndexManager.

Components added in this way will not participate in any layout, but will be rendered
upon first show in the way that Windows are.
Parameterscmp : Object


### registerWithOwnerCt

...


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`.

For example if you are extending Grid, you might decide to forward some events from store.
So you can do this inside your initComponent:

this.relayEvents(this.getStore(), ['load']);


The grid instance will then have an observable 'load' event which will be passed the
parameters of the store's load event and any function fired with the grid's load event
would have access to the grid using the `this` keyword.
Parametersorigin : ObjectThe Observable whose events this object is to relay.


### removeAnchor

Remove any anchor to this element. ...

Remove any anchor to this element. See anchorTo.
ReturnsExt.util.Positionablethis


### removeChildEls

Removes items in the childEls array based on the return value of a supplied test
function. ...

Removes items in the childEls array based on the return value of a supplied test
function. The function is called with a entry in childEls and if the test function
return true, that entry is removed. If false, that entry is kept.
ParameterstestFn : FunctionThe test function.


### removeClass

...

Available since: 2.3.0


### removeCls

Removes a CSS class from the top level element representing this component. ...

Removes a CSS class from the top level element representing this component.
Parameterscls : String/String[]The CSS class name to remove.


### removeClsWithUI

Removes a cls to the uiCls array, which will also call removeUIClsFromElement and removes it from all
elements of thi...

Removes a `cls` to the `uiCls` array, which will also call removeUIClsFromElement and removes it from all
elements of this component.
Parameterscls : String/String[]A string or an array of strings to remove to the `uiCls`.


### removeListener

Removes an event handler. ...

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


### removeManagedListener

Removes listeners that were added by the mon method. ...

Removes listeners that were added by the mon method.
Parametersitem : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### removeManagedListenerItem

inherit docs

Remove a single managed listener item ...

inherit docs

Remove a single managed listener item
ParametersisClear : BooleanTrue if this is being called during a clear


### removeOverCls

...

Overrides: Ext.AbstractComponent.removeOverCls


### removePlugin

...

Parametersplugin : Object


### removeUIClsFromElement

Method which removes a specified UI + uiCls from the components element. ...

Method which removes a specified UI + `uiCls` from the components element. The `cls` which is added to the element
will be: `this.baseCls + '-' + ui`.
Parametersui : StringThe UI to add to the element.


### removeUIFromElement

Method which removes a specified UI from the components element. ...

Method which removes a specified UI from the components element.


### render

Renders the Component into the passed HTML element. ...

Renders the Component into the passed HTML element.

If you are using a Container object to house this
Component, then do not use the render method.

A Container's child Components are rendered by that Container's
layout manager when the Container is first rendered.

If the Container is already rendered when a new child Component is added, you may need to call
the Container's doLayout to refresh the view which
causes any unrendered child Components to be rendered. This is required so that you can add
multiple child components if needed while only refreshing the layout once.

When creating complex UIs, it is important to remember that sizing and positioning
of child items is the responsibility of the Container's layout
manager.  If you expect child items to be sized in response to user interactions, you must
configure the Container with a layout manager which creates and manages the type of layout you
have in mind.

Omitting the Container's layout config means that a basic
layout manager is used which does nothing but render child components sequentially into the
Container. No sizing or positioning will be performed in this situation.
Parameterscontainer : Ext.Element/HTMLElement/String (optional)The element this Component should be
rendered into. If it is being created from existing markup, this should be omitted.


### restoreClick

...


### resumeEvent

Resumes firing of the named event(s). ...

Resumes firing of the named event(s).

After calling this method to resume events, the events will fire when requested to fire.

Note that if the suspendEvent method is called multiple times for a certain event,
this converse method will have to be called the same number of times for it to resume firing.
ParameterseventName : String...Multiple event names to resume.


### resumeEvents

Resumes firing events (see suspendEvents). ...

Resumes firing events (see suspendEvents).

If events were suspended using the `queueSuspended` parameter, then all events fired
during event suspension will be sent to any listeners now.


### resumeLayouts

...

ParametersflushOptions : Object


### savePropToState

Conditionally saves a single property from this object to the given state object. ...

Conditionally saves a single property from this object to the given state object.
The idea is to only save state which has changed from the initial state so that
current software settings do not override future software settings. Only those
values that are user-changed state should be saved.
ParameterspropName : StringThe name of the property to save.


### savePropsToState

Gathers additional named properties of the instance and adds their current values
to the passed state object. ...

Gathers additional named properties of the instance and adds their current values
to the passed state object.
ParameterspropNames : String/String[]The name (or array of names) of the property to save.


### saveState

Saves the state of the object to the persistence store. ...

Saves the state of the object to the persistence store.


### scrollBy

Scrolls this Component's target element by the passed delta values, optionally animating. ...

Scrolls this Component's target element by the passed delta values, optionally animating.

All of the following are equivalent:

 comp.scrollBy(10, 10, true);
 comp.scrollBy([10, 10], true);
 comp.scrollBy({ x: 10, y: 10 }, true);

ParametersdeltaX : Number/Number[]/ObjectEither the x delta, an Array specifying x and y deltas or
an object with "x" and "y" properties.


### sequenceFx

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. ...

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. This is the
opposite of syncFx.
ReturnsObjectthis


### setActive

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been
moved to th...

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been
moved to the top of its zIndex stack, or pushed from the top of its zIndex stack.

If a *Window* is superceded by another Window, deactivating it hides its shadow.

This method also fires the activate or
deactivate event depending on which action occurred.
Parametersactive : Boolean (optional)True to activate the Component, false to deactivate it.
Defaults to: `false`


### setArrowHandler

Sets this button's arrow click handler. ...

Sets this button's arrow click handler.
Parametershandler : FunctionThe function to call when the arrow is clicked.


### setAutoScroll

Sets the overflow on the content element of the component. ...

Sets the overflow on the content element of the component.
Parametersscroll : BooleanTrue to allow the Component to auto scroll.


### setBorder

...

Parametersborder : String/NumberThe border, see border. If a falsey value is passed
the border will be removed.


### setBorderRegion

This method changes the region config property for this border region. ...

This method changes the `region` config property for this border region. This is
only valid if this component is in a `border` layout (`Ext.layout.container.Border`).

**Defined in override Ext.layout.container.border.Region.**
Parametersregion : StringThe new `region` value (`"north"`, `"south"`, `"east"` or
`"west"`).


### setBox

Sets the element's box. ...

Sets the element's box. If animate is true then x, y, width, and height will be
animated concurrently.
Parametersbox : ObjectThe box to fill {x, y, width, height}


### setComponentCls

...


### setComponentLayout

...

Parameterslayout : Object


### setConfig

...

Parametersconfig : Object


### setDisabled

Enable or disable the component. ...

Enable or disable the component.
Parametersdisabled : Boolean`true` to disable.


### setDocked

Sets the dock position of this component in its parent panel. ...

Sets the dock position of this component in its parent panel. Note that this only has effect if this item is part
of the `dockedItems` collection of a parent that has a DockLayout (note that any Panel has a DockLayout by default)
Parametersdock : ObjectThe dock position.


### setFloatParent

...

ParametersfloatParent : Object


### setGlyph

Sets this button's glyph ...

Sets this button's glyph
Parametersglyph : Number/Stringthe numeric charCode or string charCode/font-family.
This parameter expects a format consistent with that of glyph


### setHandler

Assigns this Button's click handler ...

Assigns this Button's click handler
Parametershandler : FunctionThe function to call when the button is clicked


### setHeight

Sets the height of the component. ...

Sets the height of the component. This method fires the resize event.
Parametersheight : NumberThe new height to set. This may be one of:


A Number specifying the new height in the Element's Ext.Element.defaultUnits (by default, pixels).
A String used to set the CSS height style.
*undefined* to leave the height unchanged.


### setHiddenState

...

Parametershidden : Object


### setHref

Sets the href of the embedded anchor element to the passed URL. ...

Sets the href of the embedded anchor element to the passed URL.

Also appends any configured baseParams and parameters set through setParams.
Parametershref : StringThe URL to set in the anchor element.


### setIcon

Sets the background image (inline style) of the button. ...

Sets the background image (inline style) of the button. This method also changes the value of the icon
config internally.
Parametersicon : StringThe path to an image to display in the button


### setIconCls

Sets the CSS class that provides a background image to use as the button's icon. ...

Sets the CSS class that provides a background image to use as the button's icon. This method also changes the
value of the iconCls config internally.
Parameterscls : StringThe CSS class providing the icon image


### setLoading

This method allows you to show or hide a LoadMask on top of this component. ...

This method allows you to show or hide a LoadMask on top of this component.
Parametersload : Boolean/Object/StringTrue to show the default LoadMask, a config object that will be passed to the
LoadMask constructor, or a message String to show. False to hide the current LoadMask.


### setLocalX

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Sets the local x coordinate of this element using CSS style. When used on an
absolute positioned element this method is symmetrical with getLocalX, but
may not be symmetrical when used on a relatively positioned element.
Parametersx : NumberThe x coordinate. A value of `null` sets the left style to 'auto'.


### setLocalXY

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Sets the local x and y coordinates of this element using CSS style. When used on an
absolute positioned element this method is symmetrical with getLocalXY, but
may not be symmetrical when used on a relatively positioned element.
Parametersx : Number/ArrayThe x coordinate or an array containing [x, y]. A value of
`null` sets the left style to 'auto'


### setLocalY

Sets the local y coordinate of this element using CSS style. ...

Sets the local y coordinate of this element using CSS style. When used on an
absolute positioned element this method is symmetrical with getLocalY, but
may not be symmetrical when used on a relatively positioned element.
Parametersy : NumberThe y coordinate. A value of `null` sets the top style to 'auto'.


### setMargin

Sets the margin on the target element. ...

Sets the margin on the target element.
Parametersmargin : Number/StringThe margin to set. See the margin config.


### setOverflowXY

Sets the overflow x/y on the content element of the component. ...

Sets the overflow x/y on the content element of the component. The x/y overflow
values can be any valid CSS overflow (e.g., 'auto' or 'scroll'). By default, the
value is 'hidden'. Passing null for one of the values will erase the inline style.
Passing `undefined` will preserve the current value.
ParametersoverflowX : StringThe overflow-x value.


### setPagePosition

Sets the page XY position of the component. ...

Sets the page XY position of the component. To set the left and top instead, use setPosition.
This method fires the move event.
Parametersx : Number/Number[]The new x position or an array of `[x,y]`.


### setParams

Sets the href of the link dynamically according to the params passed, and any baseParams configured. ...

Sets the href of the link dynamically according to the params passed, and any baseParams configured.

**Only valid if the Button was originally configured with a href**
Parametersparams : ObjectParameters to use in the href URL.


### setPosition

Sets the left and top of the component. ...

Sets the left and top of the component. To set the page XY position instead, use setPagePosition. This
method fires the move event.
Parametersx : Number/Number[]/ObjectThe new left, an array of `[x,y]`, or animation config object containing `x` and `y` properties.


### setRegion

Sets the element's position and size to the specified region. ...

Sets the element's position and size to the specified region. If animation is true
then width, height, x and y will be animated concurrently.
Parametersregion : Ext.util.RegionThe region to fill


### setRegionWeight

Sets the weight config property for this component. ...

Sets the `weight` config property for this component. This is only valid if this
component is in a `border` layout (`Ext.layout.container.Border`).

**Defined in override Ext.layout.container.border.Region.**
Parametersweight : NumberThe new `weight` value.


### setScale

Method to change the scale of the button. ...

Method to change the scale of the button. See scale for allowed configurations.
Parametersscale : StringThe scale to change to.


### setSize

Sets the width and height of this Component. ...

Sets the width and height of this Component. This method fires the resize event. This method can accept
either width and height as separate arguments, or you can pass a size object like `{width:10, height:20}`.
Parameterswidth : Number/String/ObjectThe new width to set. This may be one of:


A Number specifying the new width in the Element's Ext.Element.defaultUnits (by default, pixels).
A String used to set the CSS width style.
A size object in the format `{width: widthValue, height: heightValue}`.
`undefined` to leave the width unchanged.


### setText

Sets this Button's text ...

Sets this Button's text
Parameterstext : StringThe button text


### setTextAlign

Sets the text alignment for this button. ...

Sets the text alignment for this button.
Parametersalign : StringThe new alignment of the button text. See textAlign.


### setTooltip

Sets the tooltip for this Button. ...

Sets the tooltip for this Button.
Parameterstooltip : String/ObjectThis may be:


**String** : A string to be used as innerHTML (html tags are accepted) to show in a tooltip
**Object** : A configuration object for Ext.tip.QuickTipManager.register.


### setUI

inherit docs

Sets the UI for the component. ...

inherit docs

Sets the UI for the component. This will remove any existing UIs on the component. It will also loop through any
`uiCls` set on the component and rename them so they include the new UI.
Parametersui : StringThe new UI for the component.


### setVisible

Convenience function to hide or show this component by Boolean. ...

Convenience function to hide or show this component by Boolean.
        Available since: 1.1.0
Parametersvisible : Boolean`true` to show, `false` to hide.


### setWidth

Sets the width of the component. ...

Sets the width of the component. This method fires the resize event.
Parameterswidth : NumberThe new width to setThis may be one of:


A Number specifying the new width in the Element's Ext.Element.defaultUnits (by default, pixels).
A String used to set the CSS width style.


### setX

Sets the X position of the DOM element based on page coordinates. ...

Sets the X position of the DOM element based on page coordinates.
ParametersThe : NumberX position


### setXY

Sets the position of the DOM element in page coordinates. ...

Sets the position of the DOM element in page coordinates.
Parameterspos : Number[]Contains X & Y [x, y] values for new position (coordinates
are page-based)


### setY

Sets the Y position of the DOM element based on page coordinates. ...

Sets the Y position of the DOM element based on page coordinates.
ParametersThe : NumberY position


### setZIndex

z-index is managed by the zIndexManager and may be overwritten at any time. ...

z-index is managed by the zIndexManager and may be overwritten at any time.
Returns the next z-index to be used.
If this is a Container, then it will have rebased any managed floating Components,
and so the next available z-index will be approximately 10000 above that.
Parametersindex : Object


### setupFramingTpl

Inject a reference to the function which applies the render template into the framing template. ...

Inject a reference to the function which applies the render template into the framing template. The framing template
wraps the content.
ParametersframeTpl : Object


### setupProtoEl

...


### setupRenderTpl

...

ParametersrenderTpl : Object


### show

Shows this Component, rendering it first if autoRender or floating are true. ...

Shows this Component, rendering it first if autoRender or floating are `true`.

After being shown, a floating Component (such as a Ext.window.Window), is activated it and
brought to the front of its z-index stack.
ParametersanimateTarget : String/Ext.Element (optional)only valid for floating Components such as Windows or ToolTips, or regular Components which have been configured
with `floating: true`. The target from which the Component should animate from while opening.
Defaults to: `null`


### showAt

Displays component at specific xy position. ...

Displays component at specific xy position.
A floating component (like a menu) is positioned relative to its ownerCt if any.
Useful for popping up a context menu:

listeners: {
    itemcontextmenu: function(view, record, item, index, event, options) {
        Ext.create('Ext.menu.Menu', {
            width: 100,
            height: 100,
            margin: '0 0 10 0',
            items: [{
                text: 'regular item 1'
            },{
                text: 'regular item 2'
            },{
                text: 'regular item 3'
            }]
        }).showAt(event.getXY());
    }
}

Parametersx : Number/Number[]The new x position or array of `[x,y]`.


### showBy

Shows this component by the specified Component or Element. ...

Shows this component by the specified Component or Element.
Used when this component is floating.
Parameterscomponent : Ext.Component/Ext.dom.ElementThe Ext.Component or Ext.Element to show the component by.


### showMenu

Shows this button's menu (if it has one) ...

Shows this button's menu (if it has one)
ParametersfromEvent : Object


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


### stopAnimation

Stops any running effects and clears this object's internal effects queue if it contains any additional effects
that ...

Stops any running effects and clears this object's internal effects queue if it contains any additional effects
that haven't started yet.
ReturnsExt.ElementThe Element


### stopFx

Stops any running effects and clears this object's internal effects queue if it contains any additional effects
that ...

Stops any running effects and clears this object's internal effects queue if it contains any additional effects
that haven't started yet.
        
        This method has been **deprecated** since 4.0
        Replaced by stopAnimation


### suspendEvent

Suspends firing of the named event(s). ...

Suspends firing of the named event(s).

After calling this method to suspend events, the events will no longer fire when requested to fire.

Note that if this is called multiple times for a certain event, the converse method
resumeEvent will have to be called the same number of times for it to resume firing.
ParameterseventName : String...Multiple event names to suspend.


### suspendEvents

Suspends the firing of all events. ...

Suspends the firing of all events. (see resumeEvents)
ParametersqueueSuspended : BooleanPass as true to queue up suspended events to be fired
after the resumeEvents call instead of discarding all suspended events.


### suspendLayouts

...


### syncFx

Ensures that all effects queued after syncFx is called on this object are run concurrently. ...

Ensures that all effects queued after syncFx is called on this object are run concurrently. This is the opposite
of sequenceFx.
ReturnsObjectthis


### syncHidden

synchronizes the hidden state of this component with the state of its hierarchy ...

synchronizes the hidden state of this component with the state of its hierarchy


### syncShadow

...


### toBack

Sends this Component to the back of (lower z-index than) any other visible windows ...

Sends this Component to the back of (lower z-index than) any other visible windows
ReturnsExt.Componentthis


### toFront

Brings this floating Component to the front of any other visible, floating Components managed by the same
ZIndexManag...

Brings this floating Component to the front of any other visible, floating Components managed by the same
ZIndexManager

If this Component is modal, inserts the modal mask just below this Component in the z-index stack.
ParameterspreventFocus : Boolean (optional)Specify `true` to prevent the Component from being focused.
Defaults to: `false`


### toggle

If a state it passed, it becomes the pressed state otherwise the current state is toggled. ...

If a state it passed, it becomes the pressed state otherwise the current state is toggled.
Parametersstate : Boolean (optional)Force a particular state


### translatePoints

Translates the passed page coordinates into left/top css values for the element ...

Translates the passed page coordinates into left/top css values for the element
Parametersx : Number/ArrayThe page x or an array containing [x, y]


### translateXY

Translates the passed page coordinates into x and y css values for the element ...

Translates the passed page coordinates into x and y css values for the element
Parametersx : Number/ArrayThe page x or an array containing [x, y]


### un

Shorthand for removeListener. ...

Shorthand for removeListener.

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


### unitizeBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**
Parametersbox : Object


### unmask

...


### unregisterFloatingItem

...

Parameterscmp : Object


### up

Navigates up the ownership hierarchy searching for an ancestor Container which matches any passed simple selector or ...

Navigates up the ownership hierarchy searching for an ancestor Container which matches any passed simple selector or component.

*Important.* There is not a universal upwards navigation pointer. There are several upwards relationships
such as the button which activates a menu, or the
menu item which activated a submenu, or the
column header which activated the column menu.

These differences are abstracted away by this method.

Example:

var owningTabPanel = grid.up('tabpanel');

Parametersselector : String/Ext.Component (optional)The simple selector component or actual component to test. If not passed the immediate owner/activater is returned.


### update

Update the content area of a component. ...

Update the content area of a component.
        Available since: 3.4.0
ParametershtmlOrData : String/ObjectIf this component has been configured with a template via the tpl config then
it will use this argument as data to populate the template. If this component was not configured with a template,
the components content area will be updated via Ext.Element update.


### updateAria

Injected as an override by Ext.Aria.initialize ...

Injected as an override by Ext.Aria.initialize


### updateBox

Sets the current box measurements of the component's underlying element. ...

Sets the current box measurements of the component's underlying element.
Parametersbox : ObjectAn object in the format {x, y, width, height}


### updateFrame

...


### updateLayout

Updates this component's layout. ...

Updates this component's layout. If this update affects this components ownerCt,
that component's `updateLayout` method will be called to perform the layout instead.
Otherwise, just this component (and its child items) will layout.
Parametersoptions : Object (optional)An object with layout options.
defer : Boolean`true` if this layout should be deferred.


### wrapPrimaryEl

...

Parametersdom : Object


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


### activate

Fires after a Component has been visually activated. ...

Fires after a Component has been visually activated.
Parametersthis : Ext.Component


### added

Fires after a Component had been added to a Container. ...

Fires after a Component had been added to a Container.
        Available since: 3.4.0
Parametersthis : Ext.Component


### afterrender

Fires after the component rendering is finished. ...

Fires after the component rendering is finished.

The `afterrender` event is fired after this Component has been rendered, been postprocessed by any
`afterRender` method defined for the Component.
        Available since: 3.4.0
Parametersthis : Ext.Component


### arrowclick

Fires when this button's arrow is clicked. ...

Fires when this button's arrow is clicked.
Parametersthis : Ext.button.Split


### beforeactivate

Fires before a Component has been visually activated. ...

Fires before a Component has been visually activated. Returning `false` from an event listener can prevent
the activate from occurring.
Parametersthis : Ext.Component


### beforedeactivate

Fires before a Component has been visually deactivated. ...

Fires before a Component has been visually deactivated. Returning `false` from an event listener can
prevent the deactivate from occurring.
Parametersthis : Ext.Component


### beforedestroy

Fires before the component is destroyed. ...

Fires before the component is destroyed. Return `false` from an event handler to stop the
destroy.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforehide

Fires before the component is hidden when calling the hide method. ...

Fires before the component is hidden when calling the hide method. Return `false` from an event
handler to stop the hide.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforerender

Fires before the component is rendered. ...

Fires before the component is rendered. Return `false` from an event handler to stop the
render.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforeshow

Fires before the component is shown when calling the show method. ...

Fires before the component is shown when calling the show method. Return `false` from an event
handler to stop the show.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforestaterestore

Fires before the state of the object is restored. ...

Fires before the state of the object is restored. Return false from an event handler to stop the restore.
Parametersthis : Ext.state.Stateful


### beforestatesave

Fires before the state of the object is saved to the configured state provider. ...

Fires before the state of the object is saved to the configured state provider. Return false to stop the save.
Parametersthis : Ext.state.Stateful


### blur

Fires when this Component loses focus. ...

Fires when this Component loses focus.
Parametersthis : Ext.Component


### boxready

Fires one time - after the component has been laid out for the first time at its initial size. ...

Fires *one time* - after the component has been laid out for the first time at its initial size.
Parametersthis : Ext.Component


### click

Fires when this button is clicked, before the configured handler is invoked. ...

Fires when this button is clicked, before the configured handler is invoked. Execution of the
handler may be vetoed by returning `false` to this event.
Parametersthis : Ext.button.Button


### deactivate

Fires after a Component has been visually deactivated. ...

Fires after a Component has been visually deactivated.
Parametersthis : Ext.Component


### destroy

Fires after the component is destroyed. ...

Fires after the component is destroyed.
        Available since: 1.1.0
Parametersthis : Ext.Component


### disable

Fires after the component is disabled. ...

Fires after the component is disabled.
        Available since: 1.1.0
Parametersthis : Ext.Component


### enable

Fires after the component is enabled. ...

Fires after the component is enabled.
        Available since: 1.1.0
Parametersthis : Ext.Component


### focus

Fires when this Component receives focus. ...

Fires when this Component receives focus.
Parametersthis : Ext.Component


### glyphchange

Fired when the button's glyph is changed by the setGlyph method. ...

Fired when the button's glyph is changed by the setGlyph method.
Parametersthis : Ext.button.Button


### hide

Fires after the component is hidden. ...

Fires after the component is hidden. Fires after the component is hidden when calling the hide
method.
        Available since: 1.1.0
Parametersthis : Ext.Component


### iconchange

Fired when the button's icon is changed by the setIcon or setIconCls methods. ...

Fired when the button's icon is changed by the setIcon or setIconCls methods.
Parametersthis : Ext.button.Button


### menuhide

If this button has a menu, this event fires when it is hidden ...

If this button has a menu, this event fires when it is hidden
Parametersthis : Ext.button.Button


### menushow

If this button has a menu, this event fires when it is shown ...

If this button has a menu, this event fires when it is shown
Parametersthis : Ext.button.Button


### menutriggerout

If this button has a menu, this event fires when the mouse leaves the menu triggering element ...

If this button has a menu, this event fires when the mouse leaves the menu triggering element
Parametersthis : Ext.button.Button


### menutriggerover

If this button has a menu, this event fires when the mouse enters the menu triggering element ...

If this button has a menu, this event fires when the mouse enters the menu triggering element
Parametersthis : Ext.button.Button


### mouseout

Fires when the mouse exits the button ...

Fires when the mouse exits the button
Parametersthis : Ext.button.Button


### mouseover

Fires when the mouse hovers over the button ...

Fires when the mouse hovers over the button
Parametersthis : Ext.button.Button


### move

Fires after the component is moved. ...

Fires after the component is moved.
Parametersthis : Ext.Component


### removed

Fires when a component is removed from an Ext.container.Container ...

Fires when a component is removed from an Ext.container.Container
        Available since: 3.4.0
Parametersthis : Ext.Component


### render

Fires after the component markup is rendered. ...

Fires after the component markup is rendered.
        Available since: 1.1.0
Parametersthis : Ext.Component


### resize

Fires after the component is resized. ...

Fires after the component is resized. Note that this does *not* fire when the component is first laid out at its initial
size. To hook that point in the life cycle, use the boxready event.
Parametersthis : Ext.Component


### show

Fires after the component is shown when calling the show method. ...

Fires after the component is shown when calling the show method.
        Available since: 1.1.0
Parametersthis : Ext.Component


### staterestore

Fires after the state of the object is restored. ...

Fires after the state of the object is restored.
Parametersthis : Ext.state.Stateful


### statesave

Fires after the state of the object is saved to the configured state provider. ...

Fires after the state of the object is saved to the configured state provider.
Parametersthis : Ext.state.Stateful


### textchange

Fired when the button's text is changed by the setText method. ...

Fired when the button's text is changed by the setText method.
Parametersthis : Ext.button.Button


### toggle

Fires when the 'pressed' state of this button changes (only if enableToggle = true) ...

Fires when the 'pressed' state of this button changes (only if enableToggle = true)
Parametersthis : Ext.button.Button


### $button-arrow-height

**Tipo:** number

The default height for a button's menu arrow ...

The default height for a button's menu arrow
Defaults to: `12px`


### $button-arrow-width

**Tipo:** number

The default width for a button's menu arrow ...

The default width for a button's menu arrow
Defaults to: `12px`


### $button-default-background-color

**Tipo:** color

The background-color for the default button UI ...

The background-color for the `default` button UI
Defaults to: `$button-default-base-color`


### $button-default-background-color-disabled

**Tipo:** color

The background-color for the default button UI when the button is disabled ...

The background-color for the `default` button UI when the button is disabled
Defaults to: `null`


### $button-default-background-color-focus

**Tipo:** color

The background-color for the default button UI when the button is focused ...

The background-color for the `default` button UI when the button is focused
Defaults to: `$button-default-background-color-over`


### $button-default-background-color-over

**Tipo:** color

The background-color for the default button UI when the cursor is over the button ...

The background-color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-base-color-over`


### $button-default-background-color-pressed

**Tipo:** color

The background-color for the default button UI when the button is pressed ...

The background-color for the `default` button UI when the button is pressed
Defaults to: `$button-default-base-color-pressed`


### $button-default-background-gradient

**Tipo:** string/list

The background-gradient for the default button UI. ...

The background-gradient for the `default` button UI.  Can be either the name of a
predefined gradient or a list of color stops. Used as the `$type` parameter for
Global_CSS.background-gradient.
Defaults to: `'glossy-button'`


### $button-default-background-gradient-disabled

**Tipo:** string/list

The background-gradient for the default button UI when the button is disabled. ...

The background-gradient for the `default` button UI when the button is disabled.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-disabled'`


### $button-default-background-gradient-focus

**Tipo:** string/list

The background-gradient for the default button UI when the button is focused. ...

The background-gradient for the `default` button UI when the button is focused.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `$button-default-background-gradient-over`


### $button-default-background-gradient-over

**Tipo:** string/list

The background-gradient for the default button UI when the cursor is over the button. ...

The background-gradient for the `default` button UI when the cursor is over the button.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-over'`


### $button-default-background-gradient-pressed

**Tipo:** string/list

The background-gradient for the default button UI when the button is pressed. ...

The background-gradient for the `default` button UI when the button is pressed.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-pressed'`


### $button-default-base-color

**Tipo:** color

The base color for the default button UI ...

The base color for the `default` button UI
Defaults to: `$base-color`


### $button-default-base-color-disabled

**Tipo:** color

The base color for the default button UI when the button is disabled ...

The base color for the `default` button UI when the button is disabled
Defaults to: `$base-color`


### $button-default-base-color-focus

**Tipo:** color

The base color for the default button UI when the button is focused ...

The base color for the `default` button UI when the button is focused
Defaults to: `$button-default-base-color-over`


### $button-default-base-color-over

**Tipo:** color

The base color for the default button UI when the cursor is over the button ...

The base color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-base-color`


### $button-default-base-color-pressed

**Tipo:** color

The base color for the default button UI when the button is pressed ...

The base color for the `default` button UI when the button is pressed
Defaults to: `$button-default-base-color`


### $button-default-border-color

**Tipo:** color

The border-color for the default button UI ...

The border-color for the `default` button UI
Defaults to: `$base-color`


### $button-default-border-color-disabled

**Tipo:** color

The border-color for the default button UI when the button is disabled ...

The border-color for the `default` button UI when the button is disabled
Defaults to: `$base-color`


### $button-default-border-color-focus

**Tipo:** color

The border-color for the default button UI when the button is focused ...

The border-color for the `default` button UI when the button is focused
Defaults to: `$base-color`


### $button-default-border-color-over

**Tipo:** color

The border-color for the default button UI when the cursor is over the button ...

The border-color for the `default` button UI when the cursor is over the button
Defaults to: `$base-color`


### $button-default-border-color-pressed

**Tipo:** color

The border-color for the default button UI when the button is pressed ...

The border-color for the `default` button UI when the button is pressed
Defaults to: `$base-color`


### $button-default-color

**Tipo:** color

The text color for the default button UI ...

The text color for the `default` button UI
Defaults to: `#000`


### $button-default-color-disabled

**Tipo:** color

The text color for the default button UI when the button is disabled ...

The text color for the `default` button UI when the button is disabled
Defaults to: `$button-default-color`


### $button-default-color-focus

**Tipo:** color

The text color for the default button UI when the button is focused ...

The text color for the `default` button UI when the button is focused
Defaults to: `$button-default-color-over`


### $button-default-color-over

**Tipo:** color

The text color for the default button UI when the cursor is over the button ...

The text color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-color`


### $button-default-color-pressed

**Tipo:** color

The text color for the default button UI when the button is pressed ...

The text color for the `default` button UI when the button is pressed
Defaults to: `$button-default-color`


### $button-default-glyph-color

**Tipo:** color

The color of the glyph icon for the default button UI ...

The color of the glyph icon for the `default` button UI
Defaults to: `$button-default-color`


### $button-default-glyph-opacity

**Tipo:** color

The opacity of the glyph icon for the default button UI ...

The opacity of the glyph icon for the `default` button UI
Defaults to: `.5`


### $button-icon-spacing

**Tipo:** number

The default space between a button's icon and text ...

The default space between a button's icon and text
Defaults to: `4px`


### $button-include-split-over-arrows

**Tipo:** boolean

True to include different split arrows for buttons' hover state. ...

True to include different split arrows for buttons' hover state.
Defaults to: `false`


### $button-include-ui-menu-arrows

**Tipo:** boolean

True to use a different image url for the menu button arrows for each button UI ...

True to use a different image url for the menu button arrows for each button UI
Defaults to: `false`


### $button-include-ui-split-arrows

**Tipo:** boolean

True to use a different image url for the split button arrows for each button UI ...

True to use a different image url for the split button arrows for each button UI
Defaults to: `false`


### $button-inner-opacity-disabled

**Tipo:** number

opacity to apply to the button's inner elements (icon and text) when the buton is disabled ...

opacity to apply to the button's inner elements (icon and text) when the buton is disabled
Defaults to: `1`


### $button-large-arrow-height

**Tipo:** number

The default height of a large scale button's menu arrow ...

The default height of a large scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-large-arrow-width

**Tipo:** number

The default width of a large scale button's menu arrow ...

The default width of a large scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-large-border-radius

**Tipo:** number

The default border-radius for a large scale button ...

The default border-radius for a large scale button
Defaults to: `3px`


### $button-large-border-width

**Tipo:** number

The default border-width for a large scale button ...

The default border-width for a large scale button
Defaults to: `1px`


### $button-large-font-family

**Tipo:** string

The default font-family for a large scale button ...

The default font-family for a large scale button
Defaults to: `$font-family`


### $button-large-font-family-disabled

**Tipo:** string

The default font-family for a large scale button when the button is disabled ...

The default font-family for a large scale button when the button is disabled
Defaults to: `$button-large-font-family`


### $button-large-font-family-focus

**Tipo:** string

The default font-family for a large scale button when the button is focused ...

The default font-family for a large scale button when the button is focused
Defaults to: `$button-large-font-family-over`


### $button-large-font-family-over

**Tipo:** string

The default font-family for a large scale button when the cursor is over the button ...

The default font-family for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-family`


### $button-large-font-family-pressed

**Tipo:** string

The default font-family for a large scale button when the button is pressed ...

The default font-family for a large scale button when the button is pressed
Defaults to: `$button-large-font-family`


### $button-large-font-size

**Tipo:** number

The default font-size for a large scale button ...

The default font-size for a large scale button
Defaults to: `$font-size`


### $button-large-font-size-disabled

**Tipo:** number

The default font-size for a large scale button when the button is disabled ...

The default font-size for a large scale button when the button is disabled
Defaults to: `$button-large-font-size`


### $button-large-font-size-focus

**Tipo:** number

The default font-size for a large scale button when the button is focused ...

The default font-size for a large scale button when the button is focused
Defaults to: `$button-large-font-size-over`


### $button-large-font-size-over

**Tipo:** number

The default font-size for a large scale button when the cursor is over the button ...

The default font-size for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-size`


### $button-large-font-size-pressed

**Tipo:** number

The default font-size for a large scale button when the button is pressed ...

The default font-size for a large scale button when the button is pressed
Defaults to: `$button-large-font-size`


### $button-large-font-weight

**Tipo:** string

The default font-weight for a large scale button ...

The default font-weight for a large scale button
Defaults to: `normal`


### $button-large-font-weight-disabled

**Tipo:** string

The default font-weight for a large scale button when the button is disabled ...

The default font-weight for a large scale button when the button is disabled
Defaults to: `$button-large-font-weight`


### $button-large-font-weight-focus

**Tipo:** string

The default font-weight for a large scale button when the button is focused ...

The default font-weight for a large scale button when the button is focused
Defaults to: `$button-large-font-weight-over`


### $button-large-font-weight-over

**Tipo:** string

The default font-weight for a large scale button when the cursor is over the button ...

The default font-weight for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-weight`


### $button-large-font-weight-pressed

**Tipo:** string

The default font-weight for a large scale button when the button is pressed ...

The default font-weight for a large scale button when the button is pressed
Defaults to: `$button-large-font-weight`


### $button-large-icon-size

**Tipo:** number

The default icon size for a large scale button ...

The default icon size for a large scale button
Defaults to: `32px`


### $button-large-padding

**Tipo:** number

The default padding for a large scale button ...

The default padding for a large scale button
Defaults to: `3px`


### $button-large-split-height

**Tipo:** number

The default height of a large scale Split Button's arrow ...

The default height of a large scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-large-split-width

**Tipo:** number

The default width of a large scale Split Button's arrow ...

The default width of a large scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-large-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a large scale button ...

The default horizontal padding to add to the left and right of the text element for
a large scale button
Defaults to: `3px`


### $button-medium-arrow-height

**Tipo:** number

The default height of a medium scale button's menu arrow ...

The default height of a medium scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-medium-arrow-width

**Tipo:** number

The default width of a medium scale button's menu arrow ...

The default width of a medium scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-medium-border-radius

**Tipo:** number

The default border-radius for a medium scale button ...

The default border-radius for a medium scale button
Defaults to: `3px`


### $button-medium-border-width

**Tipo:** number

The default border-width for a medium scale button ...

The default border-width for a medium scale button
Defaults to: `1px`


### $button-medium-font-family

**Tipo:** string

The default font-family for a medium scale button ...

The default font-family for a medium scale button
Defaults to: `$font-family`


### $button-medium-font-family-disabled

**Tipo:** string

The default font-family for a medium scale button when the button is disabled ...

The default font-family for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-family`


### $button-medium-font-family-focus

**Tipo:** string

The default font-family for a medium scale button when the button is focused ...

The default font-family for a medium scale button when the button is focused
Defaults to: `$button-medium-font-family-over`


### $button-medium-font-family-over

**Tipo:** string

The default font-family for a medium scale button when the cursor is over the button ...

The default font-family for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-family`


### $button-medium-font-family-pressed

**Tipo:** string

The default font-family for a medium scale button when the button is pressed ...

The default font-family for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-family`


### $button-medium-font-size

**Tipo:** number

The default font-size for a medium scale button ...

The default font-size for a medium scale button
Defaults to: `$font-size`


### $button-medium-font-size-disabled

**Tipo:** number

The default font-size for a medium scale button when the button is disabled ...

The default font-size for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-size`


### $button-medium-font-size-focus

**Tipo:** number

The default font-size for a medium scale button when the button is focused ...

The default font-size for a medium scale button when the button is focused
Defaults to: `$button-medium-font-size-over`


### $button-medium-font-size-over

**Tipo:** number

The default font-size for a medium scale button when the cursor is over the button ...

The default font-size for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-size`


### $button-medium-font-size-pressed

**Tipo:** number

The default font-size for a medium scale button when the button is pressed ...

The default font-size for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-size`


### $button-medium-font-weight

**Tipo:** string

The default font-weight for a medium scale button ...

The default font-weight for a medium scale button
Defaults to: `normal`


### $button-medium-font-weight-disabled

**Tipo:** string

The default font-weight for a medium scale button when the button is disabled ...

The default font-weight for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-weight`


### $button-medium-font-weight-focus

**Tipo:** string

The default font-weight for a medium scale button when the button is focused ...

The default font-weight for a medium scale button when the button is focused
Defaults to: `$button-medium-font-weight-over`


### $button-medium-font-weight-over

**Tipo:** string

The default font-weight for a medium scale button when the cursor is over the button ...

The default font-weight for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-weight`


### $button-medium-font-weight-pressed

**Tipo:** string

The default font-weight for a medium scale button when the button is pressed ...

The default font-weight for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-weight`


### $button-medium-icon-size

**Tipo:** number

The default icon size for a medium scale button ...

The default icon size for a medium scale button
Defaults to: `24px`


### $button-medium-padding

**Tipo:** number

The default padding for a medium scale button ...

The default padding for a medium scale button
Defaults to: `3px`


### $button-medium-split-height

**Tipo:** number

The default height of a medium scale Split Button's arrow ...

The default height of a medium scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-medium-split-width

**Tipo:** number

The default width of a medium scale Split Button's arrow ...

The default width of a medium scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-medium-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a medium scale button ...

The default horizontal padding to add to the left and right of the text element for
a medium scale button
Defaults to: `3px`


### $button-opacity-disabled

**Tipo:** number

opacity to apply to the button's main element when the buton is disabled ...

opacity to apply to the button's main element when the buton is disabled
Defaults to: `.5`


### $button-small-arrow-height

**Tipo:** number

The default height of a small scale button's menu arrow ...

The default height of a small scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-small-arrow-width

**Tipo:** number

The default width of a small scale button's menu arrow ...

The default width of a small scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-small-border-radius

**Tipo:** number

The default border-radius for a small scale button ...

The default border-radius for a small scale button
Defaults to: `3px`


### $button-small-border-width

**Tipo:** number

The default border-width for a small scale button ...

The default border-width for a small scale button
Defaults to: `1px`


### $button-small-font-family

**Tipo:** string

The default font-family for a small scale button ...

The default font-family for a small scale button
Defaults to: `$font-family`


### $button-small-font-family-disabled

**Tipo:** string

The default font-family for a small scale button when the button is disabled ...

The default font-family for a small scale button when the button is disabled
Defaults to: `$button-small-font-family`


### $button-small-font-family-focus

**Tipo:** string

The default font-family for a small scale button when the button is focused ...

The default font-family for a small scale button when the button is focused
Defaults to: `$button-small-font-family-over`


### $button-small-font-family-over

**Tipo:** string

The default font-family for a small scale button when the cursor is over the button ...

The default font-family for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-family`


### $button-small-font-family-pressed

**Tipo:** string

The default font-family for a small scale button when the button is pressed ...

The default font-family for a small scale button when the button is pressed
Defaults to: `$button-small-font-family`


### $button-small-font-size

**Tipo:** number

The default font-size for a small scale button ...

The default font-size for a small scale button
Defaults to: `ceil ( $font-size * .9 )`


### $button-small-font-size-disabled

**Tipo:** number

The default font-size for a small scale button when the button is disabled ...

The default font-size for a small scale button when the button is disabled
Defaults to: `$button-small-font-size`


### $button-small-font-size-focus

**Tipo:** number

The default font-size for a small scale button when the button is focused ...

The default font-size for a small scale button when the button is focused
Defaults to: `$button-small-font-size-over`


### $button-small-font-size-over

**Tipo:** number

The default font-size for a small scale button when the cursor is over the button ...

The default font-size for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-size`


### $button-small-font-size-pressed

**Tipo:** number

The default font-size for a small scale button when the button is pressed ...

The default font-size for a small scale button when the button is pressed
Defaults to: `$button-small-font-size`


### $button-small-font-weight

**Tipo:** string

The default font-weight for a small scale button ...

The default font-weight for a small scale button
Defaults to: `normal`


### $button-small-font-weight-disabled

**Tipo:** string

The default font-weight for a small scale button when the button is disabled ...

The default font-weight for a small scale button when the button is disabled
Defaults to: `$button-small-font-weight`


### $button-small-font-weight-focus

**Tipo:** string

The default font-weight for a small scale button when the button is focused ...

The default font-weight for a small scale button when the button is focused
Defaults to: `$button-small-font-weight-over`


### $button-small-font-weight-over

**Tipo:** string

The default font-weight for a small scale button when the cursor is over the button ...

The default font-weight for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-weight`


### $button-small-font-weight-pressed

**Tipo:** string

The default font-weight for a small scale button when the button is pressed ...

The default font-weight for a small scale button when the button is pressed
Defaults to: `$button-small-font-weight`


### $button-small-icon-size

**Tipo:** number

The default icon size for a small scale button ...

The default icon size for a small scale button
Defaults to: `16px`


### $button-small-padding

**Tipo:** number

The default padding for a small scale button ...

The default padding for a small scale button
Defaults to: `2px`


### $button-small-split-height

**Tipo:** number

The default height of a small scale Split Button's arrow ...

The default height of a small scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-small-split-width

**Tipo:** number

The default width of a small scale Split Button's arrow ...

The default width of a small scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-small-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a small scale button ...

The default horizontal padding to add to the left and right of the text element for
a small scale button
Defaults to: `4px`


### $button-split-height

**Tipo:** number

The default height for a Split Button's arrow ...

The default height for a Split Button's arrow
Defaults to: `14px`


### $button-split-width

**Tipo:** number

The default width for a Split Button's arrow ...

The default width for a Split Button's arrow
Defaults to: `14px`


### $button-toolbar-background-color

**Tipo:** color

The background-color for the default-toolbar button UI ...

The background-color for the `default-toolbar` button UI
Defaults to: `$base-color`


### $button-toolbar-background-color-disabled

**Tipo:** color

The background-color for the default-toolbar button UI when the button is disabled ...

The background-color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-color-focus

**Tipo:** color

The background-color for the default-toolbar button UI when the button is focused ...

The background-color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-background-color-over`


### $button-toolbar-background-color-over

**Tipo:** color

The background-color for the default-toolbar button UI when the cursor is over the button ...

The background-color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-color-pressed

**Tipo:** color

The background-color for the default-toolbar button UI when the button is pressed ...

The background-color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-gradient

**Tipo:** string/list

The background-gradient for the default-toolbar button UI. ...

The background-gradient for the `default-toolbar` button UI.  Can be either the name of
a predefined gradient or a list of color stops. Used as the `$type` parameter for
Global_CSS.background-gradient.
Defaults to: `'glossy-button'`


### $button-toolbar-background-gradient-disabled

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is disabled. ...

The background-gradient for the `default-toolbar` button UI when the button is disabled.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-disabled'`


### $button-toolbar-background-gradient-focus

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is focused. ...

The background-gradient for the `default-toolbar` button UI when the button is focused.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `$button-toolbar-background-gradient-over`


### $button-toolbar-background-gradient-over

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the cursor is over the
button. ...

The background-gradient for the `default-toolbar` button UI when the cursor is over the
button. Can be either the name of a predefined gradient or a list of color stops. Used
as the `$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-over'`


### $button-toolbar-background-gradient-pressed

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is pressed. ...

The background-gradient for the `default-toolbar` button UI when the button is pressed.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-pressed'`


### $button-toolbar-border-color

**Tipo:** color

The border-color for the default-toolbar button UI ...

The border-color for the `default-toolbar` button UI
Defaults to: `$base-color`


### $button-toolbar-border-color-disabled

**Tipo:** color

The border-color for the default-toolbar button UI when the button is disabled ...

The border-color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-border-color-focus

**Tipo:** color

The border-color for the default-toolbar button UI when the button is focused ...

The border-color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-border-color-over`


### $button-toolbar-border-color-over

**Tipo:** color

The border-color for the default-toolbar button UI when the cursor is over the button ...

The border-color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-border-color-pressed

**Tipo:** color

The border-color for the default-toolbar button UI when the button is pressed ...

The border-color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-color

**Tipo:** color

The text color for the default-toolbar button UI ...

The text color for the `default-toolbar` button UI
Defaults to: `#000`


### $button-toolbar-color-disabled

**Tipo:** color

The text color for the default-toolbar button UI when the button is disabled ...

The text color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-color`


### $button-toolbar-color-focus

**Tipo:** color

The text color for the default-toolbar button UI when the button is focused ...

The text color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-color-over`


### $button-toolbar-color-over

**Tipo:** color

The text color for the default-toolbar button UI when the cursor is over the button ...

The text color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-color`


### $button-toolbar-color-pressed

**Tipo:** color

The text color for the default-toolbar button UI when the button is pressed ...

The text color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-color`


### $button-toolbar-glyph-color

**Tipo:** color

The color of the glyph icon for the default-toolbar button UI ...

The color of the glyph icon for the `default-toolbar` button UI
Defaults to: `$button-toolbar-color`


### $button-toolbar-glyph-opacity

**Tipo:** color

The opacity of the glyph icon for the default-toolbar button UI ...

The opacity of the glyph icon for the `default-toolbar` button UI
Defaults to: `.5`


### $button-toolbar-include-split-noline-arrows

**Tipo:** boolean

True to include "noline" split arrows for toolbar buttons in their default state. ...

True to include "noline" split arrows for toolbar buttons in their default state.
Defaults to: `false`


### $button-toolbar-inner-opacity-disabled

**Tipo:** number

opacity to apply to the toolbar button's inner elements (icon and text) when the buton is disabled ...

opacity to apply to the toolbar button's inner elements (icon and text) when the buton is disabled
Defaults to: `1`


### $button-toolbar-opacity-disabled

**Tipo:** number

opacity to apply to the toolbar button's main element when the buton is disabled ...

opacity to apply to the toolbar button's main element when the buton is disabled
Defaults to: `.5`


### $include-button-default-large-ui

**Tipo:** boolean

True to include the "default" button UI for "large" scale buttons ...

True to include the "default" button UI for "large" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-medium-ui

**Tipo:** boolean

True to include the "default" button UI for "medium" scale buttons ...

True to include the "default" button UI for "medium" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-small-ui

**Tipo:** boolean

True to include the "default" button UI for "small" scale buttons ...

True to include the "default" button UI for "small" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-toolbar-large-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "large" scale buttons ...

True to include the "default-toolbar" button UI for "large" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-medium-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "medium" scale buttons ...

True to include the "default-toolbar" button UI for "medium" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-small-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "small" scale buttons ...

True to include the "default-toolbar" button UI for "small" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI ...

True to include the "default-toolbar" button UI
Defaults to: `$include-default-uis`


### $include-button-default-ui

**Tipo:** boolean

True to include the "default" button UI ...

True to include the "default" button UI
Defaults to: `$include-default-uis`


### extjs-button-ui

Creates a visual theme for a Button ...

Creates a visual theme for a Button
$ui : stringThe name of the UI being created. Can not included spaces or special punctuation
(used in CSS class names).


## Properties

### $className

**Tipo:** String

...

Defaults to: `'Ext.Base'`


### _alignRe

**Tipo:** RegExp

...

Defaults to: `/^([a-z]+)-([a-z]+)(\?)?$/`


### _isLayoutRoot

**Tipo:** Boolean

Setting this property to true causes the isLayoutRoot method to return
true and stop the search for the top-most comp...

Setting this property to `true` causes the isLayoutRoot method to return
`true` and stop the search for the top-most component for a layout.
Defaults to: `false`


### _positionTopLeft

**Tipo:** Array

...

Defaults to: `['position', 'top', 'left']`


### _triggerRegion

**Tipo:** Object

A reusable object used by getTriggerRegion to avoid excessive object creation. ...

A reusable object used by getTriggerRegion to avoid excessive object creation.
Defaults to: `{}`


### allowDomMove

**Tipo:** Boolean

...

Defaults to: `true`


### allowedScales

**Tipo:** Array

An array of allowed scales. ...

An array of allowed scales.
Defaults to: `['small', 'medium', 'large']`


### autoGenId

**Tipo:** Boolean

true indicates an id was auto-generated rather than provided by configuration. ...

`true` indicates an `id` was auto-generated rather than provided by configuration.
Defaults to: `false`


### borderBoxCls

**Tipo:** String

private ...

private
Defaults to: `Ext.baseCSSPrefix + 'border-box'`


### bubbleEvents

**Tipo:** Array

...

Defaults to: `[]`


### childEls

**Tipo:** Array

...

Defaults to: `[]`


### componentLayoutCounter

**Tipo:** Number

The number of component layout calls made on this object. ...

The number of component layout calls made on this object.
Defaults to: `0`


### configMap

**Tipo:** Object

...

Defaults to: `{}`


### contentPaddingProperty

**Tipo:** String

The name of the padding property that is used by the layout to manage
padding. ...

The name of the padding property that is used by the layout to manage
padding.  See managePadding
Defaults to: `'padding'`


### convertPositionSpec

**Tipo:** Object

By default this method does nothing but return the position spec passed to it. ...

By default this method does nothing but return the position spec passed to it. In
rtl mode it is overridden to convert "l" to "r" and vice versa when required.


### defaultComponentLayoutType

**Tipo:** String

...

Defaults to: `'autocomponent'`


### deferLayouts

**Tipo:** Boolean

...

Defaults to: `false`


### disabled

**Tipo:** Boolean

True if this button is disabled. ...

True if this button is disabled.
Defaults to: `false`


### draggable

**Tipo:** Boolean

Indicates whether or not the component can be dragged. ...

Indicates whether or not the component can be dragged.
Defaults to: `false`


### eventsSuspended

**Tipo:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called.
Defaults to: `0`


### floatParent

**Tipo:** Ext.Container

Only present for floating Components which were inserted as child items of Containers. ...

**Only present for floating Components which were inserted as child items of Containers.**

There are other similar relationships such as the button which activates a menu, or the
menu item which activated a submenu, or the
column header which activated the column menu.

These differences are abstracted away by the up method.

Floating Components that are programatically rendered will not have a `floatParent`
property.

See floating and zIndexManager


### frameCls

**Tipo:** String

...

Defaults to: `Ext.baseCSSPrefix + 'frame'`


### frameElNames

**Tipo:** Array

...

Defaults to: `['TL', 'TC', 'TR', 'ML', 'MC', 'MR', 'BL', 'BC', 'BR']`


### frameElementsArray

**Tipo:** Array

...

Defaults to: `['tl', 'tc', 'tr', 'ml', 'mc', 'mr', 'bl', 'bc', 'br']`


### frameIdRegex

**Tipo:** RegExp

...

Defaults to: `/[\-]frame\d+[TMB][LCR]$/`


### frameInfoCache

**Tipo:** Object

Cache the frame information object so as not to cause style recalculations ...

Cache the frame information object so as not to cause style recalculations
Defaults to: `{}`


### frameSize

**Tipo:** Object

Indicates the width of any framing elements which were added within the encapsulating
element to provide graphical, r...

Indicates the width of any framing elements which were added within the encapsulating
element to provide graphical, rounded borders. See the frame config. This
property is `null` if the component is not framed.

This is an object containing the frame width in pixels for all four sides of the
Component containing the following properties:
top : Number (optional)The width of the top framing element in pixels.
Defaults to: `0`


### frameTableTpl

**Tipo:** Object


### frameTpl

**Tipo:** Array

...

Defaults to: `['{%this.renderDockedItems(out,values,0);%}', '<tpl if="top">', '<tpl if="left"><div id="{fgid}TL" class="{frameCls}-tl {baseCls}-tl {baseCls}-{ui}-tl<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-tl</tpl>{frameElCls}" role="presentation"></tpl>', '<tpl if="right"><div id="{fgid}TR" class="{frameCls}-tr {baseCls}-tr {baseCls}-{ui}-tr<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-tr</tpl>{frameElCls}" role="presentation"></tpl>', '<div id="{fgid}TC" class="{frameCls}-tc {baseCls}-tc {baseCls}-{ui}-tc<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-tc</tpl>{frameElCls}" role="presentation"></div>', '<tpl if="right"></div></tpl>', '<tpl if="left"></div></tpl>', '</tpl>', '<tpl if="left"><div id="{fgid}ML" class="{frameCls}-ml {baseCls}-ml {baseCls}-{ui}-ml<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-ml</tpl>{frameElCls}" role="presentation"></tpl>', '<tpl if="right"><div id="{fgid}MR" class="{frameCls}-mr {baseCls}-mr {baseCls}-{ui}-mr<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-mr</tpl>{frameElCls}" role="presentation"></tpl>', '<div id="{fgid}MC" class="{frameCls}-mc {baseCls}-mc {baseCls}-{ui}-mc<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-mc</tpl>{frameElCls}" role="presentation">', '{%this.applyRenderTpl(out, values)%}', '</div>', '<tpl if="right"></div></tpl>', '<tpl if="left"></div></tpl>', '<tpl if="bottom">', '<tpl if="left"><div id="{fgid}BL" class="{frameCls}-bl {baseCls}-bl {baseCls}-{ui}-bl<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-bl</tpl>{frameElCls}" role="presentation"></tpl>', '<tpl if="right"><div id="{fgid}BR" class="{frameCls}-br {baseCls}-br {baseCls}-{ui}-br<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-br</tpl>{frameElCls}" role="presentation"></tpl>', '<div id="{fgid}BC" class="{frameCls}-bc {baseCls}-bc {baseCls}-{ui}-bc<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-bc</tpl>{frameElCls}" role="presentation"></div>', '<tpl if="right"></div></tpl>', '<tpl if="left"></div></tpl>', '</tpl>', '{%this.renderDockedItems(out,values,1);%}']`


### hasListeners

**Tipo:** Object

This object holds a key for any event that has a listener. ...

This object holds a key for any event that has a listener. The listener may be set
directly on the instance, or on its class or a super class (via observe) or
on the MVC EventBus. The values of this object are truthy
(a non-zero number) and falsy (0 or undefined). They do not represent an exact count
of listeners. The value for an event is truthy if the event must be fired and is
falsy if there is no need to fire the event.

The intended use of this property is to avoid the expense of fireEvent calls when
there are no listeners. This can be particularly helpful when one would otherwise
have to call fireEvent hundreds or thousands of times. It is used like this:

 if (this.hasListeners.foo) {
     this.fireEvent('foo', this, arg1);
 }


### hidden

**Tipo:** Boolean

True if this button is hidden. ...

True if this button is hidden.
Defaults to: `false`


### horizontalPosProp

**Tipo:** String

...

Defaults to: `'left'`


### initConfigList

**Tipo:** Array

...

Defaults to: `[]`


### initConfigMap

**Tipo:** Object

...

Defaults to: `{}`


### isAction

**Tipo:** Boolean

`true` in this class to identify an object as an instantiated Button, or subclass thereof.


### isAnimate

**Tipo:** Boolean

...

Defaults to: `true`


### isComponent

**Tipo:** Boolean

true in this class to identify an object as an instantiated Component, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Component, or subclass thereof.
Defaults to: `true`


### isInstance

**Tipo:** Boolean

...

Defaults to: `true`


### isObservable

**Tipo:** Boolean

true in this class to identify an object as an instantiated Observable, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Observable, or subclass thereof.
Defaults to: `true`


### isQueryable

**Tipo:** Boolean

...

Defaults to: `true`


### layoutSuspendCount

**Tipo:** Number

...

Defaults to: `0`


### maskOnDisable

**Tipo:** Boolean

This is an internal flag that you use when creating custom components. ...

This is an internal flag that you use when creating custom components. By default this is set to `true` which means
that every component gets a mask when it's disabled. Components like FieldContainer, FieldSet, Field, Button, Tab
override this property to `false` since they want to implement custom disable logic.
Defaults to: `true`


### menu

**Tipo:** Ext.menu.Menu

The Menu object associated with this Button when configured with the menu config
option.


### offsetsCls

**Tipo:** String

...

Defaults to: `Ext.baseCSSPrefix + 'hide-offsets'`


### ownerCt

**Tipo:** Ext.Container

This Component's owner Container (is set automatically
when this Component is added to a Container). ...

This Component's owner Container (is set automatically
when this Component is added to a Container).

*Important.* This is not a universal upwards navigation pointer. It indicates the Container which owns and manages
this Component if any. There are other similar relationships such as the button which activates a menu, or the
menu item which activated a submenu, or the
column header which activated the column menu.

These differences are abstracted away by the up method.

**Note**: to access items within the Container see itemId.
        Available since: 2.3.0


### pressed

**Tipo:** Boolean

True if this button is pressed (only if enableToggle = true). ...

True if this button is pressed (only if enableToggle = true).
Defaults to: `false`


### rendered

**Tipo:** Boolean

Indicates whether or not the component has been rendered. ...

Indicates whether or not the component has been rendered.
Defaults to: `false`        Available since: 1.1.0


### scrollFlags

**Tipo:** Object

An object property which provides unified information as to which dimensions are scrollable based upon
the autoScroll...

An object property which provides unified information as to which dimensions are scrollable based upon
the autoScroll, overflowX and overflowY settings (And for *views* of trees and grids, the owning panel's scroll setting).

Note that if you set overflow styles using the style config or bodyStyle config, this object does not include that information;
it is best to use autoScroll, overflowX and overflowY if you need to access these flags.

This object has the following properties:
x : Boolean`true` if this Component is scrollable horizontally - style setting may be `'auto'` or `'scroll'`.


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


### split

**Tipo:** Boolean

...

Defaults to: `true`


### template

**Tipo:** Ext.Template

A Template used to create the Button's DOM structure. ...

A Template used to create the Button's DOM structure.

Instances, or subclasses which need a different DOM structure may provide a different template layout in
conjunction with an implementation of getTemplateArgs.


### weight

**Tipo:** Number

...

Defaults to: `0`


### zIndexManager

**Tipo:** Ext.ZIndexManager

Only present for floating Components after they have been rendered. ...

Only present for floating Components after they have been rendered.

A reference to the ZIndexManager which is managing this Component's z-index.

The ZIndexManager maintains a stack of floating Component z-indices, and also provides
a single modal mask which is insert just beneath the topmost visible modal floating Component.

Floating Components may be brought to the front or sent to the back of the
z-index stack.

This defaults to the global ZIndexManager for floating Components that are
programatically rendered.

For floating Components which are added to a Container, the ZIndexManager is acquired from the first
ancestor Container found which is floating. If no floating ancestor is found, the global ZIndexManager is
used.

See floating and zIndexParent


### zIndexParent

**Tipo:** Ext.Container

Only present for floating Components which were inserted as child items of Containers, and which have a floating
Cont...

Only present for floating Components which were inserted as child items of Containers, and which have a floating
Container in their containment ancestry.

For floating Components which are child items of a Container, the zIndexParent will be a floating
ancestor Container which is responsible for the base z-index value of all its floating descendants. It provides
a ZIndexManager which provides z-indexing services for all its descendant floating
Components.

Floating Components that are programatically rendered will not have a `zIndexParent`
property.

For example, the dropdown BoundList of a ComboBox which is in a Window will have the
Window as its `zIndexParent`, and will always show above that Window, wherever the Window is placed in the z-index stack.

See floating and zIndexManager


### $onExtended

**Tipo:** Array

...

Defaults to: `[]`


### Ext.button.Split

Creates new Component. ...

Creates new Component.
Parametersconfig : Ext.Element/String/ObjectThe configuration options may be specified as either:





**an element** : it is set as the internal element and its id used as the component id
**a string** : it is assumed to be the id of an existing element and is used as the component id
**anything else** : it is assumed to be a standard config object and is applied to the component


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### addClass

Adds a CSS class to the top level element representing this component. ...

Adds a CSS class to the top level element representing this component.
        
        This method has been **deprecated** since 4.1
        Use addCls instead.


### addCls

Adds a CSS class to the top level element representing this component. ...

Adds a CSS class to the top level element representing this component.
Parameterscls : String/String[]The CSS class name to add.


### addClsWithUI

Adds a cls to the uiCls array, which will also call addUIClsToElement and adds to all elements of this
component. ...

Adds a `cls` to the `uiCls` array, which will also call addUIClsToElement and adds to all elements of this
component.
Parametersclasses : String/String[]A string or an array of strings to add to the `uiCls`.


### addEvents

Adds the specified events to the list of events which this Observable may fire. ...

Adds the specified events to the list of events which this Observable may fire.
ParameterseventNames : Object/String...Either an object with event names as properties with
a value of `true`. For example:

this.addEvents({
    storeloaded: true,
    storecleared: true
});


Or any number of event names as separate parameters. For example:

this.addEvents('storeloaded', 'storecleared');


### addFocusListener

Sets up the focus listener on this Component's focusEl if it has one. ...

Sets up the focus listener on this Component's focusEl if it has one.

Form Components which must implicitly participate in tabbing order usually have a naturally focusable
element as their focusEl, and it is the DOM event of that receiving focus which drives
the Component's `onFocus` handling, and the DOM event of it being blurred which drives the `onBlur` handling.

If the focusEl is **not** naturally focusable, then the listeners are only added
if the FocusManager is enabled.


### addListener

Appends an event handler to this object. ...

Appends an event handler to this object.  For example:

myGridPanel.on("mouseover", this.onMouseOver, this);


The method also allows for a single argument to be passed which is a config object
containing properties which specify multiple events. For example:

myGridPanel.on({
    cellClick: this.onCellClick,
    mouseover: this.onMouseOver,
    mouseout: this.onMouseOut,
    scope: this // Important. Ensure "this" is correct during handler execution
});


One can also specify options for each event handler separately:

myGridPanel.on({
    cellClick: {fn: this.onCellClick, scope: this, single: true},
    mouseover: {fn: panel.onMouseOver, scope: panel}
});


*Names* of methods in a specified scope may also be used. Note that
`scope` MUST be specified to use this option:

myGridPanel.on({
    cellClick: {fn: 'onCellClick', scope: this, single: true},
    mouseover: {fn: 'onMouseOver', scope: panel}
});

ParameterseventName : String/ObjectThe name of the event to listen for.
May also be an object who's property names are event names.


### addManagedListener

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destr...

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destroyed.
Parametersitem : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### addOverCls

...

Overrides: Ext.AbstractComponent.addOverCls


### addPlugin

Adds a plugin. ...

Adds a plugin. May be called at any time in the component's lifecycle.
Parametersplugin : Object


### addPropertyToState

Save a property to the given state object if it is not its default or configured
value. ...

Save a property to the given state object if it is not its default or configured
value.
Parametersstate : ObjectThe state object.


### addStateEvents

Add events that will trigger the state to be saved. ...

Add events that will trigger the state to be saved. If the first argument is an
array, each element of that array is the name of a state event. Otherwise, each
argument passed to this method is the name of a state event.
Parametersevents : String/String[]The event name or an array of event names.


### addUIClsToElement

Method which adds a specified UI + uiCls to the components element. ...

Method which adds a specified UI + `uiCls` to the components element. Can be overridden to remove the UI from more
than just the components element.
Parametersui : StringThe UI to remove from the element.


### addUIToElement

Method which adds a specified UI to the components element. ...

Method which adds a specified UI to the components element.


### adjustForConstraints

private ==>  used outside of core
TODO: currently only used by ToolTip. ...

private ==>  used outside of core
TODO: currently only used by ToolTip. does this method belong here?
Parametersxy : Object


### adjustPosition

...

Parametersx : Object


### afterComponentLayout

Called by the layout system after the Component has been laid out. ...

Called by the layout system after the Component has been laid out.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### afterFirstLayout

...

Parameterswidth : Object


### afterHide

Invoked after the Component has been hidden. ...

Invoked after the Component has been hidden.

Gets passed the same `callback` and `scope` parameters that onHide received.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### afterRender

Allows addition of behavior after rendering is complete. ...

Allows addition of behavior after rendering is complete. At this stage the Component’s Element
will have been styled according to the configuration, will have had any configured CSS class
names added, and will be in the configured visibility and the configured enable state.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### afterSetPosition

Template method called after a Component has been positioned. ...

Template method called after a Component has been positioned.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### afterShow

Invoked after the Component is shown (after onShow is called). ...

Invoked after the Component is shown (after onShow is called).

Gets passed the same parameters as show.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### alignTo

Aligns the element with another element relative to the specified anchor points. ...

Aligns the element with another element relative to the specified anchor points. If
the other element is the document it aligns it to the viewport. The position
parameter is optional, and can be specified in any one of the following formats:


**Blank**: Defaults to aligning the element's top-left corner to the target's
bottom-left corner ("tl-bl").
**One anchor (deprecated)**: The passed anchor position is used as the target
element's anchor point.  The element being aligned will position its top-left
corner (tl) to that point. This method has been deprecated in favor of the newer
two anchor syntax below.
**Two anchors**: If two values from the table below are passed separated by a dash,
the first value is used as the element's anchor point, and the second value is
used as the target's anchor point.



In addition to the anchor points, the position parameter also supports the "?"
character. If "?" is passed at the end of the position string, the element will
attempt to align as specified, but the position will be adjusted to constrain to
the viewport if necessary. Note that the element being aligned might be swapped to
align to a different position than that specified in order to enforce the viewport
constraints. Following are all of the supported anchor positions:

Value  Description
-----  -----------------------------
tl     The top left corner (default)
t      The center of the top edge
tr     The top right corner
l      The center of the left edge
c      In the center of the element
r      The center of the right edge
bl     The bottom left corner
b      The center of the bottom edge
br     The bottom right corner



Example Usage:

// align el to other-el using the default positioning
// ("tl-bl", non-constrained)
el.alignTo("other-el");

// align the top left corner of el with the top right corner of other-el
// (constrained to viewport)
el.alignTo("other-el", "tr?");

// align the bottom right corner of el with the center left edge of other-el
el.alignTo("other-el", "br-l?");

// align the center of el with the bottom left corner of other-el and
// adjust the x position by -6 pixels (and the y position by 0)
el.alignTo("other-el", "c-bl", [-6, 0]);

Parameterselement : Ext.util.Positionable/HTMLElement/StringThe Positionable,
HTMLElement, or id of the element to align to.


### anchorTo

Anchors an element to another element and realigns it when the window is resized. ...

Anchors an element to another element and realigns it when the window is resized.
Parameterselement : Ext.util.Positionable/HTMLElement/StringThe Positionable,
HTMLElement, or id of the element to align to.


### anim

process the passed fx configuration. ...

process the passed fx configuration.


Parametersconfig : Object


### animate

Performs custom animation on this object. ...

Performs custom animation on this object.

This method is applicable to both the Component class and the Sprite
class. It performs animated transitions of certain properties of this object over a specified timeline.

Animating a Component

When animating a Component, the following properties may be specified in `from`, `to`, and `keyframe` objects:


`x` - The Component's page X position in pixels.
`y` - The Component's page Y position in pixels
`left` - The Component's `left` value in pixels.
`top` - The Component's `top` value in pixels.
`width` - The Component's `width` value in pixels.
`height` - The Component's `height` value in pixels.
`dynamic` - Specify as true to update the Component's layout (if it is a Container) at every frame of the animation.
*Use sparingly as laying out on every intermediate size change is an expensive operation.*



For example, to animate a Window to a new size, ensuring that its internal layout and any shadow is correct:

myWindow = Ext.create('Ext.window.Window', {
    title: 'Test Component animation',
    width: 500,
    height: 300,
    layout: {
        type: 'hbox',
        align: 'stretch'
    },
    items: [{
        title: 'Left: 33%',
        margins: '5 0 5 5',
        flex: 1
    }, {
        title: 'Left: 66%',
        margins: '5 5 5 5',
        flex: 2
    }]
});
myWindow.show();
myWindow.header.el.on('click', function() {
    myWindow.animate({
        to: {
            width: (myWindow.getWidth() == 500) ? 700 : 500,
            height: (myWindow.getHeight() == 300) ? 400 : 300
        }
    });
});


For performance reasons, by default, the internal layout is only updated when the Window reaches its final `"to"`
size. If dynamic updating of the Window's child Components is required, then configure the animation with
`dynamic: true` and the two child items will maintain their proportions during the animation.
Parametersconfig : ObjectConfiguration for Ext.fx.Anim.
Note that the to config is required.


### applyChildEls

Sets references to elements inside the component. ...

Sets references to elements inside the component.
Parametersel : Object


### applyRenderSelectors

Sets references to elements inside the component. ...

Sets references to elements inside the component. This applies renderSelectors
as well as childEls.


### applyState

Applies the state to the object. ...

Applies the state to the object. This should be overridden in subclasses to do
more complex state operations. By default it applies the state properties onto
the current object.
Parametersstate : ObjectThe state


### beforeBlur

Template method to do any pre-blur processing. ...

Template method to do any pre-blur processing.
Parameterse : Ext.EventObjectThe event object


### beforeComponentLayout

Occurs before componentLayout is run. ...

Occurs before `componentLayout` is run. Returning `false` from this method will prevent the `componentLayout` from
being executed.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### beforeDestroy

Invoked before the Component is destroyed. ...

Invoked before the Component is destroyed.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### beforeFocus

Template method to do any pre-focus processing. ...

Template method to do any pre-focus processing.
Parameterse : Ext.EventObjectThe event object


### beforeLayout

Occurs before componentLayout is run. ...

Occurs before componentLayout is run. In previous releases, this method could
return `false` to prevent its layout but that is not supported in Ext JS 4.1 or
higher. This method is simply a notification of the impending layout to give the
component a chance to adjust the DOM. Ideally, DOM reads should be avoided at this
time to reduce expensive document reflows.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### beforeRender

...

Overrides: Ext.Component.beforeRender


### beforeSetPosition

Template method called before a Component is positioned. ...

Template method called before a Component is positioned.

Ensures that the position is adjusted so that the Component is constrained if so configured.
Parametersx : Object


### beforeShow

Invoked before the Component is shown. ...

Invoked before the Component is shown.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### blur

...

ReturnsExt.Componentthis


### bubble

Bubbles up the component/container heirarchy, calling the specified function with each component. ...

Bubbles up the component/container heirarchy, calling the specified function with each component. The scope
(*this*) of function call will be the scope provided or the current component. The arguments to the function will
be the args provided or the current component. If the function returns false at any point, the bubble is stopped.
Parametersfn : FunctionThe function to call


### calculateAnchorXY

Calculates x,y coordinates specified by the anchor position on the element, adding
extraX and extraY values. ...

Calculates x,y coordinates specified by the anchor position on the element, adding
extraX and extraY values.
Parametersanchor : String (optional)The specified anchor position.
See alignTo for details on supported anchor positions.
Defaults to: `'tl'`


### calculateConstrainedPosition

Calculates the new [x,y] position to move this Positionable into a constrain region. ...

Calculates the new [x,y] position to move this Positionable into a constrain region.

By default, this Positionable is constrained to be within the container it was added to, or the element it was
rendered to.

Priority is given to constraining the top and left within the constraint.

An alternative constraint may be passed.
ParametersconstrainTo : String/HTMLElement/Ext.Element/Ext.util.Region (optional)The Element or Region
into which this Component is to be constrained. Defaults to the element into which this Positionable
was rendered, or this Component's {@link Ext.Component.constrainTo.


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


### cancelFocus

Cancel any deferred focus on this component ...

Cancel any deferred focus on this component


### captureArgs

...

Parameterso : Object


### center

Center this Component in its container. ...

Center this Component in its container.
ReturnsExt.Componentthis


### child

Retrieves the first direct child of this container which matches the passed selector or component. ...

Retrieves the first direct child of this container which matches the passed selector or component.
The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.
Parametersselector : String/Ext.Component (optional)An Ext.ComponentQuery selector. If no selector is
specified, the first child will be returned.


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### clearTip

...


### cloneConfig

Clone the current component using the original config values passed into this instance by default. ...

Clone the current component using the original config values passed into this instance by default.
Parametersoverrides : ObjectA new config containing any properties to override in the cloned version.
An id property can be passed on this object, otherwise one will be generated to avoid duplicates.


### configClass

...


### constructPlugin

...

Parametersptype : String/Objectstring or config object containing a ptype property.

Constructs a plugin according to the passed config object/ptype string.

Ensures that the constructed plugin always has a `cmp` reference back to this component.
The setting up of this is done in PluginManager. The PluginManager ensures that a reference to this
component is passed to the constructor. It also ensures that the plugin's `setCmp` method (if any) is called.


### constructPlugins

Returns an array of fully constructed plugin instances. ...

Returns an array of fully constructed plugin instances. This converts any configs into their
appropriate instances.

It does not mutate the plugins array. It creates a new array.


### continueFireEvent

Continue to fire event. ...

Continue to fire event.
ParameterseventName : String


### convertPositionSpec

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**
ParametersposSpec : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.
ParametersnewName : StringThe name under which to refire the passed parameters.


### deleteMembers

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### didIconStateChange

Checks if the icon/iconCls changed from being empty to having a value, or having a value to being empty. ...

Checks if the icon/iconCls changed from being empty to having a value, or having a value to being empty.
Parametersold : StringThe old icon/iconCls


### disable

inherit docs

Disable the component. ...

inherit docs

Disable the component.
        Available since: 1.1.0
Parameterssilent : Boolean (optional)Passing `true` will suppress the `disable` event from being fired.
Defaults to: `false`


### doApplyRenderTpl

Called from the selected frame generation template to insert this Component's inner structure inside the framing stru...

Called from the selected frame generation template to insert this Component's inner structure inside the framing structure.

When framing is used, a selected frame generation template is used as the primary template of the getElConfig instead
of the configured renderTpl. The renderTpl is invoked by this method which is injected into the framing template.
Parametersout : Object


### doAutoRender

Handles autoRender. ...

Handles autoRender.
Floating Components may have an ownerCt. If they are asking to be constrained, constrain them within that
ownerCt, and have their z-index managed locally. Floating Components are always rendered to document.body


### doComponentLayout

This method needs to be called whenever you change something on this component that requires the Component's
layout t...

This method needs to be called whenever you change something on this component that requires the Component's
layout to be recalculated.
ReturnsExt.container.Containerthis


### doConstrain

Moves this floating Component into a constrain region. ...

Moves this floating Component into a constrain region.

By default, this Component is constrained to be within the container it was added to, or the element it was
rendered to.

An alternative constraint may be passed.
ParametersconstrainTo : String/HTMLElement/Ext.Element/Ext.util.Region (optional)The Element or Region
into which this Component is to be constrained. Defaults to the element into which this floating Component
was rendered.


### doRenderContent

...

Parametersout : Object


### doRenderFramingDockedItems

...

Parametersout : Object


### doToggle

...


### down

Retrieves the first descendant of this container which matches the passed selector. ...

Retrieves the first descendant of this container which matches the passed selector.
The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.
Parametersselector : String/Ext.Component (optional)An Ext.ComponentQuery selector or Ext.Component. If no selector is
specified, the first child will be returned.


### enable

inherit docs

Enable the component ...

inherit docs

Enable the component
        Available since: 1.1.0
Parameterssilent : Boolean (optional)Passing `true` will suppress the `enable` event from being fired.
Defaults to: `false`


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if
present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if
present. There is no implementation in the Observable base class.

This is commonly used by Ext.Components to bubble events to owner Containers.
See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the
Component's immediate owner. But if a known target is required, this can be overridden to access the
required target more quickly.

Example:

Ext.define('Ext.overrides.form.field.Base', {
    override: 'Ext.form.field.Base',

    //  Add functionality to Field's initComponent to enable the change event to bubble
    initComponent: function () {
        this.callParent();
        this.enableBubble('change');
    }
});

var myForm = Ext.create('Ext.form.Panel', {
    title: 'User Details',
    items: [{
        ...
    }],
    listeners: {
        change: function() {
            // Title goes red if form has been modified.
            myForm.header.setStyle('color', 'red');
        }
    }
});

ParameterseventNames : String/String[]The event name to bubble, or an Array of event names.


### ensureAttachedToBody

Ensures that this component is attached to document.body. ...

Ensures that this component is attached to `document.body`. If the component was
rendered to Ext.getDetachedBody, then it will be appended to `document.body`.
Any configured position is also restored.
ParametersrunLayout : Boolean (optional)True to run the component's layout.
Defaults to: `false`


### findParentBy

Find a container above this component at any level by a custom function. ...

Find a container above this component at any level by a custom function. If the passed function returns true, the
container will be returned.

See also the up method.
Parametersfn : FunctionThe custom function to call with the arguments (container, this component).


### findParentByType

Find a container above this component at any level by xtype or class

See also the up method. ...

Find a container above this component at any level by xtype or class

See also the up method.
Parametersxtype : String/Ext.ClassThe xtype string for a component, or the class of the component directly


### findPlugin

Retrieves plugin from this component's collection by its ptype. ...

Retrieves plugin from this component's collection by its `ptype`.
Parametersptype : StringThe Plugin's ptype as specified by the class's `alias` configuration.


### finishRender

This method visits the rendered component tree in a "top-down" order. ...

This method visits the rendered component tree in a "top-down" order. That is, this
code runs on a parent component before running on a child. This method calls the
onRender method of each component.
ParameterscontainerIdx : NumberThe index into the Container items of this Component.


### finishRenderChildren

...


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed
to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed
to addListener).

An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by
calling enableBubble.
ParameterseventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list.

An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by
calling enableBubble.
ParameterseventName : StringThe name of the event to fire.


### fireHandler

...

Parameterse : Object


### fireHierarchyEvent

For more information on the hierarchy events, see the note for the
hierarchyEventSource observer defined in the onCla...

For more information on the hierarchy events, see the note for the
hierarchyEventSource observer defined in the onClassCreated callback.

This functionality is contained in Component (as opposed to Container)
because a Component can be the ownerCt for a floating component (loadmask),
and the loadmask needs to know when its owner is shown/hidden via the
hierarchyEventSource so that its hidden state can be synchronized.

TODO: merge this functionality with Ext.globalEvents
Parametersename : Object


### fitContainer

...

Parametersanimate : Object


### focus

Try to focus this component. ...

Try to focus this component.
ParametersselectText : Boolean (optional)If applicable, true to also select the text in this component


### forceComponentLayout

Forces this component to redo its componentLayout. ...

Forces this component to redo its componentLayout.
        
        This method has been **deprecated** since 4.1.0
        Use updateLayout instead.


### getActionEl

inherit docs ...

inherit docs
Overrides: Ext.Component.getActionEl


### getActiveAnimation

Returns the current animation if this object has any effects actively running or queued, else returns false. ...

Returns the current animation if this object has any effects actively running or queued, else returns false.
ReturnsExt.fx.Anim/BooleanAnim if element has active effects, else false


### getAlignToXY

Gets the x,y coordinates to align this element with another element. ...

Gets the x,y coordinates to align this element with another element. See
alignTo for more info on the supported position values.
Parameterselement : Ext.util.Positionable/HTMLElement/StringThe Positionable,
HTMLElement, or id of the element to align to.


### getAnchor

private ...

private


### getAnchorToXY

Begin Positionable methods



Overridden in Ext.rtl.AbstractComponent. ...

Begin Positionable methods



**Overridden in Ext.rtl.AbstractComponent.**

Gets the x,y coordinates of an element specified by the anchor position on the
element.
Parametersel : Ext.dom.ElementThe element


### getAnchorXY

Gets the x,y coordinates specified by the anchor position on the element. ...

Gets the x,y coordinates specified by the anchor position on the element.
Parametersanchor : String (optional)The specified anchor position.
See alignTo for details on supported anchor positions.
Defaults to: `'tl'`


### getAnimateTarget

...

Parameterstarget : Object


### getAutoId

...


### getBorderPadding

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Returns the size of the element's borders and padding.
ReturnsObjectan object with the following numeric properties
- beforeX
- afterX
- beforeY
- afterY


### getBox

Return an object defining the area of this Element which can be passed to
setBox to set another Element's size/locati...

Return an object defining the area of this Element which can be passed to
setBox to set another Element's size/location to match this element.
ParameterscontentBox : Boolean (optional)If true a box for the content of the element is
returned.


### getBtnWrapFrameWidth

...

Parametersside : Object


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable
ReturnsExt.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getBubbleTarget

Implements an upward event bubbling policy. ...

Implements an upward event bubbling policy. By default a Component bubbles events up to its reference owner.

Component subclasses may implement a different bubbling strategy by overriding this method.
Overrides: Ext.AbstractComponent.getBubbleTarget


### getChildEls

...


### getClassChildEls

...

Parameterscls : Object


### getComponentCls

...


### getComponentLayout

...


### getConfig

...

Parametersname : Object


### getConstrainVector

Returns the [X, Y] vector by which this Positionable's element must be translated to make a best
attempt to constrain...

Returns the `[X, Y]` vector by which this Positionable's element must be translated to make a best
attempt to constrain within the passed constraint. Returns `false` if the element
does not need to be moved.

Priority is given to constraining the top and left within the constraint.

The constraint may either be an existing element into which the element is to be
constrained, or a Region into which this element is to be
constrained.

By default, any extra shadow around the element is **not** included in the constrain calculations - the edges
of the element are used as the element bounds. To constrain the shadow within the constrain region, set the
`constrainShadow` property on this element to `true`.
ParametersconstrainTo : Ext.util.Positionable/HTMLElement/String/Ext.util.Region (optional)The
Positionable, HTMLElement, element id, or Region into which the element is to be
constrained.


### getContentTarget

...


### getDragEl

...


### getEl

Retrieves the top level element representing this component. ...

Retrieves the top level element representing this component.
        Available since: 1.1.0
ReturnsExt.dom.Element


### getElConfig

...


### getFocusEl

inherit docs

Returns the focus holder element associated with this Component. ...

inherit docs

Returns the focus holder element associated with this Component. At the Component base class level, this function returns `undefined`.

Subclasses which use embedded focusable elements (such as Window, Field and Button) should override this
for use by the focus method.

Containers which need to participate in the FocusManager's navigation and Container focusing scheme also
need to return a `focusEl`, although focus is only listened for in this case if the FocusManager is enabled.
Overrides: Ext.AbstractComponent.getFocusEl


### getFrameInfo

On render, reads an encoded style attribute, "filter" from the style of this Component's element. ...

On render, reads an encoded style attribute, "filter" from the style of this Component's element.
This information is memoized based upon the CSS class name of this Component's element.
Because child Components are rendered as textual HTML as part of the topmost Container, a dummy div is inserted
into the document to receive the document element's CSS class name, and therefore style attributes.


### getFrameRenderData

...


### getFrameTpl

...

Parameterstable : Object


### getFramingInfoCls

...


### getHeight

Gets the current height of the component's underlying element. ...

Gets the current height of the component's underlying element.
ReturnsNumber


### getHierarchyState

A component's hierarchyState is used to keep track of aspects of a component's
state that affect its descendants hier...

A component's hierarchyState is used to keep track of aspects of a component's
state that affect its descendants hierarchically like "collapsed" and "hidden".
For example, if this.hierarchyState.hidden == true, it means that either this
component, or one of its ancestors is hidden.

Hierarchical state management is implemented by chaining each component's
hierarchyState property to its parent container's hierarchyState property via the
prototype. The result is such that if a component's hierarchyState does not have
it's own property, it inherits the property from the nearest ancestor that does.

To set a hierarchical "hidden" value:

this.getHierarchyState().hidden = true;


It is important to remember when unsetting hierarchyState properties to delete
them instead of just setting them to a falsy value.  This ensures that the
hierarchyState returns to a state of inheriting the value instead of overriding it
To unset the hierarchical "hidden" value:

delete this.getHierarchyState().hidden;


IMPORTANT! ALWAYS access hierarchyState using this method, not by accessing
this.hierarchyState directly.  The hierarchyState property does not exist until
the first time getHierarchyState() is called.  At that point getHierarchyState()
walks up the component tree to establish the hierarchyState prototype chain.
Additionally the hierarchyState property should NOT be relied upon even after
the initial call to getHierarchyState() because  it is possible for the
hierarchyState to be invalidated. Invalidation typically happens when a component
is moved to a new container. In such a case the hierarchy state remains invalid
until the next time getHierarchyState() is called on the component or one of its
descendants.
Parametersinner : Object


### getHref

If there is a configured href for this Button, returns the href with parameters appended. ...

If there is a configured href for this Button, returns the href with parameters appended.
ReturnsString/BooleanThe href string with parameters appended.


### getId

Retrieves the id of this component. ...

Retrieves the `id` of this component. Will auto-generate an `id` if one has not already been set.
ReturnsString


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### getInnerCls

...


### getInsertPosition

This function takes the position argument passed to onRender and returns a
DOM element that you can use in the insert...

This function takes the position argument passed to onRender and returns a
DOM element that you can use in the insertBefore.
Parametersposition : String/Number/Ext.dom.Element/HTMLElementIndex, element id or element you want
to put this component before.


### getItemId

Returns the value of itemId assigned to this component, or when that
is not set, returns the value of id. ...

Returns the value of itemId assigned to this component, or when that
is not set, returns the value of id.
ReturnsString


### getLoader

Gets the Ext.ComponentLoader for this Component. ...

Gets the Ext.ComponentLoader for this Component.
ReturnsExt.ComponentLoaderThe loader instance, null if it doesn't exist.


### getLocalX

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Returns the x coordinate of this element reletive to its `offsetParent`.
ReturnsNumberThe local x coordinate


### getLocalXY

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Returns the x and y coordinates of this element relative to its `offsetParent`.
ReturnsNumber[]The local XY position of the element


### getLocalY

Returns the y coordinate of this element reletive to its offsetParent. ...

Returns the y coordinate of this element reletive to its `offsetParent`.
ReturnsNumberThe local y coordinate


### getMaskTarget

...


### getOffsetsTo

Returns the offsets of this element from the passed element. ...

Returns the offsets of this element from the passed element. The element must both
be part of the DOM tree and not have display:none to have page coordinates.
ParametersoffsetsTo : Ext.util.Positionable/HTMLElement/StringThe Positionable,
HTMLElement, or element id to get get the offsets from.


### getOuterSize

Include margins ...

Include margins


### getOverflowEl

Get an el for overflowing, defaults to the target el ...

Get an el for overflowing, defaults to the target el


### getOverflowStyle

Returns the CSS style object which will set the Component's scroll styles. ...

Returns the CSS style object which will set the Component's scroll styles. This must be applied
to the target element.


### getOwningBorderContainer

Returns the owning container if that container uses border layout. ...

Returns the owning container if that container uses `border` layout. Otherwise
this method returns `null`.

**Defined in override Ext.layout.container.border.Region.**
ReturnsExt.container.ContainerThe owning border container or `null`.


### getOwningBorderLayout

Returns the owning border (Ext.layout.container.Border) instance if there is
one. ...

Returns the owning `border` (`Ext.layout.container.Border`) instance if there is
one. Otherwise this method returns `null`.

**Defined in override Ext.layout.container.border.Region.**
ReturnsExt.layout.container.BorderThe owning border layout or `null`.


### getPlugin

Retrieves a plugin from this component's collection by its pluginId. ...

Retrieves a plugin from this component's collection by its `pluginId`.
ParameterspluginId : String


### getPosition

Gets the current XY position of the component's underlying element. ...

Gets the current XY position of the component's underlying element.
Parameterslocal : Boolean (optional)If true the element's left and top are returned instead of page XY.
Defaults to: `false`


### getPositionEl

Deprecate 5.0 ...

Deprecate 5.0


### getProxy

...


### getRefItems

...

Parametersdeep : Object


### getRefOwner

Used by ComponentQuery, and the up method to find the
owning Component in the linkage hierarchy. ...

Used by ComponentQuery, and the up method to find the
owning Component in the linkage hierarchy.

By default this returns the Container which contains this Component.

This may be overriden by Component authors who implement ownership hierarchies which are not
based upon ownerCt, such as BoundLists being owned by Fields or Menus being owned by Buttons.


### getRegion

Returns a region object that defines the area of this element. ...

Returns a region object that defines the area of this element.
ReturnsExt.util.RegionA Region containing "top, left, bottom, right" properties.


### getRenderTree

...


### getResizeEl

Deprecate 5.0 ...

Deprecate 5.0


### getSize

Gets the current size of the component's underlying element. ...

Gets the current size of the component's underlying element.
ReturnsObjectAn object containing the element's size `{width: (element width), height: (element height)}`


### getSizeModel

Returns an object that describes how this component's width and height are managed. ...

Returns an object that describes how this component's width and height are managed.
All of these objects are shared and should not be modified.
ParametersownerCtSizeModel : Object


### getSplitCls

...


### getState

The supplied default state gathering method for the AbstractComponent class. ...

The supplied default state gathering method for the AbstractComponent class.

This method returns dimension settings such as `flex`, `anchor`, `width` and `height` along with `collapsed`
state.

Subclasses which implement more complex state should call the superclass's implementation, and apply their state
to the result if this basic state is to be saved.

Note that Component state will only be saved if the Component has a stateId and there as a StateProvider
configured for the document.
ReturnsObject


### getStateId

Gets the state id for this object. ...

Gets the state id for this object.
ReturnsStringThe 'stateId' or the implicit 'id' specified by component configuration.


### getStyleProxy

Returns an offscreen div with the same class name as the element this is being rendered. ...

Returns an offscreen div with the same class name as the element this is being rendered.
This is because child item rendering takes place in a detached div which, being not
part of the document, has no styling.
Parameterscls : Object


### getTargetEl

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. ...

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component.


### getTemplateArgs

This method returns an object which provides substitution parameters for the XTemplate used to
create this Button's D...

This method returns an object which provides substitution parameters for the XTemplate used to
create this Button's DOM structure.

Instances or subclasses which use a different Template to create a different DOM structure may need to provide
their own implementation of this method.
ReturnsObjectSubstitution data for a Template. The default implementation which provides data for the default
template returns an Object containing the following properties:
innerCls : StringA CSS class to apply to the button's text element.


### getText

Gets the text for this Button ...

Gets the text for this Button
ReturnsStringThe button text


### getTipAttr

...


### getTpl

...

Parametersname : Object


### getTriggerRegion

Returns an object containing begin and end properties that indicate the
left/right bounds of a right trigger or the t...

Returns an object containing `begin` and `end` properties that indicate the
left/right bounds of a right trigger or the top/bottom bounds of a bottom trigger.
ReturnsObject


### getTriggerSize

Measures the size of the trigger area for menu and split buttons. ...

Measures the size of the trigger area for menu and split buttons. Will be a width for
a right-aligned trigger and a height for a bottom-aligned trigger. Cached after first measurement.


### getViewRegion

Returns the content region of this element. ...

Returns the **content** region of this element. That is the region within the borders
and padding.
ReturnsExt.util.RegionA Region containing "top, left, bottom, right" member data.


### getVisibilityEl

Deprecate 5.0 ...

Deprecate 5.0


### getWidth

Gets the current width of the component's underlying element. ...

Gets the current width of the component's underlying element.
ReturnsNumber


### getX

Gets the current X position of the DOM element based on page coordinates. ...

Gets the current X position of the DOM element based on page coordinates.
ReturnsNumberThe X position of the element


### getXType

Gets the xtype for this component as registered with Ext.ComponentManager. ...

Gets the xtype for this component as registered with Ext.ComponentManager. For a list of all available
xtypes, see the Ext.Component header. Example usage:

var t = new Ext.form.field.Text();
alert(t.getXType());  // alerts 'textfield'

ReturnsStringThe xtype


### getXTypes

Returns this Component's xtype hierarchy as a slash-delimited string. ...

Returns this Component's xtype hierarchy as a slash-delimited string. For a list of all available xtypes, see the
Ext.Component header.

If using your own subclasses, be aware that a Component must register its own xtype to participate in
determination of inherited xtypes.

Example usage:

var t = new Ext.form.field.Text();
alert(t.getXTypes());  // alerts 'component/field/textfield'

        Available since: 2.3.0
ReturnsStringThe xtype hierarchy string


### getXY

Gets the current position of the DOM element based on page coordinates. ...

Gets the current position of the DOM element based on page coordinates.
ReturnsNumber[]The XY position of the element


### getY

Gets the current Y position of the DOM element based on page coordinates. ...

Gets the current Y position of the DOM element based on page coordinates.
ReturnsNumberThe Y position of the element


### hasActiveFx

Returns the current animation if this object has any effects actively running or queued, else returns false. ...

Returns the current animation if this object has any effects actively running or queued, else returns false.
        
        This method has been **deprecated** since 4.0
        Replaced by getActiveAnimation


### hasCls

Checks if the specified CSS class exists on this element's DOM node. ...

Checks if the specified CSS class exists on this element's DOM node.
ParametersclassName : StringThe CSS class to check for.


### hasConfig

...

Parametersconfig : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer
indicates whether the event needs firing or not.
ParameterseventName : StringThe name of the event to check for


### hasUICls

Checks if there is currently a specified uiCls. ...

Checks if there is currently a specified `uiCls`.
Parameterscls : StringThe `cls` to check.


### hasVisibleMenu

Returns true if the button has a menu and it is visible ...

Returns true if the button has a menu and it is visible
ReturnsBoolean


### hide

Hides this Component, setting it to invisible using the configured hideMode. ...

Hides this Component, setting it to invisible using the configured hideMode.
ParametersanimateTarget : String/Ext.Element/Ext.Component (optional)only valid for floating Components
such as Windows or ToolTips, or regular Components which have
been configured with `floating: true`.. The target to which the Component should animate while hiding.
Defaults to: `null`


### hideMenu

Hides this button's menu (if it has one) ...

Hides this button's menu (if it has one)
ReturnsExt.button.Buttonthis


### initBorderRegion

This method is called by the Ext.layout.container.Border class when instances are
added as regions to the layout. ...

This method is called by the `Ext.layout.container.Border` class when instances are
added as regions to the layout. Since it is valid to add any component to a border
layout as a region, this method must be added to `Ext.Component` but is only ever
called when that component is owned by a `border` layout.

**Defined in override Ext.layout.container.border.Region.**


### initCls

...


### initComponent

The initComponent template method is an important initialization step for a Component. ...

The initComponent template method is an important initialization step for a Component. It is intended to be
implemented by each subclass of Ext.Component to provide any needed constructor logic. The
initComponent method of the class being created is called first, with each initComponent method
up the hierarchy to Ext.Component being called thereafter. This makes it easy to implement and,
if needed, override the constructor logic of the Component at any step in the hierarchy.

The initComponent method **must** contain a call to callParent in order
to ensure that the parent class' initComponent method is also called.

All config options passed to the constructor are applied to `this` before initComponent is called,
so you can simply access them with `this.someOption`.

The following example demonstrates using a dynamic string for the text of a button at the time of
instantiation of the class.

Ext.define('DynamicButtonText', {
    extend: 'Ext.button.Button',

    initComponent: function() {
        this.text = new Date();
        this.renderTo = Ext.getBody();
        this.callParent();
    }
});

Ext.onReady(function() {
    Ext.create('DynamicButtonText');
});

        Available since: 1.1.0
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


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


### initContainer

...

Parameterscontainer : Object


### initDraggable

...


### initEvents

Initialize any events on this component ...

Initialize any events on this component


### initFrame

...


### initFramingTpl

Poke in a reference to applyRenderTpl(frameInfo, out) ...

Poke in a reference to applyRenderTpl(frameInfo, out)
Parameterstable : Object


### initHierarchyEvents

...


### initHierarchyState

Called by getHierarchyState to initialize the hierarchyState the first
time it is requested. ...

Called by getHierarchyState to initialize the hierarchyState the first
time it is requested.

**Overridden in Ext.rtl.AbstractComponent.**
ParametershierarchyState : Object


### initPadding

Initializes padding by applying it to the target element, or if the layout manages
padding ensures that the padding o...

Initializes padding by applying it to the target element, or if the layout manages
padding ensures that the padding on the target element is "0".
ParameterstargetEl : Object


### initPlugin

...

Parametersplugin : Object


### initRenderData

Initialized the renderData to be used when rendering the renderTpl. ...

Initialized the renderData to be used when rendering the renderTpl.
ReturnsObjectObject with keys and values that are going to be applied to the renderTpl


### initRenderTpl

Initializes the renderTpl. ...

Initializes the renderTpl.
ReturnsExt.XTemplateThe renderTpl XTemplate instance.


### initResizable

...

Parametersresizable : Object


### initState

Initializes the state of the object upon construction. ...

Initializes the state of the object upon construction.


### initStyles

Applies padding, margin, border, top, left, height, and width configs to the
appropriate elements. ...

Applies padding, margin, border, top, left, height, and width configs to the
appropriate elements.
ParameterstargetEl : Object


### is

Tests whether this Component matches the selector string. ...

Tests whether this Component matches the selector string.
Parametersselector : StringThe selector string to test against.


### isContainedFloater

Utility method to determine if a Component is floating, and has an owning Container whose coordinate system
it must b...

Utility method to determine if a Component is floating, and has an owning Container whose coordinate system
it must be positioned in when using setPosition.


### isDescendant

...

Parametersancestor : Object


### isDescendantOf

Determines whether this component is the descendant of a particular container. ...

Determines whether this component is the descendant of a particular container.
Parameterscontainer : Ext.Container


### isDisabled

Method to determine whether this Component is currently disabled. ...

Method to determine whether this Component is currently disabled.
ReturnsBooleanthe disabled state of this Component.


### isDraggable

Method to determine whether this Component is draggable. ...

Method to determine whether this Component is draggable.
ReturnsBooleanthe draggable state of this component.


### isDroppable

Method to determine whether this Component is droppable. ...

Method to determine whether this Component is droppable.
ReturnsBooleanthe droppable state of this component.


### isFloating

Method to determine whether this Component is floating. ...

Method to determine whether this Component is floating.
ReturnsBooleanthe floating state of this component.


### isFocusable

...


### isHidden

Method to determine whether this Component is currently set to hidden. ...

Method to determine whether this Component is currently set to hidden.
ReturnsBooleanthe hidden state of this Component.


### isHierarchicallyHidden

...


### isLayoutRoot

Determines whether this Component is the root of a layout. ...

Determines whether this Component is the root of a layout. This returns `true` if
this component can run its layout without assistance from or impact on its owner.
If this component cannot run its layout given these restrictions, `false` is returned
and its owner will be considered as the next candidate for the layout root.

Setting the _isLayoutRoot property to `true` causes this method to always
return `true`. This may be useful when updating a layout of a Container which shrink
wraps content, and you know that it will not change size, and so can safely be the
topmost participant in the layout run.


### isLayoutSuspended

Returns true if layout is suspended for this component. ...

Returns `true` if layout is suspended for this component. This can come from direct
suspension of this component's layout activity (Ext.Container.suspendLayout) or if one
of this component's containers is suspended.
ReturnsBoolean`true` layout of this component is suspended.


### isLocalRtl

Returns true if this component's local coordinate system is rtl. ...

Returns true if this component's local coordinate system is rtl. For normal
components this equates to the value of isParentRtl().  Floaters are a bit different
because a floater's element can be a childNode of something other than its
parent component's element.  For floaters we have to read the dom to see if the
component's element's parentNode has a css direction value of "rtl".

**Defined in override Ext.rtl.AbstractComponent.**
ReturnsBoolean


### isOppositeRootDirection

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**


### isParentRtl

Returns true if this component's parent container is rtl. ...

Returns true if this component's parent container is rtl. Used by rtl positioning
methods to determine if the component should be positioned using a right-to-left
coordinate system.

**Defined in override Ext.rtl.AbstractComponent.**
ReturnsBoolean


### isVisible

Returns true if this component is visible. ...

Returns `true` if this component is visible.
        Available since: 1.1.0
Parametersdeep : Boolean (optional)Pass `true` to interrogate the visibility status of all parent Containers to
determine whether this Component is truly visible to the user.

Generally, to determine whether a Component is hidden, the no argument form is needed. For example when creating
dynamically laid out UIs in a hidden Container before showing them.
Defaults to: `false`


### isXType

Tests whether or not this Component is of a specific xtype. ...

Tests whether or not this Component is of a specific xtype. This can test whether this Component is descended
from the xtype (default) or whether it is directly of the xtype specified (`shallow = true`).

If using your own subclasses, be aware that a Component must register its own xtype to participate in
determination of inherited xtypes.

For a list of all available xtypes, see the Ext.Component header.

Example usage:

var t = new Ext.form.field.Text();
var isText = t.isXType('textfield');        // true
var isBoxSubclass = t.isXType('field');       // true, descended from Ext.form.field.Base
var isBoxInstance = t.isXType('field', true); // false, not a direct Ext.form.field.Base instance

        Available since: 2.3.0
Parametersxtype : StringThe xtype to check for this Component


### makeFloating

...

Parametersdom : Object


### mask

...


### maybeShowMenu

...


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener.

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destroyed.
Parametersitem : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### move

Move the element relative to its current position. ...

Move the element relative to its current position.
Parametersdirection : StringPossible values are:


`"l"` (or `"left"`)
`"r"` (or `"right"`)
`"t"` (or `"top"`, or `"up"`)
`"b"` (or `"bottom"`, or `"down"`)


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener.

Removes listeners that were added by the mon method.
Parametersitem : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### nextNode

Returns the next node in the Component tree in tree traversal order. ...

Returns the next node in the Component tree in tree traversal order.

Note that this is not limited to siblings, and if invoked upon a node with no matching siblings, will walk the
tree to attempt to find a match. Contrast with nextSibling.
Parametersselector : String (optional)A ComponentQuery selector to filter the following nodes.


### nextSibling

Returns the next sibling of this Component. ...

Returns the next sibling of this Component.

Optionally selects the next sibling which matches the passed ComponentQuery selector.

May also be referred to as **`next()`**

Note that this is limited to siblings, and if no siblings of the item match, `null` is returned. Contrast with
nextNode
Parametersselector : String (optional)A ComponentQuery selector to filter the following items.


### on

Shorthand for addListener. ...

Shorthand for addListener.

Appends an event handler to this object.  For example:

myGridPanel.on("mouseover", this.onMouseOver, this);


The method also allows for a single argument to be passed which is a config object
containing properties which specify multiple events. For example:

myGridPanel.on({
    cellClick: this.onCellClick,
    mouseover: this.onMouseOver,
    mouseout: this.onMouseOut,
    scope: this // Important. Ensure "this" is correct during handler execution
});


One can also specify options for each event handler separately:

myGridPanel.on({
    cellClick: {fn: this.onCellClick, scope: this, single: true},
    mouseover: {fn: panel.onMouseOver, scope: panel}
});


*Names* of methods in a specified scope may also be used. Note that
`scope` MUST be specified to use this option:

myGridPanel.on({
    cellClick: {fn: 'onCellClick', scope: this, single: true},
    mouseover: {fn: 'onMouseOver', scope: panel}
});

ParameterseventName : String/ObjectThe name of the event to listen for.
May also be an object who's property names are event names.


### onAdded

Method to manage awareness of when components are added to their
respective Container, firing an added event. ...

Method to manage awareness of when components are added to their
respective Container, firing an added event. References are
established at add time rather than at render time.

Allows addition of behavior when a Component is added to a
Container. At this stage, the Component is in the parent
Container's collection of child items. After calling the
superclass's `onAdded`, the `ownerCt` reference will be present,
and if configured with a ref, the `refOwner` will be set.
        Available since: 3.4.0
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onAfterFloatLayout

...


### onBeforeFloatLayout

...


### onBlur

private ...

private
Parameterse : Object


### onBoxReady

...

Parameterswidth : Object


### onClick

...

Parameterse : Object


### onConfigUpdate

...

Parametersnames : Object


### onDestroy

Allows addition of behavior to the destroy operation. ...

Allows addition of behavior to the destroy operation.
After calling the superclass's onDestroy, the Component will be destroyed.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onDisable

See comments in onFocus

Allows addition of behavior to the disable operation. ...

See comments in onFocus

Allows addition of behavior to the disable operation.
After calling the superclass's `onDisable`, the Component will be disabled.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onDownKey

...

Parametersk : Object


### onEnable

Allows addition of behavior to the enable operation. ...

Allows addition of behavior to the enable operation.
After calling the superclass's `onEnable`, the Component will be enabled.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onFloatShow

...


### onFocus

private ...

private
Parameterse : Object


### onHide

Possibly animates down to a target element. ...

Possibly animates down to a target element.

Allows addition of behavior to the hide operation. After
calling the superclass’s onHide, the Component will be hidden.

Gets passed the same parameters as hide.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onKeyDown

Listen for TAB events and wrap round if tabbing of either end of the Floater ...

Listen for TAB events and wrap round if tabbing of either end of the Floater
Parameterse : Object


### onMenuHide

...

Parameterse : Object


### onMenuShow

...

Parameterse : Object


### onMenuTriggerOut

virtual mouseleave handler called when it is detected that the mouseout event
signified the mouse leaving the arrow a...

virtual mouseleave handler called when it is detected that the mouseout event
signified the mouse leaving the arrow area of the button - the `<em>`.
Parameterse : Object


### onMenuTriggerOver

virtual mouseenter handler called when it is detected that the mouseover event
signified the mouse entering the arrow...

virtual mouseenter handler called when it is detected that the mouseover event
signified the mouse entering the arrow area of the button - the `<em>`.
Parameterse : Object


### onMouseDown

...

Parameterse : Object


### onMouseEnter

virtual mouseenter handler called when it is detected that the mouseout event
signified the mouse entering the encaps...

virtual mouseenter handler called when it is detected that the mouseout event
signified the mouse entering the encapsulating element.
Parameterse : Object


### onMouseLeave

virtual mouseleave handler called when it is detected that the mouseover event
signified the mouse entering the encap...

virtual mouseleave handler called when it is detected that the mouseover event
signified the mouse entering the encapsulating element.
Parameterse : Object


### onMouseMove

mousemove handler called when the mouse moves anywhere within the encapsulating element. ...

mousemove handler called when the mouse moves anywhere within the encapsulating element.
The position is checked to determine if the mouse is entering or leaving the trigger area. Using
mousemove to check this is more resource intensive than we'd like, but it is necessary because
the trigger area does not line up exactly with sub-elements so we don't always get mouseover/out
events when needed. In the future we should consider making the trigger a separate element that
is absolutely positioned and sized over the trigger area.
Parameterse : Object


### onMouseOut

mouseout handler called when a mouseout event occurs anywhere within the encapsulating element -
or the mouse leaves ...

mouseout handler called when a mouseout event occurs anywhere within the encapsulating element -
or the mouse leaves the encapsulating element.
The targets are interrogated to see what is being exited to where.
Parameterse : Object


### onMouseOver

mouseover handler called when a mouseover event occurs anywhere within the encapsulating element. ...

mouseover handler called when a mouseover event occurs anywhere within the encapsulating element.
The targets are interrogated to see what is being entered from where.
Parameterse : Object


### onMouseUp

...

Parameterse : Object


### onPosition

Called after the component is moved, this method is empty by default but can be implemented by any
subclass that need...

Called after the component is moved, this method is empty by default but can be implemented by any
subclass that needs to perform custom logic after a move occurs.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onRemoved

Method to manage awareness of when components are removed from their
respective Container, firing a removed event. ...

Method to manage awareness of when components are removed from their
respective Container, firing a removed event. References are properly
cleaned up after removing a component from its owning container.

Allows addition of behavior when a Component is removed from
its parent Container. At this stage, the Component has been
removed from its parent Container's collection of child items,
but has not been destroyed (It will be destroyed if the parent
Container's `autoDestroy` is `true`, or if the remove call was
passed a truthy second parameter). After calling the
superclass's `onRemoved`, the `ownerCt` and the `refOwner` will not
be present.
        Available since: 3.4.0
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onRender

Template method called when this Component's DOM structure is created. ...

Template method called when this Component's DOM structure is created.

At this point, this Component's (and all descendants') DOM structure *exists* but it has not
been layed out (positioned and sized).

Subclasses which override this to gain access to the structure at render time should
call the parent class's method before attempting to access any child elements of the Component.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onRepeatClick

...

Parametersrepeat : Object


### onResize

Allows addition of behavior to the resize operation. ...

Allows addition of behavior to the resize operation.

Called when Ext.resizer.Resizer#drag event is fired.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onShow

Allows addition of behavior to the show operation. ...

Allows addition of behavior to the show operation. After
calling the superclass's onShow, the Component will be visible.

Override in subclasses where more complex behaviour is needed.

Gets passed the same parameters as show.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onShowComplete

Invoked after the afterShow method is complete. ...

Invoked after the afterShow method is complete.

Gets passed the same `callback` and `scope` parameters that afterShow received.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onShowVeto

...


### onStateChange

This method is called when any of the stateEvents are fired. ...

This method is called when any of the stateEvents are fired.


### parseBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**
Parametersbox : Object


### postBlur

Template method to do any post-blur processing. ...

Template method to do any post-blur processing.
Parameterse : Ext.EventObjectThe event object


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a
class derives from this class or uses this class as a mixin.
ParametersT : FunctionThe class constructor to prepare.


### previousNode

Returns the previous node in the Component tree in tree traversal order. ...

Returns the previous node in the Component tree in tree traversal order.

Note that this is not limited to siblings, and if invoked upon a node with no matching siblings, will walk the
tree in reverse order to attempt to find a match. Contrast with previousSibling.
Parametersselector : String (optional)A ComponentQuery selector to filter the preceding nodes.


### previousSibling

Returns the previous sibling of this Component. ...

Returns the previous sibling of this Component.

Optionally selects the previous sibling which matches the passed ComponentQuery
selector.

May also be referred to as **`prev()`**

Note that this is limited to siblings, and if no siblings of the item match, `null` is returned. Contrast with
previousNode
Parametersselector : String (optional)A ComponentQuery selector to filter the preceding items.


### prune

...

ParameterschildEls : Object


### query

Retrieves all descendant components which match the passed selector. ...

Retrieves all descendant components which match the passed selector.
Executes an Ext.ComponentQuery.query using this container as its root.
Parametersselector : String (optional)Selector complying to an Ext.ComponentQuery selector.
If no selector is specified all items will be returned.


### queryBy

Retrieves all descendant components which match the passed function. ...

Retrieves all descendant components which match the passed function.
The function should return false for components that are to be
excluded from the selection.
Parametersfn : FunctionThe matcher function. It will be called with a single argument,
the component being tested.


### queryById

Finds a component at any level under this container matching the id/itemId. ...

Finds a component at any level under this container matching the id/itemId.
This is a shorthand for calling ct.down('#' + id);
Parametersid : StringThe id to find


### registerFloatingItem

Called by Component#doAutoRender

Register a Container configured floating: true with this Component's ZIndexManager. ...

Called by Component#doAutoRender

Register a Container configured `floating: true` with this Component's ZIndexManager.

Components added in this way will not participate in any layout, but will be rendered
upon first show in the way that Windows are.
Parameterscmp : Object


### registerWithOwnerCt

...


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`.

For example if you are extending Grid, you might decide to forward some events from store.
So you can do this inside your initComponent:

this.relayEvents(this.getStore(), ['load']);


The grid instance will then have an observable 'load' event which will be passed the
parameters of the store's load event and any function fired with the grid's load event
would have access to the grid using the `this` keyword.
Parametersorigin : ObjectThe Observable whose events this object is to relay.


### removeAnchor

Remove any anchor to this element. ...

Remove any anchor to this element. See anchorTo.
ReturnsExt.util.Positionablethis


### removeChildEls

Removes items in the childEls array based on the return value of a supplied test
function. ...

Removes items in the childEls array based on the return value of a supplied test
function. The function is called with a entry in childEls and if the test function
return true, that entry is removed. If false, that entry is kept.
ParameterstestFn : FunctionThe test function.


### removeClass

...

Available since: 2.3.0


### removeCls

Removes a CSS class from the top level element representing this component. ...

Removes a CSS class from the top level element representing this component.
Parameterscls : String/String[]The CSS class name to remove.


### removeClsWithUI

Removes a cls to the uiCls array, which will also call removeUIClsFromElement and removes it from all
elements of thi...

Removes a `cls` to the `uiCls` array, which will also call removeUIClsFromElement and removes it from all
elements of this component.
Parameterscls : String/String[]A string or an array of strings to remove to the `uiCls`.


### removeListener

Removes an event handler. ...

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


### removeManagedListener

Removes listeners that were added by the mon method. ...

Removes listeners that were added by the mon method.
Parametersitem : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### removeManagedListenerItem

inherit docs

Remove a single managed listener item ...

inherit docs

Remove a single managed listener item
ParametersisClear : BooleanTrue if this is being called during a clear


### removeOverCls

...

Overrides: Ext.AbstractComponent.removeOverCls


### removePlugin

...

Parametersplugin : Object


### removeUIClsFromElement

Method which removes a specified UI + uiCls from the components element. ...

Method which removes a specified UI + `uiCls` from the components element. The `cls` which is added to the element
will be: `this.baseCls + '-' + ui`.
Parametersui : StringThe UI to add to the element.


### removeUIFromElement

Method which removes a specified UI from the components element. ...

Method which removes a specified UI from the components element.


### render

Renders the Component into the passed HTML element. ...

Renders the Component into the passed HTML element.

If you are using a Container object to house this
Component, then do not use the render method.

A Container's child Components are rendered by that Container's
layout manager when the Container is first rendered.

If the Container is already rendered when a new child Component is added, you may need to call
the Container's doLayout to refresh the view which
causes any unrendered child Components to be rendered. This is required so that you can add
multiple child components if needed while only refreshing the layout once.

When creating complex UIs, it is important to remember that sizing and positioning
of child items is the responsibility of the Container's layout
manager.  If you expect child items to be sized in response to user interactions, you must
configure the Container with a layout manager which creates and manages the type of layout you
have in mind.

Omitting the Container's layout config means that a basic
layout manager is used which does nothing but render child components sequentially into the
Container. No sizing or positioning will be performed in this situation.
Parameterscontainer : Ext.Element/HTMLElement/String (optional)The element this Component should be
rendered into. If it is being created from existing markup, this should be omitted.


### restoreClick

...


### resumeEvent

Resumes firing of the named event(s). ...

Resumes firing of the named event(s).

After calling this method to resume events, the events will fire when requested to fire.

Note that if the suspendEvent method is called multiple times for a certain event,
this converse method will have to be called the same number of times for it to resume firing.
ParameterseventName : String...Multiple event names to resume.


### resumeEvents

Resumes firing events (see suspendEvents). ...

Resumes firing events (see suspendEvents).

If events were suspended using the `queueSuspended` parameter, then all events fired
during event suspension will be sent to any listeners now.


### resumeLayouts

...

ParametersflushOptions : Object


### savePropToState

Conditionally saves a single property from this object to the given state object. ...

Conditionally saves a single property from this object to the given state object.
The idea is to only save state which has changed from the initial state so that
current software settings do not override future software settings. Only those
values that are user-changed state should be saved.
ParameterspropName : StringThe name of the property to save.


### savePropsToState

Gathers additional named properties of the instance and adds their current values
to the passed state object. ...

Gathers additional named properties of the instance and adds their current values
to the passed state object.
ParameterspropNames : String/String[]The name (or array of names) of the property to save.


### saveState

Saves the state of the object to the persistence store. ...

Saves the state of the object to the persistence store.


### scrollBy

Scrolls this Component's target element by the passed delta values, optionally animating. ...

Scrolls this Component's target element by the passed delta values, optionally animating.

All of the following are equivalent:

 comp.scrollBy(10, 10, true);
 comp.scrollBy([10, 10], true);
 comp.scrollBy({ x: 10, y: 10 }, true);

ParametersdeltaX : Number/Number[]/ObjectEither the x delta, an Array specifying x and y deltas or
an object with "x" and "y" properties.


### sequenceFx

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. ...

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. This is the
opposite of syncFx.
ReturnsObjectthis


### setActive

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been
moved to th...

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been
moved to the top of its zIndex stack, or pushed from the top of its zIndex stack.

If a *Window* is superceded by another Window, deactivating it hides its shadow.

This method also fires the activate or
deactivate event depending on which action occurred.
Parametersactive : Boolean (optional)True to activate the Component, false to deactivate it.
Defaults to: `false`


### setArrowHandler

Sets this button's arrow click handler. ...

Sets this button's arrow click handler.
Parametershandler : FunctionThe function to call when the arrow is clicked.


### setAutoScroll

Sets the overflow on the content element of the component. ...

Sets the overflow on the content element of the component.
Parametersscroll : BooleanTrue to allow the Component to auto scroll.


### setBorder

...

Parametersborder : String/NumberThe border, see border. If a falsey value is passed
the border will be removed.


### setBorderRegion

This method changes the region config property for this border region. ...

This method changes the `region` config property for this border region. This is
only valid if this component is in a `border` layout (`Ext.layout.container.Border`).

**Defined in override Ext.layout.container.border.Region.**
Parametersregion : StringThe new `region` value (`"north"`, `"south"`, `"east"` or
`"west"`).


### setBox

Sets the element's box. ...

Sets the element's box. If animate is true then x, y, width, and height will be
animated concurrently.
Parametersbox : ObjectThe box to fill {x, y, width, height}


### setComponentCls

...


### setComponentLayout

...

Parameterslayout : Object


### setConfig

...

Parametersconfig : Object


### setDisabled

Enable or disable the component. ...

Enable or disable the component.
Parametersdisabled : Boolean`true` to disable.


### setDocked

Sets the dock position of this component in its parent panel. ...

Sets the dock position of this component in its parent panel. Note that this only has effect if this item is part
of the `dockedItems` collection of a parent that has a DockLayout (note that any Panel has a DockLayout by default)
Parametersdock : ObjectThe dock position.


### setFloatParent

...

ParametersfloatParent : Object


### setGlyph

Sets this button's glyph ...

Sets this button's glyph
Parametersglyph : Number/Stringthe numeric charCode or string charCode/font-family.
This parameter expects a format consistent with that of glyph


### setHandler

Assigns this Button's click handler ...

Assigns this Button's click handler
Parametershandler : FunctionThe function to call when the button is clicked


### setHeight

Sets the height of the component. ...

Sets the height of the component. This method fires the resize event.
Parametersheight : NumberThe new height to set. This may be one of:


A Number specifying the new height in the Element's Ext.Element.defaultUnits (by default, pixels).
A String used to set the CSS height style.
*undefined* to leave the height unchanged.


### setHiddenState

...

Parametershidden : Object


### setHref

Sets the href of the embedded anchor element to the passed URL. ...

Sets the href of the embedded anchor element to the passed URL.

Also appends any configured baseParams and parameters set through setParams.
Parametershref : StringThe URL to set in the anchor element.


### setIcon

Sets the background image (inline style) of the button. ...

Sets the background image (inline style) of the button. This method also changes the value of the icon
config internally.
Parametersicon : StringThe path to an image to display in the button


### setIconCls

Sets the CSS class that provides a background image to use as the button's icon. ...

Sets the CSS class that provides a background image to use as the button's icon. This method also changes the
value of the iconCls config internally.
Parameterscls : StringThe CSS class providing the icon image


### setLoading

This method allows you to show or hide a LoadMask on top of this component. ...

This method allows you to show or hide a LoadMask on top of this component.
Parametersload : Boolean/Object/StringTrue to show the default LoadMask, a config object that will be passed to the
LoadMask constructor, or a message String to show. False to hide the current LoadMask.


### setLocalX

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Sets the local x coordinate of this element using CSS style. When used on an
absolute positioned element this method is symmetrical with getLocalX, but
may not be symmetrical when used on a relatively positioned element.
Parametersx : NumberThe x coordinate. A value of `null` sets the left style to 'auto'.


### setLocalXY

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Sets the local x and y coordinates of this element using CSS style. When used on an
absolute positioned element this method is symmetrical with getLocalXY, but
may not be symmetrical when used on a relatively positioned element.
Parametersx : Number/ArrayThe x coordinate or an array containing [x, y]. A value of
`null` sets the left style to 'auto'


### setLocalY

Sets the local y coordinate of this element using CSS style. ...

Sets the local y coordinate of this element using CSS style. When used on an
absolute positioned element this method is symmetrical with getLocalY, but
may not be symmetrical when used on a relatively positioned element.
Parametersy : NumberThe y coordinate. A value of `null` sets the top style to 'auto'.


### setMargin

Sets the margin on the target element. ...

Sets the margin on the target element.
Parametersmargin : Number/StringThe margin to set. See the margin config.


### setOverflowXY

Sets the overflow x/y on the content element of the component. ...

Sets the overflow x/y on the content element of the component. The x/y overflow
values can be any valid CSS overflow (e.g., 'auto' or 'scroll'). By default, the
value is 'hidden'. Passing null for one of the values will erase the inline style.
Passing `undefined` will preserve the current value.
ParametersoverflowX : StringThe overflow-x value.


### setPagePosition

Sets the page XY position of the component. ...

Sets the page XY position of the component. To set the left and top instead, use setPosition.
This method fires the move event.
Parametersx : Number/Number[]The new x position or an array of `[x,y]`.


### setParams

Sets the href of the link dynamically according to the params passed, and any baseParams configured. ...

Sets the href of the link dynamically according to the params passed, and any baseParams configured.

**Only valid if the Button was originally configured with a href**
Parametersparams : ObjectParameters to use in the href URL.


### setPosition

Sets the left and top of the component. ...

Sets the left and top of the component. To set the page XY position instead, use setPagePosition. This
method fires the move event.
Parametersx : Number/Number[]/ObjectThe new left, an array of `[x,y]`, or animation config object containing `x` and `y` properties.


### setRegion

Sets the element's position and size to the specified region. ...

Sets the element's position and size to the specified region. If animation is true
then width, height, x and y will be animated concurrently.
Parametersregion : Ext.util.RegionThe region to fill


### setRegionWeight

Sets the weight config property for this component. ...

Sets the `weight` config property for this component. This is only valid if this
component is in a `border` layout (`Ext.layout.container.Border`).

**Defined in override Ext.layout.container.border.Region.**
Parametersweight : NumberThe new `weight` value.


### setScale

Method to change the scale of the button. ...

Method to change the scale of the button. See scale for allowed configurations.
Parametersscale : StringThe scale to change to.


### setSize

Sets the width and height of this Component. ...

Sets the width and height of this Component. This method fires the resize event. This method can accept
either width and height as separate arguments, or you can pass a size object like `{width:10, height:20}`.
Parameterswidth : Number/String/ObjectThe new width to set. This may be one of:


A Number specifying the new width in the Element's Ext.Element.defaultUnits (by default, pixels).
A String used to set the CSS width style.
A size object in the format `{width: widthValue, height: heightValue}`.
`undefined` to leave the width unchanged.


### setText

Sets this Button's text ...

Sets this Button's text
Parameterstext : StringThe button text


### setTextAlign

Sets the text alignment for this button. ...

Sets the text alignment for this button.
Parametersalign : StringThe new alignment of the button text. See textAlign.


### setTooltip

Sets the tooltip for this Button. ...

Sets the tooltip for this Button.
Parameterstooltip : String/ObjectThis may be:


**String** : A string to be used as innerHTML (html tags are accepted) to show in a tooltip
**Object** : A configuration object for Ext.tip.QuickTipManager.register.


### setUI

inherit docs

Sets the UI for the component. ...

inherit docs

Sets the UI for the component. This will remove any existing UIs on the component. It will also loop through any
`uiCls` set on the component and rename them so they include the new UI.
Parametersui : StringThe new UI for the component.


### setVisible

Convenience function to hide or show this component by Boolean. ...

Convenience function to hide or show this component by Boolean.
        Available since: 1.1.0
Parametersvisible : Boolean`true` to show, `false` to hide.


### setWidth

Sets the width of the component. ...

Sets the width of the component. This method fires the resize event.
Parameterswidth : NumberThe new width to setThis may be one of:


A Number specifying the new width in the Element's Ext.Element.defaultUnits (by default, pixels).
A String used to set the CSS width style.


### setX

Sets the X position of the DOM element based on page coordinates. ...

Sets the X position of the DOM element based on page coordinates.
ParametersThe : NumberX position


### setXY

Sets the position of the DOM element in page coordinates. ...

Sets the position of the DOM element in page coordinates.
Parameterspos : Number[]Contains X & Y [x, y] values for new position (coordinates
are page-based)


### setY

Sets the Y position of the DOM element based on page coordinates. ...

Sets the Y position of the DOM element based on page coordinates.
ParametersThe : NumberY position


### setZIndex

z-index is managed by the zIndexManager and may be overwritten at any time. ...

z-index is managed by the zIndexManager and may be overwritten at any time.
Returns the next z-index to be used.
If this is a Container, then it will have rebased any managed floating Components,
and so the next available z-index will be approximately 10000 above that.
Parametersindex : Object


### setupFramingTpl

Inject a reference to the function which applies the render template into the framing template. ...

Inject a reference to the function which applies the render template into the framing template. The framing template
wraps the content.
ParametersframeTpl : Object


### setupProtoEl

...


### setupRenderTpl

...

ParametersrenderTpl : Object


### show

Shows this Component, rendering it first if autoRender or floating are true. ...

Shows this Component, rendering it first if autoRender or floating are `true`.

After being shown, a floating Component (such as a Ext.window.Window), is activated it and
brought to the front of its z-index stack.
ParametersanimateTarget : String/Ext.Element (optional)only valid for floating Components such as Windows or ToolTips, or regular Components which have been configured
with `floating: true`. The target from which the Component should animate from while opening.
Defaults to: `null`


### showAt

Displays component at specific xy position. ...

Displays component at specific xy position.
A floating component (like a menu) is positioned relative to its ownerCt if any.
Useful for popping up a context menu:

listeners: {
    itemcontextmenu: function(view, record, item, index, event, options) {
        Ext.create('Ext.menu.Menu', {
            width: 100,
            height: 100,
            margin: '0 0 10 0',
            items: [{
                text: 'regular item 1'
            },{
                text: 'regular item 2'
            },{
                text: 'regular item 3'
            }]
        }).showAt(event.getXY());
    }
}

Parametersx : Number/Number[]The new x position or array of `[x,y]`.


### showBy

Shows this component by the specified Component or Element. ...

Shows this component by the specified Component or Element.
Used when this component is floating.
Parameterscomponent : Ext.Component/Ext.dom.ElementThe Ext.Component or Ext.Element to show the component by.


### showMenu

Shows this button's menu (if it has one) ...

Shows this button's menu (if it has one)
ParametersfromEvent : Object


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


### stopAnimation

Stops any running effects and clears this object's internal effects queue if it contains any additional effects
that ...

Stops any running effects and clears this object's internal effects queue if it contains any additional effects
that haven't started yet.
ReturnsExt.ElementThe Element


### stopFx

Stops any running effects and clears this object's internal effects queue if it contains any additional effects
that ...

Stops any running effects and clears this object's internal effects queue if it contains any additional effects
that haven't started yet.
        
        This method has been **deprecated** since 4.0
        Replaced by stopAnimation


### suspendEvent

Suspends firing of the named event(s). ...

Suspends firing of the named event(s).

After calling this method to suspend events, the events will no longer fire when requested to fire.

Note that if this is called multiple times for a certain event, the converse method
resumeEvent will have to be called the same number of times for it to resume firing.
ParameterseventName : String...Multiple event names to suspend.


### suspendEvents

Suspends the firing of all events. ...

Suspends the firing of all events. (see resumeEvents)
ParametersqueueSuspended : BooleanPass as true to queue up suspended events to be fired
after the resumeEvents call instead of discarding all suspended events.


### suspendLayouts

...


### syncFx

Ensures that all effects queued after syncFx is called on this object are run concurrently. ...

Ensures that all effects queued after syncFx is called on this object are run concurrently. This is the opposite
of sequenceFx.
ReturnsObjectthis


### syncHidden

synchronizes the hidden state of this component with the state of its hierarchy ...

synchronizes the hidden state of this component with the state of its hierarchy


### syncShadow

...


### toBack

Sends this Component to the back of (lower z-index than) any other visible windows ...

Sends this Component to the back of (lower z-index than) any other visible windows
ReturnsExt.Componentthis


### toFront

Brings this floating Component to the front of any other visible, floating Components managed by the same
ZIndexManag...

Brings this floating Component to the front of any other visible, floating Components managed by the same
ZIndexManager

If this Component is modal, inserts the modal mask just below this Component in the z-index stack.
ParameterspreventFocus : Boolean (optional)Specify `true` to prevent the Component from being focused.
Defaults to: `false`


### toggle

If a state it passed, it becomes the pressed state otherwise the current state is toggled. ...

If a state it passed, it becomes the pressed state otherwise the current state is toggled.
Parametersstate : Boolean (optional)Force a particular state


### translatePoints

Translates the passed page coordinates into left/top css values for the element ...

Translates the passed page coordinates into left/top css values for the element
Parametersx : Number/ArrayThe page x or an array containing [x, y]


### translateXY

Translates the passed page coordinates into x and y css values for the element ...

Translates the passed page coordinates into x and y css values for the element
Parametersx : Number/ArrayThe page x or an array containing [x, y]


### un

Shorthand for removeListener. ...

Shorthand for removeListener.

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


### unitizeBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**
Parametersbox : Object


### unmask

...


### unregisterFloatingItem

...

Parameterscmp : Object


### up

Navigates up the ownership hierarchy searching for an ancestor Container which matches any passed simple selector or ...

Navigates up the ownership hierarchy searching for an ancestor Container which matches any passed simple selector or component.

*Important.* There is not a universal upwards navigation pointer. There are several upwards relationships
such as the button which activates a menu, or the
menu item which activated a submenu, or the
column header which activated the column menu.

These differences are abstracted away by this method.

Example:

var owningTabPanel = grid.up('tabpanel');

Parametersselector : String/Ext.Component (optional)The simple selector component or actual component to test. If not passed the immediate owner/activater is returned.


### update

Update the content area of a component. ...

Update the content area of a component.
        Available since: 3.4.0
ParametershtmlOrData : String/ObjectIf this component has been configured with a template via the tpl config then
it will use this argument as data to populate the template. If this component was not configured with a template,
the components content area will be updated via Ext.Element update.


### updateAria

Injected as an override by Ext.Aria.initialize ...

Injected as an override by Ext.Aria.initialize


### updateBox

Sets the current box measurements of the component's underlying element. ...

Sets the current box measurements of the component's underlying element.
Parametersbox : ObjectAn object in the format {x, y, width, height}


### updateFrame

...


### updateLayout

Updates this component's layout. ...

Updates this component's layout. If this update affects this components ownerCt,
that component's `updateLayout` method will be called to perform the layout instead.
Otherwise, just this component (and its child items) will layout.
Parametersoptions : Object (optional)An object with layout options.
defer : Boolean`true` if this layout should be deferred.


### wrapPrimaryEl

...

Parametersdom : Object


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


### activate

Fires after a Component has been visually activated. ...

Fires after a Component has been visually activated.
Parametersthis : Ext.Component


### added

Fires after a Component had been added to a Container. ...

Fires after a Component had been added to a Container.
        Available since: 3.4.0
Parametersthis : Ext.Component


### afterrender

Fires after the component rendering is finished. ...

Fires after the component rendering is finished.

The `afterrender` event is fired after this Component has been rendered, been postprocessed by any
`afterRender` method defined for the Component.
        Available since: 3.4.0
Parametersthis : Ext.Component


### arrowclick

Fires when this button's arrow is clicked. ...

Fires when this button's arrow is clicked.
Parametersthis : Ext.button.Split


### beforeactivate

Fires before a Component has been visually activated. ...

Fires before a Component has been visually activated. Returning `false` from an event listener can prevent
the activate from occurring.
Parametersthis : Ext.Component


### beforedeactivate

Fires before a Component has been visually deactivated. ...

Fires before a Component has been visually deactivated. Returning `false` from an event listener can
prevent the deactivate from occurring.
Parametersthis : Ext.Component


### beforedestroy

Fires before the component is destroyed. ...

Fires before the component is destroyed. Return `false` from an event handler to stop the
destroy.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforehide

Fires before the component is hidden when calling the hide method. ...

Fires before the component is hidden when calling the hide method. Return `false` from an event
handler to stop the hide.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforerender

Fires before the component is rendered. ...

Fires before the component is rendered. Return `false` from an event handler to stop the
render.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforeshow

Fires before the component is shown when calling the show method. ...

Fires before the component is shown when calling the show method. Return `false` from an event
handler to stop the show.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforestaterestore

Fires before the state of the object is restored. ...

Fires before the state of the object is restored. Return false from an event handler to stop the restore.
Parametersthis : Ext.state.Stateful


### beforestatesave

Fires before the state of the object is saved to the configured state provider. ...

Fires before the state of the object is saved to the configured state provider. Return false to stop the save.
Parametersthis : Ext.state.Stateful


### blur

Fires when this Component loses focus. ...

Fires when this Component loses focus.
Parametersthis : Ext.Component


### boxready

Fires one time - after the component has been laid out for the first time at its initial size. ...

Fires *one time* - after the component has been laid out for the first time at its initial size.
Parametersthis : Ext.Component


### click

Fires when this button is clicked, before the configured handler is invoked. ...

Fires when this button is clicked, before the configured handler is invoked. Execution of the
handler may be vetoed by returning `false` to this event.
Parametersthis : Ext.button.Button


### deactivate

Fires after a Component has been visually deactivated. ...

Fires after a Component has been visually deactivated.
Parametersthis : Ext.Component


### destroy

Fires after the component is destroyed. ...

Fires after the component is destroyed.
        Available since: 1.1.0
Parametersthis : Ext.Component


### disable

Fires after the component is disabled. ...

Fires after the component is disabled.
        Available since: 1.1.0
Parametersthis : Ext.Component


### enable

Fires after the component is enabled. ...

Fires after the component is enabled.
        Available since: 1.1.0
Parametersthis : Ext.Component


### focus

Fires when this Component receives focus. ...

Fires when this Component receives focus.
Parametersthis : Ext.Component


### glyphchange

Fired when the button's glyph is changed by the setGlyph method. ...

Fired when the button's glyph is changed by the setGlyph method.
Parametersthis : Ext.button.Button


### hide

Fires after the component is hidden. ...

Fires after the component is hidden. Fires after the component is hidden when calling the hide
method.
        Available since: 1.1.0
Parametersthis : Ext.Component


### iconchange

Fired when the button's icon is changed by the setIcon or setIconCls methods. ...

Fired when the button's icon is changed by the setIcon or setIconCls methods.
Parametersthis : Ext.button.Button


### menuhide

If this button has a menu, this event fires when it is hidden ...

If this button has a menu, this event fires when it is hidden
Parametersthis : Ext.button.Button


### menushow

If this button has a menu, this event fires when it is shown ...

If this button has a menu, this event fires when it is shown
Parametersthis : Ext.button.Button


### menutriggerout

If this button has a menu, this event fires when the mouse leaves the menu triggering element ...

If this button has a menu, this event fires when the mouse leaves the menu triggering element
Parametersthis : Ext.button.Button


### menutriggerover

If this button has a menu, this event fires when the mouse enters the menu triggering element ...

If this button has a menu, this event fires when the mouse enters the menu triggering element
Parametersthis : Ext.button.Button


### mouseout

Fires when the mouse exits the button ...

Fires when the mouse exits the button
Parametersthis : Ext.button.Button


### mouseover

Fires when the mouse hovers over the button ...

Fires when the mouse hovers over the button
Parametersthis : Ext.button.Button


### move

Fires after the component is moved. ...

Fires after the component is moved.
Parametersthis : Ext.Component


### removed

Fires when a component is removed from an Ext.container.Container ...

Fires when a component is removed from an Ext.container.Container
        Available since: 3.4.0
Parametersthis : Ext.Component


### render

Fires after the component markup is rendered. ...

Fires after the component markup is rendered.
        Available since: 1.1.0
Parametersthis : Ext.Component


### resize

Fires after the component is resized. ...

Fires after the component is resized. Note that this does *not* fire when the component is first laid out at its initial
size. To hook that point in the life cycle, use the boxready event.
Parametersthis : Ext.Component


### show

Fires after the component is shown when calling the show method. ...

Fires after the component is shown when calling the show method.
        Available since: 1.1.0
Parametersthis : Ext.Component


### staterestore

Fires after the state of the object is restored. ...

Fires after the state of the object is restored.
Parametersthis : Ext.state.Stateful


### statesave

Fires after the state of the object is saved to the configured state provider. ...

Fires after the state of the object is saved to the configured state provider.
Parametersthis : Ext.state.Stateful


### textchange

Fired when the button's text is changed by the setText method. ...

Fired when the button's text is changed by the setText method.
Parametersthis : Ext.button.Button


### toggle

Fires when the 'pressed' state of this button changes (only if enableToggle = true) ...

Fires when the 'pressed' state of this button changes (only if enableToggle = true)
Parametersthis : Ext.button.Button


### $button-arrow-height

**Tipo:** number

The default height for a button's menu arrow ...

The default height for a button's menu arrow
Defaults to: `12px`


### $button-arrow-width

**Tipo:** number

The default width for a button's menu arrow ...

The default width for a button's menu arrow
Defaults to: `12px`


### $button-default-background-color

**Tipo:** color

The background-color for the default button UI ...

The background-color for the `default` button UI
Defaults to: `$button-default-base-color`


### $button-default-background-color-disabled

**Tipo:** color

The background-color for the default button UI when the button is disabled ...

The background-color for the `default` button UI when the button is disabled
Defaults to: `null`


### $button-default-background-color-focus

**Tipo:** color

The background-color for the default button UI when the button is focused ...

The background-color for the `default` button UI when the button is focused
Defaults to: `$button-default-background-color-over`


### $button-default-background-color-over

**Tipo:** color

The background-color for the default button UI when the cursor is over the button ...

The background-color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-base-color-over`


### $button-default-background-color-pressed

**Tipo:** color

The background-color for the default button UI when the button is pressed ...

The background-color for the `default` button UI when the button is pressed
Defaults to: `$button-default-base-color-pressed`


### $button-default-background-gradient

**Tipo:** string/list

The background-gradient for the default button UI. ...

The background-gradient for the `default` button UI.  Can be either the name of a
predefined gradient or a list of color stops. Used as the `$type` parameter for
Global_CSS.background-gradient.
Defaults to: `'glossy-button'`


### $button-default-background-gradient-disabled

**Tipo:** string/list

The background-gradient for the default button UI when the button is disabled. ...

The background-gradient for the `default` button UI when the button is disabled.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-disabled'`


### $button-default-background-gradient-focus

**Tipo:** string/list

The background-gradient for the default button UI when the button is focused. ...

The background-gradient for the `default` button UI when the button is focused.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `$button-default-background-gradient-over`


### $button-default-background-gradient-over

**Tipo:** string/list

The background-gradient for the default button UI when the cursor is over the button. ...

The background-gradient for the `default` button UI when the cursor is over the button.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-over'`


### $button-default-background-gradient-pressed

**Tipo:** string/list

The background-gradient for the default button UI when the button is pressed. ...

The background-gradient for the `default` button UI when the button is pressed.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-pressed'`


### $button-default-base-color

**Tipo:** color

The base color for the default button UI ...

The base color for the `default` button UI
Defaults to: `$base-color`


### $button-default-base-color-disabled

**Tipo:** color

The base color for the default button UI when the button is disabled ...

The base color for the `default` button UI when the button is disabled
Defaults to: `$base-color`


### $button-default-base-color-focus

**Tipo:** color

The base color for the default button UI when the button is focused ...

The base color for the `default` button UI when the button is focused
Defaults to: `$button-default-base-color-over`


### $button-default-base-color-over

**Tipo:** color

The base color for the default button UI when the cursor is over the button ...

The base color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-base-color`


### $button-default-base-color-pressed

**Tipo:** color

The base color for the default button UI when the button is pressed ...

The base color for the `default` button UI when the button is pressed
Defaults to: `$button-default-base-color`


### $button-default-border-color

**Tipo:** color

The border-color for the default button UI ...

The border-color for the `default` button UI
Defaults to: `$base-color`


### $button-default-border-color-disabled

**Tipo:** color

The border-color for the default button UI when the button is disabled ...

The border-color for the `default` button UI when the button is disabled
Defaults to: `$base-color`


### $button-default-border-color-focus

**Tipo:** color

The border-color for the default button UI when the button is focused ...

The border-color for the `default` button UI when the button is focused
Defaults to: `$base-color`


### $button-default-border-color-over

**Tipo:** color

The border-color for the default button UI when the cursor is over the button ...

The border-color for the `default` button UI when the cursor is over the button
Defaults to: `$base-color`


### $button-default-border-color-pressed

**Tipo:** color

The border-color for the default button UI when the button is pressed ...

The border-color for the `default` button UI when the button is pressed
Defaults to: `$base-color`


### $button-default-color

**Tipo:** color

The text color for the default button UI ...

The text color for the `default` button UI
Defaults to: `#000`


### $button-default-color-disabled

**Tipo:** color

The text color for the default button UI when the button is disabled ...

The text color for the `default` button UI when the button is disabled
Defaults to: `$button-default-color`


### $button-default-color-focus

**Tipo:** color

The text color for the default button UI when the button is focused ...

The text color for the `default` button UI when the button is focused
Defaults to: `$button-default-color-over`


### $button-default-color-over

**Tipo:** color

The text color for the default button UI when the cursor is over the button ...

The text color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-color`


### $button-default-color-pressed

**Tipo:** color

The text color for the default button UI when the button is pressed ...

The text color for the `default` button UI when the button is pressed
Defaults to: `$button-default-color`


### $button-default-glyph-color

**Tipo:** color

The color of the glyph icon for the default button UI ...

The color of the glyph icon for the `default` button UI
Defaults to: `$button-default-color`


### $button-default-glyph-opacity

**Tipo:** color

The opacity of the glyph icon for the default button UI ...

The opacity of the glyph icon for the `default` button UI
Defaults to: `.5`


### $button-icon-spacing

**Tipo:** number

The default space between a button's icon and text ...

The default space between a button's icon and text
Defaults to: `4px`


### $button-include-split-over-arrows

**Tipo:** boolean

True to include different split arrows for buttons' hover state. ...

True to include different split arrows for buttons' hover state.
Defaults to: `false`


### $button-include-ui-menu-arrows

**Tipo:** boolean

True to use a different image url for the menu button arrows for each button UI ...

True to use a different image url for the menu button arrows for each button UI
Defaults to: `false`


### $button-include-ui-split-arrows

**Tipo:** boolean

True to use a different image url for the split button arrows for each button UI ...

True to use a different image url for the split button arrows for each button UI
Defaults to: `false`


### $button-inner-opacity-disabled

**Tipo:** number

opacity to apply to the button's inner elements (icon and text) when the buton is disabled ...

opacity to apply to the button's inner elements (icon and text) when the buton is disabled
Defaults to: `1`


### $button-large-arrow-height

**Tipo:** number

The default height of a large scale button's menu arrow ...

The default height of a large scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-large-arrow-width

**Tipo:** number

The default width of a large scale button's menu arrow ...

The default width of a large scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-large-border-radius

**Tipo:** number

The default border-radius for a large scale button ...

The default border-radius for a large scale button
Defaults to: `3px`


### $button-large-border-width

**Tipo:** number

The default border-width for a large scale button ...

The default border-width for a large scale button
Defaults to: `1px`


### $button-large-font-family

**Tipo:** string

The default font-family for a large scale button ...

The default font-family for a large scale button
Defaults to: `$font-family`


### $button-large-font-family-disabled

**Tipo:** string

The default font-family for a large scale button when the button is disabled ...

The default font-family for a large scale button when the button is disabled
Defaults to: `$button-large-font-family`


### $button-large-font-family-focus

**Tipo:** string

The default font-family for a large scale button when the button is focused ...

The default font-family for a large scale button when the button is focused
Defaults to: `$button-large-font-family-over`


### $button-large-font-family-over

**Tipo:** string

The default font-family for a large scale button when the cursor is over the button ...

The default font-family for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-family`


### $button-large-font-family-pressed

**Tipo:** string

The default font-family for a large scale button when the button is pressed ...

The default font-family for a large scale button when the button is pressed
Defaults to: `$button-large-font-family`


### $button-large-font-size

**Tipo:** number

The default font-size for a large scale button ...

The default font-size for a large scale button
Defaults to: `$font-size`


### $button-large-font-size-disabled

**Tipo:** number

The default font-size for a large scale button when the button is disabled ...

The default font-size for a large scale button when the button is disabled
Defaults to: `$button-large-font-size`


### $button-large-font-size-focus

**Tipo:** number

The default font-size for a large scale button when the button is focused ...

The default font-size for a large scale button when the button is focused
Defaults to: `$button-large-font-size-over`


### $button-large-font-size-over

**Tipo:** number

The default font-size for a large scale button when the cursor is over the button ...

The default font-size for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-size`


### $button-large-font-size-pressed

**Tipo:** number

The default font-size for a large scale button when the button is pressed ...

The default font-size for a large scale button when the button is pressed
Defaults to: `$button-large-font-size`


### $button-large-font-weight

**Tipo:** string

The default font-weight for a large scale button ...

The default font-weight for a large scale button
Defaults to: `normal`


### $button-large-font-weight-disabled

**Tipo:** string

The default font-weight for a large scale button when the button is disabled ...

The default font-weight for a large scale button when the button is disabled
Defaults to: `$button-large-font-weight`


### $button-large-font-weight-focus

**Tipo:** string

The default font-weight for a large scale button when the button is focused ...

The default font-weight for a large scale button when the button is focused
Defaults to: `$button-large-font-weight-over`


### $button-large-font-weight-over

**Tipo:** string

The default font-weight for a large scale button when the cursor is over the button ...

The default font-weight for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-weight`


### $button-large-font-weight-pressed

**Tipo:** string

The default font-weight for a large scale button when the button is pressed ...

The default font-weight for a large scale button when the button is pressed
Defaults to: `$button-large-font-weight`


### $button-large-icon-size

**Tipo:** number

The default icon size for a large scale button ...

The default icon size for a large scale button
Defaults to: `32px`


### $button-large-padding

**Tipo:** number

The default padding for a large scale button ...

The default padding for a large scale button
Defaults to: `3px`


### $button-large-split-height

**Tipo:** number

The default height of a large scale Split Button's arrow ...

The default height of a large scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-large-split-width

**Tipo:** number

The default width of a large scale Split Button's arrow ...

The default width of a large scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-large-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a large scale button ...

The default horizontal padding to add to the left and right of the text element for
a large scale button
Defaults to: `3px`


### $button-medium-arrow-height

**Tipo:** number

The default height of a medium scale button's menu arrow ...

The default height of a medium scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-medium-arrow-width

**Tipo:** number

The default width of a medium scale button's menu arrow ...

The default width of a medium scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-medium-border-radius

**Tipo:** number

The default border-radius for a medium scale button ...

The default border-radius for a medium scale button
Defaults to: `3px`


### $button-medium-border-width

**Tipo:** number

The default border-width for a medium scale button ...

The default border-width for a medium scale button
Defaults to: `1px`


### $button-medium-font-family

**Tipo:** string

The default font-family for a medium scale button ...

The default font-family for a medium scale button
Defaults to: `$font-family`


### $button-medium-font-family-disabled

**Tipo:** string

The default font-family for a medium scale button when the button is disabled ...

The default font-family for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-family`


### $button-medium-font-family-focus

**Tipo:** string

The default font-family for a medium scale button when the button is focused ...

The default font-family for a medium scale button when the button is focused
Defaults to: `$button-medium-font-family-over`


### $button-medium-font-family-over

**Tipo:** string

The default font-family for a medium scale button when the cursor is over the button ...

The default font-family for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-family`


### $button-medium-font-family-pressed

**Tipo:** string

The default font-family for a medium scale button when the button is pressed ...

The default font-family for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-family`


### $button-medium-font-size

**Tipo:** number

The default font-size for a medium scale button ...

The default font-size for a medium scale button
Defaults to: `$font-size`


### $button-medium-font-size-disabled

**Tipo:** number

The default font-size for a medium scale button when the button is disabled ...

The default font-size for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-size`


### $button-medium-font-size-focus

**Tipo:** number

The default font-size for a medium scale button when the button is focused ...

The default font-size for a medium scale button when the button is focused
Defaults to: `$button-medium-font-size-over`


### $button-medium-font-size-over

**Tipo:** number

The default font-size for a medium scale button when the cursor is over the button ...

The default font-size for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-size`


### $button-medium-font-size-pressed

**Tipo:** number

The default font-size for a medium scale button when the button is pressed ...

The default font-size for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-size`


### $button-medium-font-weight

**Tipo:** string

The default font-weight for a medium scale button ...

The default font-weight for a medium scale button
Defaults to: `normal`


### $button-medium-font-weight-disabled

**Tipo:** string

The default font-weight for a medium scale button when the button is disabled ...

The default font-weight for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-weight`


### $button-medium-font-weight-focus

**Tipo:** string

The default font-weight for a medium scale button when the button is focused ...

The default font-weight for a medium scale button when the button is focused
Defaults to: `$button-medium-font-weight-over`


### $button-medium-font-weight-over

**Tipo:** string

The default font-weight for a medium scale button when the cursor is over the button ...

The default font-weight for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-weight`


### $button-medium-font-weight-pressed

**Tipo:** string

The default font-weight for a medium scale button when the button is pressed ...

The default font-weight for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-weight`


### $button-medium-icon-size

**Tipo:** number

The default icon size for a medium scale button ...

The default icon size for a medium scale button
Defaults to: `24px`


### $button-medium-padding

**Tipo:** number

The default padding for a medium scale button ...

The default padding for a medium scale button
Defaults to: `3px`


### $button-medium-split-height

**Tipo:** number

The default height of a medium scale Split Button's arrow ...

The default height of a medium scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-medium-split-width

**Tipo:** number

The default width of a medium scale Split Button's arrow ...

The default width of a medium scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-medium-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a medium scale button ...

The default horizontal padding to add to the left and right of the text element for
a medium scale button
Defaults to: `3px`


### $button-opacity-disabled

**Tipo:** number

opacity to apply to the button's main element when the buton is disabled ...

opacity to apply to the button's main element when the buton is disabled
Defaults to: `.5`


### $button-small-arrow-height

**Tipo:** number

The default height of a small scale button's menu arrow ...

The default height of a small scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-small-arrow-width

**Tipo:** number

The default width of a small scale button's menu arrow ...

The default width of a small scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-small-border-radius

**Tipo:** number

The default border-radius for a small scale button ...

The default border-radius for a small scale button
Defaults to: `3px`


### $button-small-border-width

**Tipo:** number

The default border-width for a small scale button ...

The default border-width for a small scale button
Defaults to: `1px`


### $button-small-font-family

**Tipo:** string

The default font-family for a small scale button ...

The default font-family for a small scale button
Defaults to: `$font-family`


### $button-small-font-family-disabled

**Tipo:** string

The default font-family for a small scale button when the button is disabled ...

The default font-family for a small scale button when the button is disabled
Defaults to: `$button-small-font-family`


### $button-small-font-family-focus

**Tipo:** string

The default font-family for a small scale button when the button is focused ...

The default font-family for a small scale button when the button is focused
Defaults to: `$button-small-font-family-over`


### $button-small-font-family-over

**Tipo:** string

The default font-family for a small scale button when the cursor is over the button ...

The default font-family for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-family`


### $button-small-font-family-pressed

**Tipo:** string

The default font-family for a small scale button when the button is pressed ...

The default font-family for a small scale button when the button is pressed
Defaults to: `$button-small-font-family`


### $button-small-font-size

**Tipo:** number

The default font-size for a small scale button ...

The default font-size for a small scale button
Defaults to: `ceil ( $font-size * .9 )`


### $button-small-font-size-disabled

**Tipo:** number

The default font-size for a small scale button when the button is disabled ...

The default font-size for a small scale button when the button is disabled
Defaults to: `$button-small-font-size`


### $button-small-font-size-focus

**Tipo:** number

The default font-size for a small scale button when the button is focused ...

The default font-size for a small scale button when the button is focused
Defaults to: `$button-small-font-size-over`


### $button-small-font-size-over

**Tipo:** number

The default font-size for a small scale button when the cursor is over the button ...

The default font-size for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-size`


### $button-small-font-size-pressed

**Tipo:** number

The default font-size for a small scale button when the button is pressed ...

The default font-size for a small scale button when the button is pressed
Defaults to: `$button-small-font-size`


### $button-small-font-weight

**Tipo:** string

The default font-weight for a small scale button ...

The default font-weight for a small scale button
Defaults to: `normal`


### $button-small-font-weight-disabled

**Tipo:** string

The default font-weight for a small scale button when the button is disabled ...

The default font-weight for a small scale button when the button is disabled
Defaults to: `$button-small-font-weight`


### $button-small-font-weight-focus

**Tipo:** string

The default font-weight for a small scale button when the button is focused ...

The default font-weight for a small scale button when the button is focused
Defaults to: `$button-small-font-weight-over`


### $button-small-font-weight-over

**Tipo:** string

The default font-weight for a small scale button when the cursor is over the button ...

The default font-weight for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-weight`


### $button-small-font-weight-pressed

**Tipo:** string

The default font-weight for a small scale button when the button is pressed ...

The default font-weight for a small scale button when the button is pressed
Defaults to: `$button-small-font-weight`


### $button-small-icon-size

**Tipo:** number

The default icon size for a small scale button ...

The default icon size for a small scale button
Defaults to: `16px`


### $button-small-padding

**Tipo:** number

The default padding for a small scale button ...

The default padding for a small scale button
Defaults to: `2px`


### $button-small-split-height

**Tipo:** number

The default height of a small scale Split Button's arrow ...

The default height of a small scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-small-split-width

**Tipo:** number

The default width of a small scale Split Button's arrow ...

The default width of a small scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-small-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a small scale button ...

The default horizontal padding to add to the left and right of the text element for
a small scale button
Defaults to: `4px`


### $button-split-height

**Tipo:** number

The default height for a Split Button's arrow ...

The default height for a Split Button's arrow
Defaults to: `14px`


### $button-split-width

**Tipo:** number

The default width for a Split Button's arrow ...

The default width for a Split Button's arrow
Defaults to: `14px`


### $button-toolbar-background-color

**Tipo:** color

The background-color for the default-toolbar button UI ...

The background-color for the `default-toolbar` button UI
Defaults to: `$base-color`


### $button-toolbar-background-color-disabled

**Tipo:** color

The background-color for the default-toolbar button UI when the button is disabled ...

The background-color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-color-focus

**Tipo:** color

The background-color for the default-toolbar button UI when the button is focused ...

The background-color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-background-color-over`


### $button-toolbar-background-color-over

**Tipo:** color

The background-color for the default-toolbar button UI when the cursor is over the button ...

The background-color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-color-pressed

**Tipo:** color

The background-color for the default-toolbar button UI when the button is pressed ...

The background-color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-gradient

**Tipo:** string/list

The background-gradient for the default-toolbar button UI. ...

The background-gradient for the `default-toolbar` button UI.  Can be either the name of
a predefined gradient or a list of color stops. Used as the `$type` parameter for
Global_CSS.background-gradient.
Defaults to: `'glossy-button'`


### $button-toolbar-background-gradient-disabled

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is disabled. ...

The background-gradient for the `default-toolbar` button UI when the button is disabled.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-disabled'`


### $button-toolbar-background-gradient-focus

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is focused. ...

The background-gradient for the `default-toolbar` button UI when the button is focused.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `$button-toolbar-background-gradient-over`


### $button-toolbar-background-gradient-over

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the cursor is over the
button. ...

The background-gradient for the `default-toolbar` button UI when the cursor is over the
button. Can be either the name of a predefined gradient or a list of color stops. Used
as the `$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-over'`


### $button-toolbar-background-gradient-pressed

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is pressed. ...

The background-gradient for the `default-toolbar` button UI when the button is pressed.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-pressed'`


### $button-toolbar-border-color

**Tipo:** color

The border-color for the default-toolbar button UI ...

The border-color for the `default-toolbar` button UI
Defaults to: `$base-color`


### $button-toolbar-border-color-disabled

**Tipo:** color

The border-color for the default-toolbar button UI when the button is disabled ...

The border-color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-border-color-focus

**Tipo:** color

The border-color for the default-toolbar button UI when the button is focused ...

The border-color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-border-color-over`


### $button-toolbar-border-color-over

**Tipo:** color

The border-color for the default-toolbar button UI when the cursor is over the button ...

The border-color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-border-color-pressed

**Tipo:** color

The border-color for the default-toolbar button UI when the button is pressed ...

The border-color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-color

**Tipo:** color

The text color for the default-toolbar button UI ...

The text color for the `default-toolbar` button UI
Defaults to: `#000`


### $button-toolbar-color-disabled

**Tipo:** color

The text color for the default-toolbar button UI when the button is disabled ...

The text color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-color`


### $button-toolbar-color-focus

**Tipo:** color

The text color for the default-toolbar button UI when the button is focused ...

The text color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-color-over`


### $button-toolbar-color-over

**Tipo:** color

The text color for the default-toolbar button UI when the cursor is over the button ...

The text color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-color`


### $button-toolbar-color-pressed

**Tipo:** color

The text color for the default-toolbar button UI when the button is pressed ...

The text color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-color`


### $button-toolbar-glyph-color

**Tipo:** color

The color of the glyph icon for the default-toolbar button UI ...

The color of the glyph icon for the `default-toolbar` button UI
Defaults to: `$button-toolbar-color`


### $button-toolbar-glyph-opacity

**Tipo:** color

The opacity of the glyph icon for the default-toolbar button UI ...

The opacity of the glyph icon for the `default-toolbar` button UI
Defaults to: `.5`


### $button-toolbar-include-split-noline-arrows

**Tipo:** boolean

True to include "noline" split arrows for toolbar buttons in their default state. ...

True to include "noline" split arrows for toolbar buttons in their default state.
Defaults to: `false`


### $button-toolbar-inner-opacity-disabled

**Tipo:** number

opacity to apply to the toolbar button's inner elements (icon and text) when the buton is disabled ...

opacity to apply to the toolbar button's inner elements (icon and text) when the buton is disabled
Defaults to: `1`


### $button-toolbar-opacity-disabled

**Tipo:** number

opacity to apply to the toolbar button's main element when the buton is disabled ...

opacity to apply to the toolbar button's main element when the buton is disabled
Defaults to: `.5`


### $include-button-default-large-ui

**Tipo:** boolean

True to include the "default" button UI for "large" scale buttons ...

True to include the "default" button UI for "large" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-medium-ui

**Tipo:** boolean

True to include the "default" button UI for "medium" scale buttons ...

True to include the "default" button UI for "medium" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-small-ui

**Tipo:** boolean

True to include the "default" button UI for "small" scale buttons ...

True to include the "default" button UI for "small" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-toolbar-large-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "large" scale buttons ...

True to include the "default-toolbar" button UI for "large" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-medium-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "medium" scale buttons ...

True to include the "default-toolbar" button UI for "medium" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-small-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "small" scale buttons ...

True to include the "default-toolbar" button UI for "small" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI ...

True to include the "default-toolbar" button UI
Defaults to: `$include-default-uis`


### $include-button-default-ui

**Tipo:** boolean

True to include the "default" button UI ...

True to include the "default" button UI
Defaults to: `$include-default-uis`


### extjs-button-ui

Creates a visual theme for a Button ...

Creates a visual theme for a Button
$ui : stringThe name of the UI being created. Can not included spaces or special punctuation
(used in CSS class names).


## Methods

### Ext.button.Split

Creates new Component. ...

Creates new Component.
Parametersconfig : Ext.Element/String/ObjectThe configuration options may be specified as either:





**an element** : it is set as the internal element and its id used as the component id
**a string** : it is assumed to be the id of an existing element and is used as the component id
**anything else** : it is assumed to be a standard config object and is applied to the component


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### addClass

Adds a CSS class to the top level element representing this component. ...

Adds a CSS class to the top level element representing this component.
        
        This method has been **deprecated** since 4.1
        Use addCls instead.


### addCls

Adds a CSS class to the top level element representing this component. ...

Adds a CSS class to the top level element representing this component.
Parameterscls : String/String[]The CSS class name to add.


### addClsWithUI

Adds a cls to the uiCls array, which will also call addUIClsToElement and adds to all elements of this
component. ...

Adds a `cls` to the `uiCls` array, which will also call addUIClsToElement and adds to all elements of this
component.
Parametersclasses : String/String[]A string or an array of strings to add to the `uiCls`.


### addEvents

Adds the specified events to the list of events which this Observable may fire. ...

Adds the specified events to the list of events which this Observable may fire.
ParameterseventNames : Object/String...Either an object with event names as properties with
a value of `true`. For example:

this.addEvents({
    storeloaded: true,
    storecleared: true
});


Or any number of event names as separate parameters. For example:

this.addEvents('storeloaded', 'storecleared');


### addFocusListener

Sets up the focus listener on this Component's focusEl if it has one. ...

Sets up the focus listener on this Component's focusEl if it has one.

Form Components which must implicitly participate in tabbing order usually have a naturally focusable
element as their focusEl, and it is the DOM event of that receiving focus which drives
the Component's `onFocus` handling, and the DOM event of it being blurred which drives the `onBlur` handling.

If the focusEl is **not** naturally focusable, then the listeners are only added
if the FocusManager is enabled.


### addListener

Appends an event handler to this object. ...

Appends an event handler to this object.  For example:

myGridPanel.on("mouseover", this.onMouseOver, this);


The method also allows for a single argument to be passed which is a config object
containing properties which specify multiple events. For example:

myGridPanel.on({
    cellClick: this.onCellClick,
    mouseover: this.onMouseOver,
    mouseout: this.onMouseOut,
    scope: this // Important. Ensure "this" is correct during handler execution
});


One can also specify options for each event handler separately:

myGridPanel.on({
    cellClick: {fn: this.onCellClick, scope: this, single: true},
    mouseover: {fn: panel.onMouseOver, scope: panel}
});


*Names* of methods in a specified scope may also be used. Note that
`scope` MUST be specified to use this option:

myGridPanel.on({
    cellClick: {fn: 'onCellClick', scope: this, single: true},
    mouseover: {fn: 'onMouseOver', scope: panel}
});

ParameterseventName : String/ObjectThe name of the event to listen for.
May also be an object who's property names are event names.


### addManagedListener

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destr...

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destroyed.
Parametersitem : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### addOverCls

...

Overrides: Ext.AbstractComponent.addOverCls


### addPlugin

Adds a plugin. ...

Adds a plugin. May be called at any time in the component's lifecycle.
Parametersplugin : Object


### addPropertyToState

Save a property to the given state object if it is not its default or configured
value. ...

Save a property to the given state object if it is not its default or configured
value.
Parametersstate : ObjectThe state object.


### addStateEvents

Add events that will trigger the state to be saved. ...

Add events that will trigger the state to be saved. If the first argument is an
array, each element of that array is the name of a state event. Otherwise, each
argument passed to this method is the name of a state event.
Parametersevents : String/String[]The event name or an array of event names.


### addUIClsToElement

Method which adds a specified UI + uiCls to the components element. ...

Method which adds a specified UI + `uiCls` to the components element. Can be overridden to remove the UI from more
than just the components element.
Parametersui : StringThe UI to remove from the element.


### addUIToElement

Method which adds a specified UI to the components element. ...

Method which adds a specified UI to the components element.


### adjustForConstraints

private ==>  used outside of core
TODO: currently only used by ToolTip. ...

private ==>  used outside of core
TODO: currently only used by ToolTip. does this method belong here?
Parametersxy : Object


### adjustPosition

...

Parametersx : Object


### afterComponentLayout

Called by the layout system after the Component has been laid out. ...

Called by the layout system after the Component has been laid out.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### afterFirstLayout

...

Parameterswidth : Object


### afterHide

Invoked after the Component has been hidden. ...

Invoked after the Component has been hidden.

Gets passed the same `callback` and `scope` parameters that onHide received.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### afterRender

Allows addition of behavior after rendering is complete. ...

Allows addition of behavior after rendering is complete. At this stage the Component’s Element
will have been styled according to the configuration, will have had any configured CSS class
names added, and will be in the configured visibility and the configured enable state.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### afterSetPosition

Template method called after a Component has been positioned. ...

Template method called after a Component has been positioned.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### afterShow

Invoked after the Component is shown (after onShow is called). ...

Invoked after the Component is shown (after onShow is called).

Gets passed the same parameters as show.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### alignTo

Aligns the element with another element relative to the specified anchor points. ...

Aligns the element with another element relative to the specified anchor points. If
the other element is the document it aligns it to the viewport. The position
parameter is optional, and can be specified in any one of the following formats:


**Blank**: Defaults to aligning the element's top-left corner to the target's
bottom-left corner ("tl-bl").
**One anchor (deprecated)**: The passed anchor position is used as the target
element's anchor point.  The element being aligned will position its top-left
corner (tl) to that point. This method has been deprecated in favor of the newer
two anchor syntax below.
**Two anchors**: If two values from the table below are passed separated by a dash,
the first value is used as the element's anchor point, and the second value is
used as the target's anchor point.



In addition to the anchor points, the position parameter also supports the "?"
character. If "?" is passed at the end of the position string, the element will
attempt to align as specified, but the position will be adjusted to constrain to
the viewport if necessary. Note that the element being aligned might be swapped to
align to a different position than that specified in order to enforce the viewport
constraints. Following are all of the supported anchor positions:

Value  Description
-----  -----------------------------
tl     The top left corner (default)
t      The center of the top edge
tr     The top right corner
l      The center of the left edge
c      In the center of the element
r      The center of the right edge
bl     The bottom left corner
b      The center of the bottom edge
br     The bottom right corner



Example Usage:

// align el to other-el using the default positioning
// ("tl-bl", non-constrained)
el.alignTo("other-el");

// align the top left corner of el with the top right corner of other-el
// (constrained to viewport)
el.alignTo("other-el", "tr?");

// align the bottom right corner of el with the center left edge of other-el
el.alignTo("other-el", "br-l?");

// align the center of el with the bottom left corner of other-el and
// adjust the x position by -6 pixels (and the y position by 0)
el.alignTo("other-el", "c-bl", [-6, 0]);

Parameterselement : Ext.util.Positionable/HTMLElement/StringThe Positionable,
HTMLElement, or id of the element to align to.


### anchorTo

Anchors an element to another element and realigns it when the window is resized. ...

Anchors an element to another element and realigns it when the window is resized.
Parameterselement : Ext.util.Positionable/HTMLElement/StringThe Positionable,
HTMLElement, or id of the element to align to.


### anim

process the passed fx configuration. ...

process the passed fx configuration.


Parametersconfig : Object


### animate

Performs custom animation on this object. ...

Performs custom animation on this object.

This method is applicable to both the Component class and the Sprite
class. It performs animated transitions of certain properties of this object over a specified timeline.

Animating a Component

When animating a Component, the following properties may be specified in `from`, `to`, and `keyframe` objects:


`x` - The Component's page X position in pixels.
`y` - The Component's page Y position in pixels
`left` - The Component's `left` value in pixels.
`top` - The Component's `top` value in pixels.
`width` - The Component's `width` value in pixels.
`height` - The Component's `height` value in pixels.
`dynamic` - Specify as true to update the Component's layout (if it is a Container) at every frame of the animation.
*Use sparingly as laying out on every intermediate size change is an expensive operation.*



For example, to animate a Window to a new size, ensuring that its internal layout and any shadow is correct:

myWindow = Ext.create('Ext.window.Window', {
    title: 'Test Component animation',
    width: 500,
    height: 300,
    layout: {
        type: 'hbox',
        align: 'stretch'
    },
    items: [{
        title: 'Left: 33%',
        margins: '5 0 5 5',
        flex: 1
    }, {
        title: 'Left: 66%',
        margins: '5 5 5 5',
        flex: 2
    }]
});
myWindow.show();
myWindow.header.el.on('click', function() {
    myWindow.animate({
        to: {
            width: (myWindow.getWidth() == 500) ? 700 : 500,
            height: (myWindow.getHeight() == 300) ? 400 : 300
        }
    });
});


For performance reasons, by default, the internal layout is only updated when the Window reaches its final `"to"`
size. If dynamic updating of the Window's child Components is required, then configure the animation with
`dynamic: true` and the two child items will maintain their proportions during the animation.
Parametersconfig : ObjectConfiguration for Ext.fx.Anim.
Note that the to config is required.


### applyChildEls

Sets references to elements inside the component. ...

Sets references to elements inside the component.
Parametersel : Object


### applyRenderSelectors

Sets references to elements inside the component. ...

Sets references to elements inside the component. This applies renderSelectors
as well as childEls.


### applyState

Applies the state to the object. ...

Applies the state to the object. This should be overridden in subclasses to do
more complex state operations. By default it applies the state properties onto
the current object.
Parametersstate : ObjectThe state


### beforeBlur

Template method to do any pre-blur processing. ...

Template method to do any pre-blur processing.
Parameterse : Ext.EventObjectThe event object


### beforeComponentLayout

Occurs before componentLayout is run. ...

Occurs before `componentLayout` is run. Returning `false` from this method will prevent the `componentLayout` from
being executed.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### beforeDestroy

Invoked before the Component is destroyed. ...

Invoked before the Component is destroyed.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### beforeFocus

Template method to do any pre-focus processing. ...

Template method to do any pre-focus processing.
Parameterse : Ext.EventObjectThe event object


### beforeLayout

Occurs before componentLayout is run. ...

Occurs before componentLayout is run. In previous releases, this method could
return `false` to prevent its layout but that is not supported in Ext JS 4.1 or
higher. This method is simply a notification of the impending layout to give the
component a chance to adjust the DOM. Ideally, DOM reads should be avoided at this
time to reduce expensive document reflows.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### beforeRender

...

Overrides: Ext.Component.beforeRender


### beforeSetPosition

Template method called before a Component is positioned. ...

Template method called before a Component is positioned.

Ensures that the position is adjusted so that the Component is constrained if so configured.
Parametersx : Object


### beforeShow

Invoked before the Component is shown. ...

Invoked before the Component is shown.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### blur

...

ReturnsExt.Componentthis


### bubble

Bubbles up the component/container heirarchy, calling the specified function with each component. ...

Bubbles up the component/container heirarchy, calling the specified function with each component. The scope
(*this*) of function call will be the scope provided or the current component. The arguments to the function will
be the args provided or the current component. If the function returns false at any point, the bubble is stopped.
Parametersfn : FunctionThe function to call


### calculateAnchorXY

Calculates x,y coordinates specified by the anchor position on the element, adding
extraX and extraY values. ...

Calculates x,y coordinates specified by the anchor position on the element, adding
extraX and extraY values.
Parametersanchor : String (optional)The specified anchor position.
See alignTo for details on supported anchor positions.
Defaults to: `'tl'`


### calculateConstrainedPosition

Calculates the new [x,y] position to move this Positionable into a constrain region. ...

Calculates the new [x,y] position to move this Positionable into a constrain region.

By default, this Positionable is constrained to be within the container it was added to, or the element it was
rendered to.

Priority is given to constraining the top and left within the constraint.

An alternative constraint may be passed.
ParametersconstrainTo : String/HTMLElement/Ext.Element/Ext.util.Region (optional)The Element or Region
into which this Component is to be constrained. Defaults to the element into which this Positionable
was rendered, or this Component's {@link Ext.Component.constrainTo.


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


### cancelFocus

Cancel any deferred focus on this component ...

Cancel any deferred focus on this component


### captureArgs

...

Parameterso : Object


### center

Center this Component in its container. ...

Center this Component in its container.
ReturnsExt.Componentthis


### child

Retrieves the first direct child of this container which matches the passed selector or component. ...

Retrieves the first direct child of this container which matches the passed selector or component.
The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.
Parametersselector : String/Ext.Component (optional)An Ext.ComponentQuery selector. If no selector is
specified, the first child will be returned.


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### clearTip

...


### cloneConfig

Clone the current component using the original config values passed into this instance by default. ...

Clone the current component using the original config values passed into this instance by default.
Parametersoverrides : ObjectA new config containing any properties to override in the cloned version.
An id property can be passed on this object, otherwise one will be generated to avoid duplicates.


### configClass

...


### constructPlugin

...

Parametersptype : String/Objectstring or config object containing a ptype property.

Constructs a plugin according to the passed config object/ptype string.

Ensures that the constructed plugin always has a `cmp` reference back to this component.
The setting up of this is done in PluginManager. The PluginManager ensures that a reference to this
component is passed to the constructor. It also ensures that the plugin's `setCmp` method (if any) is called.


### constructPlugins

Returns an array of fully constructed plugin instances. ...

Returns an array of fully constructed plugin instances. This converts any configs into their
appropriate instances.

It does not mutate the plugins array. It creates a new array.


### continueFireEvent

Continue to fire event. ...

Continue to fire event.
ParameterseventName : String


### convertPositionSpec

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**
ParametersposSpec : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.
ParametersnewName : StringThe name under which to refire the passed parameters.


### deleteMembers

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### didIconStateChange

Checks if the icon/iconCls changed from being empty to having a value, or having a value to being empty. ...

Checks if the icon/iconCls changed from being empty to having a value, or having a value to being empty.
Parametersold : StringThe old icon/iconCls


### disable

inherit docs

Disable the component. ...

inherit docs

Disable the component.
        Available since: 1.1.0
Parameterssilent : Boolean (optional)Passing `true` will suppress the `disable` event from being fired.
Defaults to: `false`


### doApplyRenderTpl

Called from the selected frame generation template to insert this Component's inner structure inside the framing stru...

Called from the selected frame generation template to insert this Component's inner structure inside the framing structure.

When framing is used, a selected frame generation template is used as the primary template of the getElConfig instead
of the configured renderTpl. The renderTpl is invoked by this method which is injected into the framing template.
Parametersout : Object


### doAutoRender

Handles autoRender. ...

Handles autoRender.
Floating Components may have an ownerCt. If they are asking to be constrained, constrain them within that
ownerCt, and have their z-index managed locally. Floating Components are always rendered to document.body


### doComponentLayout

This method needs to be called whenever you change something on this component that requires the Component's
layout t...

This method needs to be called whenever you change something on this component that requires the Component's
layout to be recalculated.
ReturnsExt.container.Containerthis


### doConstrain

Moves this floating Component into a constrain region. ...

Moves this floating Component into a constrain region.

By default, this Component is constrained to be within the container it was added to, or the element it was
rendered to.

An alternative constraint may be passed.
ParametersconstrainTo : String/HTMLElement/Ext.Element/Ext.util.Region (optional)The Element or Region
into which this Component is to be constrained. Defaults to the element into which this floating Component
was rendered.


### doRenderContent

...

Parametersout : Object


### doRenderFramingDockedItems

...

Parametersout : Object


### doToggle

...


### down

Retrieves the first descendant of this container which matches the passed selector. ...

Retrieves the first descendant of this container which matches the passed selector.
The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.
Parametersselector : String/Ext.Component (optional)An Ext.ComponentQuery selector or Ext.Component. If no selector is
specified, the first child will be returned.


### enable

inherit docs

Enable the component ...

inherit docs

Enable the component
        Available since: 1.1.0
Parameterssilent : Boolean (optional)Passing `true` will suppress the `enable` event from being fired.
Defaults to: `false`


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if
present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if
present. There is no implementation in the Observable base class.

This is commonly used by Ext.Components to bubble events to owner Containers.
See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the
Component's immediate owner. But if a known target is required, this can be overridden to access the
required target more quickly.

Example:

Ext.define('Ext.overrides.form.field.Base', {
    override: 'Ext.form.field.Base',

    //  Add functionality to Field's initComponent to enable the change event to bubble
    initComponent: function () {
        this.callParent();
        this.enableBubble('change');
    }
});

var myForm = Ext.create('Ext.form.Panel', {
    title: 'User Details',
    items: [{
        ...
    }],
    listeners: {
        change: function() {
            // Title goes red if form has been modified.
            myForm.header.setStyle('color', 'red');
        }
    }
});

ParameterseventNames : String/String[]The event name to bubble, or an Array of event names.


### ensureAttachedToBody

Ensures that this component is attached to document.body. ...

Ensures that this component is attached to `document.body`. If the component was
rendered to Ext.getDetachedBody, then it will be appended to `document.body`.
Any configured position is also restored.
ParametersrunLayout : Boolean (optional)True to run the component's layout.
Defaults to: `false`


### findParentBy

Find a container above this component at any level by a custom function. ...

Find a container above this component at any level by a custom function. If the passed function returns true, the
container will be returned.

See also the up method.
Parametersfn : FunctionThe custom function to call with the arguments (container, this component).


### findParentByType

Find a container above this component at any level by xtype or class

See also the up method. ...

Find a container above this component at any level by xtype or class

See also the up method.
Parametersxtype : String/Ext.ClassThe xtype string for a component, or the class of the component directly


### findPlugin

Retrieves plugin from this component's collection by its ptype. ...

Retrieves plugin from this component's collection by its `ptype`.
Parametersptype : StringThe Plugin's ptype as specified by the class's `alias` configuration.


### finishRender

This method visits the rendered component tree in a "top-down" order. ...

This method visits the rendered component tree in a "top-down" order. That is, this
code runs on a parent component before running on a child. This method calls the
onRender method of each component.
ParameterscontainerIdx : NumberThe index into the Container items of this Component.


### finishRenderChildren

...


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed
to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed
to addListener).

An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by
calling enableBubble.
ParameterseventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list.

An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by
calling enableBubble.
ParameterseventName : StringThe name of the event to fire.


### fireHandler

...

Parameterse : Object


### fireHierarchyEvent

For more information on the hierarchy events, see the note for the
hierarchyEventSource observer defined in the onCla...

For more information on the hierarchy events, see the note for the
hierarchyEventSource observer defined in the onClassCreated callback.

This functionality is contained in Component (as opposed to Container)
because a Component can be the ownerCt for a floating component (loadmask),
and the loadmask needs to know when its owner is shown/hidden via the
hierarchyEventSource so that its hidden state can be synchronized.

TODO: merge this functionality with Ext.globalEvents
Parametersename : Object


### fitContainer

...

Parametersanimate : Object


### focus

Try to focus this component. ...

Try to focus this component.
ParametersselectText : Boolean (optional)If applicable, true to also select the text in this component


### forceComponentLayout

Forces this component to redo its componentLayout. ...

Forces this component to redo its componentLayout.
        
        This method has been **deprecated** since 4.1.0
        Use updateLayout instead.


### getActionEl

inherit docs ...

inherit docs
Overrides: Ext.Component.getActionEl


### getActiveAnimation

Returns the current animation if this object has any effects actively running or queued, else returns false. ...

Returns the current animation if this object has any effects actively running or queued, else returns false.
ReturnsExt.fx.Anim/BooleanAnim if element has active effects, else false


### getAlignToXY

Gets the x,y coordinates to align this element with another element. ...

Gets the x,y coordinates to align this element with another element. See
alignTo for more info on the supported position values.
Parameterselement : Ext.util.Positionable/HTMLElement/StringThe Positionable,
HTMLElement, or id of the element to align to.


### getAnchor

private ...

private


### getAnchorToXY

Begin Positionable methods



Overridden in Ext.rtl.AbstractComponent. ...

Begin Positionable methods



**Overridden in Ext.rtl.AbstractComponent.**

Gets the x,y coordinates of an element specified by the anchor position on the
element.
Parametersel : Ext.dom.ElementThe element


### getAnchorXY

Gets the x,y coordinates specified by the anchor position on the element. ...

Gets the x,y coordinates specified by the anchor position on the element.
Parametersanchor : String (optional)The specified anchor position.
See alignTo for details on supported anchor positions.
Defaults to: `'tl'`


### getAnimateTarget

...

Parameterstarget : Object


### getAutoId

...


### getBorderPadding

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Returns the size of the element's borders and padding.
ReturnsObjectan object with the following numeric properties
- beforeX
- afterX
- beforeY
- afterY


### getBox

Return an object defining the area of this Element which can be passed to
setBox to set another Element's size/locati...

Return an object defining the area of this Element which can be passed to
setBox to set another Element's size/location to match this element.
ParameterscontentBox : Boolean (optional)If true a box for the content of the element is
returned.


### getBtnWrapFrameWidth

...

Parametersside : Object


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable
ReturnsExt.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getBubbleTarget

Implements an upward event bubbling policy. ...

Implements an upward event bubbling policy. By default a Component bubbles events up to its reference owner.

Component subclasses may implement a different bubbling strategy by overriding this method.
Overrides: Ext.AbstractComponent.getBubbleTarget


### getChildEls

...


### getClassChildEls

...

Parameterscls : Object


### getComponentCls

...


### getComponentLayout

...


### getConfig

...

Parametersname : Object


### getConstrainVector

Returns the [X, Y] vector by which this Positionable's element must be translated to make a best
attempt to constrain...

Returns the `[X, Y]` vector by which this Positionable's element must be translated to make a best
attempt to constrain within the passed constraint. Returns `false` if the element
does not need to be moved.

Priority is given to constraining the top and left within the constraint.

The constraint may either be an existing element into which the element is to be
constrained, or a Region into which this element is to be
constrained.

By default, any extra shadow around the element is **not** included in the constrain calculations - the edges
of the element are used as the element bounds. To constrain the shadow within the constrain region, set the
`constrainShadow` property on this element to `true`.
ParametersconstrainTo : Ext.util.Positionable/HTMLElement/String/Ext.util.Region (optional)The
Positionable, HTMLElement, element id, or Region into which the element is to be
constrained.


### getContentTarget

...


### getDragEl

...


### getEl

Retrieves the top level element representing this component. ...

Retrieves the top level element representing this component.
        Available since: 1.1.0
ReturnsExt.dom.Element


### getElConfig

...


### getFocusEl

inherit docs

Returns the focus holder element associated with this Component. ...

inherit docs

Returns the focus holder element associated with this Component. At the Component base class level, this function returns `undefined`.

Subclasses which use embedded focusable elements (such as Window, Field and Button) should override this
for use by the focus method.

Containers which need to participate in the FocusManager's navigation and Container focusing scheme also
need to return a `focusEl`, although focus is only listened for in this case if the FocusManager is enabled.
Overrides: Ext.AbstractComponent.getFocusEl


### getFrameInfo

On render, reads an encoded style attribute, "filter" from the style of this Component's element. ...

On render, reads an encoded style attribute, "filter" from the style of this Component's element.
This information is memoized based upon the CSS class name of this Component's element.
Because child Components are rendered as textual HTML as part of the topmost Container, a dummy div is inserted
into the document to receive the document element's CSS class name, and therefore style attributes.


### getFrameRenderData

...


### getFrameTpl

...

Parameterstable : Object


### getFramingInfoCls

...


### getHeight

Gets the current height of the component's underlying element. ...

Gets the current height of the component's underlying element.
ReturnsNumber


### getHierarchyState

A component's hierarchyState is used to keep track of aspects of a component's
state that affect its descendants hier...

A component's hierarchyState is used to keep track of aspects of a component's
state that affect its descendants hierarchically like "collapsed" and "hidden".
For example, if this.hierarchyState.hidden == true, it means that either this
component, or one of its ancestors is hidden.

Hierarchical state management is implemented by chaining each component's
hierarchyState property to its parent container's hierarchyState property via the
prototype. The result is such that if a component's hierarchyState does not have
it's own property, it inherits the property from the nearest ancestor that does.

To set a hierarchical "hidden" value:

this.getHierarchyState().hidden = true;


It is important to remember when unsetting hierarchyState properties to delete
them instead of just setting them to a falsy value.  This ensures that the
hierarchyState returns to a state of inheriting the value instead of overriding it
To unset the hierarchical "hidden" value:

delete this.getHierarchyState().hidden;


IMPORTANT! ALWAYS access hierarchyState using this method, not by accessing
this.hierarchyState directly.  The hierarchyState property does not exist until
the first time getHierarchyState() is called.  At that point getHierarchyState()
walks up the component tree to establish the hierarchyState prototype chain.
Additionally the hierarchyState property should NOT be relied upon even after
the initial call to getHierarchyState() because  it is possible for the
hierarchyState to be invalidated. Invalidation typically happens when a component
is moved to a new container. In such a case the hierarchy state remains invalid
until the next time getHierarchyState() is called on the component or one of its
descendants.
Parametersinner : Object


### getHref

If there is a configured href for this Button, returns the href with parameters appended. ...

If there is a configured href for this Button, returns the href with parameters appended.
ReturnsString/BooleanThe href string with parameters appended.


### getId

Retrieves the id of this component. ...

Retrieves the `id` of this component. Will auto-generate an `id` if one has not already been set.
ReturnsString


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### getInnerCls

...


### getInsertPosition

This function takes the position argument passed to onRender and returns a
DOM element that you can use in the insert...

This function takes the position argument passed to onRender and returns a
DOM element that you can use in the insertBefore.
Parametersposition : String/Number/Ext.dom.Element/HTMLElementIndex, element id or element you want
to put this component before.


### getItemId

Returns the value of itemId assigned to this component, or when that
is not set, returns the value of id. ...

Returns the value of itemId assigned to this component, or when that
is not set, returns the value of id.
ReturnsString


### getLoader

Gets the Ext.ComponentLoader for this Component. ...

Gets the Ext.ComponentLoader for this Component.
ReturnsExt.ComponentLoaderThe loader instance, null if it doesn't exist.


### getLocalX

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Returns the x coordinate of this element reletive to its `offsetParent`.
ReturnsNumberThe local x coordinate


### getLocalXY

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Returns the x and y coordinates of this element relative to its `offsetParent`.
ReturnsNumber[]The local XY position of the element


### getLocalY

Returns the y coordinate of this element reletive to its offsetParent. ...

Returns the y coordinate of this element reletive to its `offsetParent`.
ReturnsNumberThe local y coordinate


### getMaskTarget

...


### getOffsetsTo

Returns the offsets of this element from the passed element. ...

Returns the offsets of this element from the passed element. The element must both
be part of the DOM tree and not have display:none to have page coordinates.
ParametersoffsetsTo : Ext.util.Positionable/HTMLElement/StringThe Positionable,
HTMLElement, or element id to get get the offsets from.


### getOuterSize

Include margins ...

Include margins


### getOverflowEl

Get an el for overflowing, defaults to the target el ...

Get an el for overflowing, defaults to the target el


### getOverflowStyle

Returns the CSS style object which will set the Component's scroll styles. ...

Returns the CSS style object which will set the Component's scroll styles. This must be applied
to the target element.


### getOwningBorderContainer

Returns the owning container if that container uses border layout. ...

Returns the owning container if that container uses `border` layout. Otherwise
this method returns `null`.

**Defined in override Ext.layout.container.border.Region.**
ReturnsExt.container.ContainerThe owning border container or `null`.


### getOwningBorderLayout

Returns the owning border (Ext.layout.container.Border) instance if there is
one. ...

Returns the owning `border` (`Ext.layout.container.Border`) instance if there is
one. Otherwise this method returns `null`.

**Defined in override Ext.layout.container.border.Region.**
ReturnsExt.layout.container.BorderThe owning border layout or `null`.


### getPlugin

Retrieves a plugin from this component's collection by its pluginId. ...

Retrieves a plugin from this component's collection by its `pluginId`.
ParameterspluginId : String


### getPosition

Gets the current XY position of the component's underlying element. ...

Gets the current XY position of the component's underlying element.
Parameterslocal : Boolean (optional)If true the element's left and top are returned instead of page XY.
Defaults to: `false`


### getPositionEl

Deprecate 5.0 ...

Deprecate 5.0


### getProxy

...


### getRefItems

...

Parametersdeep : Object


### getRefOwner

Used by ComponentQuery, and the up method to find the
owning Component in the linkage hierarchy. ...

Used by ComponentQuery, and the up method to find the
owning Component in the linkage hierarchy.

By default this returns the Container which contains this Component.

This may be overriden by Component authors who implement ownership hierarchies which are not
based upon ownerCt, such as BoundLists being owned by Fields or Menus being owned by Buttons.


### getRegion

Returns a region object that defines the area of this element. ...

Returns a region object that defines the area of this element.
ReturnsExt.util.RegionA Region containing "top, left, bottom, right" properties.


### getRenderTree

...


### getResizeEl

Deprecate 5.0 ...

Deprecate 5.0


### getSize

Gets the current size of the component's underlying element. ...

Gets the current size of the component's underlying element.
ReturnsObjectAn object containing the element's size `{width: (element width), height: (element height)}`


### getSizeModel

Returns an object that describes how this component's width and height are managed. ...

Returns an object that describes how this component's width and height are managed.
All of these objects are shared and should not be modified.
ParametersownerCtSizeModel : Object


### getSplitCls

...


### getState

The supplied default state gathering method for the AbstractComponent class. ...

The supplied default state gathering method for the AbstractComponent class.

This method returns dimension settings such as `flex`, `anchor`, `width` and `height` along with `collapsed`
state.

Subclasses which implement more complex state should call the superclass's implementation, and apply their state
to the result if this basic state is to be saved.

Note that Component state will only be saved if the Component has a stateId and there as a StateProvider
configured for the document.
ReturnsObject


### getStateId

Gets the state id for this object. ...

Gets the state id for this object.
ReturnsStringThe 'stateId' or the implicit 'id' specified by component configuration.


### getStyleProxy

Returns an offscreen div with the same class name as the element this is being rendered. ...

Returns an offscreen div with the same class name as the element this is being rendered.
This is because child item rendering takes place in a detached div which, being not
part of the document, has no styling.
Parameterscls : Object


### getTargetEl

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. ...

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component.


### getTemplateArgs

This method returns an object which provides substitution parameters for the XTemplate used to
create this Button's D...

This method returns an object which provides substitution parameters for the XTemplate used to
create this Button's DOM structure.

Instances or subclasses which use a different Template to create a different DOM structure may need to provide
their own implementation of this method.
ReturnsObjectSubstitution data for a Template. The default implementation which provides data for the default
template returns an Object containing the following properties:
innerCls : StringA CSS class to apply to the button's text element.


### getText

Gets the text for this Button ...

Gets the text for this Button
ReturnsStringThe button text


### getTipAttr

...


### getTpl

...

Parametersname : Object


### getTriggerRegion

Returns an object containing begin and end properties that indicate the
left/right bounds of a right trigger or the t...

Returns an object containing `begin` and `end` properties that indicate the
left/right bounds of a right trigger or the top/bottom bounds of a bottom trigger.
ReturnsObject


### getTriggerSize

Measures the size of the trigger area for menu and split buttons. ...

Measures the size of the trigger area for menu and split buttons. Will be a width for
a right-aligned trigger and a height for a bottom-aligned trigger. Cached after first measurement.


### getViewRegion

Returns the content region of this element. ...

Returns the **content** region of this element. That is the region within the borders
and padding.
ReturnsExt.util.RegionA Region containing "top, left, bottom, right" member data.


### getVisibilityEl

Deprecate 5.0 ...

Deprecate 5.0


### getWidth

Gets the current width of the component's underlying element. ...

Gets the current width of the component's underlying element.
ReturnsNumber


### getX

Gets the current X position of the DOM element based on page coordinates. ...

Gets the current X position of the DOM element based on page coordinates.
ReturnsNumberThe X position of the element


### getXType

Gets the xtype for this component as registered with Ext.ComponentManager. ...

Gets the xtype for this component as registered with Ext.ComponentManager. For a list of all available
xtypes, see the Ext.Component header. Example usage:

var t = new Ext.form.field.Text();
alert(t.getXType());  // alerts 'textfield'

ReturnsStringThe xtype


### getXTypes

Returns this Component's xtype hierarchy as a slash-delimited string. ...

Returns this Component's xtype hierarchy as a slash-delimited string. For a list of all available xtypes, see the
Ext.Component header.

If using your own subclasses, be aware that a Component must register its own xtype to participate in
determination of inherited xtypes.

Example usage:

var t = new Ext.form.field.Text();
alert(t.getXTypes());  // alerts 'component/field/textfield'

        Available since: 2.3.0
ReturnsStringThe xtype hierarchy string


### getXY

Gets the current position of the DOM element based on page coordinates. ...

Gets the current position of the DOM element based on page coordinates.
ReturnsNumber[]The XY position of the element


### getY

Gets the current Y position of the DOM element based on page coordinates. ...

Gets the current Y position of the DOM element based on page coordinates.
ReturnsNumberThe Y position of the element


### hasActiveFx

Returns the current animation if this object has any effects actively running or queued, else returns false. ...

Returns the current animation if this object has any effects actively running or queued, else returns false.
        
        This method has been **deprecated** since 4.0
        Replaced by getActiveAnimation


### hasCls

Checks if the specified CSS class exists on this element's DOM node. ...

Checks if the specified CSS class exists on this element's DOM node.
ParametersclassName : StringThe CSS class to check for.


### hasConfig

...

Parametersconfig : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer
indicates whether the event needs firing or not.
ParameterseventName : StringThe name of the event to check for


### hasUICls

Checks if there is currently a specified uiCls. ...

Checks if there is currently a specified `uiCls`.
Parameterscls : StringThe `cls` to check.


### hasVisibleMenu

Returns true if the button has a menu and it is visible ...

Returns true if the button has a menu and it is visible
ReturnsBoolean


### hide

Hides this Component, setting it to invisible using the configured hideMode. ...

Hides this Component, setting it to invisible using the configured hideMode.
ParametersanimateTarget : String/Ext.Element/Ext.Component (optional)only valid for floating Components
such as Windows or ToolTips, or regular Components which have
been configured with `floating: true`.. The target to which the Component should animate while hiding.
Defaults to: `null`


### hideMenu

Hides this button's menu (if it has one) ...

Hides this button's menu (if it has one)
ReturnsExt.button.Buttonthis


### initBorderRegion

This method is called by the Ext.layout.container.Border class when instances are
added as regions to the layout. ...

This method is called by the `Ext.layout.container.Border` class when instances are
added as regions to the layout. Since it is valid to add any component to a border
layout as a region, this method must be added to `Ext.Component` but is only ever
called when that component is owned by a `border` layout.

**Defined in override Ext.layout.container.border.Region.**


### initCls

...


### initComponent

The initComponent template method is an important initialization step for a Component. ...

The initComponent template method is an important initialization step for a Component. It is intended to be
implemented by each subclass of Ext.Component to provide any needed constructor logic. The
initComponent method of the class being created is called first, with each initComponent method
up the hierarchy to Ext.Component being called thereafter. This makes it easy to implement and,
if needed, override the constructor logic of the Component at any step in the hierarchy.

The initComponent method **must** contain a call to callParent in order
to ensure that the parent class' initComponent method is also called.

All config options passed to the constructor are applied to `this` before initComponent is called,
so you can simply access them with `this.someOption`.

The following example demonstrates using a dynamic string for the text of a button at the time of
instantiation of the class.

Ext.define('DynamicButtonText', {
    extend: 'Ext.button.Button',

    initComponent: function() {
        this.text = new Date();
        this.renderTo = Ext.getBody();
        this.callParent();
    }
});

Ext.onReady(function() {
    Ext.create('DynamicButtonText');
});

        Available since: 1.1.0
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


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


### initContainer

...

Parameterscontainer : Object


### initDraggable

...


### initEvents

Initialize any events on this component ...

Initialize any events on this component


### initFrame

...


### initFramingTpl

Poke in a reference to applyRenderTpl(frameInfo, out) ...

Poke in a reference to applyRenderTpl(frameInfo, out)
Parameterstable : Object


### initHierarchyEvents

...


### initHierarchyState

Called by getHierarchyState to initialize the hierarchyState the first
time it is requested. ...

Called by getHierarchyState to initialize the hierarchyState the first
time it is requested.

**Overridden in Ext.rtl.AbstractComponent.**
ParametershierarchyState : Object


### initPadding

Initializes padding by applying it to the target element, or if the layout manages
padding ensures that the padding o...

Initializes padding by applying it to the target element, or if the layout manages
padding ensures that the padding on the target element is "0".
ParameterstargetEl : Object


### initPlugin

...

Parametersplugin : Object


### initRenderData

Initialized the renderData to be used when rendering the renderTpl. ...

Initialized the renderData to be used when rendering the renderTpl.
ReturnsObjectObject with keys and values that are going to be applied to the renderTpl


### initRenderTpl

Initializes the renderTpl. ...

Initializes the renderTpl.
ReturnsExt.XTemplateThe renderTpl XTemplate instance.


### initResizable

...

Parametersresizable : Object


### initState

Initializes the state of the object upon construction. ...

Initializes the state of the object upon construction.


### initStyles

Applies padding, margin, border, top, left, height, and width configs to the
appropriate elements. ...

Applies padding, margin, border, top, left, height, and width configs to the
appropriate elements.
ParameterstargetEl : Object


### is

Tests whether this Component matches the selector string. ...

Tests whether this Component matches the selector string.
Parametersselector : StringThe selector string to test against.


### isContainedFloater

Utility method to determine if a Component is floating, and has an owning Container whose coordinate system
it must b...

Utility method to determine if a Component is floating, and has an owning Container whose coordinate system
it must be positioned in when using setPosition.


### isDescendant

...

Parametersancestor : Object


### isDescendantOf

Determines whether this component is the descendant of a particular container. ...

Determines whether this component is the descendant of a particular container.
Parameterscontainer : Ext.Container


### isDisabled

Method to determine whether this Component is currently disabled. ...

Method to determine whether this Component is currently disabled.
ReturnsBooleanthe disabled state of this Component.


### isDraggable

Method to determine whether this Component is draggable. ...

Method to determine whether this Component is draggable.
ReturnsBooleanthe draggable state of this component.


### isDroppable

Method to determine whether this Component is droppable. ...

Method to determine whether this Component is droppable.
ReturnsBooleanthe droppable state of this component.


### isFloating

Method to determine whether this Component is floating. ...

Method to determine whether this Component is floating.
ReturnsBooleanthe floating state of this component.


### isFocusable

...


### isHidden

Method to determine whether this Component is currently set to hidden. ...

Method to determine whether this Component is currently set to hidden.
ReturnsBooleanthe hidden state of this Component.


### isHierarchicallyHidden

...


### isLayoutRoot

Determines whether this Component is the root of a layout. ...

Determines whether this Component is the root of a layout. This returns `true` if
this component can run its layout without assistance from or impact on its owner.
If this component cannot run its layout given these restrictions, `false` is returned
and its owner will be considered as the next candidate for the layout root.

Setting the _isLayoutRoot property to `true` causes this method to always
return `true`. This may be useful when updating a layout of a Container which shrink
wraps content, and you know that it will not change size, and so can safely be the
topmost participant in the layout run.


### isLayoutSuspended

Returns true if layout is suspended for this component. ...

Returns `true` if layout is suspended for this component. This can come from direct
suspension of this component's layout activity (Ext.Container.suspendLayout) or if one
of this component's containers is suspended.
ReturnsBoolean`true` layout of this component is suspended.


### isLocalRtl

Returns true if this component's local coordinate system is rtl. ...

Returns true if this component's local coordinate system is rtl. For normal
components this equates to the value of isParentRtl().  Floaters are a bit different
because a floater's element can be a childNode of something other than its
parent component's element.  For floaters we have to read the dom to see if the
component's element's parentNode has a css direction value of "rtl".

**Defined in override Ext.rtl.AbstractComponent.**
ReturnsBoolean


### isOppositeRootDirection

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**


### isParentRtl

Returns true if this component's parent container is rtl. ...

Returns true if this component's parent container is rtl. Used by rtl positioning
methods to determine if the component should be positioned using a right-to-left
coordinate system.

**Defined in override Ext.rtl.AbstractComponent.**
ReturnsBoolean


### isVisible

Returns true if this component is visible. ...

Returns `true` if this component is visible.
        Available since: 1.1.0
Parametersdeep : Boolean (optional)Pass `true` to interrogate the visibility status of all parent Containers to
determine whether this Component is truly visible to the user.

Generally, to determine whether a Component is hidden, the no argument form is needed. For example when creating
dynamically laid out UIs in a hidden Container before showing them.
Defaults to: `false`


### isXType

Tests whether or not this Component is of a specific xtype. ...

Tests whether or not this Component is of a specific xtype. This can test whether this Component is descended
from the xtype (default) or whether it is directly of the xtype specified (`shallow = true`).

If using your own subclasses, be aware that a Component must register its own xtype to participate in
determination of inherited xtypes.

For a list of all available xtypes, see the Ext.Component header.

Example usage:

var t = new Ext.form.field.Text();
var isText = t.isXType('textfield');        // true
var isBoxSubclass = t.isXType('field');       // true, descended from Ext.form.field.Base
var isBoxInstance = t.isXType('field', true); // false, not a direct Ext.form.field.Base instance

        Available since: 2.3.0
Parametersxtype : StringThe xtype to check for this Component


### makeFloating

...

Parametersdom : Object


### mask

...


### maybeShowMenu

...


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener.

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destroyed.
Parametersitem : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### move

Move the element relative to its current position. ...

Move the element relative to its current position.
Parametersdirection : StringPossible values are:


`"l"` (or `"left"`)
`"r"` (or `"right"`)
`"t"` (or `"top"`, or `"up"`)
`"b"` (or `"bottom"`, or `"down"`)


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener.

Removes listeners that were added by the mon method.
Parametersitem : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### nextNode

Returns the next node in the Component tree in tree traversal order. ...

Returns the next node in the Component tree in tree traversal order.

Note that this is not limited to siblings, and if invoked upon a node with no matching siblings, will walk the
tree to attempt to find a match. Contrast with nextSibling.
Parametersselector : String (optional)A ComponentQuery selector to filter the following nodes.


### nextSibling

Returns the next sibling of this Component. ...

Returns the next sibling of this Component.

Optionally selects the next sibling which matches the passed ComponentQuery selector.

May also be referred to as **`next()`**

Note that this is limited to siblings, and if no siblings of the item match, `null` is returned. Contrast with
nextNode
Parametersselector : String (optional)A ComponentQuery selector to filter the following items.


### on

Shorthand for addListener. ...

Shorthand for addListener.

Appends an event handler to this object.  For example:

myGridPanel.on("mouseover", this.onMouseOver, this);


The method also allows for a single argument to be passed which is a config object
containing properties which specify multiple events. For example:

myGridPanel.on({
    cellClick: this.onCellClick,
    mouseover: this.onMouseOver,
    mouseout: this.onMouseOut,
    scope: this // Important. Ensure "this" is correct during handler execution
});


One can also specify options for each event handler separately:

myGridPanel.on({
    cellClick: {fn: this.onCellClick, scope: this, single: true},
    mouseover: {fn: panel.onMouseOver, scope: panel}
});


*Names* of methods in a specified scope may also be used. Note that
`scope` MUST be specified to use this option:

myGridPanel.on({
    cellClick: {fn: 'onCellClick', scope: this, single: true},
    mouseover: {fn: 'onMouseOver', scope: panel}
});

ParameterseventName : String/ObjectThe name of the event to listen for.
May also be an object who's property names are event names.


### onAdded

Method to manage awareness of when components are added to their
respective Container, firing an added event. ...

Method to manage awareness of when components are added to their
respective Container, firing an added event. References are
established at add time rather than at render time.

Allows addition of behavior when a Component is added to a
Container. At this stage, the Component is in the parent
Container's collection of child items. After calling the
superclass's `onAdded`, the `ownerCt` reference will be present,
and if configured with a ref, the `refOwner` will be set.
        Available since: 3.4.0
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onAfterFloatLayout

...


### onBeforeFloatLayout

...


### onBlur

private ...

private
Parameterse : Object


### onBoxReady

...

Parameterswidth : Object


### onClick

...

Parameterse : Object


### onConfigUpdate

...

Parametersnames : Object


### onDestroy

Allows addition of behavior to the destroy operation. ...

Allows addition of behavior to the destroy operation.
After calling the superclass's onDestroy, the Component will be destroyed.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onDisable

See comments in onFocus

Allows addition of behavior to the disable operation. ...

See comments in onFocus

Allows addition of behavior to the disable operation.
After calling the superclass's `onDisable`, the Component will be disabled.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onDownKey

...

Parametersk : Object


### onEnable

Allows addition of behavior to the enable operation. ...

Allows addition of behavior to the enable operation.
After calling the superclass's `onEnable`, the Component will be enabled.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onFloatShow

...


### onFocus

private ...

private
Parameterse : Object


### onHide

Possibly animates down to a target element. ...

Possibly animates down to a target element.

Allows addition of behavior to the hide operation. After
calling the superclass’s onHide, the Component will be hidden.

Gets passed the same parameters as hide.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onKeyDown

Listen for TAB events and wrap round if tabbing of either end of the Floater ...

Listen for TAB events and wrap round if tabbing of either end of the Floater
Parameterse : Object


### onMenuHide

...

Parameterse : Object


### onMenuShow

...

Parameterse : Object


### onMenuTriggerOut

virtual mouseleave handler called when it is detected that the mouseout event
signified the mouse leaving the arrow a...

virtual mouseleave handler called when it is detected that the mouseout event
signified the mouse leaving the arrow area of the button - the `<em>`.
Parameterse : Object


### onMenuTriggerOver

virtual mouseenter handler called when it is detected that the mouseover event
signified the mouse entering the arrow...

virtual mouseenter handler called when it is detected that the mouseover event
signified the mouse entering the arrow area of the button - the `<em>`.
Parameterse : Object


### onMouseDown

...

Parameterse : Object


### onMouseEnter

virtual mouseenter handler called when it is detected that the mouseout event
signified the mouse entering the encaps...

virtual mouseenter handler called when it is detected that the mouseout event
signified the mouse entering the encapsulating element.
Parameterse : Object


### onMouseLeave

virtual mouseleave handler called when it is detected that the mouseover event
signified the mouse entering the encap...

virtual mouseleave handler called when it is detected that the mouseover event
signified the mouse entering the encapsulating element.
Parameterse : Object


### onMouseMove

mousemove handler called when the mouse moves anywhere within the encapsulating element. ...

mousemove handler called when the mouse moves anywhere within the encapsulating element.
The position is checked to determine if the mouse is entering or leaving the trigger area. Using
mousemove to check this is more resource intensive than we'd like, but it is necessary because
the trigger area does not line up exactly with sub-elements so we don't always get mouseover/out
events when needed. In the future we should consider making the trigger a separate element that
is absolutely positioned and sized over the trigger area.
Parameterse : Object


### onMouseOut

mouseout handler called when a mouseout event occurs anywhere within the encapsulating element -
or the mouse leaves ...

mouseout handler called when a mouseout event occurs anywhere within the encapsulating element -
or the mouse leaves the encapsulating element.
The targets are interrogated to see what is being exited to where.
Parameterse : Object


### onMouseOver

mouseover handler called when a mouseover event occurs anywhere within the encapsulating element. ...

mouseover handler called when a mouseover event occurs anywhere within the encapsulating element.
The targets are interrogated to see what is being entered from where.
Parameterse : Object


### onMouseUp

...

Parameterse : Object


### onPosition

Called after the component is moved, this method is empty by default but can be implemented by any
subclass that need...

Called after the component is moved, this method is empty by default but can be implemented by any
subclass that needs to perform custom logic after a move occurs.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onRemoved

Method to manage awareness of when components are removed from their
respective Container, firing a removed event. ...

Method to manage awareness of when components are removed from their
respective Container, firing a removed event. References are properly
cleaned up after removing a component from its owning container.

Allows addition of behavior when a Component is removed from
its parent Container. At this stage, the Component has been
removed from its parent Container's collection of child items,
but has not been destroyed (It will be destroyed if the parent
Container's `autoDestroy` is `true`, or if the remove call was
passed a truthy second parameter). After calling the
superclass's `onRemoved`, the `ownerCt` and the `refOwner` will not
be present.
        Available since: 3.4.0
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onRender

Template method called when this Component's DOM structure is created. ...

Template method called when this Component's DOM structure is created.

At this point, this Component's (and all descendants') DOM structure *exists* but it has not
been layed out (positioned and sized).

Subclasses which override this to gain access to the structure at render time should
call the parent class's method before attempting to access any child elements of the Component.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onRepeatClick

...

Parametersrepeat : Object


### onResize

Allows addition of behavior to the resize operation. ...

Allows addition of behavior to the resize operation.

Called when Ext.resizer.Resizer#drag event is fired.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onShow

Allows addition of behavior to the show operation. ...

Allows addition of behavior to the show operation. After
calling the superclass's onShow, the Component will be visible.

Override in subclasses where more complex behaviour is needed.

Gets passed the same parameters as show.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onShowComplete

Invoked after the afterShow method is complete. ...

Invoked after the afterShow method is complete.

Gets passed the same `callback` and `scope` parameters that afterShow received.
      
      This is a template method.
         a hook into the functionality of this class.
         Feel free to override it in child classes.


### onShowVeto

...


### onStateChange

This method is called when any of the stateEvents are fired. ...

This method is called when any of the stateEvents are fired.


### parseBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**
Parametersbox : Object


### postBlur

Template method to do any post-blur processing. ...

Template method to do any post-blur processing.
Parameterse : Ext.EventObjectThe event object


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a
class derives from this class or uses this class as a mixin.
ParametersT : FunctionThe class constructor to prepare.


### previousNode

Returns the previous node in the Component tree in tree traversal order. ...

Returns the previous node in the Component tree in tree traversal order.

Note that this is not limited to siblings, and if invoked upon a node with no matching siblings, will walk the
tree in reverse order to attempt to find a match. Contrast with previousSibling.
Parametersselector : String (optional)A ComponentQuery selector to filter the preceding nodes.


### previousSibling

Returns the previous sibling of this Component. ...

Returns the previous sibling of this Component.

Optionally selects the previous sibling which matches the passed ComponentQuery
selector.

May also be referred to as **`prev()`**

Note that this is limited to siblings, and if no siblings of the item match, `null` is returned. Contrast with
previousNode
Parametersselector : String (optional)A ComponentQuery selector to filter the preceding items.


### prune

...

ParameterschildEls : Object


### query

Retrieves all descendant components which match the passed selector. ...

Retrieves all descendant components which match the passed selector.
Executes an Ext.ComponentQuery.query using this container as its root.
Parametersselector : String (optional)Selector complying to an Ext.ComponentQuery selector.
If no selector is specified all items will be returned.


### queryBy

Retrieves all descendant components which match the passed function. ...

Retrieves all descendant components which match the passed function.
The function should return false for components that are to be
excluded from the selection.
Parametersfn : FunctionThe matcher function. It will be called with a single argument,
the component being tested.


### queryById

Finds a component at any level under this container matching the id/itemId. ...

Finds a component at any level under this container matching the id/itemId.
This is a shorthand for calling ct.down('#' + id);
Parametersid : StringThe id to find


### registerFloatingItem

Called by Component#doAutoRender

Register a Container configured floating: true with this Component's ZIndexManager. ...

Called by Component#doAutoRender

Register a Container configured `floating: true` with this Component's ZIndexManager.

Components added in this way will not participate in any layout, but will be rendered
upon first show in the way that Windows are.
Parameterscmp : Object


### registerWithOwnerCt

...


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`.

For example if you are extending Grid, you might decide to forward some events from store.
So you can do this inside your initComponent:

this.relayEvents(this.getStore(), ['load']);


The grid instance will then have an observable 'load' event which will be passed the
parameters of the store's load event and any function fired with the grid's load event
would have access to the grid using the `this` keyword.
Parametersorigin : ObjectThe Observable whose events this object is to relay.


### removeAnchor

Remove any anchor to this element. ...

Remove any anchor to this element. See anchorTo.
ReturnsExt.util.Positionablethis


### removeChildEls

Removes items in the childEls array based on the return value of a supplied test
function. ...

Removes items in the childEls array based on the return value of a supplied test
function. The function is called with a entry in childEls and if the test function
return true, that entry is removed. If false, that entry is kept.
ParameterstestFn : FunctionThe test function.


### removeClass

...

Available since: 2.3.0


### removeCls

Removes a CSS class from the top level element representing this component. ...

Removes a CSS class from the top level element representing this component.
Parameterscls : String/String[]The CSS class name to remove.


### removeClsWithUI

Removes a cls to the uiCls array, which will also call removeUIClsFromElement and removes it from all
elements of thi...

Removes a `cls` to the `uiCls` array, which will also call removeUIClsFromElement and removes it from all
elements of this component.
Parameterscls : String/String[]A string or an array of strings to remove to the `uiCls`.


### removeListener

Removes an event handler. ...

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


### removeManagedListener

Removes listeners that were added by the mon method. ...

Removes listeners that were added by the mon method.
Parametersitem : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### removeManagedListenerItem

inherit docs

Remove a single managed listener item ...

inherit docs

Remove a single managed listener item
ParametersisClear : BooleanTrue if this is being called during a clear


### removeOverCls

...

Overrides: Ext.AbstractComponent.removeOverCls


### removePlugin

...

Parametersplugin : Object


### removeUIClsFromElement

Method which removes a specified UI + uiCls from the components element. ...

Method which removes a specified UI + `uiCls` from the components element. The `cls` which is added to the element
will be: `this.baseCls + '-' + ui`.
Parametersui : StringThe UI to add to the element.


### removeUIFromElement

Method which removes a specified UI from the components element. ...

Method which removes a specified UI from the components element.


### render

Renders the Component into the passed HTML element. ...

Renders the Component into the passed HTML element.

If you are using a Container object to house this
Component, then do not use the render method.

A Container's child Components are rendered by that Container's
layout manager when the Container is first rendered.

If the Container is already rendered when a new child Component is added, you may need to call
the Container's doLayout to refresh the view which
causes any unrendered child Components to be rendered. This is required so that you can add
multiple child components if needed while only refreshing the layout once.

When creating complex UIs, it is important to remember that sizing and positioning
of child items is the responsibility of the Container's layout
manager.  If you expect child items to be sized in response to user interactions, you must
configure the Container with a layout manager which creates and manages the type of layout you
have in mind.

Omitting the Container's layout config means that a basic
layout manager is used which does nothing but render child components sequentially into the
Container. No sizing or positioning will be performed in this situation.
Parameterscontainer : Ext.Element/HTMLElement/String (optional)The element this Component should be
rendered into. If it is being created from existing markup, this should be omitted.


### restoreClick

...


### resumeEvent

Resumes firing of the named event(s). ...

Resumes firing of the named event(s).

After calling this method to resume events, the events will fire when requested to fire.

Note that if the suspendEvent method is called multiple times for a certain event,
this converse method will have to be called the same number of times for it to resume firing.
ParameterseventName : String...Multiple event names to resume.


### resumeEvents

Resumes firing events (see suspendEvents). ...

Resumes firing events (see suspendEvents).

If events were suspended using the `queueSuspended` parameter, then all events fired
during event suspension will be sent to any listeners now.


### resumeLayouts

...

ParametersflushOptions : Object


### savePropToState

Conditionally saves a single property from this object to the given state object. ...

Conditionally saves a single property from this object to the given state object.
The idea is to only save state which has changed from the initial state so that
current software settings do not override future software settings. Only those
values that are user-changed state should be saved.
ParameterspropName : StringThe name of the property to save.


### savePropsToState

Gathers additional named properties of the instance and adds their current values
to the passed state object. ...

Gathers additional named properties of the instance and adds their current values
to the passed state object.
ParameterspropNames : String/String[]The name (or array of names) of the property to save.


### saveState

Saves the state of the object to the persistence store. ...

Saves the state of the object to the persistence store.


### scrollBy

Scrolls this Component's target element by the passed delta values, optionally animating. ...

Scrolls this Component's target element by the passed delta values, optionally animating.

All of the following are equivalent:

 comp.scrollBy(10, 10, true);
 comp.scrollBy([10, 10], true);
 comp.scrollBy({ x: 10, y: 10 }, true);

ParametersdeltaX : Number/Number[]/ObjectEither the x delta, an Array specifying x and y deltas or
an object with "x" and "y" properties.


### sequenceFx

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. ...

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. This is the
opposite of syncFx.
ReturnsObjectthis


### setActive

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been
moved to th...

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been
moved to the top of its zIndex stack, or pushed from the top of its zIndex stack.

If a *Window* is superceded by another Window, deactivating it hides its shadow.

This method also fires the activate or
deactivate event depending on which action occurred.
Parametersactive : Boolean (optional)True to activate the Component, false to deactivate it.
Defaults to: `false`


### setArrowHandler

Sets this button's arrow click handler. ...

Sets this button's arrow click handler.
Parametershandler : FunctionThe function to call when the arrow is clicked.


### setAutoScroll

Sets the overflow on the content element of the component. ...

Sets the overflow on the content element of the component.
Parametersscroll : BooleanTrue to allow the Component to auto scroll.


### setBorder

...

Parametersborder : String/NumberThe border, see border. If a falsey value is passed
the border will be removed.


### setBorderRegion

This method changes the region config property for this border region. ...

This method changes the `region` config property for this border region. This is
only valid if this component is in a `border` layout (`Ext.layout.container.Border`).

**Defined in override Ext.layout.container.border.Region.**
Parametersregion : StringThe new `region` value (`"north"`, `"south"`, `"east"` or
`"west"`).


### setBox

Sets the element's box. ...

Sets the element's box. If animate is true then x, y, width, and height will be
animated concurrently.
Parametersbox : ObjectThe box to fill {x, y, width, height}


### setComponentCls

...


### setComponentLayout

...

Parameterslayout : Object


### setConfig

...

Parametersconfig : Object


### setDisabled

Enable or disable the component. ...

Enable or disable the component.
Parametersdisabled : Boolean`true` to disable.


### setDocked

Sets the dock position of this component in its parent panel. ...

Sets the dock position of this component in its parent panel. Note that this only has effect if this item is part
of the `dockedItems` collection of a parent that has a DockLayout (note that any Panel has a DockLayout by default)
Parametersdock : ObjectThe dock position.


### setFloatParent

...

ParametersfloatParent : Object


### setGlyph

Sets this button's glyph ...

Sets this button's glyph
Parametersglyph : Number/Stringthe numeric charCode or string charCode/font-family.
This parameter expects a format consistent with that of glyph


### setHandler

Assigns this Button's click handler ...

Assigns this Button's click handler
Parametershandler : FunctionThe function to call when the button is clicked


### setHeight

Sets the height of the component. ...

Sets the height of the component. This method fires the resize event.
Parametersheight : NumberThe new height to set. This may be one of:


A Number specifying the new height in the Element's Ext.Element.defaultUnits (by default, pixels).
A String used to set the CSS height style.
*undefined* to leave the height unchanged.


### setHiddenState

...

Parametershidden : Object


### setHref

Sets the href of the embedded anchor element to the passed URL. ...

Sets the href of the embedded anchor element to the passed URL.

Also appends any configured baseParams and parameters set through setParams.
Parametershref : StringThe URL to set in the anchor element.


### setIcon

Sets the background image (inline style) of the button. ...

Sets the background image (inline style) of the button. This method also changes the value of the icon
config internally.
Parametersicon : StringThe path to an image to display in the button


### setIconCls

Sets the CSS class that provides a background image to use as the button's icon. ...

Sets the CSS class that provides a background image to use as the button's icon. This method also changes the
value of the iconCls config internally.
Parameterscls : StringThe CSS class providing the icon image


### setLoading

This method allows you to show or hide a LoadMask on top of this component. ...

This method allows you to show or hide a LoadMask on top of this component.
Parametersload : Boolean/Object/StringTrue to show the default LoadMask, a config object that will be passed to the
LoadMask constructor, or a message String to show. False to hide the current LoadMask.


### setLocalX

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Sets the local x coordinate of this element using CSS style. When used on an
absolute positioned element this method is symmetrical with getLocalX, but
may not be symmetrical when used on a relatively positioned element.
Parametersx : NumberThe x coordinate. A value of `null` sets the left style to 'auto'.


### setLocalXY

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

Sets the local x and y coordinates of this element using CSS style. When used on an
absolute positioned element this method is symmetrical with getLocalXY, but
may not be symmetrical when used on a relatively positioned element.
Parametersx : Number/ArrayThe x coordinate or an array containing [x, y]. A value of
`null` sets the left style to 'auto'


### setLocalY

Sets the local y coordinate of this element using CSS style. ...

Sets the local y coordinate of this element using CSS style. When used on an
absolute positioned element this method is symmetrical with getLocalY, but
may not be symmetrical when used on a relatively positioned element.
Parametersy : NumberThe y coordinate. A value of `null` sets the top style to 'auto'.


### setMargin

Sets the margin on the target element. ...

Sets the margin on the target element.
Parametersmargin : Number/StringThe margin to set. See the margin config.


### setOverflowXY

Sets the overflow x/y on the content element of the component. ...

Sets the overflow x/y on the content element of the component. The x/y overflow
values can be any valid CSS overflow (e.g., 'auto' or 'scroll'). By default, the
value is 'hidden'. Passing null for one of the values will erase the inline style.
Passing `undefined` will preserve the current value.
ParametersoverflowX : StringThe overflow-x value.


### setPagePosition

Sets the page XY position of the component. ...

Sets the page XY position of the component. To set the left and top instead, use setPosition.
This method fires the move event.
Parametersx : Number/Number[]The new x position or an array of `[x,y]`.


### setParams

Sets the href of the link dynamically according to the params passed, and any baseParams configured. ...

Sets the href of the link dynamically according to the params passed, and any baseParams configured.

**Only valid if the Button was originally configured with a href**
Parametersparams : ObjectParameters to use in the href URL.


### setPosition

Sets the left and top of the component. ...

Sets the left and top of the component. To set the page XY position instead, use setPagePosition. This
method fires the move event.
Parametersx : Number/Number[]/ObjectThe new left, an array of `[x,y]`, or animation config object containing `x` and `y` properties.


### setRegion

Sets the element's position and size to the specified region. ...

Sets the element's position and size to the specified region. If animation is true
then width, height, x and y will be animated concurrently.
Parametersregion : Ext.util.RegionThe region to fill


### setRegionWeight

Sets the weight config property for this component. ...

Sets the `weight` config property for this component. This is only valid if this
component is in a `border` layout (`Ext.layout.container.Border`).

**Defined in override Ext.layout.container.border.Region.**
Parametersweight : NumberThe new `weight` value.


### setScale

Method to change the scale of the button. ...

Method to change the scale of the button. See scale for allowed configurations.
Parametersscale : StringThe scale to change to.


### setSize

Sets the width and height of this Component. ...

Sets the width and height of this Component. This method fires the resize event. This method can accept
either width and height as separate arguments, or you can pass a size object like `{width:10, height:20}`.
Parameterswidth : Number/String/ObjectThe new width to set. This may be one of:


A Number specifying the new width in the Element's Ext.Element.defaultUnits (by default, pixels).
A String used to set the CSS width style.
A size object in the format `{width: widthValue, height: heightValue}`.
`undefined` to leave the width unchanged.


### setText

Sets this Button's text ...

Sets this Button's text
Parameterstext : StringThe button text


### setTextAlign

Sets the text alignment for this button. ...

Sets the text alignment for this button.
Parametersalign : StringThe new alignment of the button text. See textAlign.


### setTooltip

Sets the tooltip for this Button. ...

Sets the tooltip for this Button.
Parameterstooltip : String/ObjectThis may be:


**String** : A string to be used as innerHTML (html tags are accepted) to show in a tooltip
**Object** : A configuration object for Ext.tip.QuickTipManager.register.


### setUI

inherit docs

Sets the UI for the component. ...

inherit docs

Sets the UI for the component. This will remove any existing UIs on the component. It will also loop through any
`uiCls` set on the component and rename them so they include the new UI.
Parametersui : StringThe new UI for the component.


### setVisible

Convenience function to hide or show this component by Boolean. ...

Convenience function to hide or show this component by Boolean.
        Available since: 1.1.0
Parametersvisible : Boolean`true` to show, `false` to hide.


### setWidth

Sets the width of the component. ...

Sets the width of the component. This method fires the resize event.
Parameterswidth : NumberThe new width to setThis may be one of:


A Number specifying the new width in the Element's Ext.Element.defaultUnits (by default, pixels).
A String used to set the CSS width style.


### setX

Sets the X position of the DOM element based on page coordinates. ...

Sets the X position of the DOM element based on page coordinates.
ParametersThe : NumberX position


### setXY

Sets the position of the DOM element in page coordinates. ...

Sets the position of the DOM element in page coordinates.
Parameterspos : Number[]Contains X & Y [x, y] values for new position (coordinates
are page-based)


### setY

Sets the Y position of the DOM element based on page coordinates. ...

Sets the Y position of the DOM element based on page coordinates.
ParametersThe : NumberY position


### setZIndex

z-index is managed by the zIndexManager and may be overwritten at any time. ...

z-index is managed by the zIndexManager and may be overwritten at any time.
Returns the next z-index to be used.
If this is a Container, then it will have rebased any managed floating Components,
and so the next available z-index will be approximately 10000 above that.
Parametersindex : Object


### setupFramingTpl

Inject a reference to the function which applies the render template into the framing template. ...

Inject a reference to the function which applies the render template into the framing template. The framing template
wraps the content.
ParametersframeTpl : Object


### setupProtoEl

...


### setupRenderTpl

...

ParametersrenderTpl : Object


### show

Shows this Component, rendering it first if autoRender or floating are true. ...

Shows this Component, rendering it first if autoRender or floating are `true`.

After being shown, a floating Component (such as a Ext.window.Window), is activated it and
brought to the front of its z-index stack.
ParametersanimateTarget : String/Ext.Element (optional)only valid for floating Components such as Windows or ToolTips, or regular Components which have been configured
with `floating: true`. The target from which the Component should animate from while opening.
Defaults to: `null`


### showAt

Displays component at specific xy position. ...

Displays component at specific xy position.
A floating component (like a menu) is positioned relative to its ownerCt if any.
Useful for popping up a context menu:

listeners: {
    itemcontextmenu: function(view, record, item, index, event, options) {
        Ext.create('Ext.menu.Menu', {
            width: 100,
            height: 100,
            margin: '0 0 10 0',
            items: [{
                text: 'regular item 1'
            },{
                text: 'regular item 2'
            },{
                text: 'regular item 3'
            }]
        }).showAt(event.getXY());
    }
}

Parametersx : Number/Number[]The new x position or array of `[x,y]`.


### showBy

Shows this component by the specified Component or Element. ...

Shows this component by the specified Component or Element.
Used when this component is floating.
Parameterscomponent : Ext.Component/Ext.dom.ElementThe Ext.Component or Ext.Element to show the component by.


### showMenu

Shows this button's menu (if it has one) ...

Shows this button's menu (if it has one)
ParametersfromEvent : Object


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


### stopAnimation

Stops any running effects and clears this object's internal effects queue if it contains any additional effects
that ...

Stops any running effects and clears this object's internal effects queue if it contains any additional effects
that haven't started yet.
ReturnsExt.ElementThe Element


### stopFx

Stops any running effects and clears this object's internal effects queue if it contains any additional effects
that ...

Stops any running effects and clears this object's internal effects queue if it contains any additional effects
that haven't started yet.
        
        This method has been **deprecated** since 4.0
        Replaced by stopAnimation


### suspendEvent

Suspends firing of the named event(s). ...

Suspends firing of the named event(s).

After calling this method to suspend events, the events will no longer fire when requested to fire.

Note that if this is called multiple times for a certain event, the converse method
resumeEvent will have to be called the same number of times for it to resume firing.
ParameterseventName : String...Multiple event names to suspend.


### suspendEvents

Suspends the firing of all events. ...

Suspends the firing of all events. (see resumeEvents)
ParametersqueueSuspended : BooleanPass as true to queue up suspended events to be fired
after the resumeEvents call instead of discarding all suspended events.


### suspendLayouts

...


### syncFx

Ensures that all effects queued after syncFx is called on this object are run concurrently. ...

Ensures that all effects queued after syncFx is called on this object are run concurrently. This is the opposite
of sequenceFx.
ReturnsObjectthis


### syncHidden

synchronizes the hidden state of this component with the state of its hierarchy ...

synchronizes the hidden state of this component with the state of its hierarchy


### syncShadow

...


### toBack

Sends this Component to the back of (lower z-index than) any other visible windows ...

Sends this Component to the back of (lower z-index than) any other visible windows
ReturnsExt.Componentthis


### toFront

Brings this floating Component to the front of any other visible, floating Components managed by the same
ZIndexManag...

Brings this floating Component to the front of any other visible, floating Components managed by the same
ZIndexManager

If this Component is modal, inserts the modal mask just below this Component in the z-index stack.
ParameterspreventFocus : Boolean (optional)Specify `true` to prevent the Component from being focused.
Defaults to: `false`


### toggle

If a state it passed, it becomes the pressed state otherwise the current state is toggled. ...

If a state it passed, it becomes the pressed state otherwise the current state is toggled.
Parametersstate : Boolean (optional)Force a particular state


### translatePoints

Translates the passed page coordinates into left/top css values for the element ...

Translates the passed page coordinates into left/top css values for the element
Parametersx : Number/ArrayThe page x or an array containing [x, y]


### translateXY

Translates the passed page coordinates into x and y css values for the element ...

Translates the passed page coordinates into x and y css values for the element
Parametersx : Number/ArrayThe page x or an array containing [x, y]


### un

Shorthand for removeListener. ...

Shorthand for removeListener.

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


### unitizeBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**
Parametersbox : Object


### unmask

...


### unregisterFloatingItem

...

Parameterscmp : Object


### up

Navigates up the ownership hierarchy searching for an ancestor Container which matches any passed simple selector or ...

Navigates up the ownership hierarchy searching for an ancestor Container which matches any passed simple selector or component.

*Important.* There is not a universal upwards navigation pointer. There are several upwards relationships
such as the button which activates a menu, or the
menu item which activated a submenu, or the
column header which activated the column menu.

These differences are abstracted away by this method.

Example:

var owningTabPanel = grid.up('tabpanel');

Parametersselector : String/Ext.Component (optional)The simple selector component or actual component to test. If not passed the immediate owner/activater is returned.


### update

Update the content area of a component. ...

Update the content area of a component.
        Available since: 3.4.0
ParametershtmlOrData : String/ObjectIf this component has been configured with a template via the tpl config then
it will use this argument as data to populate the template. If this component was not configured with a template,
the components content area will be updated via Ext.Element update.


### updateAria

Injected as an override by Ext.Aria.initialize ...

Injected as an override by Ext.Aria.initialize


### updateBox

Sets the current box measurements of the component's underlying element. ...

Sets the current box measurements of the component's underlying element.
Parametersbox : ObjectAn object in the format {x, y, width, height}


### updateFrame

...


### updateLayout

Updates this component's layout. ...

Updates this component's layout. If this update affects this components ownerCt,
that component's `updateLayout` method will be called to perform the layout instead.
Otherwise, just this component (and its child items) will layout.
Parametersoptions : Object (optional)An object with layout options.
defer : Boolean`true` if this layout should be deferred.


### wrapPrimaryEl

...

Parametersdom : Object


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


### activate

Fires after a Component has been visually activated. ...

Fires after a Component has been visually activated.
Parametersthis : Ext.Component


### added

Fires after a Component had been added to a Container. ...

Fires after a Component had been added to a Container.
        Available since: 3.4.0
Parametersthis : Ext.Component


### afterrender

Fires after the component rendering is finished. ...

Fires after the component rendering is finished.

The `afterrender` event is fired after this Component has been rendered, been postprocessed by any
`afterRender` method defined for the Component.
        Available since: 3.4.0
Parametersthis : Ext.Component


### arrowclick

Fires when this button's arrow is clicked. ...

Fires when this button's arrow is clicked.
Parametersthis : Ext.button.Split


### beforeactivate

Fires before a Component has been visually activated. ...

Fires before a Component has been visually activated. Returning `false` from an event listener can prevent
the activate from occurring.
Parametersthis : Ext.Component


### beforedeactivate

Fires before a Component has been visually deactivated. ...

Fires before a Component has been visually deactivated. Returning `false` from an event listener can
prevent the deactivate from occurring.
Parametersthis : Ext.Component


### beforedestroy

Fires before the component is destroyed. ...

Fires before the component is destroyed. Return `false` from an event handler to stop the
destroy.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforehide

Fires before the component is hidden when calling the hide method. ...

Fires before the component is hidden when calling the hide method. Return `false` from an event
handler to stop the hide.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforerender

Fires before the component is rendered. ...

Fires before the component is rendered. Return `false` from an event handler to stop the
render.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforeshow

Fires before the component is shown when calling the show method. ...

Fires before the component is shown when calling the show method. Return `false` from an event
handler to stop the show.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforestaterestore

Fires before the state of the object is restored. ...

Fires before the state of the object is restored. Return false from an event handler to stop the restore.
Parametersthis : Ext.state.Stateful


### beforestatesave

Fires before the state of the object is saved to the configured state provider. ...

Fires before the state of the object is saved to the configured state provider. Return false to stop the save.
Parametersthis : Ext.state.Stateful


### blur

Fires when this Component loses focus. ...

Fires when this Component loses focus.
Parametersthis : Ext.Component


### boxready

Fires one time - after the component has been laid out for the first time at its initial size. ...

Fires *one time* - after the component has been laid out for the first time at its initial size.
Parametersthis : Ext.Component


### click

Fires when this button is clicked, before the configured handler is invoked. ...

Fires when this button is clicked, before the configured handler is invoked. Execution of the
handler may be vetoed by returning `false` to this event.
Parametersthis : Ext.button.Button


### deactivate

Fires after a Component has been visually deactivated. ...

Fires after a Component has been visually deactivated.
Parametersthis : Ext.Component


### destroy

Fires after the component is destroyed. ...

Fires after the component is destroyed.
        Available since: 1.1.0
Parametersthis : Ext.Component


### disable

Fires after the component is disabled. ...

Fires after the component is disabled.
        Available since: 1.1.0
Parametersthis : Ext.Component


### enable

Fires after the component is enabled. ...

Fires after the component is enabled.
        Available since: 1.1.0
Parametersthis : Ext.Component


### focus

Fires when this Component receives focus. ...

Fires when this Component receives focus.
Parametersthis : Ext.Component


### glyphchange

Fired when the button's glyph is changed by the setGlyph method. ...

Fired when the button's glyph is changed by the setGlyph method.
Parametersthis : Ext.button.Button


### hide

Fires after the component is hidden. ...

Fires after the component is hidden. Fires after the component is hidden when calling the hide
method.
        Available since: 1.1.0
Parametersthis : Ext.Component


### iconchange

Fired when the button's icon is changed by the setIcon or setIconCls methods. ...

Fired when the button's icon is changed by the setIcon or setIconCls methods.
Parametersthis : Ext.button.Button


### menuhide

If this button has a menu, this event fires when it is hidden ...

If this button has a menu, this event fires when it is hidden
Parametersthis : Ext.button.Button


### menushow

If this button has a menu, this event fires when it is shown ...

If this button has a menu, this event fires when it is shown
Parametersthis : Ext.button.Button


### menutriggerout

If this button has a menu, this event fires when the mouse leaves the menu triggering element ...

If this button has a menu, this event fires when the mouse leaves the menu triggering element
Parametersthis : Ext.button.Button


### menutriggerover

If this button has a menu, this event fires when the mouse enters the menu triggering element ...

If this button has a menu, this event fires when the mouse enters the menu triggering element
Parametersthis : Ext.button.Button


### mouseout

Fires when the mouse exits the button ...

Fires when the mouse exits the button
Parametersthis : Ext.button.Button


### mouseover

Fires when the mouse hovers over the button ...

Fires when the mouse hovers over the button
Parametersthis : Ext.button.Button


### move

Fires after the component is moved. ...

Fires after the component is moved.
Parametersthis : Ext.Component


### removed

Fires when a component is removed from an Ext.container.Container ...

Fires when a component is removed from an Ext.container.Container
        Available since: 3.4.0
Parametersthis : Ext.Component


### render

Fires after the component markup is rendered. ...

Fires after the component markup is rendered.
        Available since: 1.1.0
Parametersthis : Ext.Component


### resize

Fires after the component is resized. ...

Fires after the component is resized. Note that this does *not* fire when the component is first laid out at its initial
size. To hook that point in the life cycle, use the boxready event.
Parametersthis : Ext.Component


### show

Fires after the component is shown when calling the show method. ...

Fires after the component is shown when calling the show method.
        Available since: 1.1.0
Parametersthis : Ext.Component


### staterestore

Fires after the state of the object is restored. ...

Fires after the state of the object is restored.
Parametersthis : Ext.state.Stateful


### statesave

Fires after the state of the object is saved to the configured state provider. ...

Fires after the state of the object is saved to the configured state provider.
Parametersthis : Ext.state.Stateful


### textchange

Fired when the button's text is changed by the setText method. ...

Fired when the button's text is changed by the setText method.
Parametersthis : Ext.button.Button


### toggle

Fires when the 'pressed' state of this button changes (only if enableToggle = true) ...

Fires when the 'pressed' state of this button changes (only if enableToggle = true)
Parametersthis : Ext.button.Button


### $button-arrow-height

**Tipo:** number

The default height for a button's menu arrow ...

The default height for a button's menu arrow
Defaults to: `12px`


### $button-arrow-width

**Tipo:** number

The default width for a button's menu arrow ...

The default width for a button's menu arrow
Defaults to: `12px`


### $button-default-background-color

**Tipo:** color

The background-color for the default button UI ...

The background-color for the `default` button UI
Defaults to: `$button-default-base-color`


### $button-default-background-color-disabled

**Tipo:** color

The background-color for the default button UI when the button is disabled ...

The background-color for the `default` button UI when the button is disabled
Defaults to: `null`


### $button-default-background-color-focus

**Tipo:** color

The background-color for the default button UI when the button is focused ...

The background-color for the `default` button UI when the button is focused
Defaults to: `$button-default-background-color-over`


### $button-default-background-color-over

**Tipo:** color

The background-color for the default button UI when the cursor is over the button ...

The background-color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-base-color-over`


### $button-default-background-color-pressed

**Tipo:** color

The background-color for the default button UI when the button is pressed ...

The background-color for the `default` button UI when the button is pressed
Defaults to: `$button-default-base-color-pressed`


### $button-default-background-gradient

**Tipo:** string/list

The background-gradient for the default button UI. ...

The background-gradient for the `default` button UI.  Can be either the name of a
predefined gradient or a list of color stops. Used as the `$type` parameter for
Global_CSS.background-gradient.
Defaults to: `'glossy-button'`


### $button-default-background-gradient-disabled

**Tipo:** string/list

The background-gradient for the default button UI when the button is disabled. ...

The background-gradient for the `default` button UI when the button is disabled.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-disabled'`


### $button-default-background-gradient-focus

**Tipo:** string/list

The background-gradient for the default button UI when the button is focused. ...

The background-gradient for the `default` button UI when the button is focused.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `$button-default-background-gradient-over`


### $button-default-background-gradient-over

**Tipo:** string/list

The background-gradient for the default button UI when the cursor is over the button. ...

The background-gradient for the `default` button UI when the cursor is over the button.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-over'`


### $button-default-background-gradient-pressed

**Tipo:** string/list

The background-gradient for the default button UI when the button is pressed. ...

The background-gradient for the `default` button UI when the button is pressed.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-pressed'`


### $button-default-base-color

**Tipo:** color

The base color for the default button UI ...

The base color for the `default` button UI
Defaults to: `$base-color`


### $button-default-base-color-disabled

**Tipo:** color

The base color for the default button UI when the button is disabled ...

The base color for the `default` button UI when the button is disabled
Defaults to: `$base-color`


### $button-default-base-color-focus

**Tipo:** color

The base color for the default button UI when the button is focused ...

The base color for the `default` button UI when the button is focused
Defaults to: `$button-default-base-color-over`


### $button-default-base-color-over

**Tipo:** color

The base color for the default button UI when the cursor is over the button ...

The base color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-base-color`


### $button-default-base-color-pressed

**Tipo:** color

The base color for the default button UI when the button is pressed ...

The base color for the `default` button UI when the button is pressed
Defaults to: `$button-default-base-color`


### $button-default-border-color

**Tipo:** color

The border-color for the default button UI ...

The border-color for the `default` button UI
Defaults to: `$base-color`


### $button-default-border-color-disabled

**Tipo:** color

The border-color for the default button UI when the button is disabled ...

The border-color for the `default` button UI when the button is disabled
Defaults to: `$base-color`


### $button-default-border-color-focus

**Tipo:** color

The border-color for the default button UI when the button is focused ...

The border-color for the `default` button UI when the button is focused
Defaults to: `$base-color`


### $button-default-border-color-over

**Tipo:** color

The border-color for the default button UI when the cursor is over the button ...

The border-color for the `default` button UI when the cursor is over the button
Defaults to: `$base-color`


### $button-default-border-color-pressed

**Tipo:** color

The border-color for the default button UI when the button is pressed ...

The border-color for the `default` button UI when the button is pressed
Defaults to: `$base-color`


### $button-default-color

**Tipo:** color

The text color for the default button UI ...

The text color for the `default` button UI
Defaults to: `#000`


### $button-default-color-disabled

**Tipo:** color

The text color for the default button UI when the button is disabled ...

The text color for the `default` button UI when the button is disabled
Defaults to: `$button-default-color`


### $button-default-color-focus

**Tipo:** color

The text color for the default button UI when the button is focused ...

The text color for the `default` button UI when the button is focused
Defaults to: `$button-default-color-over`


### $button-default-color-over

**Tipo:** color

The text color for the default button UI when the cursor is over the button ...

The text color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-color`


### $button-default-color-pressed

**Tipo:** color

The text color for the default button UI when the button is pressed ...

The text color for the `default` button UI when the button is pressed
Defaults to: `$button-default-color`


### $button-default-glyph-color

**Tipo:** color

The color of the glyph icon for the default button UI ...

The color of the glyph icon for the `default` button UI
Defaults to: `$button-default-color`


### $button-default-glyph-opacity

**Tipo:** color

The opacity of the glyph icon for the default button UI ...

The opacity of the glyph icon for the `default` button UI
Defaults to: `.5`


### $button-icon-spacing

**Tipo:** number

The default space between a button's icon and text ...

The default space between a button's icon and text
Defaults to: `4px`


### $button-include-split-over-arrows

**Tipo:** boolean

True to include different split arrows for buttons' hover state. ...

True to include different split arrows for buttons' hover state.
Defaults to: `false`


### $button-include-ui-menu-arrows

**Tipo:** boolean

True to use a different image url for the menu button arrows for each button UI ...

True to use a different image url for the menu button arrows for each button UI
Defaults to: `false`


### $button-include-ui-split-arrows

**Tipo:** boolean

True to use a different image url for the split button arrows for each button UI ...

True to use a different image url for the split button arrows for each button UI
Defaults to: `false`


### $button-inner-opacity-disabled

**Tipo:** number

opacity to apply to the button's inner elements (icon and text) when the buton is disabled ...

opacity to apply to the button's inner elements (icon and text) when the buton is disabled
Defaults to: `1`


### $button-large-arrow-height

**Tipo:** number

The default height of a large scale button's menu arrow ...

The default height of a large scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-large-arrow-width

**Tipo:** number

The default width of a large scale button's menu arrow ...

The default width of a large scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-large-border-radius

**Tipo:** number

The default border-radius for a large scale button ...

The default border-radius for a large scale button
Defaults to: `3px`


### $button-large-border-width

**Tipo:** number

The default border-width for a large scale button ...

The default border-width for a large scale button
Defaults to: `1px`


### $button-large-font-family

**Tipo:** string

The default font-family for a large scale button ...

The default font-family for a large scale button
Defaults to: `$font-family`


### $button-large-font-family-disabled

**Tipo:** string

The default font-family for a large scale button when the button is disabled ...

The default font-family for a large scale button when the button is disabled
Defaults to: `$button-large-font-family`


### $button-large-font-family-focus

**Tipo:** string

The default font-family for a large scale button when the button is focused ...

The default font-family for a large scale button when the button is focused
Defaults to: `$button-large-font-family-over`


### $button-large-font-family-over

**Tipo:** string

The default font-family for a large scale button when the cursor is over the button ...

The default font-family for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-family`


### $button-large-font-family-pressed

**Tipo:** string

The default font-family for a large scale button when the button is pressed ...

The default font-family for a large scale button when the button is pressed
Defaults to: `$button-large-font-family`


### $button-large-font-size

**Tipo:** number

The default font-size for a large scale button ...

The default font-size for a large scale button
Defaults to: `$font-size`


### $button-large-font-size-disabled

**Tipo:** number

The default font-size for a large scale button when the button is disabled ...

The default font-size for a large scale button when the button is disabled
Defaults to: `$button-large-font-size`


### $button-large-font-size-focus

**Tipo:** number

The default font-size for a large scale button when the button is focused ...

The default font-size for a large scale button when the button is focused
Defaults to: `$button-large-font-size-over`


### $button-large-font-size-over

**Tipo:** number

The default font-size for a large scale button when the cursor is over the button ...

The default font-size for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-size`


### $button-large-font-size-pressed

**Tipo:** number

The default font-size for a large scale button when the button is pressed ...

The default font-size for a large scale button when the button is pressed
Defaults to: `$button-large-font-size`


### $button-large-font-weight

**Tipo:** string

The default font-weight for a large scale button ...

The default font-weight for a large scale button
Defaults to: `normal`


### $button-large-font-weight-disabled

**Tipo:** string

The default font-weight for a large scale button when the button is disabled ...

The default font-weight for a large scale button when the button is disabled
Defaults to: `$button-large-font-weight`


### $button-large-font-weight-focus

**Tipo:** string

The default font-weight for a large scale button when the button is focused ...

The default font-weight for a large scale button when the button is focused
Defaults to: `$button-large-font-weight-over`


### $button-large-font-weight-over

**Tipo:** string

The default font-weight for a large scale button when the cursor is over the button ...

The default font-weight for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-weight`


### $button-large-font-weight-pressed

**Tipo:** string

The default font-weight for a large scale button when the button is pressed ...

The default font-weight for a large scale button when the button is pressed
Defaults to: `$button-large-font-weight`


### $button-large-icon-size

**Tipo:** number

The default icon size for a large scale button ...

The default icon size for a large scale button
Defaults to: `32px`


### $button-large-padding

**Tipo:** number

The default padding for a large scale button ...

The default padding for a large scale button
Defaults to: `3px`


### $button-large-split-height

**Tipo:** number

The default height of a large scale Split Button's arrow ...

The default height of a large scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-large-split-width

**Tipo:** number

The default width of a large scale Split Button's arrow ...

The default width of a large scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-large-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a large scale button ...

The default horizontal padding to add to the left and right of the text element for
a large scale button
Defaults to: `3px`


### $button-medium-arrow-height

**Tipo:** number

The default height of a medium scale button's menu arrow ...

The default height of a medium scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-medium-arrow-width

**Tipo:** number

The default width of a medium scale button's menu arrow ...

The default width of a medium scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-medium-border-radius

**Tipo:** number

The default border-radius for a medium scale button ...

The default border-radius for a medium scale button
Defaults to: `3px`


### $button-medium-border-width

**Tipo:** number

The default border-width for a medium scale button ...

The default border-width for a medium scale button
Defaults to: `1px`


### $button-medium-font-family

**Tipo:** string

The default font-family for a medium scale button ...

The default font-family for a medium scale button
Defaults to: `$font-family`


### $button-medium-font-family-disabled

**Tipo:** string

The default font-family for a medium scale button when the button is disabled ...

The default font-family for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-family`


### $button-medium-font-family-focus

**Tipo:** string

The default font-family for a medium scale button when the button is focused ...

The default font-family for a medium scale button when the button is focused
Defaults to: `$button-medium-font-family-over`


### $button-medium-font-family-over

**Tipo:** string

The default font-family for a medium scale button when the cursor is over the button ...

The default font-family for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-family`


### $button-medium-font-family-pressed

**Tipo:** string

The default font-family for a medium scale button when the button is pressed ...

The default font-family for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-family`


### $button-medium-font-size

**Tipo:** number

The default font-size for a medium scale button ...

The default font-size for a medium scale button
Defaults to: `$font-size`


### $button-medium-font-size-disabled

**Tipo:** number

The default font-size for a medium scale button when the button is disabled ...

The default font-size for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-size`


### $button-medium-font-size-focus

**Tipo:** number

The default font-size for a medium scale button when the button is focused ...

The default font-size for a medium scale button when the button is focused
Defaults to: `$button-medium-font-size-over`


### $button-medium-font-size-over

**Tipo:** number

The default font-size for a medium scale button when the cursor is over the button ...

The default font-size for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-size`


### $button-medium-font-size-pressed

**Tipo:** number

The default font-size for a medium scale button when the button is pressed ...

The default font-size for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-size`


### $button-medium-font-weight

**Tipo:** string

The default font-weight for a medium scale button ...

The default font-weight for a medium scale button
Defaults to: `normal`


### $button-medium-font-weight-disabled

**Tipo:** string

The default font-weight for a medium scale button when the button is disabled ...

The default font-weight for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-weight`


### $button-medium-font-weight-focus

**Tipo:** string

The default font-weight for a medium scale button when the button is focused ...

The default font-weight for a medium scale button when the button is focused
Defaults to: `$button-medium-font-weight-over`


### $button-medium-font-weight-over

**Tipo:** string

The default font-weight for a medium scale button when the cursor is over the button ...

The default font-weight for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-weight`


### $button-medium-font-weight-pressed

**Tipo:** string

The default font-weight for a medium scale button when the button is pressed ...

The default font-weight for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-weight`


### $button-medium-icon-size

**Tipo:** number

The default icon size for a medium scale button ...

The default icon size for a medium scale button
Defaults to: `24px`


### $button-medium-padding

**Tipo:** number

The default padding for a medium scale button ...

The default padding for a medium scale button
Defaults to: `3px`


### $button-medium-split-height

**Tipo:** number

The default height of a medium scale Split Button's arrow ...

The default height of a medium scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-medium-split-width

**Tipo:** number

The default width of a medium scale Split Button's arrow ...

The default width of a medium scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-medium-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a medium scale button ...

The default horizontal padding to add to the left and right of the text element for
a medium scale button
Defaults to: `3px`


### $button-opacity-disabled

**Tipo:** number

opacity to apply to the button's main element when the buton is disabled ...

opacity to apply to the button's main element when the buton is disabled
Defaults to: `.5`


### $button-small-arrow-height

**Tipo:** number

The default height of a small scale button's menu arrow ...

The default height of a small scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-small-arrow-width

**Tipo:** number

The default width of a small scale button's menu arrow ...

The default width of a small scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-small-border-radius

**Tipo:** number

The default border-radius for a small scale button ...

The default border-radius for a small scale button
Defaults to: `3px`


### $button-small-border-width

**Tipo:** number

The default border-width for a small scale button ...

The default border-width for a small scale button
Defaults to: `1px`


### $button-small-font-family

**Tipo:** string

The default font-family for a small scale button ...

The default font-family for a small scale button
Defaults to: `$font-family`


### $button-small-font-family-disabled

**Tipo:** string

The default font-family for a small scale button when the button is disabled ...

The default font-family for a small scale button when the button is disabled
Defaults to: `$button-small-font-family`


### $button-small-font-family-focus

**Tipo:** string

The default font-family for a small scale button when the button is focused ...

The default font-family for a small scale button when the button is focused
Defaults to: `$button-small-font-family-over`


### $button-small-font-family-over

**Tipo:** string

The default font-family for a small scale button when the cursor is over the button ...

The default font-family for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-family`


### $button-small-font-family-pressed

**Tipo:** string

The default font-family for a small scale button when the button is pressed ...

The default font-family for a small scale button when the button is pressed
Defaults to: `$button-small-font-family`


### $button-small-font-size

**Tipo:** number

The default font-size for a small scale button ...

The default font-size for a small scale button
Defaults to: `ceil ( $font-size * .9 )`


### $button-small-font-size-disabled

**Tipo:** number

The default font-size for a small scale button when the button is disabled ...

The default font-size for a small scale button when the button is disabled
Defaults to: `$button-small-font-size`


### $button-small-font-size-focus

**Tipo:** number

The default font-size for a small scale button when the button is focused ...

The default font-size for a small scale button when the button is focused
Defaults to: `$button-small-font-size-over`


### $button-small-font-size-over

**Tipo:** number

The default font-size for a small scale button when the cursor is over the button ...

The default font-size for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-size`


### $button-small-font-size-pressed

**Tipo:** number

The default font-size for a small scale button when the button is pressed ...

The default font-size for a small scale button when the button is pressed
Defaults to: `$button-small-font-size`


### $button-small-font-weight

**Tipo:** string

The default font-weight for a small scale button ...

The default font-weight for a small scale button
Defaults to: `normal`


### $button-small-font-weight-disabled

**Tipo:** string

The default font-weight for a small scale button when the button is disabled ...

The default font-weight for a small scale button when the button is disabled
Defaults to: `$button-small-font-weight`


### $button-small-font-weight-focus

**Tipo:** string

The default font-weight for a small scale button when the button is focused ...

The default font-weight for a small scale button when the button is focused
Defaults to: `$button-small-font-weight-over`


### $button-small-font-weight-over

**Tipo:** string

The default font-weight for a small scale button when the cursor is over the button ...

The default font-weight for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-weight`


### $button-small-font-weight-pressed

**Tipo:** string

The default font-weight for a small scale button when the button is pressed ...

The default font-weight for a small scale button when the button is pressed
Defaults to: `$button-small-font-weight`


### $button-small-icon-size

**Tipo:** number

The default icon size for a small scale button ...

The default icon size for a small scale button
Defaults to: `16px`


### $button-small-padding

**Tipo:** number

The default padding for a small scale button ...

The default padding for a small scale button
Defaults to: `2px`


### $button-small-split-height

**Tipo:** number

The default height of a small scale Split Button's arrow ...

The default height of a small scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-small-split-width

**Tipo:** number

The default width of a small scale Split Button's arrow ...

The default width of a small scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-small-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a small scale button ...

The default horizontal padding to add to the left and right of the text element for
a small scale button
Defaults to: `4px`


### $button-split-height

**Tipo:** number

The default height for a Split Button's arrow ...

The default height for a Split Button's arrow
Defaults to: `14px`


### $button-split-width

**Tipo:** number

The default width for a Split Button's arrow ...

The default width for a Split Button's arrow
Defaults to: `14px`


### $button-toolbar-background-color

**Tipo:** color

The background-color for the default-toolbar button UI ...

The background-color for the `default-toolbar` button UI
Defaults to: `$base-color`


### $button-toolbar-background-color-disabled

**Tipo:** color

The background-color for the default-toolbar button UI when the button is disabled ...

The background-color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-color-focus

**Tipo:** color

The background-color for the default-toolbar button UI when the button is focused ...

The background-color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-background-color-over`


### $button-toolbar-background-color-over

**Tipo:** color

The background-color for the default-toolbar button UI when the cursor is over the button ...

The background-color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-color-pressed

**Tipo:** color

The background-color for the default-toolbar button UI when the button is pressed ...

The background-color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-gradient

**Tipo:** string/list

The background-gradient for the default-toolbar button UI. ...

The background-gradient for the `default-toolbar` button UI.  Can be either the name of
a predefined gradient or a list of color stops. Used as the `$type` parameter for
Global_CSS.background-gradient.
Defaults to: `'glossy-button'`


### $button-toolbar-background-gradient-disabled

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is disabled. ...

The background-gradient for the `default-toolbar` button UI when the button is disabled.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-disabled'`


### $button-toolbar-background-gradient-focus

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is focused. ...

The background-gradient for the `default-toolbar` button UI when the button is focused.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `$button-toolbar-background-gradient-over`


### $button-toolbar-background-gradient-over

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the cursor is over the
button. ...

The background-gradient for the `default-toolbar` button UI when the cursor is over the
button. Can be either the name of a predefined gradient or a list of color stops. Used
as the `$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-over'`


### $button-toolbar-background-gradient-pressed

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is pressed. ...

The background-gradient for the `default-toolbar` button UI when the button is pressed.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-pressed'`


### $button-toolbar-border-color

**Tipo:** color

The border-color for the default-toolbar button UI ...

The border-color for the `default-toolbar` button UI
Defaults to: `$base-color`


### $button-toolbar-border-color-disabled

**Tipo:** color

The border-color for the default-toolbar button UI when the button is disabled ...

The border-color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-border-color-focus

**Tipo:** color

The border-color for the default-toolbar button UI when the button is focused ...

The border-color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-border-color-over`


### $button-toolbar-border-color-over

**Tipo:** color

The border-color for the default-toolbar button UI when the cursor is over the button ...

The border-color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-border-color-pressed

**Tipo:** color

The border-color for the default-toolbar button UI when the button is pressed ...

The border-color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-color

**Tipo:** color

The text color for the default-toolbar button UI ...

The text color for the `default-toolbar` button UI
Defaults to: `#000`


### $button-toolbar-color-disabled

**Tipo:** color

The text color for the default-toolbar button UI when the button is disabled ...

The text color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-color`


### $button-toolbar-color-focus

**Tipo:** color

The text color for the default-toolbar button UI when the button is focused ...

The text color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-color-over`


### $button-toolbar-color-over

**Tipo:** color

The text color for the default-toolbar button UI when the cursor is over the button ...

The text color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-color`


### $button-toolbar-color-pressed

**Tipo:** color

The text color for the default-toolbar button UI when the button is pressed ...

The text color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-color`


### $button-toolbar-glyph-color

**Tipo:** color

The color of the glyph icon for the default-toolbar button UI ...

The color of the glyph icon for the `default-toolbar` button UI
Defaults to: `$button-toolbar-color`


### $button-toolbar-glyph-opacity

**Tipo:** color

The opacity of the glyph icon for the default-toolbar button UI ...

The opacity of the glyph icon for the `default-toolbar` button UI
Defaults to: `.5`


### $button-toolbar-include-split-noline-arrows

**Tipo:** boolean

True to include "noline" split arrows for toolbar buttons in their default state. ...

True to include "noline" split arrows for toolbar buttons in their default state.
Defaults to: `false`


### $button-toolbar-inner-opacity-disabled

**Tipo:** number

opacity to apply to the toolbar button's inner elements (icon and text) when the buton is disabled ...

opacity to apply to the toolbar button's inner elements (icon and text) when the buton is disabled
Defaults to: `1`


### $button-toolbar-opacity-disabled

**Tipo:** number

opacity to apply to the toolbar button's main element when the buton is disabled ...

opacity to apply to the toolbar button's main element when the buton is disabled
Defaults to: `.5`


### $include-button-default-large-ui

**Tipo:** boolean

True to include the "default" button UI for "large" scale buttons ...

True to include the "default" button UI for "large" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-medium-ui

**Tipo:** boolean

True to include the "default" button UI for "medium" scale buttons ...

True to include the "default" button UI for "medium" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-small-ui

**Tipo:** boolean

True to include the "default" button UI for "small" scale buttons ...

True to include the "default" button UI for "small" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-toolbar-large-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "large" scale buttons ...

True to include the "default-toolbar" button UI for "large" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-medium-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "medium" scale buttons ...

True to include the "default-toolbar" button UI for "medium" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-small-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "small" scale buttons ...

True to include the "default-toolbar" button UI for "small" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI ...

True to include the "default-toolbar" button UI
Defaults to: `$include-default-uis`


### $include-button-default-ui

**Tipo:** boolean

True to include the "default" button UI ...

True to include the "default" button UI
Defaults to: `$include-default-uis`


### extjs-button-ui

Creates a visual theme for a Button ...

Creates a visual theme for a Button
$ui : stringThe name of the UI being created. Can not included spaces or special punctuation
(used in CSS class names).


## Events

### activate

Fires after a Component has been visually activated. ...

Fires after a Component has been visually activated.
Parametersthis : Ext.Component


### added

Fires after a Component had been added to a Container. ...

Fires after a Component had been added to a Container.
        Available since: 3.4.0
Parametersthis : Ext.Component


### afterrender

Fires after the component rendering is finished. ...

Fires after the component rendering is finished.

The `afterrender` event is fired after this Component has been rendered, been postprocessed by any
`afterRender` method defined for the Component.
        Available since: 3.4.0
Parametersthis : Ext.Component


### arrowclick

Fires when this button's arrow is clicked. ...

Fires when this button's arrow is clicked.
Parametersthis : Ext.button.Split


### beforeactivate

Fires before a Component has been visually activated. ...

Fires before a Component has been visually activated. Returning `false` from an event listener can prevent
the activate from occurring.
Parametersthis : Ext.Component


### beforedeactivate

Fires before a Component has been visually deactivated. ...

Fires before a Component has been visually deactivated. Returning `false` from an event listener can
prevent the deactivate from occurring.
Parametersthis : Ext.Component


### beforedestroy

Fires before the component is destroyed. ...

Fires before the component is destroyed. Return `false` from an event handler to stop the
destroy.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforehide

Fires before the component is hidden when calling the hide method. ...

Fires before the component is hidden when calling the hide method. Return `false` from an event
handler to stop the hide.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforerender

Fires before the component is rendered. ...

Fires before the component is rendered. Return `false` from an event handler to stop the
render.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforeshow

Fires before the component is shown when calling the show method. ...

Fires before the component is shown when calling the show method. Return `false` from an event
handler to stop the show.
        Available since: 1.1.0
Parametersthis : Ext.Component


### beforestaterestore

Fires before the state of the object is restored. ...

Fires before the state of the object is restored. Return false from an event handler to stop the restore.
Parametersthis : Ext.state.Stateful


### beforestatesave

Fires before the state of the object is saved to the configured state provider. ...

Fires before the state of the object is saved to the configured state provider. Return false to stop the save.
Parametersthis : Ext.state.Stateful


### blur

Fires when this Component loses focus. ...

Fires when this Component loses focus.
Parametersthis : Ext.Component


### boxready

Fires one time - after the component has been laid out for the first time at its initial size. ...

Fires *one time* - after the component has been laid out for the first time at its initial size.
Parametersthis : Ext.Component


### click

Fires when this button is clicked, before the configured handler is invoked. ...

Fires when this button is clicked, before the configured handler is invoked. Execution of the
handler may be vetoed by returning `false` to this event.
Parametersthis : Ext.button.Button


### deactivate

Fires after a Component has been visually deactivated. ...

Fires after a Component has been visually deactivated.
Parametersthis : Ext.Component


### destroy

Fires after the component is destroyed. ...

Fires after the component is destroyed.
        Available since: 1.1.0
Parametersthis : Ext.Component


### disable

Fires after the component is disabled. ...

Fires after the component is disabled.
        Available since: 1.1.0
Parametersthis : Ext.Component


### enable

Fires after the component is enabled. ...

Fires after the component is enabled.
        Available since: 1.1.0
Parametersthis : Ext.Component


### focus

Fires when this Component receives focus. ...

Fires when this Component receives focus.
Parametersthis : Ext.Component


### glyphchange

Fired when the button's glyph is changed by the setGlyph method. ...

Fired when the button's glyph is changed by the setGlyph method.
Parametersthis : Ext.button.Button


### hide

Fires after the component is hidden. ...

Fires after the component is hidden. Fires after the component is hidden when calling the hide
method.
        Available since: 1.1.0
Parametersthis : Ext.Component


### iconchange

Fired when the button's icon is changed by the setIcon or setIconCls methods. ...

Fired when the button's icon is changed by the setIcon or setIconCls methods.
Parametersthis : Ext.button.Button


### menuhide

If this button has a menu, this event fires when it is hidden ...

If this button has a menu, this event fires when it is hidden
Parametersthis : Ext.button.Button


### menushow

If this button has a menu, this event fires when it is shown ...

If this button has a menu, this event fires when it is shown
Parametersthis : Ext.button.Button


### menutriggerout

If this button has a menu, this event fires when the mouse leaves the menu triggering element ...

If this button has a menu, this event fires when the mouse leaves the menu triggering element
Parametersthis : Ext.button.Button


### menutriggerover

If this button has a menu, this event fires when the mouse enters the menu triggering element ...

If this button has a menu, this event fires when the mouse enters the menu triggering element
Parametersthis : Ext.button.Button


### mouseout

Fires when the mouse exits the button ...

Fires when the mouse exits the button
Parametersthis : Ext.button.Button


### mouseover

Fires when the mouse hovers over the button ...

Fires when the mouse hovers over the button
Parametersthis : Ext.button.Button


### move

Fires after the component is moved. ...

Fires after the component is moved.
Parametersthis : Ext.Component


### removed

Fires when a component is removed from an Ext.container.Container ...

Fires when a component is removed from an Ext.container.Container
        Available since: 3.4.0
Parametersthis : Ext.Component


### render

Fires after the component markup is rendered. ...

Fires after the component markup is rendered.
        Available since: 1.1.0
Parametersthis : Ext.Component


### resize

Fires after the component is resized. ...

Fires after the component is resized. Note that this does *not* fire when the component is first laid out at its initial
size. To hook that point in the life cycle, use the boxready event.
Parametersthis : Ext.Component


### show

Fires after the component is shown when calling the show method. ...

Fires after the component is shown when calling the show method.
        Available since: 1.1.0
Parametersthis : Ext.Component


### staterestore

Fires after the state of the object is restored. ...

Fires after the state of the object is restored.
Parametersthis : Ext.state.Stateful


### statesave

Fires after the state of the object is saved to the configured state provider. ...

Fires after the state of the object is saved to the configured state provider.
Parametersthis : Ext.state.Stateful


### textchange

Fired when the button's text is changed by the setText method. ...

Fired when the button's text is changed by the setText method.
Parametersthis : Ext.button.Button


### toggle

Fires when the 'pressed' state of this button changes (only if enableToggle = true) ...

Fires when the 'pressed' state of this button changes (only if enableToggle = true)
Parametersthis : Ext.button.Button


### $button-arrow-height

**Tipo:** number

The default height for a button's menu arrow ...

The default height for a button's menu arrow
Defaults to: `12px`


### $button-arrow-width

**Tipo:** number

The default width for a button's menu arrow ...

The default width for a button's menu arrow
Defaults to: `12px`


### $button-default-background-color

**Tipo:** color

The background-color for the default button UI ...

The background-color for the `default` button UI
Defaults to: `$button-default-base-color`


### $button-default-background-color-disabled

**Tipo:** color

The background-color for the default button UI when the button is disabled ...

The background-color for the `default` button UI when the button is disabled
Defaults to: `null`


### $button-default-background-color-focus

**Tipo:** color

The background-color for the default button UI when the button is focused ...

The background-color for the `default` button UI when the button is focused
Defaults to: `$button-default-background-color-over`


### $button-default-background-color-over

**Tipo:** color

The background-color for the default button UI when the cursor is over the button ...

The background-color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-base-color-over`


### $button-default-background-color-pressed

**Tipo:** color

The background-color for the default button UI when the button is pressed ...

The background-color for the `default` button UI when the button is pressed
Defaults to: `$button-default-base-color-pressed`


### $button-default-background-gradient

**Tipo:** string/list

The background-gradient for the default button UI. ...

The background-gradient for the `default` button UI.  Can be either the name of a
predefined gradient or a list of color stops. Used as the `$type` parameter for
Global_CSS.background-gradient.
Defaults to: `'glossy-button'`


### $button-default-background-gradient-disabled

**Tipo:** string/list

The background-gradient for the default button UI when the button is disabled. ...

The background-gradient for the `default` button UI when the button is disabled.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-disabled'`


### $button-default-background-gradient-focus

**Tipo:** string/list

The background-gradient for the default button UI when the button is focused. ...

The background-gradient for the `default` button UI when the button is focused.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `$button-default-background-gradient-over`


### $button-default-background-gradient-over

**Tipo:** string/list

The background-gradient for the default button UI when the cursor is over the button. ...

The background-gradient for the `default` button UI when the cursor is over the button.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-over'`


### $button-default-background-gradient-pressed

**Tipo:** string/list

The background-gradient for the default button UI when the button is pressed. ...

The background-gradient for the `default` button UI when the button is pressed.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-pressed'`


### $button-default-base-color

**Tipo:** color

The base color for the default button UI ...

The base color for the `default` button UI
Defaults to: `$base-color`


### $button-default-base-color-disabled

**Tipo:** color

The base color for the default button UI when the button is disabled ...

The base color for the `default` button UI when the button is disabled
Defaults to: `$base-color`


### $button-default-base-color-focus

**Tipo:** color

The base color for the default button UI when the button is focused ...

The base color for the `default` button UI when the button is focused
Defaults to: `$button-default-base-color-over`


### $button-default-base-color-over

**Tipo:** color

The base color for the default button UI when the cursor is over the button ...

The base color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-base-color`


### $button-default-base-color-pressed

**Tipo:** color

The base color for the default button UI when the button is pressed ...

The base color for the `default` button UI when the button is pressed
Defaults to: `$button-default-base-color`


### $button-default-border-color

**Tipo:** color

The border-color for the default button UI ...

The border-color for the `default` button UI
Defaults to: `$base-color`


### $button-default-border-color-disabled

**Tipo:** color

The border-color for the default button UI when the button is disabled ...

The border-color for the `default` button UI when the button is disabled
Defaults to: `$base-color`


### $button-default-border-color-focus

**Tipo:** color

The border-color for the default button UI when the button is focused ...

The border-color for the `default` button UI when the button is focused
Defaults to: `$base-color`


### $button-default-border-color-over

**Tipo:** color

The border-color for the default button UI when the cursor is over the button ...

The border-color for the `default` button UI when the cursor is over the button
Defaults to: `$base-color`


### $button-default-border-color-pressed

**Tipo:** color

The border-color for the default button UI when the button is pressed ...

The border-color for the `default` button UI when the button is pressed
Defaults to: `$base-color`


### $button-default-color

**Tipo:** color

The text color for the default button UI ...

The text color for the `default` button UI
Defaults to: `#000`


### $button-default-color-disabled

**Tipo:** color

The text color for the default button UI when the button is disabled ...

The text color for the `default` button UI when the button is disabled
Defaults to: `$button-default-color`


### $button-default-color-focus

**Tipo:** color

The text color for the default button UI when the button is focused ...

The text color for the `default` button UI when the button is focused
Defaults to: `$button-default-color-over`


### $button-default-color-over

**Tipo:** color

The text color for the default button UI when the cursor is over the button ...

The text color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-color`


### $button-default-color-pressed

**Tipo:** color

The text color for the default button UI when the button is pressed ...

The text color for the `default` button UI when the button is pressed
Defaults to: `$button-default-color`


### $button-default-glyph-color

**Tipo:** color

The color of the glyph icon for the default button UI ...

The color of the glyph icon for the `default` button UI
Defaults to: `$button-default-color`


### $button-default-glyph-opacity

**Tipo:** color

The opacity of the glyph icon for the default button UI ...

The opacity of the glyph icon for the `default` button UI
Defaults to: `.5`


### $button-icon-spacing

**Tipo:** number

The default space between a button's icon and text ...

The default space between a button's icon and text
Defaults to: `4px`


### $button-include-split-over-arrows

**Tipo:** boolean

True to include different split arrows for buttons' hover state. ...

True to include different split arrows for buttons' hover state.
Defaults to: `false`


### $button-include-ui-menu-arrows

**Tipo:** boolean

True to use a different image url for the menu button arrows for each button UI ...

True to use a different image url for the menu button arrows for each button UI
Defaults to: `false`


### $button-include-ui-split-arrows

**Tipo:** boolean

True to use a different image url for the split button arrows for each button UI ...

True to use a different image url for the split button arrows for each button UI
Defaults to: `false`


### $button-inner-opacity-disabled

**Tipo:** number

opacity to apply to the button's inner elements (icon and text) when the buton is disabled ...

opacity to apply to the button's inner elements (icon and text) when the buton is disabled
Defaults to: `1`


### $button-large-arrow-height

**Tipo:** number

The default height of a large scale button's menu arrow ...

The default height of a large scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-large-arrow-width

**Tipo:** number

The default width of a large scale button's menu arrow ...

The default width of a large scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-large-border-radius

**Tipo:** number

The default border-radius for a large scale button ...

The default border-radius for a large scale button
Defaults to: `3px`


### $button-large-border-width

**Tipo:** number

The default border-width for a large scale button ...

The default border-width for a large scale button
Defaults to: `1px`


### $button-large-font-family

**Tipo:** string

The default font-family for a large scale button ...

The default font-family for a large scale button
Defaults to: `$font-family`


### $button-large-font-family-disabled

**Tipo:** string

The default font-family for a large scale button when the button is disabled ...

The default font-family for a large scale button when the button is disabled
Defaults to: `$button-large-font-family`


### $button-large-font-family-focus

**Tipo:** string

The default font-family for a large scale button when the button is focused ...

The default font-family for a large scale button when the button is focused
Defaults to: `$button-large-font-family-over`


### $button-large-font-family-over

**Tipo:** string

The default font-family for a large scale button when the cursor is over the button ...

The default font-family for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-family`


### $button-large-font-family-pressed

**Tipo:** string

The default font-family for a large scale button when the button is pressed ...

The default font-family for a large scale button when the button is pressed
Defaults to: `$button-large-font-family`


### $button-large-font-size

**Tipo:** number

The default font-size for a large scale button ...

The default font-size for a large scale button
Defaults to: `$font-size`


### $button-large-font-size-disabled

**Tipo:** number

The default font-size for a large scale button when the button is disabled ...

The default font-size for a large scale button when the button is disabled
Defaults to: `$button-large-font-size`


### $button-large-font-size-focus

**Tipo:** number

The default font-size for a large scale button when the button is focused ...

The default font-size for a large scale button when the button is focused
Defaults to: `$button-large-font-size-over`


### $button-large-font-size-over

**Tipo:** number

The default font-size for a large scale button when the cursor is over the button ...

The default font-size for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-size`


### $button-large-font-size-pressed

**Tipo:** number

The default font-size for a large scale button when the button is pressed ...

The default font-size for a large scale button when the button is pressed
Defaults to: `$button-large-font-size`


### $button-large-font-weight

**Tipo:** string

The default font-weight for a large scale button ...

The default font-weight for a large scale button
Defaults to: `normal`


### $button-large-font-weight-disabled

**Tipo:** string

The default font-weight for a large scale button when the button is disabled ...

The default font-weight for a large scale button when the button is disabled
Defaults to: `$button-large-font-weight`


### $button-large-font-weight-focus

**Tipo:** string

The default font-weight for a large scale button when the button is focused ...

The default font-weight for a large scale button when the button is focused
Defaults to: `$button-large-font-weight-over`


### $button-large-font-weight-over

**Tipo:** string

The default font-weight for a large scale button when the cursor is over the button ...

The default font-weight for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-weight`


### $button-large-font-weight-pressed

**Tipo:** string

The default font-weight for a large scale button when the button is pressed ...

The default font-weight for a large scale button when the button is pressed
Defaults to: `$button-large-font-weight`


### $button-large-icon-size

**Tipo:** number

The default icon size for a large scale button ...

The default icon size for a large scale button
Defaults to: `32px`


### $button-large-padding

**Tipo:** number

The default padding for a large scale button ...

The default padding for a large scale button
Defaults to: `3px`


### $button-large-split-height

**Tipo:** number

The default height of a large scale Split Button's arrow ...

The default height of a large scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-large-split-width

**Tipo:** number

The default width of a large scale Split Button's arrow ...

The default width of a large scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-large-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a large scale button ...

The default horizontal padding to add to the left and right of the text element for
a large scale button
Defaults to: `3px`


### $button-medium-arrow-height

**Tipo:** number

The default height of a medium scale button's menu arrow ...

The default height of a medium scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-medium-arrow-width

**Tipo:** number

The default width of a medium scale button's menu arrow ...

The default width of a medium scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-medium-border-radius

**Tipo:** number

The default border-radius for a medium scale button ...

The default border-radius for a medium scale button
Defaults to: `3px`


### $button-medium-border-width

**Tipo:** number

The default border-width for a medium scale button ...

The default border-width for a medium scale button
Defaults to: `1px`


### $button-medium-font-family

**Tipo:** string

The default font-family for a medium scale button ...

The default font-family for a medium scale button
Defaults to: `$font-family`


### $button-medium-font-family-disabled

**Tipo:** string

The default font-family for a medium scale button when the button is disabled ...

The default font-family for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-family`


### $button-medium-font-family-focus

**Tipo:** string

The default font-family for a medium scale button when the button is focused ...

The default font-family for a medium scale button when the button is focused
Defaults to: `$button-medium-font-family-over`


### $button-medium-font-family-over

**Tipo:** string

The default font-family for a medium scale button when the cursor is over the button ...

The default font-family for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-family`


### $button-medium-font-family-pressed

**Tipo:** string

The default font-family for a medium scale button when the button is pressed ...

The default font-family for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-family`


### $button-medium-font-size

**Tipo:** number

The default font-size for a medium scale button ...

The default font-size for a medium scale button
Defaults to: `$font-size`


### $button-medium-font-size-disabled

**Tipo:** number

The default font-size for a medium scale button when the button is disabled ...

The default font-size for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-size`


### $button-medium-font-size-focus

**Tipo:** number

The default font-size for a medium scale button when the button is focused ...

The default font-size for a medium scale button when the button is focused
Defaults to: `$button-medium-font-size-over`


### $button-medium-font-size-over

**Tipo:** number

The default font-size for a medium scale button when the cursor is over the button ...

The default font-size for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-size`


### $button-medium-font-size-pressed

**Tipo:** number

The default font-size for a medium scale button when the button is pressed ...

The default font-size for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-size`


### $button-medium-font-weight

**Tipo:** string

The default font-weight for a medium scale button ...

The default font-weight for a medium scale button
Defaults to: `normal`


### $button-medium-font-weight-disabled

**Tipo:** string

The default font-weight for a medium scale button when the button is disabled ...

The default font-weight for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-weight`


### $button-medium-font-weight-focus

**Tipo:** string

The default font-weight for a medium scale button when the button is focused ...

The default font-weight for a medium scale button when the button is focused
Defaults to: `$button-medium-font-weight-over`


### $button-medium-font-weight-over

**Tipo:** string

The default font-weight for a medium scale button when the cursor is over the button ...

The default font-weight for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-weight`


### $button-medium-font-weight-pressed

**Tipo:** string

The default font-weight for a medium scale button when the button is pressed ...

The default font-weight for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-weight`


### $button-medium-icon-size

**Tipo:** number

The default icon size for a medium scale button ...

The default icon size for a medium scale button
Defaults to: `24px`


### $button-medium-padding

**Tipo:** number

The default padding for a medium scale button ...

The default padding for a medium scale button
Defaults to: `3px`


### $button-medium-split-height

**Tipo:** number

The default height of a medium scale Split Button's arrow ...

The default height of a medium scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-medium-split-width

**Tipo:** number

The default width of a medium scale Split Button's arrow ...

The default width of a medium scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-medium-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a medium scale button ...

The default horizontal padding to add to the left and right of the text element for
a medium scale button
Defaults to: `3px`


### $button-opacity-disabled

**Tipo:** number

opacity to apply to the button's main element when the buton is disabled ...

opacity to apply to the button's main element when the buton is disabled
Defaults to: `.5`


### $button-small-arrow-height

**Tipo:** number

The default height of a small scale button's menu arrow ...

The default height of a small scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-small-arrow-width

**Tipo:** number

The default width of a small scale button's menu arrow ...

The default width of a small scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-small-border-radius

**Tipo:** number

The default border-radius for a small scale button ...

The default border-radius for a small scale button
Defaults to: `3px`


### $button-small-border-width

**Tipo:** number

The default border-width for a small scale button ...

The default border-width for a small scale button
Defaults to: `1px`


### $button-small-font-family

**Tipo:** string

The default font-family for a small scale button ...

The default font-family for a small scale button
Defaults to: `$font-family`


### $button-small-font-family-disabled

**Tipo:** string

The default font-family for a small scale button when the button is disabled ...

The default font-family for a small scale button when the button is disabled
Defaults to: `$button-small-font-family`


### $button-small-font-family-focus

**Tipo:** string

The default font-family for a small scale button when the button is focused ...

The default font-family for a small scale button when the button is focused
Defaults to: `$button-small-font-family-over`


### $button-small-font-family-over

**Tipo:** string

The default font-family for a small scale button when the cursor is over the button ...

The default font-family for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-family`


### $button-small-font-family-pressed

**Tipo:** string

The default font-family for a small scale button when the button is pressed ...

The default font-family for a small scale button when the button is pressed
Defaults to: `$button-small-font-family`


### $button-small-font-size

**Tipo:** number

The default font-size for a small scale button ...

The default font-size for a small scale button
Defaults to: `ceil ( $font-size * .9 )`


### $button-small-font-size-disabled

**Tipo:** number

The default font-size for a small scale button when the button is disabled ...

The default font-size for a small scale button when the button is disabled
Defaults to: `$button-small-font-size`


### $button-small-font-size-focus

**Tipo:** number

The default font-size for a small scale button when the button is focused ...

The default font-size for a small scale button when the button is focused
Defaults to: `$button-small-font-size-over`


### $button-small-font-size-over

**Tipo:** number

The default font-size for a small scale button when the cursor is over the button ...

The default font-size for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-size`


### $button-small-font-size-pressed

**Tipo:** number

The default font-size for a small scale button when the button is pressed ...

The default font-size for a small scale button when the button is pressed
Defaults to: `$button-small-font-size`


### $button-small-font-weight

**Tipo:** string

The default font-weight for a small scale button ...

The default font-weight for a small scale button
Defaults to: `normal`


### $button-small-font-weight-disabled

**Tipo:** string

The default font-weight for a small scale button when the button is disabled ...

The default font-weight for a small scale button when the button is disabled
Defaults to: `$button-small-font-weight`


### $button-small-font-weight-focus

**Tipo:** string

The default font-weight for a small scale button when the button is focused ...

The default font-weight for a small scale button when the button is focused
Defaults to: `$button-small-font-weight-over`


### $button-small-font-weight-over

**Tipo:** string

The default font-weight for a small scale button when the cursor is over the button ...

The default font-weight for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-weight`


### $button-small-font-weight-pressed

**Tipo:** string

The default font-weight for a small scale button when the button is pressed ...

The default font-weight for a small scale button when the button is pressed
Defaults to: `$button-small-font-weight`


### $button-small-icon-size

**Tipo:** number

The default icon size for a small scale button ...

The default icon size for a small scale button
Defaults to: `16px`


### $button-small-padding

**Tipo:** number

The default padding for a small scale button ...

The default padding for a small scale button
Defaults to: `2px`


### $button-small-split-height

**Tipo:** number

The default height of a small scale Split Button's arrow ...

The default height of a small scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-small-split-width

**Tipo:** number

The default width of a small scale Split Button's arrow ...

The default width of a small scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-small-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a small scale button ...

The default horizontal padding to add to the left and right of the text element for
a small scale button
Defaults to: `4px`


### $button-split-height

**Tipo:** number

The default height for a Split Button's arrow ...

The default height for a Split Button's arrow
Defaults to: `14px`


### $button-split-width

**Tipo:** number

The default width for a Split Button's arrow ...

The default width for a Split Button's arrow
Defaults to: `14px`


### $button-toolbar-background-color

**Tipo:** color

The background-color for the default-toolbar button UI ...

The background-color for the `default-toolbar` button UI
Defaults to: `$base-color`


### $button-toolbar-background-color-disabled

**Tipo:** color

The background-color for the default-toolbar button UI when the button is disabled ...

The background-color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-color-focus

**Tipo:** color

The background-color for the default-toolbar button UI when the button is focused ...

The background-color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-background-color-over`


### $button-toolbar-background-color-over

**Tipo:** color

The background-color for the default-toolbar button UI when the cursor is over the button ...

The background-color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-color-pressed

**Tipo:** color

The background-color for the default-toolbar button UI when the button is pressed ...

The background-color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-gradient

**Tipo:** string/list

The background-gradient for the default-toolbar button UI. ...

The background-gradient for the `default-toolbar` button UI.  Can be either the name of
a predefined gradient or a list of color stops. Used as the `$type` parameter for
Global_CSS.background-gradient.
Defaults to: `'glossy-button'`


### $button-toolbar-background-gradient-disabled

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is disabled. ...

The background-gradient for the `default-toolbar` button UI when the button is disabled.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-disabled'`


### $button-toolbar-background-gradient-focus

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is focused. ...

The background-gradient for the `default-toolbar` button UI when the button is focused.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `$button-toolbar-background-gradient-over`


### $button-toolbar-background-gradient-over

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the cursor is over the
button. ...

The background-gradient for the `default-toolbar` button UI when the cursor is over the
button. Can be either the name of a predefined gradient or a list of color stops. Used
as the `$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-over'`


### $button-toolbar-background-gradient-pressed

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is pressed. ...

The background-gradient for the `default-toolbar` button UI when the button is pressed.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-pressed'`


### $button-toolbar-border-color

**Tipo:** color

The border-color for the default-toolbar button UI ...

The border-color for the `default-toolbar` button UI
Defaults to: `$base-color`


### $button-toolbar-border-color-disabled

**Tipo:** color

The border-color for the default-toolbar button UI when the button is disabled ...

The border-color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-border-color-focus

**Tipo:** color

The border-color for the default-toolbar button UI when the button is focused ...

The border-color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-border-color-over`


### $button-toolbar-border-color-over

**Tipo:** color

The border-color for the default-toolbar button UI when the cursor is over the button ...

The border-color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-border-color-pressed

**Tipo:** color

The border-color for the default-toolbar button UI when the button is pressed ...

The border-color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-color

**Tipo:** color

The text color for the default-toolbar button UI ...

The text color for the `default-toolbar` button UI
Defaults to: `#000`


### $button-toolbar-color-disabled

**Tipo:** color

The text color for the default-toolbar button UI when the button is disabled ...

The text color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-color`


### $button-toolbar-color-focus

**Tipo:** color

The text color for the default-toolbar button UI when the button is focused ...

The text color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-color-over`


### $button-toolbar-color-over

**Tipo:** color

The text color for the default-toolbar button UI when the cursor is over the button ...

The text color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-color`


### $button-toolbar-color-pressed

**Tipo:** color

The text color for the default-toolbar button UI when the button is pressed ...

The text color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-color`


### $button-toolbar-glyph-color

**Tipo:** color

The color of the glyph icon for the default-toolbar button UI ...

The color of the glyph icon for the `default-toolbar` button UI
Defaults to: `$button-toolbar-color`


### $button-toolbar-glyph-opacity

**Tipo:** color

The opacity of the glyph icon for the default-toolbar button UI ...

The opacity of the glyph icon for the `default-toolbar` button UI
Defaults to: `.5`


### $button-toolbar-include-split-noline-arrows

**Tipo:** boolean

True to include "noline" split arrows for toolbar buttons in their default state. ...

True to include "noline" split arrows for toolbar buttons in their default state.
Defaults to: `false`


### $button-toolbar-inner-opacity-disabled

**Tipo:** number

opacity to apply to the toolbar button's inner elements (icon and text) when the buton is disabled ...

opacity to apply to the toolbar button's inner elements (icon and text) when the buton is disabled
Defaults to: `1`


### $button-toolbar-opacity-disabled

**Tipo:** number

opacity to apply to the toolbar button's main element when the buton is disabled ...

opacity to apply to the toolbar button's main element when the buton is disabled
Defaults to: `.5`


### $include-button-default-large-ui

**Tipo:** boolean

True to include the "default" button UI for "large" scale buttons ...

True to include the "default" button UI for "large" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-medium-ui

**Tipo:** boolean

True to include the "default" button UI for "medium" scale buttons ...

True to include the "default" button UI for "medium" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-small-ui

**Tipo:** boolean

True to include the "default" button UI for "small" scale buttons ...

True to include the "default" button UI for "small" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-toolbar-large-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "large" scale buttons ...

True to include the "default-toolbar" button UI for "large" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-medium-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "medium" scale buttons ...

True to include the "default-toolbar" button UI for "medium" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-small-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "small" scale buttons ...

True to include the "default-toolbar" button UI for "small" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI ...

True to include the "default-toolbar" button UI
Defaults to: `$include-default-uis`


### $include-button-default-ui

**Tipo:** boolean

True to include the "default" button UI ...

True to include the "default" button UI
Defaults to: `$include-default-uis`


### extjs-button-ui

Creates a visual theme for a Button ...

Creates a visual theme for a Button
$ui : stringThe name of the UI being created. Can not included spaces or special punctuation
(used in CSS class names).


## CSS Variables

### $button-arrow-height

**Tipo:** number

The default height for a button's menu arrow ...

The default height for a button's menu arrow
Defaults to: `12px`


### $button-arrow-width

**Tipo:** number

The default width for a button's menu arrow ...

The default width for a button's menu arrow
Defaults to: `12px`


### $button-default-background-color

**Tipo:** color

The background-color for the default button UI ...

The background-color for the `default` button UI
Defaults to: `$button-default-base-color`


### $button-default-background-color-disabled

**Tipo:** color

The background-color for the default button UI when the button is disabled ...

The background-color for the `default` button UI when the button is disabled
Defaults to: `null`


### $button-default-background-color-focus

**Tipo:** color

The background-color for the default button UI when the button is focused ...

The background-color for the `default` button UI when the button is focused
Defaults to: `$button-default-background-color-over`


### $button-default-background-color-over

**Tipo:** color

The background-color for the default button UI when the cursor is over the button ...

The background-color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-base-color-over`


### $button-default-background-color-pressed

**Tipo:** color

The background-color for the default button UI when the button is pressed ...

The background-color for the `default` button UI when the button is pressed
Defaults to: `$button-default-base-color-pressed`


### $button-default-background-gradient

**Tipo:** string/list

The background-gradient for the default button UI. ...

The background-gradient for the `default` button UI.  Can be either the name of a
predefined gradient or a list of color stops. Used as the `$type` parameter for
Global_CSS.background-gradient.
Defaults to: `'glossy-button'`


### $button-default-background-gradient-disabled

**Tipo:** string/list

The background-gradient for the default button UI when the button is disabled. ...

The background-gradient for the `default` button UI when the button is disabled.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-disabled'`


### $button-default-background-gradient-focus

**Tipo:** string/list

The background-gradient for the default button UI when the button is focused. ...

The background-gradient for the `default` button UI when the button is focused.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `$button-default-background-gradient-over`


### $button-default-background-gradient-over

**Tipo:** string/list

The background-gradient for the default button UI when the cursor is over the button. ...

The background-gradient for the `default` button UI when the cursor is over the button.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-over'`


### $button-default-background-gradient-pressed

**Tipo:** string/list

The background-gradient for the default button UI when the button is pressed. ...

The background-gradient for the `default` button UI when the button is pressed.  Can be
either the name of a predefined gradient or a list of color stops. Used as the `$type`
parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-pressed'`


### $button-default-base-color

**Tipo:** color

The base color for the default button UI ...

The base color for the `default` button UI
Defaults to: `$base-color`


### $button-default-base-color-disabled

**Tipo:** color

The base color for the default button UI when the button is disabled ...

The base color for the `default` button UI when the button is disabled
Defaults to: `$base-color`


### $button-default-base-color-focus

**Tipo:** color

The base color for the default button UI when the button is focused ...

The base color for the `default` button UI when the button is focused
Defaults to: `$button-default-base-color-over`


### $button-default-base-color-over

**Tipo:** color

The base color for the default button UI when the cursor is over the button ...

The base color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-base-color`


### $button-default-base-color-pressed

**Tipo:** color

The base color for the default button UI when the button is pressed ...

The base color for the `default` button UI when the button is pressed
Defaults to: `$button-default-base-color`


### $button-default-border-color

**Tipo:** color

The border-color for the default button UI ...

The border-color for the `default` button UI
Defaults to: `$base-color`


### $button-default-border-color-disabled

**Tipo:** color

The border-color for the default button UI when the button is disabled ...

The border-color for the `default` button UI when the button is disabled
Defaults to: `$base-color`


### $button-default-border-color-focus

**Tipo:** color

The border-color for the default button UI when the button is focused ...

The border-color for the `default` button UI when the button is focused
Defaults to: `$base-color`


### $button-default-border-color-over

**Tipo:** color

The border-color for the default button UI when the cursor is over the button ...

The border-color for the `default` button UI when the cursor is over the button
Defaults to: `$base-color`


### $button-default-border-color-pressed

**Tipo:** color

The border-color for the default button UI when the button is pressed ...

The border-color for the `default` button UI when the button is pressed
Defaults to: `$base-color`


### $button-default-color

**Tipo:** color

The text color for the default button UI ...

The text color for the `default` button UI
Defaults to: `#000`


### $button-default-color-disabled

**Tipo:** color

The text color for the default button UI when the button is disabled ...

The text color for the `default` button UI when the button is disabled
Defaults to: `$button-default-color`


### $button-default-color-focus

**Tipo:** color

The text color for the default button UI when the button is focused ...

The text color for the `default` button UI when the button is focused
Defaults to: `$button-default-color-over`


### $button-default-color-over

**Tipo:** color

The text color for the default button UI when the cursor is over the button ...

The text color for the `default` button UI when the cursor is over the button
Defaults to: `$button-default-color`


### $button-default-color-pressed

**Tipo:** color

The text color for the default button UI when the button is pressed ...

The text color for the `default` button UI when the button is pressed
Defaults to: `$button-default-color`


### $button-default-glyph-color

**Tipo:** color

The color of the glyph icon for the default button UI ...

The color of the glyph icon for the `default` button UI
Defaults to: `$button-default-color`


### $button-default-glyph-opacity

**Tipo:** color

The opacity of the glyph icon for the default button UI ...

The opacity of the glyph icon for the `default` button UI
Defaults to: `.5`


### $button-icon-spacing

**Tipo:** number

The default space between a button's icon and text ...

The default space between a button's icon and text
Defaults to: `4px`


### $button-include-split-over-arrows

**Tipo:** boolean

True to include different split arrows for buttons' hover state. ...

True to include different split arrows for buttons' hover state.
Defaults to: `false`


### $button-include-ui-menu-arrows

**Tipo:** boolean

True to use a different image url for the menu button arrows for each button UI ...

True to use a different image url for the menu button arrows for each button UI
Defaults to: `false`


### $button-include-ui-split-arrows

**Tipo:** boolean

True to use a different image url for the split button arrows for each button UI ...

True to use a different image url for the split button arrows for each button UI
Defaults to: `false`


### $button-inner-opacity-disabled

**Tipo:** number

opacity to apply to the button's inner elements (icon and text) when the buton is disabled ...

opacity to apply to the button's inner elements (icon and text) when the buton is disabled
Defaults to: `1`


### $button-large-arrow-height

**Tipo:** number

The default height of a large scale button's menu arrow ...

The default height of a large scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-large-arrow-width

**Tipo:** number

The default width of a large scale button's menu arrow ...

The default width of a large scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-large-border-radius

**Tipo:** number

The default border-radius for a large scale button ...

The default border-radius for a large scale button
Defaults to: `3px`


### $button-large-border-width

**Tipo:** number

The default border-width for a large scale button ...

The default border-width for a large scale button
Defaults to: `1px`


### $button-large-font-family

**Tipo:** string

The default font-family for a large scale button ...

The default font-family for a large scale button
Defaults to: `$font-family`


### $button-large-font-family-disabled

**Tipo:** string

The default font-family for a large scale button when the button is disabled ...

The default font-family for a large scale button when the button is disabled
Defaults to: `$button-large-font-family`


### $button-large-font-family-focus

**Tipo:** string

The default font-family for a large scale button when the button is focused ...

The default font-family for a large scale button when the button is focused
Defaults to: `$button-large-font-family-over`


### $button-large-font-family-over

**Tipo:** string

The default font-family for a large scale button when the cursor is over the button ...

The default font-family for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-family`


### $button-large-font-family-pressed

**Tipo:** string

The default font-family for a large scale button when the button is pressed ...

The default font-family for a large scale button when the button is pressed
Defaults to: `$button-large-font-family`


### $button-large-font-size

**Tipo:** number

The default font-size for a large scale button ...

The default font-size for a large scale button
Defaults to: `$font-size`


### $button-large-font-size-disabled

**Tipo:** number

The default font-size for a large scale button when the button is disabled ...

The default font-size for a large scale button when the button is disabled
Defaults to: `$button-large-font-size`


### $button-large-font-size-focus

**Tipo:** number

The default font-size for a large scale button when the button is focused ...

The default font-size for a large scale button when the button is focused
Defaults to: `$button-large-font-size-over`


### $button-large-font-size-over

**Tipo:** number

The default font-size for a large scale button when the cursor is over the button ...

The default font-size for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-size`


### $button-large-font-size-pressed

**Tipo:** number

The default font-size for a large scale button when the button is pressed ...

The default font-size for a large scale button when the button is pressed
Defaults to: `$button-large-font-size`


### $button-large-font-weight

**Tipo:** string

The default font-weight for a large scale button ...

The default font-weight for a large scale button
Defaults to: `normal`


### $button-large-font-weight-disabled

**Tipo:** string

The default font-weight for a large scale button when the button is disabled ...

The default font-weight for a large scale button when the button is disabled
Defaults to: `$button-large-font-weight`


### $button-large-font-weight-focus

**Tipo:** string

The default font-weight for a large scale button when the button is focused ...

The default font-weight for a large scale button when the button is focused
Defaults to: `$button-large-font-weight-over`


### $button-large-font-weight-over

**Tipo:** string

The default font-weight for a large scale button when the cursor is over the button ...

The default font-weight for a large scale button when the cursor is over the button
Defaults to: `$button-large-font-weight`


### $button-large-font-weight-pressed

**Tipo:** string

The default font-weight for a large scale button when the button is pressed ...

The default font-weight for a large scale button when the button is pressed
Defaults to: `$button-large-font-weight`


### $button-large-icon-size

**Tipo:** number

The default icon size for a large scale button ...

The default icon size for a large scale button
Defaults to: `32px`


### $button-large-padding

**Tipo:** number

The default padding for a large scale button ...

The default padding for a large scale button
Defaults to: `3px`


### $button-large-split-height

**Tipo:** number

The default height of a large scale Split Button's arrow ...

The default height of a large scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-large-split-width

**Tipo:** number

The default width of a large scale Split Button's arrow ...

The default width of a large scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-large-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a large scale button ...

The default horizontal padding to add to the left and right of the text element for
a large scale button
Defaults to: `3px`


### $button-medium-arrow-height

**Tipo:** number

The default height of a medium scale button's menu arrow ...

The default height of a medium scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-medium-arrow-width

**Tipo:** number

The default width of a medium scale button's menu arrow ...

The default width of a medium scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-medium-border-radius

**Tipo:** number

The default border-radius for a medium scale button ...

The default border-radius for a medium scale button
Defaults to: `3px`


### $button-medium-border-width

**Tipo:** number

The default border-width for a medium scale button ...

The default border-width for a medium scale button
Defaults to: `1px`


### $button-medium-font-family

**Tipo:** string

The default font-family for a medium scale button ...

The default font-family for a medium scale button
Defaults to: `$font-family`


### $button-medium-font-family-disabled

**Tipo:** string

The default font-family for a medium scale button when the button is disabled ...

The default font-family for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-family`


### $button-medium-font-family-focus

**Tipo:** string

The default font-family for a medium scale button when the button is focused ...

The default font-family for a medium scale button when the button is focused
Defaults to: `$button-medium-font-family-over`


### $button-medium-font-family-over

**Tipo:** string

The default font-family for a medium scale button when the cursor is over the button ...

The default font-family for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-family`


### $button-medium-font-family-pressed

**Tipo:** string

The default font-family for a medium scale button when the button is pressed ...

The default font-family for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-family`


### $button-medium-font-size

**Tipo:** number

The default font-size for a medium scale button ...

The default font-size for a medium scale button
Defaults to: `$font-size`


### $button-medium-font-size-disabled

**Tipo:** number

The default font-size for a medium scale button when the button is disabled ...

The default font-size for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-size`


### $button-medium-font-size-focus

**Tipo:** number

The default font-size for a medium scale button when the button is focused ...

The default font-size for a medium scale button when the button is focused
Defaults to: `$button-medium-font-size-over`


### $button-medium-font-size-over

**Tipo:** number

The default font-size for a medium scale button when the cursor is over the button ...

The default font-size for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-size`


### $button-medium-font-size-pressed

**Tipo:** number

The default font-size for a medium scale button when the button is pressed ...

The default font-size for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-size`


### $button-medium-font-weight

**Tipo:** string

The default font-weight for a medium scale button ...

The default font-weight for a medium scale button
Defaults to: `normal`


### $button-medium-font-weight-disabled

**Tipo:** string

The default font-weight for a medium scale button when the button is disabled ...

The default font-weight for a medium scale button when the button is disabled
Defaults to: `$button-medium-font-weight`


### $button-medium-font-weight-focus

**Tipo:** string

The default font-weight for a medium scale button when the button is focused ...

The default font-weight for a medium scale button when the button is focused
Defaults to: `$button-medium-font-weight-over`


### $button-medium-font-weight-over

**Tipo:** string

The default font-weight for a medium scale button when the cursor is over the button ...

The default font-weight for a medium scale button when the cursor is over the button
Defaults to: `$button-medium-font-weight`


### $button-medium-font-weight-pressed

**Tipo:** string

The default font-weight for a medium scale button when the button is pressed ...

The default font-weight for a medium scale button when the button is pressed
Defaults to: `$button-medium-font-weight`


### $button-medium-icon-size

**Tipo:** number

The default icon size for a medium scale button ...

The default icon size for a medium scale button
Defaults to: `24px`


### $button-medium-padding

**Tipo:** number

The default padding for a medium scale button ...

The default padding for a medium scale button
Defaults to: `3px`


### $button-medium-split-height

**Tipo:** number

The default height of a medium scale Split Button's arrow ...

The default height of a medium scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-medium-split-width

**Tipo:** number

The default width of a medium scale Split Button's arrow ...

The default width of a medium scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-medium-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a medium scale button ...

The default horizontal padding to add to the left and right of the text element for
a medium scale button
Defaults to: `3px`


### $button-opacity-disabled

**Tipo:** number

opacity to apply to the button's main element when the buton is disabled ...

opacity to apply to the button's main element when the buton is disabled
Defaults to: `.5`


### $button-small-arrow-height

**Tipo:** number

The default height of a small scale button's menu arrow ...

The default height of a small scale button's menu arrow
Defaults to: `$button-arrow-height`


### $button-small-arrow-width

**Tipo:** number

The default width of a small scale button's menu arrow ...

The default width of a small scale button's menu arrow
Defaults to: `$button-arrow-width`


### $button-small-border-radius

**Tipo:** number

The default border-radius for a small scale button ...

The default border-radius for a small scale button
Defaults to: `3px`


### $button-small-border-width

**Tipo:** number

The default border-width for a small scale button ...

The default border-width for a small scale button
Defaults to: `1px`


### $button-small-font-family

**Tipo:** string

The default font-family for a small scale button ...

The default font-family for a small scale button
Defaults to: `$font-family`


### $button-small-font-family-disabled

**Tipo:** string

The default font-family for a small scale button when the button is disabled ...

The default font-family for a small scale button when the button is disabled
Defaults to: `$button-small-font-family`


### $button-small-font-family-focus

**Tipo:** string

The default font-family for a small scale button when the button is focused ...

The default font-family for a small scale button when the button is focused
Defaults to: `$button-small-font-family-over`


### $button-small-font-family-over

**Tipo:** string

The default font-family for a small scale button when the cursor is over the button ...

The default font-family for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-family`


### $button-small-font-family-pressed

**Tipo:** string

The default font-family for a small scale button when the button is pressed ...

The default font-family for a small scale button when the button is pressed
Defaults to: `$button-small-font-family`


### $button-small-font-size

**Tipo:** number

The default font-size for a small scale button ...

The default font-size for a small scale button
Defaults to: `ceil ( $font-size * .9 )`


### $button-small-font-size-disabled

**Tipo:** number

The default font-size for a small scale button when the button is disabled ...

The default font-size for a small scale button when the button is disabled
Defaults to: `$button-small-font-size`


### $button-small-font-size-focus

**Tipo:** number

The default font-size for a small scale button when the button is focused ...

The default font-size for a small scale button when the button is focused
Defaults to: `$button-small-font-size-over`


### $button-small-font-size-over

**Tipo:** number

The default font-size for a small scale button when the cursor is over the button ...

The default font-size for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-size`


### $button-small-font-size-pressed

**Tipo:** number

The default font-size for a small scale button when the button is pressed ...

The default font-size for a small scale button when the button is pressed
Defaults to: `$button-small-font-size`


### $button-small-font-weight

**Tipo:** string

The default font-weight for a small scale button ...

The default font-weight for a small scale button
Defaults to: `normal`


### $button-small-font-weight-disabled

**Tipo:** string

The default font-weight for a small scale button when the button is disabled ...

The default font-weight for a small scale button when the button is disabled
Defaults to: `$button-small-font-weight`


### $button-small-font-weight-focus

**Tipo:** string

The default font-weight for a small scale button when the button is focused ...

The default font-weight for a small scale button when the button is focused
Defaults to: `$button-small-font-weight-over`


### $button-small-font-weight-over

**Tipo:** string

The default font-weight for a small scale button when the cursor is over the button ...

The default font-weight for a small scale button when the cursor is over the button
Defaults to: `$button-small-font-weight`


### $button-small-font-weight-pressed

**Tipo:** string

The default font-weight for a small scale button when the button is pressed ...

The default font-weight for a small scale button when the button is pressed
Defaults to: `$button-small-font-weight`


### $button-small-icon-size

**Tipo:** number

The default icon size for a small scale button ...

The default icon size for a small scale button
Defaults to: `16px`


### $button-small-padding

**Tipo:** number

The default padding for a small scale button ...

The default padding for a small scale button
Defaults to: `2px`


### $button-small-split-height

**Tipo:** number

The default height of a small scale Split Button's arrow ...

The default height of a small scale Split Button's arrow
Defaults to: `$button-split-height`


### $button-small-split-width

**Tipo:** number

The default width of a small scale Split Button's arrow ...

The default width of a small scale Split Button's arrow
Defaults to: `$button-split-width`


### $button-small-text-padding

**Tipo:** number

The default horizontal padding to add to the left and right of the text element for
a small scale button ...

The default horizontal padding to add to the left and right of the text element for
a small scale button
Defaults to: `4px`


### $button-split-height

**Tipo:** number

The default height for a Split Button's arrow ...

The default height for a Split Button's arrow
Defaults to: `14px`


### $button-split-width

**Tipo:** number

The default width for a Split Button's arrow ...

The default width for a Split Button's arrow
Defaults to: `14px`


### $button-toolbar-background-color

**Tipo:** color

The background-color for the default-toolbar button UI ...

The background-color for the `default-toolbar` button UI
Defaults to: `$base-color`


### $button-toolbar-background-color-disabled

**Tipo:** color

The background-color for the default-toolbar button UI when the button is disabled ...

The background-color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-color-focus

**Tipo:** color

The background-color for the default-toolbar button UI when the button is focused ...

The background-color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-background-color-over`


### $button-toolbar-background-color-over

**Tipo:** color

The background-color for the default-toolbar button UI when the cursor is over the button ...

The background-color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-color-pressed

**Tipo:** color

The background-color for the default-toolbar button UI when the button is pressed ...

The background-color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-background-color`


### $button-toolbar-background-gradient

**Tipo:** string/list

The background-gradient for the default-toolbar button UI. ...

The background-gradient for the `default-toolbar` button UI.  Can be either the name of
a predefined gradient or a list of color stops. Used as the `$type` parameter for
Global_CSS.background-gradient.
Defaults to: `'glossy-button'`


### $button-toolbar-background-gradient-disabled

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is disabled. ...

The background-gradient for the `default-toolbar` button UI when the button is disabled.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-disabled'`


### $button-toolbar-background-gradient-focus

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is focused. ...

The background-gradient for the `default-toolbar` button UI when the button is focused.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `$button-toolbar-background-gradient-over`


### $button-toolbar-background-gradient-over

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the cursor is over the
button. ...

The background-gradient for the `default-toolbar` button UI when the cursor is over the
button. Can be either the name of a predefined gradient or a list of color stops. Used
as the `$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-over'`


### $button-toolbar-background-gradient-pressed

**Tipo:** string/list

The background-gradient for the default-toolbar button UI when the button is pressed. ...

The background-gradient for the `default-toolbar` button UI when the button is pressed.
Can be either the name of a predefined gradient or a list of color stops. Used as the
`$type` parameter for Global_CSS.background-gradient.
Defaults to: `'glossy-button-pressed'`


### $button-toolbar-border-color

**Tipo:** color

The border-color for the default-toolbar button UI ...

The border-color for the `default-toolbar` button UI
Defaults to: `$base-color`


### $button-toolbar-border-color-disabled

**Tipo:** color

The border-color for the default-toolbar button UI when the button is disabled ...

The border-color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-border-color-focus

**Tipo:** color

The border-color for the default-toolbar button UI when the button is focused ...

The border-color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-border-color-over`


### $button-toolbar-border-color-over

**Tipo:** color

The border-color for the default-toolbar button UI when the cursor is over the button ...

The border-color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-border-color-pressed

**Tipo:** color

The border-color for the default-toolbar button UI when the button is pressed ...

The border-color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-border-color`


### $button-toolbar-color

**Tipo:** color

The text color for the default-toolbar button UI ...

The text color for the `default-toolbar` button UI
Defaults to: `#000`


### $button-toolbar-color-disabled

**Tipo:** color

The text color for the default-toolbar button UI when the button is disabled ...

The text color for the `default-toolbar` button UI when the button is disabled
Defaults to: `$button-toolbar-color`


### $button-toolbar-color-focus

**Tipo:** color

The text color for the default-toolbar button UI when the button is focused ...

The text color for the `default-toolbar` button UI when the button is focused
Defaults to: `$button-toolbar-color-over`


### $button-toolbar-color-over

**Tipo:** color

The text color for the default-toolbar button UI when the cursor is over the button ...

The text color for the `default-toolbar` button UI when the cursor is over the button
Defaults to: `$button-toolbar-color`


### $button-toolbar-color-pressed

**Tipo:** color

The text color for the default-toolbar button UI when the button is pressed ...

The text color for the `default-toolbar` button UI when the button is pressed
Defaults to: `$button-toolbar-color`


### $button-toolbar-glyph-color

**Tipo:** color

The color of the glyph icon for the default-toolbar button UI ...

The color of the glyph icon for the `default-toolbar` button UI
Defaults to: `$button-toolbar-color`


### $button-toolbar-glyph-opacity

**Tipo:** color

The opacity of the glyph icon for the default-toolbar button UI ...

The opacity of the glyph icon for the `default-toolbar` button UI
Defaults to: `.5`


### $button-toolbar-include-split-noline-arrows

**Tipo:** boolean

True to include "noline" split arrows for toolbar buttons in their default state. ...

True to include "noline" split arrows for toolbar buttons in their default state.
Defaults to: `false`


### $button-toolbar-inner-opacity-disabled

**Tipo:** number

opacity to apply to the toolbar button's inner elements (icon and text) when the buton is disabled ...

opacity to apply to the toolbar button's inner elements (icon and text) when the buton is disabled
Defaults to: `1`


### $button-toolbar-opacity-disabled

**Tipo:** number

opacity to apply to the toolbar button's main element when the buton is disabled ...

opacity to apply to the toolbar button's main element when the buton is disabled
Defaults to: `.5`


### $include-button-default-large-ui

**Tipo:** boolean

True to include the "default" button UI for "large" scale buttons ...

True to include the "default" button UI for "large" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-medium-ui

**Tipo:** boolean

True to include the "default" button UI for "medium" scale buttons ...

True to include the "default" button UI for "medium" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-small-ui

**Tipo:** boolean

True to include the "default" button UI for "small" scale buttons ...

True to include the "default" button UI for "small" scale buttons
Defaults to: `$include-button-default-ui`


### $include-button-default-toolbar-large-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "large" scale buttons ...

True to include the "default-toolbar" button UI for "large" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-medium-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "medium" scale buttons ...

True to include the "default-toolbar" button UI for "medium" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-small-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI for "small" scale buttons ...

True to include the "default-toolbar" button UI for "small" scale buttons
Defaults to: `$include-button-default-toolbar-ui`


### $include-button-default-toolbar-ui

**Tipo:** boolean

True to include the "default-toolbar" button UI ...

True to include the "default-toolbar" button UI
Defaults to: `$include-default-uis`


### $include-button-default-ui

**Tipo:** boolean

True to include the "default" button UI ...

True to include the "default" button UI
Defaults to: `$include-default-uis`


### extjs-button-ui

Creates a visual theme for a Button ...

Creates a visual theme for a Button
$ui : stringThe name of the UI being created. Can not included spaces or special punctuation
(used in CSS class names).


## CSS Mixins

### extjs-button-ui

Creates a visual theme for a Button ...

Creates a visual theme for a Button
$ui : stringThe name of the UI being created. Can not included spaces or special punctuation
(used in CSS class names).


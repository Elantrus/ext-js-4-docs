# Ext.panel.Table

**Extends:** Ext.panel.Panel

**Widget Alias:** tablepanel

## Description

TablePanel is the basis of both TreePanel and GridPanel.

TablePanel aggregates:

## Config options

### store

**Type:** Ext.data.Store

The Store the grid should use as its data source.


### activeItem

**Type:** String/Number

A string component id or the numeric index of the component that should be initially activated within the container's...

A string component id or the numeric index of the component that should be initially activated within the container's layout on render. For example, activeItem: 'item-1' or activeItem: 0 (index 0 = the first item in the container's collection). activeItem only applies to layout styles that can display items one at a time (like Ext.layout.container.Card and Ext.layout.container.Fit). Available since: 2.3.0


### allowDeselect

**Type:** Boolean

True to allow deselecting a record. ...

True to allow deselecting a record. This config is forwarded to Ext.selection.Model.allowDeselect. Defaults to: `false`


### anchorSize

**Type:** Number/Object

Defines the anchoring size of container. ...

Defines the anchoring size of container. Either a number to define the width of the container or an object with `width` and `height` fields.


### animCollapse

**Type:** Boolean

true to animate the transition when the panel is collapsed, false to skip the animation (defaults to true if the Ext....

`true` to animate the transition when the panel is collapsed, `false` to skip the animation (defaults to `true` if the Ext.fx.Anim class is available, otherwise `false`). May also be specified as the animation duration in milliseconds.


### autoDestroy

**Type:** Boolean

If true the container will automatically destroy any contained component that is removed from it, else destruction mu...

If true the container will automatically destroy any contained component that is removed from it, else destruction must be handled manually. Defaults to: `true` Available since: 2.3.0


### autoEl

**Type:** String/Object

A tag name or DomHelper spec used to create the Element which will encapsulate this Component. ...

A tag name or DomHelper spec used to create the Element which will encapsulate this Component. You do not normally need to specify this. For the base classes Ext.Component and Ext.container.Container, this defaults to **'div'**. The more complex Sencha classes use a more complex DOM structure specified by their own renderTpls. This is intended to allow the developer to create application-specific utility Components encapsulated by different DOM elements. Example usage: Available since: 2.3.0


### autoLoad

**Type:** Ext.ComponentLoader/Object/String/Boolean

An alias for loader config which also allows to specify just a string which will be used as the url that's automatica...

An alias for loader config which also allows to specify just a string which will be used as the url that's automatically loaded: The above is the same as: Don't use it together with loader config. This cfg has been **deprecated** since 4.1.1 Use loader config instead.


### autoRender

**Type:** Boolean/String/HTMLElement/Ext.Element

This config is intended mainly for non-floating Components which may or may not be shown. ...

This config is intended mainly for non-floating Components which may or may not be shown. Instead of using renderTo in the configuration, and rendering upon construction, this allows a Component to render itself upon first *show*. If floating is `true`, the value of this config is omitted as if it is `true`. Specify as `true` to have this Component render to the document body upon first show. Specify as an element, or the ID of an element to have this Component render to a specific element upon first show. Defaults to: `false`


### autoScroll

**Type:** Boolean

true to use overflow:'auto' on the components layout element and show scroll bars automatically when necessary, false...

`true` to use overflow:'auto' on the components layout element and show scroll bars automatically when necessary, `false` to clip any overflowing content. This should not be combined with overflowX or overflowY. Defaults to: `false`


### autoShow

**Type:** Boolean

true to automatically show the component upon creation. ...

`true` to automatically show the component upon creation. This config option may only be used for floating components or components that use autoRender. Defaults to: `false` Available since: 2.3.0


### baseCls

**Type:** String

The base CSS class to apply to this panel's element. ...

The base CSS class to apply to this panel's element. Defaults to: `x-panel` Available since: 2.3.0 Overrides: Ext.container.AbstractContainer.baseCls


### bbar

**Type:** Object/Object[]

Convenience config. ...

Convenience config. Short for 'Bottom Bar'. is equivalent to


### bodyBorder

**Type:** Boolean

A shortcut to add or remove the border on the body of a panel. ...

A shortcut to add or remove the border on the body of a panel. In the classic theme this only applies to a panel which has the frame configuration set to `true`. Available since: 2.3.0


### bodyCls

**Type:** String/String[]

A CSS class, space-delimited string of classes, or array of classes to be applied to the panel's body element. ...

A CSS class, space-delimited string of classes, or array of classes to be applied to the panel's body element. The following examples are all valid:


### bodyPadding

**Type:** Number/String

A shortcut for setting a padding style on the body element. ...

A shortcut for setting a padding style on the body element. The value can either be a number to be applied to all sides, or a normal css string describing padding. Defaults to `undefined`.


### bodyStyle

**Type:** String/Object/Function

Custom CSS styles to be applied to the panel's body element, which can be supplied as a valid CSS style string, an ob...

Custom CSS styles to be applied to the panel's body element, which can be supplied as a valid CSS style string, an object containing style property name/value pairs or a function that returns such a string or object. For example, these two formats are interpreted to be equivalent: Available since: 2.3.0


### border

**Type:** Number/String/Boolean

Specifies the border size for this component. ...

Specifies the border size for this component. The border can be a single numeric value to apply to all sides or it can be a CSS style specification for each style, for example: '10 5 3 10' (top, right, bottom, left). For components that have no border by default, setting this won't make the border appear by itself. You also need to specify border color and style: To turn off the border, use `border: false`. Defaults to: `true` Available since: 2.3.0 Overrides: Ext.AbstractComponent.border


### bubbleEvents

**Type:** String[]

An array of events that, when fired, should be bubbled to any parent container. ...

An array of events that, when fired, should be bubbled to any parent container. See Ext.util.Observable.enableBubble. Available since: 3.4.0


### buttonAlign

**Type:** String

The alignment of any buttons added to this panel. ...

The alignment of any buttons added to this panel. Valid values are 'right', 'left' and 'center' (defaults to 'right' for buttons/fbar, 'left' for other toolbar types). **NOTE:** The prefered way to specify toolbars is to use the dockedItems config. Instead of buttonAlign you would add the layout: { pack: 'start' | 'center' | 'end' } option to the dockedItem config.


### buttons

**Type:** Object/Object[]

Convenience config used for adding buttons docked to the bottom of the panel. ...

Convenience config used for adding buttons docked to the bottom of the panel. This is a synonym for the fbar config. is equivalent to The minButtonWidth is used as the default minWidth for each of the buttons in the buttons toolbar.


### childEls

**Type:** Object[]

An array describing the child elements of the Component. ...

An array describing the child elements of the Component. Each member of the array is an object with these properties: - `name` - The property name on the Component for the child element. - `itemId` - The id to combine with the Component's id that is the id of the child element. - `id` - The id of the child element. If the array member is a string, it is equivalent to `{ name: m, itemId: m }`. For example, a Component which renders a title and body text: A more flexible, but somewhat slower, approach is renderSelectors.


### closable

**Type:** Boolean

True to display the 'close' tool button and allow the user to close the window, false to hide the button and disallow...

True to display the 'close' tool button and allow the user to close the window, false to hide the button and disallow closing the window. By default, when close is requested by clicking the close button in the header, the close method will be called. This will *destroy* the Panel and its content meaning that it may not be reused. To make closing a Panel *hide* the Panel so that it may be reused, set closeAction to 'hide'. Defaults to: `false`


### closeAction

**Type:** String

The action to take when the close header tool is clicked: 'destroy' : remove the window from the DOM and destroy i...

The action to take when the close header tool is clicked: - **`'destroy'`** : remove the window from the DOM and destroy it and all descendant Components. The window will **not** be available to be redisplayed via the show method. - **`'hide'`** : hide the window by setting visibility to hidden and applying negative offsets. The window will be available to be redisplayed via the show method. **Note:** This behavior has changed! setting *does* affect the close method which will invoke the approriate closeAction. Defaults to: `'destroy'`


### cls

**Type:** String

An optional extra CSS class that will be added to this component's Element. ...

An optional extra CSS class that will be added to this component's Element. This can be useful for adding customized styles to the component or any of its children using standard CSS rules. Defaults to: `''` Available since: 1.1.0


### collapseDirection

**Type:** String

The direction to collapse the Panel when the toggle button is clicked. ...

The direction to collapse the Panel when the toggle button is clicked. Defaults to the headerPosition **Important: This config is *ignored* for collapsible Panels which are direct child items of a border layout.** Specify as `'top'`, `'bottom'`, `'left'` or `'right'`.


### collapseFirst

**Type:** Boolean

true to make sure the collapse/expand toggle button always renders first (to the left of) any other tools in the pane...

`true` to make sure the collapse/expand toggle button always renders first (to the left of) any other tools in the panel's title bar, `false` to render it last. Defaults to: `true`


### collapseMode

**Type:** String

Important: this config is only effective for collapsible Panels which are direct child items of a border layout. ...

Important: this config is only effective for collapsible Panels which are direct child items of a border layout. When *not* a direct child item of a border layout, then the Panel's header remains visible, and the body is collapsed to zero dimensions. If the Panel has no header, then a new header (orientated correctly depending on the collapseDirection) will be inserted to show a the title and a re- expand tool. When a child item of a border layout, this config has three possible values: - `undefined` - When collapsed, a placeholder Header is injected into the layout to represent the Panel and to provide a UI with a Tool to allow the user to re-expand the Panel. - `"header"` - The Panel collapses to leave its header visible as when not inside a border layout. - `"mini"` - The Panel collapses without a visible header.


### collapsed

**Type:** Boolean

true to render the panel collapsed, false to render it expanded. ...

`true` to render the panel collapsed, `false` to render it expanded. Defaults to: `false`


### collapsedCls

**Type:** String

A CSS class to add to the panel's element after it has been collapsed. ...

A CSS class to add to the panel's element after it has been collapsed. Defaults to: `'collapsed'`


### collapsible

**Type:** Boolean

True to make the panel collapsible and have an expand/collapse toggle Tool added into the header tool button area. ...

True to make the panel collapsible and have an expand/collapse toggle Tool added into the header tool button area. False to keep the panel sized either statically, or by an owning layout manager, with no toggle Tool. When a panel is used in a border layout, the floatable option can influence the behavior of collapsing. See collapseMode and collapseDirection


### columnLines

**Type:** Boolean

Adds column line styling


### columnWidth

**Type:** Number/String

Defines the column width inside column layout. ...

Defines the column width inside column layout. Can be specified as a number or as a percentage.


### columns

**Type:** Ext.grid.column.Column[]/Object

An array of column definition objects which define all columns that appear in this grid. ...

An array of column definition objects which define all columns that appear in this grid. Each column definition provides the header text for the column, and a definition of where the data for that column comes from. This can also be a configuration object for a {Ext.grid.header.Container HeaderContainer} which may override certain default configurations if necessary. For example, the special layout may be overridden to use a simpler layout, or one can set default values shared by all columns:


### componentCls

**Type:** String

CSS Class to be added to a components root level element to give distinction to it via styling.


### componentLayout

**Type:** String/Object

The sizing and positioning of a Component's internal Elements is the responsibility of the Component's layout manager...

The sizing and positioning of a Component's internal Elements is the responsibility of the Component's layout manager which sizes a Component's internal structure in response to the Component being sized. Generally, developers will not use this configuration as all provided Components which need their internal elements sizing (Such as input fields) come with their own componentLayout managers. The default layout manager will be used on instances of the base Ext.Component class which simply sizes the Component's encapsulating element to the height and width specified in the setSize method. Defaults to: `'dock'` Overrides: Ext.AbstractComponent.componentLayout


### constrain

**Type:** Boolean

True to constrain the panel within its containing element, false to allow it to fall outside of its containing element. ...

True to constrain the panel within its containing element, false to allow it to fall outside of its containing element. By default floating components such as Windows will be rendered to `document.body`. To render and constrain the window within another element specify renderTo. Optionally the header only can be constrained using constrainHeader. Defaults to: `false` Overrides: Ext.util.Floating.constrain


### constrainHeader

**Type:** Boolean

True to constrain the panel header within its containing element (allowing the panel body to fall outside of its cont...

True to constrain the panel header within its containing element (allowing the panel body to fall outside of its containing element) or false to allow the header to fall outside its containing element. Optionally the entire panel can be constrained using constrain. Defaults to: `false`


### constrainTo

**Type:** Ext.util.Region/Ext.Element

A Region (or an element from which a Region measurement will be read) which is used to constrain the component. ...

A Region (or an element from which a Region measurement will be read) which is used to constrain the component. Only applies when the component is floating.


### constraintInsets

**Type:** Object/String

An object or a string (in TRBL order) specifying insets from the configured constrain region within which this compon...

An object or a string (in TRBL order) specifying insets from the configured constrain region within which this component must be constrained when positioning or sizing. example: constraintInsets: '10 10 10 10' // Constrain with 10px insets from parent


### contentEl

**Type:** String

Specify an existing HTML element, or the id of an existing HTML element to use as the content for this component. ...

Specify an existing HTML element, or the `id` of an existing HTML element to use as the content for this component. This config option is used to take an existing HTML element and place it in the layout element of a new component (it simply moves the specified DOM element *after the Component is rendered* to use as the content. **Notes:** The specified HTML element is appended to the layout element of the component after any configured HTML has been inserted, and so the document will not contain this element at the time the render event is fired. The specified HTML element used will not participate in any **`layout`** scheme that the Component may use. It is just HTML. Layouts operate on child **`items`**. Add either the `x-hidden` or the `x-hide-display` CSS class to prevent a brief flicker of the content before it is rendered to the panel. Available since: 3.4.0


### data

**Type:** Object

The initial set of data to apply to the `tpl` to update the content area of the Component.

The initial set of data to apply to the `tpl` to update the content area of the Component. Available since: 3.4.0


### defaultAlign

**Type:** String

The default Ext.Element#getAlignToXY anchor position value for this menu relative to its element of origin. ...

The default Ext.Element#getAlignToXY anchor position value for this menu relative to its element of origin. Used in conjunction with showBy. Defaults to: `"tl-bl?"`


### defaultDockWeights

**Type:** Object

This object holds the default weights applied to dockedItems that have no weight. ...

This object holds the default weights applied to dockedItems that have no weight. These start with a weight of 1, to allow negative weights to insert before top items and are odd numbers so that even weights can be used to get between different dock orders. To make default docking order match border layout, do this: Changing these defaults as above or individually on this object will effect all Panels. To change the defaults on a single panel, you should replace the entire object: To change only one of the default values, you do this: Defaults to: `{top: {render: 1, visual: 1}, left: {render: 3, visual: 5}, right: {render: 5, visual: 7}, bottom: {render: 7, visual: 3}}`


### defaultType

**Type:** String

The default xtype of child Components to create in this Container when a child item is specified as a raw configurati...

The default xtype of child Components to create in this Container when a child item is specified as a raw configuration object, rather than as an instantiated Component. Defaults to: `"panel"` Available since: 2.3.0


### defaults

**Type:** Object/Function

This option is a means of applying default settings to all added items whether added through the items config or via ...

This option is a means of applying default settings to all added items whether added through the items config or via the add or insert methods. Defaults are applied to both config objects and instantiated components conditionally so as not to override existing properties in the item (see Ext.applyIf). If the defaults option is specified as a function, then the function will be called using this Container as the scope (`this` reference) and passing the added item as the first parameter. Any resulting object from that call is then applied to the item as default properties. For example, to automatically apply padding to the body of each of a set of contained Ext.panel.Panel items, you could pass: `defaults: {bodyStyle:'padding:15px'}`. Usage: Available since: 2.3.0


### deferRowRender

**Type:** Boolean

Defaults to true to enable deferred row rendering. ...

Defaults to true to enable deferred row rendering. This allows the View to execute a refresh quickly, with the expensive update of the row structure deferred so that layouts with GridPanels appear, and lay out more quickly.


### detachOnRemove

**Type:** Boolean

True to move any component to the detachedBody when the component is removed from this container. ...

True to move any component to the detachedBody when the component is removed from this container. This option is only applicable when the component is not destroyed while being removed, see autoDestroy and remove. If this option is set to false, the DOM of the component will remain in the current place until it is explicitly moved. Defaults to: `true`


### disableSelection

**Type:** Boolean

True to disable selection model. ...

True to disable selection model. Defaults to: `false`


### disabled

**Type:** Boolean

true to disable the component. ...

`true` to disable the component. Defaults to: `false` Available since: 2.3.0


### disabledCls

**Type:** String

CSS class to add when the Component is disabled. ...

CSS class to add when the Component is disabled. Defaults to: `'x-item-disabled'`


### dockedItems

**Type:** Object/Object[]

A component or series of components to be added as docked items to this panel. ...

A component or series of components to be added as docked items to this panel. The docked items can be docked to either the top, right, left or bottom of a panel. This is typically used for things like toolbars or tab bars: Overrides: Ext.panel.AbstractPanel.dockedItems


### draggable

**Type:** Boolean/Object

Specify as true to make a floating Component draggable using the Component's encapsulating element as the drag handle. ...

Specify as true to make a floating Component draggable using the Component's encapsulating element as the drag handle. This may also be specified as a config object for the ComponentDragger which is instantiated to perform dragging. For example to create a Component which may only be dragged around using a certain internal element as the drag handle, use the delegate option: Defaults to: `false` Overrides: Ext.AbstractComponent.draggable


### emptyText

**Type:** String

Default text (html tags are accepted) to display in the Panel body when the Store is empty. ...

Default text (html tags are accepted) to display in the Panel body when the Store is empty. When specified, and the Store is empty, the text will be rendered inside a DIV with the CSS class "x-grid-empty".


### enableColumnHide

**Type:** Boolean

False to disable column hiding within this grid. ...

False to disable column hiding within this grid. Defaults to: `true`


### enableColumnMove

**Type:** Boolean

False to disable column dragging within this grid. ...

False to disable column dragging within this grid. Defaults to: `true`


### enableColumnResize

**Type:** Boolean

False to disable column resizing within this grid. ...

False to disable column resizing within this grid. Defaults to: `true`


### enableLocking

**Type:** Boolean

Configure as true to enable locking support for this grid. ...

Configure as `true` to enable locking support for this grid. Alternatively, locking will also be automatically enabled if any of the columns in the columns configuration contain a locked config option. A locking grid is processed in a special way. The configuration options are cloned and *two* grids are created to be the locked (left) side and the normal (right) side. This Panel becomes merely a container which arranges both in an HBox layout. Plugins may be targeted at either locked, or unlocked grid, or, both, in which case the plugin is cloned and used on both sides. Plugins may also be targeted at the containing locking Panel. This is configured by specifying a `lockableScope` property in your plugin which may have the following values: - `"both"` (the default) - The plugin is added to both grids - `"top"` - The plugin is added to the containing Panel - `"locked"` - The plugin is added to the locked (left) grid - `"normal"` - The plugin is added to the normal (right) grid If `both` is specified, then each copy of the plugin gains a property `lockingPartner` which references its sibling on the other side so that they can synchronize operations is necessary. Features may also be configured with `lockableScope` and may target the locked grid, the normal grid or both grids. Features also get a `lockingPartner` reference injected. Defaults to: `false`


### fbar

**Type:** Object/Object[]

Convenience config used for adding items to the bottom of the panel. ...

Convenience config used for adding items to the bottom of the panel. Short for Footer Bar. is equivalent to The minButtonWidth is used as the default minWidth for each of the buttons in the fbar.


### features

**Type:** Ext.grid.feature.Feature[]/Object[]/Ext.enums.Feature[]

An array of grid Features to be added to this grid. ...

An array of grid Features to be added to this grid. Can also be just a single feature instead of array. Features config behaves much like plugins. A feature can be added by either directly referencing the instance: By using config object with ftype: Or with just a ftype: See Ext.enums.Feature for list of all ftypes.


### fixed

**Type:** Boolean

Configure as true to have this Component fixed at its X, Y coordinates in the browser viewport, immune to scrolling t...

Configure as `true` to have this Component fixed at its `X, Y` coordinates in the browser viewport, immune to scrolling the document. *Only in browsers that support `position:fixed`* *IE6 and IE7, 8 and 9 quirks do not support `position: fixed`* Defaults to: `false`


### floatable

**Type:** Boolean

Important: This config is only effective for collapsible Panels which are direct child items of a border layout. ...

Important: This config is only effective for collapsible Panels which are direct child items of a border layout. true to allow clicking a collapsed Panel's placeholder to display the Panel floated above the layout, false to force the user to fully expand a collapsed region by clicking the expand button to see it again. Defaults to: `true`


### floating

**Type:** Boolean

Specify as true to float the Component outside of the document flow using CSS absolute positioning. ...

Specify as true to float the Component outside of the document flow using CSS absolute positioning. Components such as Windows and Menus are floating by default. Floating Components that are programatically rendered will register themselves with the global ZIndexManager Floating Components as child items of a Container A floating Component may be used as a child item of a Container. This just allows the floating Component to seek a ZIndexManager by examining the ownerCt chain. When configured as floating, Components acquire, at render time, a ZIndexManager which manages a stack of related floating Components. The ZIndexManager brings a single floating Component to the top of its stack when the Component's toFront method is called. The ZIndexManager is found by traversing up the ownerCt chain to find an ancestor which itself is floating. This is so that descendant floating Components of floating *Containers* (Such as a ComboBox dropdown within a Window) can have its zIndex managed relative to any siblings, but always **above** that floating ancestor Container. If no floating ancestor is found, a floating Component registers itself with the default ZIndexManager. Floating components *do not participate in the Container's layout*. Because of this, they are not rendered until you explicitly show them. After rendering, the ownerCt reference is deleted, and the floatParent property is set to the found floating ancestor Container. If no floating ancestor Container was found the floatParent property will not be set. Defaults to: `false` Overrides: Ext.AbstractComponent.floating


### focusOnToFront

**Type:** Boolean

Specifies whether the floated component should be automatically focused when it is brought to the front. ...

Specifies whether the floated component should be automatically focused when it is brought to the front. Defaults to: `true`


### forceFit

**Type:** Boolean

True to force the columns to fit into the available width. ...

True to force the columns to fit into the available width. Headers are first sized according to configuration, whether that be a specific width, or flex. Then they are all proportionally changed in width so that the entire content width is used. For more accurate control, it is more optimal to specify a flex setting on the columns that are to be stretched & explicit widths on columns that are not.


### formBind

**Type:** Boolean

When inside FormPanel, any component configured with formBind: true will be enabled/disabled depending on the validit...

When inside FormPanel, any component configured with `formBind: true` will be enabled/disabled depending on the validity state of the form. See Ext.form.Panel for more information and example. Defaults to: `false`


### frame

**Type:** Boolean

True to apply a frame to the panel. ...

True to apply a frame to the panel. Defaults to: `false` Overrides: Ext.AbstractComponent.frame


### frameHeader

**Type:** Boolean

True to apply a frame to the panel panels header (if 'frame' is true). ...

True to apply a frame to the panel panels header (if 'frame' is true). Defaults to: `true`


### glyph

**Type:** Number/String

A numeric unicode character code to use as the icon for the panel header. ...

A numeric unicode character code to use as the icon for the panel header. The default font-family for glyphs can be set globally using Ext.setGlyphFontFamily(). Alternatively, this config option accepts a string with the charCode and font-family separated by the `@` symbol. For example '65@My Font Family'.


### header

**Type:** Boolean/Object

Pass as false to prevent a Header from being created and shown. ...

Pass as `false` to prevent a Header from being created and shown. Pass as a config object (optionally containing an `xtype`) to custom-configure this Panel's header. See Ext.panel.Header for all the options that may be specified here. A panel header is a Ext.container.Container which contains the Panel's title and tools. You may also configure the Panel's `header` option with its own child items which go *before* the tools By default the panel title is inserted after items configured in this config, but before any tools. To insert the title at any point in the full array, specify the #titlePosition config: new Ext.panel.Panel({ });


### headerOverCls

**Type:** String

Optional CSS class to apply to the header element on mouseover


### headerPosition

**Type:** String

Specify as 'top', 'bottom', 'left' or 'right'. ...

Specify as `'top'`, `'bottom'`, `'left'` or `'right'`. Defaults to: `'top'`


### height

**Type:** Number

The height of this component in pixels.


### hidden

**Type:** Boolean

true to hide the component. ...

`true` to hide the component. Defaults to: `false` Available since: 2.3.0


### hideCollapseTool

**Type:** Boolean

true to hide the expand/collapse toggle button when collapsible == true, false to display it. ...

`true` to hide the expand/collapse toggle button when `collapsible == true`, `false` to display it. Defaults to: `false`


### hideHeaders

**Type:** Boolean

True to hide column headers. ...

True to hide column headers. Defaults to: `false`


### hideMode

**Type:** String

A String which specifies how this Component's encapsulating DOM element will be hidden. ...

A String which specifies how this Component's encapsulating DOM element will be hidden. Values may be: - `'display'` : The Component will be hidden using the `display: none` style. - `'visibility'` : The Component will be hidden using the `visibility: hidden` style. - `'offsets'` : The Component will be hidden by absolutely positioning it out of the visible area of the document. This is useful when a hidden Component must maintain measurable dimensions. Hiding using `display` results in a Component having zero dimensions. Defaults to: `'display'` Available since: 1.1.0


### html

**Type:** String/Object

An HTML fragment, or a DomHelper specification to use as the layout element content. ...

An HTML fragment, or a DomHelper specification to use as the layout element content. The HTML content is added after the component is rendered, so the document will not contain this HTML at the time the render event is fired. This content is inserted into the body *before* any configured contentEl is appended. Defaults to: `''` Available since: 3.4.0


### icon

**Type:** String

Path to image for an icon in the header. ...

Path to image for an icon in the header. Used for displaying an icon to the left of a title.


### iconCls

**Type:** String

CSS class for an icon in the header. ...

CSS class for an icon in the header. Used for displaying an icon to the left of a title.


### id

**Type:** String

The unique id of this component instance. ...

The **unique id of this component instance.** It should not be necessary to use this configuration except for singleton objects in your application. Components created with an `id` may be accessed globally using Ext.getCmp. Instead of using assigned ids, use the itemId config, and ComponentQuery which provides selector-based searching for Sencha Components analogous to DOM querying. The Container class contains shortcut methods to query its descendant Components by selector. Note that this `id` will also be used as the element id for the containing HTML element that is rendered to the page for this component. This allows you to write id-based CSS rules to style the specific instance of this component uniquely, and also to select sub-elements using this component's `id` as the parent. **Note:** To avoid complications imposed by a unique `id` also see `itemId`. **Note:** To access the container of a Component see `ownerCt`. Defaults to an auto-assigned id. Available since: 1.1.0


### itemId

**Type:** String

An itemId can be used as an alternative way to get a reference to a component when no object reference is available. ...

An `itemId` can be used as an alternative way to get a reference to a component when no object reference is available. Instead of using an `id` with Ext.getCmp, use `itemId` with Ext.container.Container.getComponent which will retrieve `itemId`'s or id's. Since `itemId`'s are an index to the container's internal MixedCollection, the `itemId` is scoped locally to the container -- avoiding potential conflicts with Ext.ComponentManager which requires a **unique** `id`. Also see id, `Ext.container.Container.query`, `Ext.container.Container.down` and `Ext.container.Container.child`. **Note**: to access the container of an item see ownerCt. Available since: 3.4.0


### items

**Type:** Object/Object[]

A single item, or an array of child Components to be added to this container Unless configured with a layout, a Cont...

A single item, or an array of child Components to be added to this container Unless configured with a layout, a Container simply renders child Components serially into its encapsulating element and performs no sizing or positioning upon them. Example: Each item may be: - A Component - A Component configuration object If a configuration object is specified, the actual type of Component to be instantiated my be indicated by using the xtype option. Every Component class has its own xtype. If an xtype is not explicitly specified, the defaultType for the Container is used, which by default is usually `panel`. Notes: Ext uses lazy rendering. Child Components will only be rendered should it become necessary. Items are automatically laid out when they are first shown (no sizing is done while hidden), or in response to a doLayout call. Do not specify contentEl or html with `items`. Available since: 2.3.0


### layout

**Type:** Ext.enums.Layout/Object

Important: In order for child items to be correctly sized and positioned, typically a layout manager must be specifie...

**Important**: In order for child items to be correctly sized and positioned, typically a layout manager **must** be specified through the `layout` configuration option. The sizing and positioning of child items is the responsibility of the Container's layout manager which creates and manages the type of layout you have in mind. For example: If the layout configuration is not explicitly specified for a general purpose container (e.g. Container or Panel) the default layout manager will be used which does nothing but render child components sequentially into the Container (no sizing or positioning will be performed in this situation). **layout** may be specified as either as an Object or as a String: Specify as an Object Example usage: - **type** The layout type to be used for this container. If not specified, a default Ext.layout.container.Auto will be created and used. Valid layout `type` values are listed in Ext.enums.Layout. - Layout specific configuration properties Additional layout specific configuration properties may also be specified. For complete details regarding the valid config options for each layout type, see the layout class corresponding to the `type` specified. Specify as a String Example usage: - **layout** The layout `type` to be used for this container (see Ext.enums.Layout for list of valid values). Additional layout specific configuration properties. For complete details regarding the valid config options for each layout type, see the layout class corresponding to the `layout` specified. Configuring the default layout type If a certain Container class has a default layout (For example a Toolbar with a default `Box` layout), then to simply configure the default layout, use an object, but without the `type` property: Defaults to: `'fit'` Available since: 2.3.0 Overrides: Ext.container.AbstractContainer.layout


### lbar

**Type:** Object/Object[]

Convenience config. ...

Convenience config. Short for 'Left Bar' (left-docked, vertical toolbar). is equivalent to


### listeners

**Type:** Object

A config object containing one or more event handlers to be added to this object during initialization. ...

A config object containing one or more event handlers to be added to this object during initialization. This should be a valid listeners config object as specified in the addListener example for attaching multiple handlers at once. **DOM events from Ext JS Components** While *some* Ext JS Component classes export selected DOM events (e.g. "click", "mouseover" etc), this is usually only done when extra value can be added. For example the DataView's **`itemclick`** event passing the node clicked on. To access DOM events directly from a child element of a Component, we need to specify the `element` option to identify the Component property to add a DOM listener to:


### loader

**Type:** Ext.ComponentLoader/Object

A configuration object or an instance of a Ext.ComponentLoader to load remote content for this Component. ...

A configuration object or an instance of a Ext.ComponentLoader to load remote content for this Component.


### lockedGridConfig

**Type:** Object

Any special configuration options for the locked part of the grid


### lockedViewConfig

**Type:** Object

A view configuration to be applied to the locked side of the grid. ...

A view configuration to be applied to the locked side of the grid. Any conflicting configurations between lockedViewConfig and viewConfig will be overwritten by the lockedViewConfig.


### manageHeight

**Type:** Boolean

When true, the dock component layout writes height information to the panel's DOM elements based on its shrink wrap h...

When true, the dock component layout writes height information to the panel's DOM elements based on its shrink wrap height calculation. This ensures that the browser respects the calculated height. When false, the dock component layout will not write heights on the panel or its body element. In some simple layout cases, not writing the heights to the DOM may be desired because this allows the browser to respond to direct DOM manipulations (like animations). Defaults to: `true`


### margin

**Type:** Number/String

Specifies the margin for this component. ...

Specifies the margin for this component. The margin can be a single numeric value to apply to all sides or it can be a CSS style specification for each style, for example: '10 5 3 10' (top, right, bottom, left).


### maxHeight

**Type:** Number

The maximum value in pixels which this Component will set its height to. ...

The maximum value in pixels which this Component will set its height to. **Warning:** This will override any size management applied by layout managers.


### maxWidth

**Type:** Number

The maximum value in pixels which this Component will set its width to. ...

The maximum value in pixels which this Component will set its width to. **Warning:** This will override any size management applied by layout managers.


### minButtonWidth

**Type:** Number

Minimum width of all footer toolbar buttons in pixels. ...

Minimum width of all footer toolbar buttons in pixels. If set, this will be used as the default value for the Ext.button.Button.minWidth config of each Button added to the **footer toolbar** via the fbar or buttons configurations. It will be ignored for buttons that have a minWidth configured some other way, e.g. in their own config object or via the defaults of their parent container. Defaults to: `75`


### minHeight

**Type:** Number

The minimum value in pixels which this Component will set its height to. ...

The minimum value in pixels which this Component will set its height to. **Warning:** This will override any size management applied by layout managers.


### minWidth

**Type:** Number

The minimum value in pixels which this Component will set its width to. ...

The minimum value in pixels which this Component will set its width to. **Warning:** This will override any size management applied by layout managers.


### multiSelect

**Type:** Boolean

True to enable 'MULTI' selection mode on selection model. ...

True to enable 'MULTI' selection mode on selection model. Defaults to: `false` This cfg has been **deprecated** since 4.1.1 Use Ext.selection.Model.mode 'MULTI' instead.


### normalGridConfig

**Type:** Object

Any special configuration options for the normal part of the grid


### normalViewConfig

**Type:** Object

A view configuration to be applied to the normal/unlocked side of the grid. ...

A view configuration to be applied to the normal/unlocked side of the grid. Any conflicting configurations between normalViewConfig and viewConfig will be overwritten by the normalViewConfig.


### overCls

**Type:** String

An optional extra CSS class that will be added to this component's Element when the mouse moves over the Element, and...

An optional extra CSS class that will be added to this component's Element when the mouse moves over the Element, and removed when the mouse moves out. This can be useful for adding customized 'active' or 'hover' styles to the component or any of its children using standard CSS rules. Defaults to: `''` Available since: 2.3.0


### overflowX

**Type:** String

Possible values are: * 'auto' to enable automatic horizontal scrollbar (overflow-x: 'auto'). ...

Possible values are: * `'auto'` to enable automatic horizontal scrollbar (overflow-x: 'auto'). * `'scroll'` to always enable horizontal scrollbar (overflow-x: 'scroll'). The default is overflow-x: 'hidden'. This should not be combined with autoScroll.


### overflowY

**Type:** String

Possible values are: * 'auto' to enable automatic vertical scrollbar (overflow-y: 'auto'). ...

Possible values are: * `'auto'` to enable automatic vertical scrollbar (overflow-y: 'auto'). * `'scroll'` to always enable vertical scrollbar (overflow-y: 'scroll'). The default is overflow-y: 'hidden'. This should not be combined with autoScroll.


### overlapHeader

**Type:** Boolean

True to overlap the header in a panel over the framing of the panel itself. ...

True to overlap the header in a panel over the framing of the panel itself. This is needed when frame:true (and is done automatically for you). Otherwise it is undefined. If you manually add rounded corners to a panel header which does not have frame:true, this will need to be set to true.


### padding

**Type:** Number/String

Specifies the padding for this component. ...

Specifies the padding for this component. The padding can be a single numeric value to apply to all sides or it can be a CSS style specification for each style, for example: '10 5 3 10' (top, right, bottom, left).


### placeholder

**Type:** Ext.Component/Object

Important: This config is only effective for collapsible Panels which are direct child items of a border layout when ...

Important: This config is only effective for collapsible Panels which are direct child items of a border layout when not using the `'header'` collapseMode. **Optional.** A Component (or config object for a Component) to show in place of this Panel when this Panel is collapsed by a border layout. Defaults to a generated Header containing a Tool to re-expand the Panel.


### placeholderCollapseHideMode

**Type:** Number

The mode for hiding collapsed panels when using collapseMode "placeholder".


### plugins

**Type:** Ext.AbstractPlugin[]/Ext.AbstractPlugin/Object[]/Object/Ext.enums.Plugin[]/Ext.enums.Plugin

An array of plugins to be added to this component. ...

An array of plugins to be added to this component. Can also be just a single plugin instead of array. Plugins provide custom functionality for a component. The only requirement for a valid plugin is that it contain an `init` method that accepts a reference of type Ext.Component. When a component is created, if any plugins are available, the component will call the init method on each plugin, passing a reference to itself. Each plugin can then call methods or respond to events on the component as needed to provide its functionality. Plugins can be added to component by either directly referencing the plugin instance: By using config object with ptype: Or with just a ptype: See Ext.enums.Plugin for list of all ptypes. Available since: 2.3.0


### preventHeader

**Type:** Boolean

...

Defaults to: `false` This cfg has been **deprecated** 4.1.0 Use header instead. Prevent a Header from being created and shown.


### rbar

**Type:** Object/Object[]

Convenience config. ...

Convenience config. Short for 'Right Bar' (right-docked, vertical toolbar). is equivalent to


### region

**Type:** "north"/"south"/"east"/"west"/"center"

Defines the region inside border layout. ...

Defines the region inside border layout. Possible values: - north - Positions component at top. - south - Positions component at bottom. - east - Positions component at right. - west - Positions component at left. - center - Positions component at the remaining space. There **must** be a component with `region: "center"` in every border layout.


### renderData

**Type:** Object

The data used by renderTpl in addition to the following property values of the component: id ui uiCls baseCls compo...

The data used by renderTpl in addition to the following property values of the component: - id - ui - uiCls - baseCls - componentCls - frame See renderSelectors and childEls for usage examples.


### renderSelectors

**Type:** Object

An object containing properties specifying DomQuery selectors which identify child elements created by the render pro...

An object containing properties specifying DomQuery selectors which identify child elements created by the render process. After the Component's internal structure is rendered according to the renderTpl, this object is iterated through, and the found Elements are added as properties to the Component using the `renderSelector` property name. For example, a Component which renders a title and description into its element: For a faster, but less flexible, alternative that achieves the same end result (properties for child elements on the Component after render), see childEls and addChildEls.


### renderTo

**Type:** String/HTMLElement/Ext.Element

Specify the id of the element, a DOM element or an existing Element that this component will be rendered into. ...

Specify the `id` of the element, a DOM element or an existing Element that this component will be rendered into. **Notes:** Do *not* use this option if the Component is to be a child item of a Container. It is the responsibility of the Container's layout manager to render and manage its child items. When using this config, a call to `render()` is not required. See also: render. Available since: 2.3.0


### renderTpl

**Type:** Ext.XTemplate/String/String[]

An XTemplate used to create the internal structure inside this Component's encapsulating Element. ...

An XTemplate used to create the internal structure inside this Component's encapsulating Element. You do not normally need to specify this. For the base classes Ext.Component and Ext.container.Container, this defaults to **`null`** which means that they will be initially rendered with no internal structure; they render their Element empty. The more specialized Ext JS and Sencha Touch classes which use a more complex DOM structure, provide their own template definitions. This is intended to allow the developer to create application-specific utility Components with customized internal structure. Upon rendering, any created child elements may be automatically imported into object properties using the renderSelectors and childEls options. Overrides: Ext.container.AbstractContainer.renderTpl


### resizable

**Type:** Boolean/Object

Specify as true to apply a Resizer to this Component after rendering. ...

Specify as `true` to apply a Resizer to this Component after rendering. May also be specified as a config object to be passed to the constructor of Resizer to override any defaults. By default the Component passes its minimum and maximum size, and uses `Ext.resizer.Resizer.dynamic: false`


### resizeHandles

**Type:** String

A valid Ext.resizer.Resizer handles config string. ...

A valid Ext.resizer.Resizer handles config string. Only applies when resizable = true. Defaults to: `'all'`


### rowLines

**Type:** Boolean

Adds row line styling ...

Adds row line styling Defaults to: `true`


### rtl

**Type:** Boolean

True to layout this component and its descendants in "rtl" (right-to-left) mode. ...

True to layout this component and its descendants in "rtl" (right-to-left) mode. Can be explicitly set to false to override a true value inherited from an ancestor. **Defined in override Ext.rtl.AbstractComponent.**


### saveDelay

**Type:** Number

A buffer to be applied if many state events are fired within a short period. ...

A buffer to be applied if many state events are fired within a short period. Defaults to: `100`


### scroll

**Type:** String/Boolean

Scrollers configuration. ...

Scrollers configuration. Valid values are 'both', 'horizontal' or 'vertical'. True implies 'both'. False implies 'none'. Defaults to: `true`


### scrollDelta

**Type:** Number

Number of pixels to scroll when scrolling the locked section with mousewheel. ...

Number of pixels to scroll when scrolling the locked section with mousewheel. Defaults to: `40`


### sealedColumns

**Type:** Boolean

True to constrain column dragging so that a column cannot be dragged in or out of it's current group. ...

True to constrain column dragging so that a column cannot be dragged in or out of it's current group. Only relevant while enableColumnMove is enabled. Defaults to: `false`


### selModel

**Type:** Ext.selection.Model/Object

A selection model instance or config object. ...

A selection model instance or config object. In latter case the selType config option determines to which type of selection model this config is applied.


### selType

**Type:** String

An xtype of selection model to use. ...

An xtype of selection model to use. Defaults to 'rowmodel'. This is used to create selection model if just a config object or nothing at all given in selModel config. Defaults to: `'rowmodel'`


### shadow

**Type:** String/Boolean

Specifies whether the floating component should be given a shadow. ...

Specifies whether the floating component should be given a shadow. Set to true to automatically create an Ext.Shadow, or a string indicating the shadow's display Ext.Shadow.mode. Set to false to disable the shadow. Defaults to: `'sides'`


### shadowOffset

**Type:** Number

Number of pixels to offset the shadow.


### shrinkWrap

**Type:** Boolean/Number

If this property is a number, it is interpreted as follows: 0: Neither width nor height depend on content. ...

If this property is a number, it is interpreted as follows: - 0: Neither width nor height depend on content. This is equivalent to `false`. - 1: Width depends on content (shrink wraps), but height does not. - 2: Height depends on content (shrink wraps), but width does not. The default. - 3: Both width and height depend on content (shrink wrap). This is equivalent to `true`. In CSS terms, shrink-wrap width is analogous to an inline-block element as opposed to a block-level element. Some container layouts always shrink-wrap their children, effectively ignoring this property (e.g., Ext.layout.container.HBox, Ext.layout.container.VBox, Ext.layout.component.Dock). Defaults to: `2`


### shrinkWrapDock

**Type:** Boolean/Number

Allows for this panel to include the dockedItems when trying to determine the overall size of the panel. ...

Allows for this panel to include the dockedItems when trying to determine the overall size of the panel. This option is only applicable when this panel is also shrink wrapping in the same dimensions. See Ext.AbstractComponent.shrinkWrap for an explanation of the configuration options. Defaults to: `false`


### simpleDrag

**Type:** Boolean

When draggable is true, Specify this as true to cause the draggable config to work the same as it does in Window. ...

When draggable is `true`, Specify this as `true` to cause the `draggable` config to work the same as it does in Window. This Panel just becomes movable. No DragDrop instances receive any notifications. For example: Defaults to: `false`


### simpleSelect

**Type:** Boolean

True to enable 'SIMPLE' selection mode on selection model. ...

True to enable 'SIMPLE' selection mode on selection model. Defaults to: `false` This cfg has been **deprecated** since 4.1.1 Use Ext.selection.Model.mode 'SIMPLE' instead.


### sortableColumns

**Type:** Boolean

False to disable column sorting via clicking the header and via the Sorting menu items. ...

False to disable column sorting via clicking the header and via the Sorting menu items. Defaults to: `true`


### stateEvents

**Type:** String[]

An array of events that, when fired, should trigger this object to save its state. ...

An array of events that, when fired, should trigger this object to save its state. Defaults to none. `stateEvents` may be any type of event supported by this object, including browser or custom events (e.g., ['click', 'customerchange']). See `stateful` for an explanation of saving and restoring object state.


### stateId

**Type:** String

The unique id for this object to use for state management purposes. ...

The unique id for this object to use for state management purposes. See stateful for an explanation of saving and restoring state.


### stateful

**Type:** Boolean

A flag which causes the object to attempt to restore the state of internal properties from a saved state on startup. ...

A flag which causes the object to attempt to restore the state of internal properties from a saved state on startup. The object must have a stateId for state to be managed. Auto-generated ids are not guaranteed to be stable across page loads and cannot be relied upon to save and restore the same state for a object. For state saving to work, the state manager's provider must have been set to an implementation of Ext.state.Provider which overrides the set and get methods to save and recall name/value pairs. A built-in implementation, Ext.state.CookieProvider is available. To set the state provider for the current page: Ext.state.Manager.setProvider(new Ext.state.CookieProvider({ })); A stateful object attempts to save state when one of the events listed in the stateEvents configuration fires. To save state, a stateful object first serializes its state by calling *getState*. The Component base class implements getState to save its width and height within the state only if they were initially configured, and have changed from the configured value. The Panel class saves its collapsed state in addition to that. The Grid class saves its column state in addition to its superclass state. If there is more application state to be save, the developer must provide an implementation which first calls the superclass method to inherit the above behaviour, and then injects new properties into the returned object. The value yielded by getState is passed to Ext.state.Manager.set which uses the configured Ext.state.Provider to save the object keyed by the stateId. During construction, a stateful object attempts to *restore* its state by calling Ext.state.Manager.get passing the stateId The resulting object is passed to applyState*. The default implementation of applyState simply copies properties into the object, but a developer may override this to support restoration of more complex application state. You can perform extra processing on state save and restore by attaching handlers to the beforestaterestore, staterestore, beforestatesave and statesave events. Defaults to: `false`


### style

**Type:** String/Object

A custom style specification to be applied to this component's Element. ...

A custom style specification to be applied to this component's Element. Should be a valid argument to Ext.Element.applyStyles. Available since: 1.1.0


### subGridXType

**Type:** String

The xtype of the subgrid to specify. ...

The xtype of the subgrid to specify. If this is not specified lockable will determine the subgrid xtype to create by the following rule. Use the superclasses xtype if the superclass is NOT tablepanel, otherwise use the xtype itself.


### suspendLayout

**Type:** Boolean

If true, suspend calls to doLayout. ...

If true, suspend calls to doLayout. Useful when batching multiple adds to a container and not passing them as multiple arguments or an array. Defaults to: `false`


### syncRowHeight

**Type:** Boolean

Synchronize rowHeight between the normal and locked grid view. ...

Synchronize rowHeight between the normal and locked grid view. This is turned on by default. If your grid is guaranteed to have rows of all the same height, you should set this to false to optimize performance. Defaults to: `true`


### tbar

**Type:** Object/Object[]

Convenience config. ...

Convenience config. Short for 'Top Bar'. is equivalent to


### title

**Type:** String

The title text to be used to display in the panel header. ...

The title text to be used to display in the panel header. When a `title` is specified the Ext.panel.Header will automatically be created and displayed unless header is set to `false`. Defaults to: `''`


### titleAlign

**Type:** String

The alignment of the title text within the available space between the icon and the tools. ...

The alignment of the title text within the available space between the icon and the tools. May be `"left"`, `"right"` or `"center"`. Defaults to the browser's natural behavior depending on the css direction property - `"left"` when direction is ltr and `"right"` when direction is rtl (see Ext.AbstractComponent.rtl).


### titleCollapse

**Type:** Boolean

true to allow expanding and collapsing the panel (when collapsible = true) by clicking anywhere in the header bar, fa...

`true` to allow expanding and collapsing the panel (when `collapsible = true`) by clicking anywhere in the header bar, `false`) to allow it only by clicking to tool button). When a panel is used in a border layout, the floatable option can influence the behavior of collapsing.


### toFrontOnShow

**Type:** Boolean

True to automatically call toFront when the show method is called on an already visible, floating component. ...

True to automatically call toFront when the show method is called on an already visible, floating component. Defaults to: `true`


### tools

**Type:** Object[]/Ext.panel.Tool[]

An array of Ext.panel.Tool configs/instances to be added to the header tool area. ...

An array of Ext.panel.Tool configs/instances to be added to the header tool area. The tools are stored as child components of the header container. They can be accessed using down and {query}, as well as the other component methods. The toggle tool is automatically created if collapsible is set to true. Note that, apart from the toggle tool which is provided when a panel is collapsible, these tools only provide the visual button. Any required functionality must be provided by adding handlers that implement the necessary behavior. Example usage: The difference between `handler` and `callback` is the signature. For details on the distinction, see Ext.panel.Tool.


### tpl

**Type:** Ext.XTemplate/Ext.Template/String/String[]

An Ext.Template, Ext.XTemplate or an array of strings to form an Ext.XTemplate. ...

An Ext.Template, Ext.XTemplate or an array of strings to form an Ext.XTemplate. Used in conjunction with the `data` and `tplWriteMode` configurations. Available since: 3.4.0


### tplWriteMode

**Type:** String

The Ext.(X)Template method to use when updating the content area of the Component. ...

The Ext.(X)Template method to use when updating the content area of the Component. See `Ext.XTemplate.overwrite` for information on default mode. Defaults to: `'overwrite'` Available since: 3.4.0


### ui

**Type:** String

A UI style for a component. ...

A UI style for a component. Defaults to: `'default'`


### uiCls

**Type:** String[]

An array of of classNames which are currently applied to this component. ...

An array of of `classNames` which are currently applied to this component. Defaults to: `[]`


### verticalScroller

**Type:** Object

A config object to be used when configuring the scroll monitor to control refreshing of data in an "infinite grid". ...

A config object to be used when configuring the scroll monitor to control refreshing of data in an "infinite grid". Configurations of this object allow fine tuning of data caching which can improve performance and usability of the infinite grid.


### view

**Type:** Ext.view.Table

The Ext.view.Table used by the grid. ...

The Ext.view.Table used by the grid. Use viewConfig to just supply some config options to view (instead of creating an entire View instance).


### viewConfig

**Type:** Object

A config object that will be applied to the grid's UI view. ...

A config object that will be applied to the grid's UI view. Any of the config options available for Ext.view.Table can be specified here. This option is ignored if view is specified.


### viewType

**Type:** String

An xtype of view to use. ...

An xtype of view to use. This is automatically set to 'gridview' by Grid and to 'treeview' by Tree.


### width

**Type:** Number

The width of this component in pixels.


### xtype

**Type:** Ext.enums.Widget

This property provides a shorter alternative to creating objects than using a full class name. ...

This property provides a shorter alternative to creating objects than using a full class name. Using `xtype` is the most common way to define component instances, especially in a container. For example, the items in a form containing text fields could be created explicitly like so: But by using `xtype`, the above becomes: When the `xtype` is common to many items, Ext.container.AbstractContainer.defaultType is another way to specify the `xtype` for all items that don't have an explicit `xtype`: Each member of the `items` array is now just a "configuration object". These objects are used to create and configure component instances. A configuration object can be manually used to instantiate a component using Ext.widget: This conversion of configuration objects into instantiated components is done when a container is created as part of its {Ext.container.AbstractContainer.initComponent} process. As part of the same process, the `items` array is converted from its raw array form into a Ext.util.MixedCollection instance. You can define your own `xtype` on a custom component by specifying the `xtype` property in Ext.define. For example: Care should be taken when naming an `xtype` in a custom component because there is a single, shared scope for all xtypes. Third part components should consider using a prefix to avoid collisions. See Ext.enums.Widget for list of all available xtypes. Available since: 2.3.0


### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### _alignRe

**Type:** RegExp

...

Defaults to: `/^([a-z]+)-([a-z]+)(\?)?$/`


### _isLayoutRoot

**Type:** Boolean

Setting this property to true causes the isLayoutRoot method to return true and stop the search for the top-most comp...

Setting this property to `true` causes the isLayoutRoot method to return `true` and stop the search for the top-most component for a layout. Defaults to: `false`


### _positionTopLeft

**Type:** Array

...

Defaults to: `['position', 'top', 'left']`


### allowDomMove

**Type:** Boolean

...

Defaults to: `true`


### autoGenId

**Type:** Boolean

true indicates an id was auto-generated rather than provided by configuration. ...

`true` indicates an `id` was auto-generated rather than provided by configuration. Defaults to: `false`


### body

**Type:** Ext.dom.Element

The Panel's body Element which may be used to contain HTML content. ...

The Panel's body Element which may be used to contain HTML content. The content may be specified in the html config, or it may be loaded using the loader config. Read-only. If this is used to load visible HTML elements in either way, then the Panel may not be used as a Layout for hosting nested Panels. If this Panel is intended to be used as the host of a Layout (See layout then the body Element must not be loaded or changed - it is under the control of the Panel's Layout.


### bodyPosProps

**Type:** Object

...

Defaults to: `{x: 'x', y: 'y'}`


### borderBoxCls

**Type:** String

private ...

private Defaults to: `Ext.baseCSSPrefix + 'border-box'`


### bothCfgCopy

**Type:** Array

Required for the Lockable Mixin. ...

Required for the Lockable Mixin. These are the configurations which will be copied to the normal and locked sub tablepanels Defaults to: `['invalidateScrollerOnRefresh', 'hideHeaders', 'enableColumnHide', 'enableColumnMove', 'enableColumnResize', 'sortableColumns', 'columnLines', 'rowLines']`


### bubbleEvents

**Type:** Array

...

Defaults to: `[]`


### childEls

**Type:** Array

...

Defaults to: `['body']` Overrides: Ext.util.ElementContainer.childEls


### componentLayoutCounter

**Type:** Number

The number of component layout calls made on this object. ...

The number of component layout calls made on this object. Defaults to: `0`


### configMap

**Type:** Object

...

Defaults to: `{}`


### contentPaddingProperty

**Type:** String

The name of the padding property that is used by the layout to manage padding. ...

The name of the padding property that is used by the layout to manage padding. See managePadding Defaults to: `'bodyPadding'` Overrides: Ext.AbstractComponent.contentPaddingProperty


### convertPositionSpec

**Type:** Object

By default this method does nothing but return the position spec passed to it. ...

By default this method does nothing but return the position spec passed to it. In rtl mode it is overridden to convert "l" to "r" and vice versa when required.


### dd

**Type:** Ext.dd.DragSource/Ext.util.ComponentDragger

Only present if this Panel has been configured with draggable true. ...

Only present if this Panel has been configured with draggable `true`. Simple dragging If this Panel is configured simpleDrag `true` (the default is `false`), this property will reference an instance of Ext.util.ComponentDragger (A subclass of DragTracker) which handles moving the Panel's DOM Element, and constraining according to the constrain and constrainHeader . This object fires various events during its lifecycle and during a drag operation. Complex dragging interacting with other DragDrop instances By default, this property in a draggable Panel will contain an instance of Ext.dd.DragSource which handles dragging the Panel. The developer must provide implementations of the abstract methods of Ext.dd.DragSource in order to supply behaviour for each stage of the drag/drop process. See draggable.


### defaultComponentLayoutType

**Type:** String

...

Defaults to: `'autocomponent'`


### deferLayouts

**Type:** Boolean

...

Defaults to: `false`


### dockOrder

**Type:** Object

Values to decide which side of the body element docked items must go This overides any weight. ...

Values to decide which side of the body element docked items must go This overides any weight. A left/top will *always* sort before a right/bottom regardless of any weight value. Weights sort at either side of the "body" dividing point.


### draggable

**Type:** Boolean

Indicates whether or not the component can be dragged. ...

Indicates whether or not the component can be dragged. Defaults to: `false`


### emptyArray

**Type:** Array

...

Defaults to: `[]`


### emptyCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid-empty'`


### eventsSuspended

**Type:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called. Defaults to: `0`


### extraBaseCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid'`


### extraBodyCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid-body'`


### floatParent

**Type:** Ext.Container

Only present for floating Components which were inserted as child items of Containers. ...

**Only present for floating Components which were inserted as child items of Containers.** There are other similar relationships such as the button which activates a menu, or the menu item which activated a submenu, or the column header which activated the column menu. These differences are abstracted away by the up method. Floating Components that are programatically rendered will not have a `floatParent` property. See floating and zIndexManager


### frameCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'frame'`


### frameElNames

**Type:** Array

...

Defaults to: `['TL', 'TC', 'TR', 'ML', 'MC', 'MR', 'BL', 'BC', 'BR']`


### frameElementsArray

**Type:** Array

...

Defaults to: `['tl', 'tc', 'tr', 'ml', 'mc', 'mr', 'bl', 'bc', 'br']`


### frameIdRegex

**Type:** RegExp

...

Defaults to: `/[\-]frame\d+[TMB][LCR]$/`


### frameInfoCache

**Type:** Object

Cache the frame information object so as not to cause style recalculations ...

Cache the frame information object so as not to cause style recalculations Defaults to: `{}`


### frameSize

**Type:** Object

Indicates the width of any framing elements which were added within the encapsulating element to provide graphical, r...

Indicates the width of any framing elements which were added within the encapsulating element to provide graphical, rounded borders. See the frame config. This property is `null` if the component is not framed. This is an object containing the frame width in pixels for all four sides of the Component containing the following properties: top : Number (optional)The width of the top framing element in pixels. Defaults to: `0`


### frameTableTpl

**Type:** Object


### frameTpl

**Type:** Array

...

Defaults to: `['{%this.renderDockedItems(out,values,0);%}', '<tpl if="top">', '<tpl if="left"><div id="{fgid}TL" class="{frameCls}-tl {baseCls}-tl {baseCls}-{ui}-tl<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-tl</tpl>{frameElCls}" role="presentation"></tpl>', '<tpl if="right"><div id="{fgid}TR" class="{frameCls}-tr {baseCls}-tr {baseCls}-{ui}-tr<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-tr</tpl>{frameElCls}" role="presentation"></tpl>', '<div id="{fgid}TC" class="{frameCls}-tc {baseCls}-tc {baseCls}-{ui}-tc<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-tc</tpl>{frameElCls}" role="presentation"></div>', '<tpl if="right"></div></tpl>', '<tpl if="left"></div></tpl>', '</tpl>', '<tpl if="left"><div id="{fgid}ML" class="{frameCls}-ml {baseCls}-ml {baseCls}-{ui}-ml<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-ml</tpl>{frameElCls}" role="presentation"></tpl>', '<tpl if="right"><div id="{fgid}MR" class="{frameCls}-mr {baseCls}-mr {baseCls}-{ui}-mr<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-mr</tpl>{frameElCls}" role="presentation"></tpl>', '<div id="{fgid}MC" class="{frameCls}-mc {baseCls}-mc {baseCls}-{ui}-mc<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-mc</tpl>{frameElCls}" role="presentation">', '{%this.applyRenderTpl(out, values)%}', '</div>', '<tpl if="right"></div></tpl>', '<tpl if="left"></div></tpl>', '<tpl if="bottom">', '<tpl if="left"><div id="{fgid}BL" class="{frameCls}-bl {baseCls}-bl {baseCls}-{ui}-bl<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-bl</tpl>{frameElCls}" role="presentation"></tpl>', '<tpl if="right"><div id="{fgid}BR" class="{frameCls}-br {baseCls}-br {baseCls}-{ui}-br<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-br</tpl>{frameElCls}" role="presentation"></tpl>', '<div id="{fgid}BC" class="{frameCls}-bc {baseCls}-bc {baseCls}-{ui}-bc<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-bc</tpl>{frameElCls}" role="presentation"></div>', '<tpl if="right"></div></tpl>', '<tpl if="left"></div></tpl>', '</tpl>', '{%this.renderDockedItems(out,values,1);%}']`


### hasListeners

**Type:** Object

This object holds a key for any event that has a listener. ...

This object holds a key for any event that has a listener. The listener may be set directly on the instance, or on its class or a super class (via observe) or on the MVC EventBus. The values of this object are truthy (a non-zero number) and falsy (0 or undefined). They do not represent an exact count of listeners. The value for an event is truthy if the event must be fired and is falsy if there is no need to fire the event. The intended use of this property is to avoid the expense of fireEvent calls when there are no listeners. This can be particularly helpful when one would otherwise have to call fireEvent hundreds or thousands of times. It is used like this:


### hasView

**Type:** Boolean

True to indicate that a view has been injected into the panel. ...

True to indicate that a view has been injected into the panel. Defaults to: `false`


### hiddenHeaderCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid-header-hidden'`


### hiddenHeaderCtCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid-header-ct-hidden'`


### horizontalDocks

**Type:** Number

Number of dock 'left' and 'right' items. ...

Number of dock 'left' and 'right' items. Defaults to: `0`


### horizontalPosProp

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


### isAnimate

**Type:** Boolean

...

Defaults to: `true`


### isComponent

**Type:** Boolean

true in this class to identify an object as an instantiated Component, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Component, or subclass thereof. Defaults to: `true`


### isContainer

**Type:** Boolean

true in this class to identify an object as an instantiated Container, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Container, or subclass thereof. Defaults to: `true`


### isDockingContainer

**Type:** Boolean

End Definitions ...

End Definitions Defaults to: `true`


### isInstance

**Type:** Boolean

...

Defaults to: `true`


### isObservable

**Type:** Boolean

true in this class to identify an object as an instantiated Observable, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Observable, or subclass thereof. Defaults to: `true`


### isPanel

**Type:** Boolean

true in this class to identify an object as an instantiated Panel, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Panel, or subclass thereof. Defaults to: `true`


### isQueryable

**Type:** Boolean

...

Defaults to: `true`


### items

**Type:** Ext.util.AbstractMixedCollection

The MixedCollection containing all the child items of this container.

The MixedCollection containing all the child items of this container. Available since: 2.3.0


### layoutCounter

**Type:** Number

The number of container layout calls made on this object. ...

The number of container layout calls made on this object. Defaults to: `0`


### layoutSuspendCount

**Type:** Number

...

Defaults to: `0`


### lockText

**Type:** String

...

Defaults to: `'Lock'`


### lockedCfgCopy

**Type:** Array

...

Defaults to: `[]`


### maskOnDisable

**Type:** Boolean

This is an internal flag that you use when creating custom components. ...

This is an internal flag that you use when creating custom components. By default this is set to `true` which means that every component gets a mask when it's disabled. Components like FieldContainer, FieldSet, Field, Button, Tab override this property to `false` since they want to implement custom disable logic. Defaults to: `true`


### noRowLinesCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid-no-row-lines'`


### normalCfgCopy

**Type:** Array

...

Defaults to: `['verticalScroller', 'verticalScrollDock', 'verticalScrollerType', 'scroll']`


### offsetsCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'hide-offsets'`


### optimizedColumnMove

**Type:** Boolean

If you are writing a grid plugin or a {Ext.grid.feature.Feature Feature} which creates a column-based structure which...

If you are writing a grid plugin or a {Ext.grid.feature.Feature Feature} which creates a column-based structure which needs a view refresh when columns are moved, then set this property in the grid. An example is the built in Summary Feature. This creates summary rows, and the summary columns must be in the same order as the data columns. This plugin sets the `optimizedColumnMove` to `false.


### ownerCt

**Type:** Ext.Container

This Component's owner Container (is set automatically when this Component is added to a Container). ...

This Component's owner Container (is set automatically when this Component is added to a Container). *Important.* This is not a universal upwards navigation pointer. It indicates the Container which owns and manages this Component if any. There are other similar relationships such as the button which activates a menu, or the menu item which activated a submenu, or the column header which activated the column menu. These differences are abstracted away by the up method. **Note**: to access items within the Container see itemId. Available since: 2.3.0


### rendered

**Type:** Boolean

Indicates whether or not the component has been rendered. ...

Indicates whether or not the component has been rendered. Defaults to: `false` Available since: 1.1.0


### resizeMarkerCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid-resize-marker'`


### rowLinesCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid-with-row-lines'`


### scrollFlags

**Type:** Object

An object property which provides unified information as to which dimensions are scrollable based upon the autoScroll...

An object property which provides unified information as to which dimensions are scrollable based upon the autoScroll, overflowX and overflowY settings (And for *views* of trees and grids, the owning panel's scroll setting). Note that if you set overflow styles using the style config or bodyStyle config, this object does not include that information; it is best to use autoScroll, overflowX and overflowY if you need to access these flags. This object has the following properties: x : Boolean`true` if this Component is scrollable horizontally - style setting may be `'auto'` or `'scroll'`.


### scrollerOwner

**Type:** Boolean

private property used to determine where to go down to find views this is here to support locking. ...

private property used to determine where to go down to find views this is here to support locking. Defaults to: `true`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### unlockText

**Type:** String

i8n text ...

i8n text Defaults to: `'Unlock'`


### weight

**Type:** Number

...

Defaults to: `0`


### zIndexManager

**Type:** Ext.ZIndexManager

Only present for floating Components after they have been rendered. ...

Only present for floating Components after they have been rendered. A reference to the ZIndexManager which is managing this Component's z-index. The ZIndexManager maintains a stack of floating Component z-indices, and also provides a single modal mask which is insert just beneath the topmost visible modal floating Component. Floating Components may be brought to the front or sent to the back of the z-index stack. This defaults to the global ZIndexManager for floating Components that are programatically rendered. For floating Components which are added to a Container, the ZIndexManager is acquired from the first ancestor Container found which is floating. If no floating ancestor is found, the global ZIndexManager is used. See floating and zIndexParent


### zIndexParent

**Type:** Ext.Container

Only present for floating Components which were inserted as child items of Containers, and which have a floating Cont...

Only present for floating Components which were inserted as child items of Containers, and which have a floating Container in their containment ancestry. For floating Components which are child items of a Container, the zIndexParent will be a floating ancestor Container which is responsible for the base z-index value of all its floating descendants. It provides a ZIndexManager which provides z-indexing services for all its descendant floating Components. Floating Components that are programatically rendered will not have a `zIndexParent` property. For example, the dropdown BoundList of a ComboBox which is in a Window will have the Window as its `zIndexParent`, and will always show above that Window, wherever the Window is placed in the z-index stack. See floating and zIndexManager


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.panel.Table

Creates new Component. ...

Creates new Component.

**Parameters:** - config : Ext.Element/String/ObjectThe configuration options may be specified as either: **an element** : it is set as the internal element and its id used as the component id - **a string** : it is assumed to be the id of an existing element and is used as the component id - **anything else** : it is assumed to be a standard config object and is applied to the component


### add

Adds Component(s) to this Container. ...

Adds Component(s) to this Container. Description: - Fires the beforeadd event before adding. - The Container's default config values will be applied accordingly (see `defaults` for details). - Fires the `add` event after the component has been added. Notes: If the Container is **already rendered** when `add` is called, it will render the newly added Component into its content area. **If** the Container was configured with a size-managing layout manager, the Container will recalculate its internal layout at this time too. Note that the default layout manager simply renders child Components sequentially into the content area and thereafter performs no sizing. If adding multiple new child Components, pass them as an array to the `add` method, so that only one layout recalculation is performed. To inject components between existing ones, use the insert method. Warning: Components directly managed by the BorderLayout layout manager may not be removed or added. See the Notes for BorderLayout for more details. Available since: 2.3.0

**Parameters:** component : Ext.Component[]|Object[]/Ext.Component.../Object...Either one or more Components to add or an Array of Components to add. See `items` for additional information.


### addBodyCls

Adds a CSS class to the body element. ...

Adds a CSS class to the body element. If not rendered, the class will be added when the panel is rendered.

**Parameters:** cls : StringThe class to add


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### addClass

Adds a CSS class to the top level element representing this component. ...

Adds a CSS class to the top level element representing this component. This method has been **deprecated** since 4.1 Use addCls instead.


### addCls

Adds a CSS class to the top level element representing this component. ...

Adds a CSS class to the top level element representing this component.

**Parameters:** cls : String/String[]The CSS class name to add.


### addClsWithUI

Adds a cls to the uiCls array, which will also call addUIClsToElement and adds to all elements of this component. ...

Adds a `cls` to the `uiCls` array, which will also call addUIClsToElement and adds to all elements of this component.

**Parameters:** classes : String/String[]A string or an array of strings to add to the `uiCls`.


### addDocked

Adds docked item(s) to the container. ...

Adds docked item(s) to the container.

**Parameters:** component : Object/Object[]The Component or array of components to add. The components must include a 'dock' parameter on each component to indicate where it should be docked ('top', 'right', 'bottom', 'left').


### addEvents

Adds the specified events to the list of events which this Observable may fire. ...

Adds the specified events to the list of events which this Observable may fire.

**Parameters:** eventNames : Object/String...Either an object with event names as properties with a value of `true`. For example: Or any number of event names as separate parameters. For example:


### addFocusListener

Sets up the focus listener on this Component's focusEl if it has one. ...

Sets up the focus listener on this Component's focusEl if it has one. Form Components which must implicitly participate in tabbing order usually have a naturally focusable element as their focusEl, and it is the DOM event of that receiving focus which drives the Component's `onFocus` handling, and the DOM event of it being blurred which drives the `onBlur` handling. If the focusEl is **not** naturally focusable, then the listeners are only added if the FocusManager is enabled.


### addListener

Appends an event handler to this object. ...

Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### addManagedListener

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destr...

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### addOverCls

...


### addPlugin

Adds a plugin. ...

Adds a plugin. May be called at any time in the component's lifecycle.

**Parameters:** plugin : Object


### addPropertyToState

Save a property to the given state object if it is not its default or configured value. ...

Save a property to the given state object if it is not its default or configured value.

**Parameters:** state : ObjectThe state object.


### addStateEvents

Add events that will trigger the state to be saved. ...

Add events that will trigger the state to be saved. If the first argument is an array, each element of that array is the name of a state event. Otherwise, each argument passed to this method is the name of a state event.

**Parameters:** events : String/String[]The event name or an array of event names.


### addTool

Add tools to this panel ...

Add tools to this panel

**Parameters:** tools : Object[]/Ext.panel.Tool[]The tools to add


### addTools

Template method to be implemented in subclasses to add their tools after the collapsible tool. ...

Template method to be implemented in subclasses to add their tools after the collapsible tool. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### addUIClsToElement

inherit docs Method which adds a specified UI + uiCls to the components element. ...

inherit docs Method which adds a specified UI + `uiCls` to the components element. Can be overridden to remove the UI from more than just the components element.

**Parameters:** ui : StringThe UI to remove from the element.


### addUIToElement

inherit docs Method which adds a specified UI to the components element. ...

inherit docs Method which adds a specified UI to the components element. Overrides: Ext.AbstractComponent.addUIToElement


### adjustForConstraints

private ==> used outside of core TODO: currently only used by ToolTip. ...

private ==> used outside of core TODO: currently only used by ToolTip. does this method belong here?

**Parameters:** xy : Object


### adjustPosition

...

**Parameters:** x : Object


### afterCollapse

Invoked after the Panel is Collapsed. ...

Invoked after the Panel is Collapsed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterComponentLayout

Called by the layout system after the Component has been laid out. ...

Called by the layout system after the Component has been laid out. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterExpand

Invoked after the Panel is Expanded. ...

Invoked after the Panel is Expanded. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterFirstLayout

...

**Parameters:** width : Object


### afterHide

Invoked after the Component has been hidden. ...

Invoked after the Component has been hidden. Gets passed the same `callback` and `scope` parameters that onHide received. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterLayout

Invoked after the Container has laid out (and rendered if necessary) its child Components. ...

Invoked after the Container has laid out (and rendered if necessary) its child Components. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterLockedViewLayout

Due to automatic component border setting using inline style, to create the scrollbar-replacing bottom border, we hav...

Due to automatic component border setting using inline style, to create the scrollbar-replacing bottom border, we have to postprocess the locked view *after* render. If there are visible normal columns, we do need the fat bottom border.


### afterRender

Allows addition of behavior after rendering is complete. ...

Allows addition of behavior after rendering is complete. At this stage the Component’s Element will have been styled according to the configuration, will have had any configured CSS class names added, and will be in the configured visibility and the configured enable state. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterSetPosition

Template method called after a Component has been positioned. ...

Template method called after a Component has been positioned. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterShow

Invoked after the Component is shown (after onShow is called). ...

Invoked after the Component is shown (after onShow is called). Gets passed the same parameters as show. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### alignTo

Aligns the element with another element relative to the specified anchor points. ...

Aligns the element with another element relative to the specified anchor points. If the other element is the document it aligns it to the viewport. The position parameter is optional, and can be specified in any one of the following formats: - **Blank**: Defaults to aligning the element's top-left corner to the target's bottom-left corner ("tl-bl"). - **One anchor (deprecated)**: The passed anchor position is used as the target element's anchor point. The element being aligned will position its top-left corner (tl) to that point. This method has been deprecated in favor of the newer two anchor syntax below. - **Two anchors**: If two values from the table below are passed separated by a dash, the first value is used as the element's anchor point, and the second value is used as the target's anchor point. In addition to the anchor points, the position parameter also supports the "?" character. If "?" is passed at the end of the position string, the element will attempt to align as specified, but the position will be adjusted to constrain to the viewport if necessary. Note that the element being aligned might be swapped to align to a different position than that specified in order to enforce the viewport constraints. Following are all of the supported anchor positions: Example Usage:

**Parameters:** element : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or id of the element to align to.


### anchorTo

Anchors an element to another element and realigns it when the window is resized. ...

Anchors an element to another element and realigns it when the window is resized.

**Parameters:** element : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or id of the element to align to.


### anim

process the passed fx configuration. ...

- process the passed fx configuration.

**Parameters:** config : Object


### animate

Performs custom animation on this object. ...

Performs custom animation on this object. This method is applicable to both the Component class and the Sprite class. It performs animated transitions of certain properties of this object over a specified timeline. Animating a Component When animating a Component, the following properties may be specified in `from`, `to`, and `keyframe` objects: - `x` - The Component's page X position in pixels. - `y` - The Component's page Y position in pixels - `left` - The Component's `left` value in pixels. - `top` - The Component's `top` value in pixels. - `width` - The Component's `width` value in pixels. - `height` - The Component's `height` value in pixels. - `dynamic` - Specify as true to update the Component's layout (if it is a Container) at every frame of the animation. *Use sparingly as laying out on every intermediate size change is an expensive operation.* For example, to animate a Window to a new size, ensuring that its internal layout and any shadow is correct: For performance reasons, by default, the internal layout is only updated when the Window reaches its final `"to"` size. If dynamic updating of the Window's child Components is required, then configure the animation with `dynamic: true` and the two child items will maintain their proportions during the animation.

**Parameters:** config : ObjectConfiguration for Ext.fx.Anim. Note that the to config is required.


### applyChildEls

Sets references to elements inside the component. ...

Sets references to elements inside the component.

**Parameters:** el : Object


### applyDefaults

...

**Parameters:** config : Object


### applyRenderSelectors

Sets references to elements inside the component. ...

Sets references to elements inside the component. This applies renderSelectors as well as childEls.


### applyState

Applies the state to the object. ...

Applies the state to the object. This should be overridden in subclasses to do more complex state operations. By default it applies the state properties onto the current object.

**Parameters:** state : ObjectThe state


### applyTargetCls

...

**Parameters:** targetCls : Object


### beforeBlur

Template method to do any pre-blur processing. ...

Template method to do any pre-blur processing.

**Parameters:** e : Ext.EventObjectThe event object


### beforeComponentLayout

Occurs before componentLayout is run. ...

Occurs before `componentLayout` is run. Returning `false` from this method will prevent the `componentLayout` from being executed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeDestroy

Invoked before the Component is destroyed. ...

Invoked before the Component is destroyed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeFocus

Template method to do any pre-focus processing. ...

Template method to do any pre-focus processing.

**Parameters:** e : Ext.EventObjectThe event object


### beforeLayout

Occurs before componentLayout is run. ...

Occurs before componentLayout is run. In previous releases, this method could return `false` to prevent its layout but that is not supported in Ext JS 4.1 or higher. This method is simply a notification of the impending layout to give the component a chance to adjust the DOM. Ideally, DOM reads should be avoided at this time to reduce expensive document reflows. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeRender

...

Overrides: Ext.container.AbstractContainer.beforeRender


### beforeSetPosition

Template method called before a Component is positioned. ...

Template method called before a Component is positioned. Ensures that the position is adjusted so that the Component is constrained if so configured.

**Parameters:** x : Object


### beforeShow

Invoked before the Component is shown. ...

Invoked before the Component is shown. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beginCollapse

Called before the change from default, configured state into the collapsed state. ...

Called before the change from default, configured state into the collapsed state. This method may be called at render time to enable rendering in an initially collapsed state, or at runtime when an existing, fully layed out Panel may be collapsed. It basically saves configs which need to be clobbered for the duration of the collapsed state.


### beginDrag

...


### beginExpand

...


### bindStore

...

**Parameters:** store : Object


### blur

...

**Returns:** Ext.Componentthis


### bridgeToolbars

...


### bubble

Bubbles up the component/container heirarchy, calling the specified function with each component. ...

Bubbles up the component/container heirarchy, calling the specified function with each component. The scope (*this*) of function call will be the scope provided or the current component. The arguments to the function will be the args provided or the current component. If the function returns false at any point, the bubble is stopped.

**Parameters:** fn : FunctionThe function to call


### calculateAnchorXY

Calculates x,y coordinates specified by the anchor position on the element, adding extraX and extraY values. ...

Calculates x,y coordinates specified by the anchor position on the element, adding extraX and extraY values.

**Parameters:** anchor : String (optional)The specified anchor position. See alignTo for details on supported anchor positions. Defaults to: `'tl'`


### calculateConstrainedPosition

Calculates the new [x,y] position to move this Positionable into a constrain region. ...

Calculates the new [x,y] position to move this Positionable into a constrain region. By default, this Positionable is constrained to be within the container it was added to, or the element it was rendered to. Priority is given to constraining the top and left within the constraint. An alternative constraint may be passed.

**Parameters:** constrainTo : String/HTMLElement/Ext.Element/Ext.util.Region (optional)The Element or Region into which this Component is to be constrained. Defaults to the element into which this Positionable was rendered, or this Component's {@link Ext.Component.constrainTo.


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


### cancelFocus

Cancel any deferred focus on this component ...

Cancel any deferred focus on this component


### captureArgs

...

**Parameters:** o : Object


### cascade

Cascades down the component/container heirarchy from this component (passed in the first call), calling the specified...

Cascades down the component/container heirarchy from this component (passed in the first call), calling the specified function with each component. The scope (this reference) of the function call will be the scope provided or the current component. The arguments to the function will be the args provided or the current component. If the function returns false at any point, the cascade is stopped on that branch. Available since: 2.3.0

**Parameters:** fn : FunctionThe function to call


### center

Center this Component in its container. ...

Center this Component in its container.

**Returns:** Ext.Componentthis


### child

Retrieves the first direct child of this container which matches the passed selector or component. ...

Retrieves the first direct child of this container which matches the passed selector or component. The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.

**Parameters:** selector : String/Ext.Component (optional)An Ext.ComponentQuery selector. If no selector is specified, the first child will be returned.


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### cloneConfig

Clone the current component using the original config values passed into this instance by default. ...

Clone the current component using the original config values passed into this instance by default.

**Parameters:** overrides : ObjectA new config containing any properties to override in the cloned version. An id property can be passed on this object, otherwise one will be generated to avoid duplicates.


### close

Closes the Panel. ...

Closes the Panel. By default, this method, removes it from the DOM, destroys the Panel object and all its descendant Components. The beforeclose event is fired before the close happens and will cancel the close action if it returns false. **Note:** This method is also affected by the closeAction setting. For more explicit control use destroy and hide methods.


### collapse

Collapses the panel body so that the body becomes hidden. ...

Collapses the panel body so that the body becomes hidden. Docked Components parallel to the border towards which the collapse takes place will remain visible. Fires the beforecollapse event which will cancel the collapse action if it returns false.

**Parameters:** - direction : String (optional)The direction to collapse towards. Must be one of Ext.Component.DIRECTION_TOP - Ext.Component.DIRECTION_RIGHT - Ext.Component.DIRECTION_BOTTOM - Ext.Component.DIRECTION_LEFT Defaults to collapseDirection.


### collapsedHorizontal

...


### collapsedVertical

...


### configClass

...


### constructLockableFeatures

...


### constructLockablePlugins

...


### constructPlugin

...

**Parameters:** ptype : String/Objectstring or config object containing a ptype property. Constructs a plugin according to the passed config object/ptype string. Ensures that the constructed plugin always has a `cmp` reference back to this component. The setting up of this is done in PluginManager. The PluginManager ensures that a reference to this component is passed to the constructor. It also ensures that the plugin's `setCmp` method (if any) is called.


### constructPlugins

Returns an array of fully constructed plugin instances. ...

**Returns:** an array of fully constructed plugin instances. This converts any configs into their appropriate instances. It does not mutate the plugins array. It creates a new array.


### contains

Determines whether the passed Component is either an immediate child of this Container, or whether it is a descendant. ...

Determines whether the passed Component is either an immediate child of this Container, or whether it is a descendant.

**Parameters:** comp : Ext.ComponentThe Component to test.


### continueFireEvent

Continue to fire event. ...

Continue to fire event.

**Parameters:** eventName : String


### convertCollapseDir

converts a collapsdDir into an anchor argument for Element.slideIn overridden in rtl mode to switch "l" and "r" ...

converts a collapsdDir into an anchor argument for Element.slideIn overridden in rtl mode to switch "l" and "r"

**Parameters:** collapseDir : Object


### convertPositionSpec

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**

**Parameters:** posSpec : Object


### createReExpander

...

**Parameters:** direction : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### delayScroll

...


### deleteMembers

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### destroyDockedItems

...


### destroyLockable

...


### detachComponent

Detach a component from the DOM ...

Detach a component from the DOM

**Parameters:** component : Object


### determineScrollbars

This method is obsolete in 4.1. ...

This method is obsolete in 4.1. The closest equivalent in 4.1 is doLayout, but it is also possible that no layout is needed. This method has been **deprecated** since 4.1


### determineXTypeToCreate

...

**Parameters:** lockedSide : Object


### disable

Inherit docs Disable all immediate children that was previously disabled Override disable because onDisable only gets...

Inherit docs Disable all immediate children that was previously disabled Override disable because onDisable only gets called when rendered Disable the component. Available since: 1.1.0

**Parameters:** silent : Boolean (optional)Passing `true` will suppress the `disable` event from being fired. Defaults to: `false`


### doApplyRenderTpl

Called from the selected frame generation template to insert this Component's inner structure inside the framing stru...

Called from the selected frame generation template to insert this Component's inner structure inside the framing structure. When framing is used, a selected frame generation template is used as the primary template of the getElConfig instead of the configured renderTpl. The renderTpl is invoked by this method which is injected into the framing template.

**Parameters:** out : Object


### doAutoRender

Handles autoRender. ...

Handles autoRender. Floating Components may have an ownerCt. If they are asking to be constrained, constrain them within that ownerCt, and have their z-index managed locally. Floating Components are always rendered to document.body


### doClose

...


### doCollapseExpand

...

**Parameters:** flags : Object


### doComponentLayout

This method needs to be called whenever you change something on this component that requires the Component's layout t...

This method needs to be called whenever you change something on this component that requires the Component's layout to be recalculated.

**Returns:** Ext.container.Containerthis


### doConstrain

Moves this floating Component into a constrain region. ...

Moves this floating Component into a constrain region. By default, this Component is constrained to be within the container it was added to, or the element it was rendered to. An alternative constraint may be passed.

**Parameters:** constrainTo : String/HTMLElement/Ext.Element/Ext.util.Region (optional)The Element or Region into which this Component is to be constrained. Defaults to the element into which this floating Component was rendered.


### doLayout

Manually force this container's layout to be recalculated. ...

Manually force this container's layout to be recalculated. The framework uses this internally to refresh layouts form most cases. Available since: 2.3.0

**Returns:** Ext.container.Containerthis


### doRemove

...

**Parameters:** component : Object


### doRenderContent

...

**Parameters:** out : Object


### doRenderDockedItems

...

**Parameters:** out : Object


### doRenderFramingDockedItems

...

**Parameters:** out : Object


### down

Retrieves the first descendant of this container which matches the passed selector. ...

Retrieves the first descendant of this container which matches the passed selector. The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.

**Parameters:** selector : String/Ext.Component (optional)An Ext.ComponentQuery selector or Ext.Component. If no selector is specified, the first child will be returned.


### enable

Enable all immediate children that was previously disabled Override enable because onEnable only gets called when ren...

Enable all immediate children that was previously disabled Override enable because onEnable only gets called when rendered Enable the component Available since: 1.1.0

**Parameters:** silent : Boolean (optional)Passing `true` will suppress the `enable` event from being fired. Defaults to: `false`


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if present. There is no implementation in the Observable base class. This is commonly used by Ext.Components to bubble events to owner Containers. See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the Component's immediate owner. But if a known target is required, this can be overridden to access the required target more quickly. Example:

**Parameters:** eventNames : String/String[]The event name to bubble, or an Array of event names.


### endDrag

...


### ensureAttachedToBody

Ensures that this component is attached to document.body. ...

Ensures that this component is attached to `document.body`. If the component was rendered to Ext.getDetachedBody, then it will be appended to `document.body`. Any configured position is also restored.

**Parameters:** runLayout : Boolean (optional)True to run the component's layout. Defaults to: `false`


### expand

Expands the panel body so that it becomes visible. ...

Expands the panel body so that it becomes visible. Fires the beforeexpand event which will cancel the expand action if it returns false.

**Parameters:** animate : Boolean (optional)True to animate the transition, else false (defaults to the value of the animCollapse panel config). May also be specified as the animation duration in milliseconds.


### findParentBy

Find a container above this component at any level by a custom function. ...

Find a container above this component at any level by a custom function. If the passed function returns true, the container will be returned. See also the up method.

**Parameters:** fn : FunctionThe custom function to call with the arguments (container, this component).


### findParentByType

Find a container above this component at any level by xtype or class See also the up method. ...

Find a container above this component at any level by xtype or class See also the up method.

**Parameters:** xtype : String/Ext.ClassThe xtype string for a component, or the class of the component directly


### findPlugin

Retrieves plugin from this component's collection by its ptype. ...

Retrieves plugin from this component's collection by its `ptype`.

**Parameters:** ptype : StringThe Plugin's ptype as specified by the class's `alias` configuration.


### findReExpander

...

**Parameters:** direction : Object


### finishRender

This method visits the rendered component tree in a "top-down" order. ...

This method visits the rendered component tree in a "top-down" order. That is, this code runs on a parent component before running on a child. This method calls the onRender method of each component.

**Parameters:** containerIdx : NumberThe index into the Container items of this Component.


### finishRenderChildren

...

Overrides: Ext.util.Renderable.finishRenderChildren


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed to addListener). An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list. An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### fireHierarchyEvent

For more information on the hierarchy events, see the note for the hierarchyEventSource observer defined in the onCla...

For more information on the hierarchy events, see the note for the hierarchyEventSource observer defined in the onClassCreated callback. This functionality is contained in Component (as opposed to Container) because a Component can be the ownerCt for a floating component (loadmask), and the loadmask needs to know when its owner is shown/hidden via the hierarchyEventSource so that its hidden state can be synchronized. TODO: merge this functionality with Ext.globalEvents

**Parameters:** ename : Object


### fitContainer

...

**Parameters:** animate : Object


### floatCollapsedPanel

...


### focus

Try to focus this component. ...

Try to focus this component.

**Parameters:** selectText : Boolean (optional)If applicable, true to also select the text in this component


### forceComponentLayout

Forces this component to redo its componentLayout. ...

Forces this component to redo its componentLayout. This method has been **deprecated** since 4.1.0 Use updateLayout instead.


### getActionEl

Deprecate 5.0 ...

Deprecate 5.0


### getActiveAnimation

Returns the current animation if this object has any effects actively running or queued, else returns false. ...

**Returns:** the current animation if this object has any effects actively running or queued, else returns false. ReturnsExt.fx.Anim/BooleanAnim if element has active effects, else false


### getAlignToXY

Gets the x,y coordinates to align this element with another element. ...

Gets the x,y coordinates to align this element with another element. See alignTo for more info on the supported position values.

**Parameters:** element : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or id of the element to align to.


### getAnchor

private ...

private


### getAnchorToXY

Begin Positionable methods Overridden in Ext.rtl.AbstractComponent. ...

Begin Positionable methods **Overridden in Ext.rtl.AbstractComponent.** Gets the x,y coordinates of an element specified by the anchor position on the element.

**Parameters:** el : Ext.dom.ElementThe element


### getAnchorXY

Gets the x,y coordinates specified by the anchor position on the element. ...

Gets the x,y coordinates specified by the anchor position on the element.

**Parameters:** anchor : String (optional)The specified anchor position. See alignTo for details on supported anchor positions. Defaults to: `'tl'`


### getAnimateTarget

...

**Parameters:** target : Object


### getAutoId

...


### getBorderPadding

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Returns:** the size of the element's borders and padding. ReturnsObjectan object with the following numeric properties - beforeX - afterX - beforeY - afterY


### getBox

Return an object defining the area of this Element which can be passed to setBox to set another Element's size/locati...

Return an object defining the area of this Element which can be passed to setBox to set another Element's size/location to match this element.

**Parameters:** contentBox : Boolean (optional)If true a box for the content of the element is returned.


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getBubbleTarget

Implements an upward event bubbling policy. ...

Implements an upward event bubbling policy. By default a Component bubbles events up to its reference owner. Component subclasses may implement a different bubbling strategy by overriding this method. Overrides: Ext.AbstractComponent.getBubbleTarget


### getChildByElement

Return the immediate child Component in which the passed element is located. ...

Return the immediate child Component in which the passed element is located.

**Parameters:** el : Ext.Element/HTMLElement/StringThe element to test (or ID of element).


### getChildEls

...


### getChildItemsToDisable

Gets a list of child components to enable/disable when the container is enabled/disabled ...

Gets a list of child components to enable/disable when the container is enabled/disabled

**Returns:** Ext.Component[]Items to be enabled/disabled


### getClassChildEls

...

**Parameters:** cls : Object


### getCollapsed

Returns the current collapsed state of the panel. ...

**Returns:** the current collapsed state of the panel. ReturnsBoolean/StringFalse when not collapsed, otherwise the value of collapseDirection.


### getCollapsedDockedItems

...


### getColumnWidth

Used when calculating total locked column width in processColumns Use shrinkwrapping of child columns if no top level...

Used when calculating total locked column width in processColumns Use shrinkwrapping of child columns if no top level width.

**Parameters:** column : Object


### getComponent

Attempts a default component lookup (see Ext.container.Container.getComponent). ...

Attempts a default component lookup (see Ext.container.Container.getComponent). If the component is not found in the normal items, the dockedItems are searched and the matched component (if any) returned (see getDockedComponent). Note that docked items will only be matched by component id or itemId -- if you pass a numeric index only non-docked child components will be searched. Available since: 2.3.0

**Parameters:** comp : String/NumberThe component id, itemId or position to find


### getComponentId

used as the key lookup function for the items collection ...

- used as the key lookup function for the items collection

**Parameters:** comp : Object


### getComponentLayout

...


### getConfig

...

**Parameters:** name : Object


### getConstrainVector

Returns the [X, Y] vector by which this Positionable's element must be translated to make a best attempt to constrain...

**Parameters:** constrainTo : Ext.util.Positionable/HTMLElement/String/Ext.util.Region (optional)The Positionable, HTMLElement, element id, or Region into which the element is to be constrained.

**Returns:** the `[X, Y]` vector by which this Positionable's element must be translated to make a best attempt to constrain within the passed constraint. Returns `false` if the element does not need to be moved. Priority is given to constraining the top and left within the constraint. The constraint may either be an existing element into which the element is to be constrained, or a Region into which this element is to be constrained. By default, any extra shadow around the element is **not** included in the constrain calculations - the edges of the element are used as the element bounds. To constrain the shadow within the constrain region, set the `constrainShadow` property on this element to `true`.


### getContentTarget

...

Overrides: Ext.Component.getContentTarget


### getDefaultContentTarget

...

Overrides: Ext.container.AbstractContainer.getDefaultContentTarget


### getDockedComponent

Finds a docked component by id, itemId or position. ...

Finds a docked component by id, itemId or position. Also see getDockedItems

**Parameters:** comp : String/NumberThe id, itemId or position of the docked component (see getComponent for details)


### getDockedItems

Retrieves an array of all currently docked Components. ...

Retrieves an array of all currently docked Components. For example to find a toolbar that has been docked at top:

**Parameters:** selector : StringA ComponentQuery selector string to filter the returned items.


### getDockingRefItems

...

**Parameters:** deep : Object


### getDragEl

...


### getEditorParent

...


### getEl

Retrieves the top level element representing this component. ...

Retrieves the top level element representing this component. Available since: 1.1.0

**Returns:** Ext.dom.Element


### getElConfig

...


### getFocusEl

Returns the focus holder element associated with this Container. ...

**Returns:** the focus holder element associated with this Container. By default, this is the Container's target element. Subclasses which use embedded focusable elements (such as Window and Button) should override this for use by the focus method. ReturnsExt.Elementthe focus holding element.


### getFrameInfo

On render, reads an encoded style attribute, "filter" from the style of this Component's element. ...

On render, reads an encoded style attribute, "filter" from the style of this Component's element. This information is memoized based upon the CSS class name of this Component's element. Because child Components are rendered as textual HTML as part of the topmost Container, a dummy div is inserted into the document to receive the document element's CSS class name, and therefore style attributes.


### getFrameRenderData

...


### getFrameTpl

...

**Parameters:** table : Object


### getFramingInfoCls

...


### getHeader

Gets the Header for this panel. ...

Gets the Header for this panel.


### getHeaderCollapsedClasses

Create the class array to add to the Header when collpsed. ...

Create the class array to add to the Header when collpsed.

**Parameters:** header : Object


### getHeight

Gets the current height of the component's underlying element. ...

Gets the current height of the component's underlying element.

**Returns:** Number


### getHeightAuthority

...


### getHierarchyState

A component's hierarchyState is used to keep track of aspects of a component's state that affect its descendants hier...

A component's hierarchyState is used to keep track of aspects of a component's state that affect its descendants hierarchically like "collapsed" and "hidden". For example, if this.hierarchyState.hidden == true, it means that either this component, or one of its ancestors is hidden. Hierarchical state management is implemented by chaining each component's hierarchyState property to its parent container's hierarchyState property via the prototype. The result is such that if a component's hierarchyState does not have it's own property, it inherits the property from the nearest ancestor that does. To set a hierarchical "hidden" value: It is important to remember when unsetting hierarchyState properties to delete them instead of just setting them to a falsy value. This ensures that the hierarchyState returns to a state of inheriting the value instead of overriding it To unset the hierarchical "hidden" value: IMPORTANT! ALWAYS access hierarchyState using this method, not by accessing this.hierarchyState directly. The hierarchyState property does not exist until the first time getHierarchyState() is called. At that point getHierarchyState() walks up the component tree to establish the hierarchyState prototype chain. Additionally the hierarchyState property should NOT be relied upon even after the initial call to getHierarchyState() because it is possible for the hierarchyState to be invalidated. Invalidation typically happens when a component is moved to a new container. In such a case the hierarchy state remains invalid until the next time getHierarchyState() is called on the component or one of its descendants.

**Parameters:** inner : Object


### getId

Retrieves the id of this component. ...

Retrieves the `id` of this component. Will auto-generate an `id` if one has not already been set.

**Returns:** String


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getInsertPosition

This function takes the position argument passed to onRender and returns a DOM element that you can use in the insert...

This function takes the position argument passed to onRender and returns a DOM element that you can use in the insertBefore.

**Parameters:** position : String/Number/Ext.dom.Element/HTMLElementIndex, element id or element you want to put this component before.


### getItemId

Returns the value of itemId assigned to this component, or when that is not set, returns the value of id. ...

**Returns:** the value of itemId assigned to this component, or when that is not set, returns the value of id. ReturnsString


### getKeyMap

...


### getLayout

Returns the layout instance currently associated with this Container. ...

**Returns:** the layout instance currently associated with this Container. If a layout has not been instantiated yet, that is done first ReturnsExt.layout.container.ContainerThe layout


### getLhsMarker

Gets left hand side marker for header resizing. ...

Gets left hand side marker for header resizing.


### getLoader

Gets the Ext.ComponentLoader for this Component. ...

Gets the Ext.ComponentLoader for this Component.

**Returns:** Ext.ComponentLoaderThe loader instance, null if it doesn't exist.


### getLocalX

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Returns:** the x coordinate of this element reletive to its `offsetParent`. ReturnsNumberThe local x coordinate


### getLocalXY

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Returns:** the x and y coordinates of this element relative to its `offsetParent`. ReturnsNumber[]The local XY position of the element


### getLocalY

Returns the y coordinate of this element reletive to its offsetParent. ...

**Returns:** the y coordinate of this element reletive to its `offsetParent`. ReturnsNumberThe local y coordinate


### getLockingViewConfig

...


### getMaskTarget

...


### getMenuItems

...

**Parameters:** getMenuItems : Object


### getOffsetsTo

Returns the offsets of this element from the passed element. ...

**Parameters:** offsetsTo : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or element id to get get the offsets from.

**Returns:** the offsets of this element from the passed element. The element must both be part of the DOM tree and not have display:none to have page coordinates.


### getOppositeDirection

...

**Parameters:** d : Object


### getOuterSize

Include margins ...

Include margins


### getOverflowEl

Get an el for overflowing, defaults to the target el ...

Get an el for overflowing, defaults to the target el


### getOverflowStyle

Returns the CSS style object which will set the Component's scroll styles. ...

**Returns:** the CSS style object which will set the Component's scroll styles. This must be applied to the target element.


### getOwningBorderContainer

Returns the owning container if that container uses border layout. ...

**Returns:** the owning container if that container uses `border` layout. Otherwise this method returns `null`. **Defined in override Ext.layout.container.border.Region.** ReturnsExt.container.ContainerThe owning border container or `null`.


### getOwningBorderLayout

Returns the owning border (Ext.layout.container.Border) instance if there is one. ...

**Returns:** the owning `border` (`Ext.layout.container.Border`) instance if there is one. Otherwise this method returns `null`. **Defined in override Ext.layout.container.border.Region.** ReturnsExt.layout.container.BorderThe owning border layout or `null`.


### getPlaceholder

...

**Parameters:** direction : Object


### getPlugin

Retrieves a plugin from this component's collection by its pluginId. ...

Retrieves a plugin from this component's collection by its `pluginId`.

**Parameters:** pluginId : String


### getPosition

Gets the current XY position of the component's underlying element. ...

Gets the current XY position of the component's underlying element.

**Parameters:** local : Boolean (optional)If true the element's left and top are returned instead of page XY. Defaults to: `false`


### getPositionEl

Deprecate 5.0 ...

Deprecate 5.0


### getProtoBody

...


### getProxy

...


### getReExpander

...

**Parameters:** direction : Object


### getRefItems

Used by ComponentQuery, child and down to retrieve all of the items which can potentially be considered a child of th...

Used by ComponentQuery, child and down to retrieve all of the items which can potentially be considered a child of this Container. This may be overriden by Components which have ownership of Components that are not contained in the items collection. NOTE: IMPORTANT note for maintainers: Items are returned in tree traversal order. Each item is appended to the result array followed by the results of that child's getRefItems call. Floating child items are appended after internal child items.

**Parameters:** deep : Object


### getRefOwner

Used by ComponentQuery, and the up method to find the owning Component in the linkage hierarchy. ...

Used by ComponentQuery, and the up method to find the owning Component in the linkage hierarchy. By default this returns the Container which contains this Component. This may be overriden by Component authors who implement ownership hierarchies which are not based upon ownerCt, such as BoundLists being owned by Fields or Menus being owned by Buttons.


### getRegion

Returns a region object that defines the area of this element. ...

**Returns:** a region object that defines the area of this element. ReturnsExt.util.RegionA Region containing "top, left, bottom, right" properties.


### getRenderTree

...


### getResizeEl

Deprecate 5.0 ...

Deprecate 5.0


### getRhsMarker

Gets right hand side marker for header resizing. ...

Gets right hand side marker for header resizing.


### getScrollTarget

...


### getScrollerOwner

...


### getSelectionModel

Returns the selection model being used and creates it via the configuration if it has not been created already. ...

**Returns:** the selection model being used and creates it via the configuration if it has not been created already. ReturnsExt.selection.ModelselModel


### getSize

Gets the current size of the component's underlying element. ...

Gets the current size of the component's underlying element.

**Returns:** ObjectAn object containing the element's size `{width: (element width), height: (element height)}`


### getSizeModel

Returns an object that describes how this component's width and height are managed. ...

**Parameters:** ownerCtSizeModel : Object

**Returns:** an object that describes how this component's width and height are managed. All of these objects are shared and should not be modified.


### getState

The supplied default state gathering method for the AbstractComponent class. ...

The supplied default state gathering method for the AbstractComponent class. This method returns dimension settings such as `flex`, `anchor`, `width` and `height` along with `collapsed` state. Subclasses which implement more complex state should call the superclass's implementation, and apply their state to the result if this basic state is to be saved. Note that Component state will only be saved if the Component has a stateId and there as a StateProvider configured for the document.

**Returns:** Object


### getStateId

Gets the state id for this object. ...

Gets the state id for this object.

**Returns:** StringThe 'stateId' or the implicit 'id' specified by component configuration.


### getStore

Returns the store associated with this Panel. ...

**Returns:** the store associated with this Panel. ReturnsExt.data.StoreThe store


### getStyleProxy

Returns an offscreen div with the same class name as the element this is being rendered. ...

**Parameters:** cls : Object

**Returns:** an offscreen div with the same class name as the element this is being rendered. This is because child item rendering takes place in a detached div which, being not part of the document, has no styling.


### getTargetEl

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. ...

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. Overrides: Ext.panel.AbstractPanel.getTargetEl


### getTpl

...

**Parameters:** name : Object


### getView

Gets the view for this panel. ...

Gets the view for this panel.

**Returns:** Ext.view.Table


### getViewRegion

Returns the content region of this element. ...

**Returns:** the **content** region of this element. That is the region within the borders and padding. ReturnsExt.util.RegionA Region containing "top, left, bottom, right" member data.


### getVisibilityEl

Deprecate 5.0 ...

Deprecate 5.0


### getWidth

Gets the current width of the component's underlying element. ...

Gets the current width of the component's underlying element.

**Returns:** Number


### getWidthAuthority

...


### getX

Gets the current X position of the DOM element based on page coordinates. ...

Gets the current X position of the DOM element based on page coordinates.

**Returns:** NumberThe X position of the element


### getXType

Gets the xtype for this component as registered with Ext.ComponentManager. ...

Gets the xtype for this component as registered with Ext.ComponentManager. For a list of all available xtypes, see the Ext.Component header. Example usage:

**Returns:** StringThe xtype


### getXTypes

Returns this Component's xtype hierarchy as a slash-delimited string. ...

**Returns:** this Component's xtype hierarchy as a slash-delimited string. For a list of all available xtypes, see the Ext.Component header. If using your own subclasses, be aware that a Component must register its own xtype to participate in determination of inherited xtypes. Example usage: Available since: 2.3.0 ReturnsStringThe xtype hierarchy string


### getXY

Gets the current position of the DOM element based on page coordinates. ...

Gets the current position of the DOM element based on page coordinates.

**Returns:** Number[]The XY position of the element


### getY

Gets the current Y position of the DOM element based on page coordinates. ...

Gets the current Y position of the DOM element based on page coordinates.

**Returns:** NumberThe Y position of the element


### ghost

used for dragging ...

used for dragging

**Parameters:** cls : Object


### ghostTools

helper function for ghost ...

helper function for ghost


### hasActiveFx

Returns the current animation if this object has any effects actively running or queued, else returns false. ...

**Returns:** the current animation if this object has any effects actively running or queued, else returns false. This method has been **deprecated** since 4.0 Replaced by getActiveAnimation


### hasCls

Checks if the specified CSS class exists on this element's DOM node. ...

Checks if the specified CSS class exists on this element's DOM node.

**Parameters:** className : StringThe CSS class to check for.


### hasConfig

...

**Parameters:** config : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer indicates whether the event needs firing or not.

**Parameters:** eventName : StringThe name of the event to check for


### hasLockedColumns

Private. ...

Private. Determine if there are any columns with a locked configuration option

**Parameters:** columns : Object


### hasUICls

Checks if there is currently a specified uiCls. ...

Checks if there is currently a specified `uiCls`.

**Parameters:** cls : StringThe `cls` to check.


### hide

Hides this Component, setting it to invisible using the configured hideMode. ...

Hides this Component, setting it to invisible using the configured hideMode.

**Parameters:** animateTarget : String/Ext.Element/Ext.Component (optional)only valid for floating Components such as Windows or ToolTips, or regular Components which have been configured with `floating: true`.. The target to which the Component should animate while hiding. Defaults to: `null`


### initAria

...


### initBodyBorder

...


### initBodyStyles

Parses the bodyStyle config if available to create a style string that will be applied to the body element. ...

Parses the bodyStyle config if available to create a style string that will be applied to the body element. This also includes bodyPadding and bodyBorder if available.

**Returns:** StringA CSS style string with body styles, padding and border.


### initBorderProps

...


### initBorderRegion

This method is called by the Ext.layout.container.Border class when instances are added as regions to the layout. ...

This method is called by the `Ext.layout.container.Border` class when instances are added as regions to the layout. Since it is valid to add any component to a border layout as a region, this method must be added to `Ext.Component` but is only ever called when that component is owned by a `border` layout. **Defined in override Ext.layout.container.border.Region.**


### initCls

...


### initComponent

The initComponent template method is an important initialization step for a Component. ...

The initComponent template method is an important initialization step for a Component. It is intended to be implemented by each subclass of Ext.Component to provide any needed constructor logic. The initComponent method of the class being created is called first, with each initComponent method up the hierarchy to Ext.Component being called thereafter. This makes it easy to implement and, if needed, override the constructor logic of the Component at any step in the hierarchy. The initComponent method **must** contain a call to callParent in order to ensure that the parent class' initComponent method is also called. All config options passed to the constructor are applied to `this` before initComponent is called, so you can simply access them with `this.someOption`. The following example demonstrates using a dynamic string for the text of a button at the time of instantiation of the class. Available since: 1.1.0 This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initContainer

...

**Parameters:** container : Object


### initDockingItems

...


### initDraggable

...

Overrides: Ext.Component.initDraggable


### initEvents

Initialize any events on this component ...

Initialize any events on this component


### initFrame

...


### initFramingTpl

Poke in a reference to applyRenderTpl(frameInfo, out) ...

Poke in a reference to applyRenderTpl(frameInfo, out)

**Parameters:** table : Object


### initHeaderAria

...


### initHierarchyEvents

...


### initHierarchyState

Called by getHierarchyState to initialize the hierarchyState the first time it is requested. ...

Called by getHierarchyState to initialize the hierarchyState the first time it is requested. **Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** hierarchyState : Object


### initItems

...

Overrides: Ext.container.AbstractContainer.initItems


### initPadding

Initializes padding by applying it to the target element, or if the layout manages padding ensures that the padding o...

Initializes padding by applying it to the target element, or if the layout manages padding ensures that the padding on the target element is "0".

**Parameters:** targetEl : Object


### initPlugin

...

**Parameters:** plugin : Object


### initRenderData

Initialized the renderData to be used when rendering the renderTpl. ...

Initialized the renderData to be used when rendering the renderTpl.

**Returns:** ObjectObject with keys and values that are going to be applied to the renderTpl


### initRenderTpl

Initializes the renderTpl. ...

Initializes the renderTpl.

**Returns:** Ext.XTemplateThe renderTpl XTemplate instance.


### initResizable

...

Overrides: Ext.Component.initResizable


### initSimpleDraggable

Override Component.initDraggable. ...

Override Component.initDraggable. Panel (and subclasses) use the header element as the delegate.


### initState

Initializes the state of the object upon construction. ...

Initializes the state of the object upon construction.


### initStyles

Applies padding, margin, border, top, left, height, and width configs to the appropriate elements. ...

Applies padding, margin, border, top, left, height, and width configs to the appropriate elements.

**Parameters:** targetEl : Object


### initTools

Tools are a Panel-specific capabilty. ...

Tools are a Panel-specific capabilty. Panel uses initTools. Subclasses may contribute tools by implementing addTools.


### injectLockable

injectLockable will be invoked before initComponent's parent class implementation is called, so throughout this metho...

injectLockable will be invoked before initComponent's parent class implementation is called, so throughout this method this. are configurations


### insert

Inserts a Component into this Container at a specified index. ...

Inserts a Component into this Container at a specified index. Fires the beforeadd event before inserting, then fires the add event after the Component has been inserted. Available since: 2.3.0

**Parameters:** index : NumberThe index at which the Component will be inserted into the Container's items collection


### insertDocked

Inserts docked item(s) to the panel at the indicated position. ...

Inserts docked item(s) to the panel at the indicated position.

**Parameters:** pos : NumberThe index at which the Component will be inserted


### invalidateScroller

This method is obsolete in 4.1. ...

This method is obsolete in 4.1. The closest equivalent in 4.1 is Ext.AbstractComponent.updateLayout, but it is also possible that no layout is needed. This method has been **deprecated** since 4.1


### is

Tests whether this Component matches the selector string. ...

Tests whether this Component matches the selector string.

**Parameters:** selector : StringThe selector string to test against.


### isAncestor

Determines whether this Container is an ancestor of the passed Component. ...

Determines whether **this Container** is an ancestor of the passed Component. This will return `true` if the passed Component is anywhere within the subtree beneath this Container.

**Parameters:** possibleDescendant : Ext.ComponentThe Component to test for presence within this Container's subtree.


### isContainedFloater

Utility method to determine if a Component is floating, and has an owning Container whose coordinate system it must b...

Utility method to determine if a Component is floating, and has an owning Container whose coordinate system it must be positioned in when using setPosition.


### isDescendant

...

**Parameters:** ancestor : Object


### isDescendantOf

Determines whether this component is the descendant of a particular container. ...

Determines whether this component is the descendant of a particular container.

**Parameters:** container : Ext.Container


### isDisabled

Method to determine whether this Component is currently disabled. ...

Method to determine whether this Component is currently disabled.

**Returns:** Booleanthe disabled state of this Component.


### isDraggable

Method to determine whether this Component is draggable. ...

Method to determine whether this Component is draggable.

**Returns:** Booleanthe draggable state of this component.


### isDroppable

Method to determine whether this Component is droppable. ...

Method to determine whether this Component is droppable.

**Returns:** Booleanthe droppable state of this component.


### isFloating

Method to determine whether this Component is floating. ...

Method to determine whether this Component is floating.

**Returns:** Booleanthe floating state of this component.


### isFocusable

...


### isHidden

Method to determine whether this Component is currently set to hidden. ...

Method to determine whether this Component is currently set to hidden.

**Returns:** Booleanthe hidden state of this Component.


### isHierarchicallyHidden

...


### isLayoutRoot

Determines whether this Component is the root of a layout. ...

Determines whether this Component is the root of a layout. This returns `true` if this component can run its layout without assistance from or impact on its owner. If this component cannot run its layout given these restrictions, `false` is returned and its owner will be considered as the next candidate for the layout root. Setting the _isLayoutRoot property to `true` causes this method to always return `true`. This may be useful when updating a layout of a Container which shrink wraps content, and you know that it will not change size, and so can safely be the topmost participant in the layout run. Overrides: Ext.AbstractComponent.isLayoutRoot


### isLayoutSuspended

Returns true if layout is suspended for this component. ...

**Returns:** `true` if layout is suspended for this component. This can come from direct suspension of this component's layout activity (Ext.Container.suspendLayout) or if one of this component's containers is suspended. ReturnsBoolean`true` layout of this component is suspended.


### isLocalRtl

Returns true if this component's local coordinate system is rtl. ...

**Returns:** true if this component's local coordinate system is rtl. For normal components this equates to the value of isParentRtl(). Floaters are a bit different because a floater's element can be a childNode of something other than its parent component's element. For floaters we have to read the dom to see if the component's element's parentNode has a css direction value of "rtl". **Defined in override Ext.rtl.AbstractComponent.** ReturnsBoolean


### isOppositeRootDirection

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**


### isParentRtl

Returns true if this component's parent container is rtl. ...

**Returns:** true if this component's parent container is rtl. Used by rtl positioning methods to determine if the component should be positioned using a right-to-left coordinate system. **Defined in override Ext.rtl.AbstractComponent.** ReturnsBoolean


### isPlaceHolderCollapse

...


### isVisible

Returns true if this component is visible. ...

**Parameters:** deep : Boolean (optional)Pass `true` to interrogate the visibility status of all parent Containers to determine whether this Component is truly visible to the user. Generally, to determine whether a Component is hidden, the no argument form is needed. For example when creating dynamically laid out UIs in a hidden Container before showing them. Defaults to: `false`

**Returns:** `true` if this component is visible. Available since: 1.1.0


### isXType

Tests whether or not this Component is of a specific xtype. ...

Tests whether or not this Component is of a specific xtype. This can test whether this Component is descended from the xtype (default) or whether it is directly of the xtype specified (`shallow = true`). If using your own subclasses, be aware that a Component must register its own xtype to participate in determination of inherited xtypes. For a list of all available xtypes, see the Ext.Component header. Example usage: Available since: 2.3.0

**Parameters:** xtype : StringThe xtype to check for this Component


### lock

Locks the activeHeader as determined by which menu is open OR a header as specified. ...

Locks the activeHeader as determined by which menu is open OR a header as specified.

**Parameters:** header : Ext.grid.column.Column (optional)Header to unlock from the locked section. Defaults to the header which has the menu open currently.


### lookupComponent

...

**Parameters:** comp : Object


### makeFloating

...

**Parameters:** dom : Object


### mask

...


### modifyHeaderCt

inject Lock and Unlock text Hide/show Lock/Unlock options ...

inject Lock and Unlock text Hide/show Lock/Unlock options


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener. Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### move

Moves a Component within the Container ...

Moves a Component within the Container

**Parameters:** fromIdx : Number/Ext.ComponentThe index/component to move.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener. Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### nextChild

...

**Parameters:** child : Object


### nextNode

Returns the next node in the Component tree in tree traversal order. ...

**Parameters:** selector : String (optional)A ComponentQuery selector to filter the following nodes.

**Returns:** the next node in the Component tree in tree traversal order. Note that this is not limited to siblings, and if invoked upon a node with no matching siblings, will walk the tree to attempt to find a match. Contrast with nextSibling.


### nextSibling

Returns the next sibling of this Component. ...

**Parameters:** selector : String (optional)A ComponentQuery selector to filter the following items.

**Returns:** the next sibling of this Component. Optionally selects the next sibling which matches the passed ComponentQuery selector. May also be referred to as **`next()`** Note that this is limited to siblings, and if no siblings of the item match, `null` is returned. Contrast with nextNode


### on

Shorthand for addListener. ...

Shorthand for addListener. Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### onAdd

This method is invoked after a new Component has been added. ...

This method is invoked after a new Component has been added. It is passed the Component which has been added. This method may be used to update any internal structure which may depend upon the state of the child items. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onAdded

Method to manage awareness of when components are added to their respective Container, firing an added event. ...

Method to manage awareness of when components are added to their respective Container, firing an added event. References are established at add time rather than at render time. Allows addition of behavior when a Component is added to a Container. At this stage, the Component is in the parent Container's collection of child items. After calling the superclass's `onAdded`, the `ownerCt` reference will be present, and if configured with a ref, the `refOwner` will be set. Available since: 3.4.0 This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onAfterFloatLayout

...


### onBeforeAdd

This method is invoked before adding a new child Component. ...

This method is invoked before adding a new child Component. It is passed the new Component, and may be used to modify the Component, or prepare the Container in some way. Returning false aborts the add operation. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onBeforeFloatLayout

...


### onBlur

private ...

private

**Parameters:** e : Object


### onBoxReady

...

Overrides: Ext.AbstractComponent.onBoxReady


### onConfigUpdate

...

**Parameters:** names : Object


### onDestroy

Allows addition of behavior to the destroy operation. ...

Allows addition of behavior to the destroy operation. After calling the superclass's onDestroy, the Component will be destroyed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onDisable

Allows addition of behavior to the disable operation. ...

Allows addition of behavior to the disable operation. After calling the superclass's `onDisable`, the Component will be disabled. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onDockedAdd

Invoked after a docked item is added to the Panel. ...

Invoked after a docked item is added to the Panel. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onDockedRemove

Invoked after a docked item is removed from the Panel. ...

Invoked after a docked item is removed from the Panel. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onEnable

Allows addition of behavior to the enable operation. ...

Allows addition of behavior to the enable operation. After calling the superclass's `onEnable`, the Component will be enabled. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onFloatShow

...


### onFocus

private ...

private

**Parameters:** e : Object


### onHeaderHide

Section onHeaderHide is invoked after view. ...

Section onHeaderHide is invoked after view.

**Parameters:** headerCt : Object


### onHeaderMove

Update the view when a header moves ...

Update the view when a header moves

**Parameters:** headerCt : Object


### onHeaderResize

...


### onHeaderShow

...

**Parameters:** headerCt : Object


### onHide

Possibly animates down to a target element. ...

Possibly animates down to a target element. Allows addition of behavior to the hide operation. After calling the superclass’s onHide, the Component will be hidden. Gets passed the same parameters as hide. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onHorizontalScroll

...

**Parameters:** event : Object


### onKeyDown

Listen for TAB events and wrap round if tabbing of either end of the Floater ...

Listen for TAB events and wrap round if tabbing of either end of the Floater

**Parameters:** e : Object


### onLockMenuClick

...


### onLockedHeaderAdd

...


### onLockedHeaderHide

...


### onLockedHeaderResize

...


### onLockedHeaderShow

...


### onLockedHeaderSortChange

...

**Parameters:** headerCt : Object


### onLockedViewMouseWheel

Listen for mousewheel events on the locked section which does not scroll. ...

Listen for mousewheel events on the locked section which does not scroll. Scroll it in response, and the other section will automatically sync.

**Parameters:** e : Object


### onLockedViewScroll

...


### onMouseDown

Mousedown brings to front, and programatically grabs focus unless the mousedown was on a focusable element ...

Mousedown brings to front, and programatically grabs focus *unless the mousedown was on a focusable element*

**Parameters:** e : Object


### onMouseEnterFloated

...

**Parameters:** e : Object


### onMouseLeaveFloated

...

**Parameters:** e : Object


### onMove

...


### onNormalHeaderSortChange

...

**Parameters:** headerCt : Object


### onNormalViewScroll

...


### onPosition

Called after the component is moved, this method is empty by default but can be implemented by any subclass that need...

Called after the component is moved, this method is empty by default but can be implemented by any subclass that needs to perform custom logic after a move occurs. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRemove

This method is invoked after a new Component has been removed. ...

This method is invoked after a new Component has been removed. It is passed the Component which has been removed. This method may be used to update any internal structure which may depend upon the state of the child items. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRemoved

Method to manage awareness of when components are removed from their respective Container, firing a removed event. ...

Method to manage awareness of when components are removed from their respective Container, firing a removed event. References are properly cleaned up after removing a component from its owning container. Allows addition of behavior when a Component is removed from its parent Container. At this stage, the Component has been removed from its parent Container's collection of child items, but has not been destroyed (It will be destroyed if the parent Container's `autoDestroy` is `true`, or if the remove call was passed a truthy second parameter). After calling the superclass's `onRemoved`, the `ownerCt` and the `refOwner` will not be present. Available since: 3.4.0 This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRender

Template method called when this Component's DOM structure is created. ...

Template method called when this Component's DOM structure is created. At this point, this Component's (and all descendants') DOM structure *exists* but it has not been layed out (positioned and sized). Subclasses which override this to gain access to the structure at render time should call the parent class's method before attempting to access any child elements of the Component. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onResize

Allows addition of behavior to the resize operation. ...

Allows addition of behavior to the resize operation. Called when Ext.resizer.Resizer#drag event is fired. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRestoreHorzScroll

Tracks when things happen to the view and preserves the horizontal scroll position. ...

Tracks when things happen to the view and preserves the horizontal scroll position.


### onShow

Allows addition of behavior to the show operation. ...

Allows addition of behavior to the show operation. After calling the superclass's onShow, the Component will be visible. Override in subclasses where more complex behaviour is needed. Gets passed the same parameters as show. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onShowComplete

Invoked after the afterShow method is complete. ...

Invoked after the afterShow method is complete. Gets passed the same `callback` and `scope` parameters that afterShow received. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onShowVeto

...


### onStateChange

This method is called when any of the stateEvents are fired. ...

This method is called when any of the stateEvents are fired.


### onStoreLoad

template method meant to be overriden ...

template method meant to be overriden


### onUnlockMenuClick

...


### onViewReady

Fires the TablePanel's viewready event when the view declares that its internal DOM is ready ...

Fires the TablePanel's viewready event when the view declares that its internal DOM is ready


### parseBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** box : Object


### placeholderCollapse

...

**Parameters:** direction : Object


### placeholderExpand

...

**Parameters:** animate : Object


### postBlur

Template method to do any post-blur processing. ...

Template method to do any post-blur processing.

**Parameters:** e : Ext.EventObjectThe event object


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a class derives from this class or uses this class as a mixin.

**Parameters:** T : FunctionThe class constructor to prepare.


### prepareItems

...

**Parameters:** items : Object


### prevChild

...

**Parameters:** child : Object


### previousNode

Returns the previous node in the Component tree in tree traversal order. ...

**Parameters:** selector : String (optional)A ComponentQuery selector to filter the preceding nodes.

**Returns:** the previous node in the Component tree in tree traversal order. Note that this is not limited to siblings, and if invoked upon a node with no matching siblings, will walk the tree in reverse order to attempt to find a match. Contrast with previousSibling.


### previousSibling

Returns the previous sibling of this Component. ...

**Parameters:** selector : String (optional)A ComponentQuery selector to filter the preceding items.

**Returns:** the previous sibling of this Component. Optionally selects the previous sibling which matches the passed ComponentQuery selector. May also be referred to as **`prev()`** Note that this is limited to siblings, and if no siblings of the item match, `null` is returned. Contrast with previousNode


### processColumns

...

**Parameters:** columns : Object


### processEvent

Processes UI events from the view. ...

Processes UI events from the view. Propagates them to whatever internal Components need to process them.

**Parameters:** type : StringEvent type, eg 'click'


### prune

...

**Parameters:** childEls : Object


### query

Retrieves all descendant components which match the passed selector. ...

Retrieves all descendant components which match the passed selector. Executes an Ext.ComponentQuery.query using this container as its root.

**Parameters:** selector : String (optional)Selector complying to an Ext.ComponentQuery selector. If no selector is specified all items will be returned.


### queryBy

Retrieves all descendant components which match the passed function. ...

Retrieves all descendant components which match the passed function. The function should return false for components that are to be excluded from the selection.

**Parameters:** fn : FunctionThe matcher function. It will be called with a single argument, the component being tested.


### queryById

Finds a component at any level under this container matching the id/itemId. ...

Finds a component at any level under this container matching the id/itemId. This is a shorthand for calling ct.down('#' + id);

**Parameters:** id : StringThe id to find


### reconfigure

documented on GridPanel ...

documented on GridPanel

**Parameters:** store : Object


### reconfigureLockable

we want to totally override the reconfigure behaviour here, since we're creating 2 sub-grids ...

we want to totally override the reconfigure behaviour here, since we're creating 2 sub-grids

**Parameters:** store : Object


### registerFloatingItem

Called by Component#doAutoRender Register a Container configured floating: true with this Component's ZIndexManager. ...

Called by Component#doAutoRender Register a Container configured `floating: true` with this Component's ZIndexManager. Components added in this way will not participate in any layout, but will be rendered upon first show in the way that Windows are.

**Parameters:** cmp : Object


### registerWithOwnerCt

...


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`. For example if you are extending Grid, you might decide to forward some events from store. So you can do this inside your initComponent: The grid instance will then have an observable 'load' event which will be passed the parameters of the store's load event and any function fired with the grid's load event would have access to the grid using the `this` keyword.

**Parameters:** origin : ObjectThe Observable whose events this object is to relay.


### relayHeaderCtEvents

...

**Parameters:** headerCt : Object


### remove

Removes a component from this container. ...

Removes a component from this container. Fires the beforeremove event before removing, then fires the remove event after the component has been removed. Available since: 2.3.0

**Parameters:** component : Ext.Component/StringThe component reference or id to remove.


### removeAll

Removes all components from this container. ...

Removes all components from this container. Available since: 2.3.0

**Parameters:** autoDestroy : Boolean (optional)True to automatically invoke the removed Component's Ext.Component.destroy function. Defaults to the value of this Container's autoDestroy config.


### removeAnchor

Remove any anchor to this element. ...

Remove any anchor to this element. See anchorTo.

**Returns:** Ext.util.Positionablethis


### removeBodyCls

Removes a CSS class from the body element. ...

Removes a CSS class from the body element.

**Parameters:** cls : StringThe class to remove


### removeChildEls

Removes items in the childEls array based on the return value of a supplied test function. ...

Removes items in the childEls array based on the return value of a supplied test function. The function is called with a entry in childEls and if the test function return true, that entry is removed. If false, that entry is kept.

**Parameters:** testFn : FunctionThe test function.


### removeClass

...

Available since: 2.3.0


### removeCls

Removes a CSS class from the top level element representing this component. ...

Removes a CSS class from the top level element representing this component.

**Parameters:** cls : String/String[]The CSS class name to remove.


### removeClsWithUI

Removes a cls to the uiCls array, which will also call removeUIClsFromElement and removes it from all elements of thi...

Removes a `cls` to the `uiCls` array, which will also call removeUIClsFromElement and removes it from all elements of this component.

**Parameters:** cls : String/String[]A string or an array of strings to remove to the `uiCls`.


### removeDocked

Removes the docked item from the panel. ...

Removes the docked item from the panel.

**Parameters:** item : Ext.ComponentThe Component to remove.


### removeListener

Removes an event handler. ...

Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### removeManagedListener

Removes listeners that were added by the mon method. ...

Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### removeManagedListenerItem

inherit docs Remove a single managed listener item ...

inherit docs Remove a single managed listener item

**Parameters:** isClear : BooleanTrue if this is being called during a clear


### removeOverCls

...


### removePlugin

...

**Parameters:** plugin : Object


### removeUIClsFromElement

inherit docs Method which removes a specified UI + uiCls from the components element. ...

inherit docs Method which removes a specified UI + `uiCls` from the components element. The `cls` which is added to the element will be: `this.baseCls + '-' + ui`.

**Parameters:** ui : StringThe UI to add to the element.


### removeUIFromElement

inherit docs Method which removes a specified UI from the components element. ...

inherit docs Method which removes a specified UI from the components element. Overrides: Ext.AbstractComponent.removeUIFromElement


### render

Renders the Component into the passed HTML element. ...

Renders the Component into the passed HTML element. If you are using a Container object to house this Component, then do not use the render method. A Container's child Components are rendered by that Container's layout manager when the Container is first rendered. If the Container is already rendered when a new child Component is added, you may need to call the Container's doLayout to refresh the view which causes any unrendered child Components to be rendered. This is required so that you can add multiple child components if needed while only refreshing the layout once. When creating complex UIs, it is important to remember that sizing and positioning of child items is the responsibility of the Container's layout manager. If you expect child items to be sized in response to user interactions, you must configure the Container with a layout manager which creates and manages the type of layout you have in mind. Omitting the Container's layout config means that a basic layout manager is used which does nothing but render child components sequentially into the Container. No sizing or positioning will be performed in this situation.

**Parameters:** container : Ext.Element/HTMLElement/String (optional)The element this Component should be rendered into. If it is being created from existing markup, this should be omitted.


### repositionFloatingItems

...


### restoreDimension

...


### restoreHiddenDocked

...


### restoreScrollPos

...


### resumeEvent

Resumes firing of the named event(s). ...

Resumes firing of the named event(s). After calling this method to resume events, the events will fire when requested to fire. Note that if the suspendEvent method is called multiple times for a certain event, this converse method will have to be called the same number of times for it to resume firing.

**Parameters:** eventName : String...Multiple event names to resume.


### resumeEvents

Resumes firing events (see suspendEvents). ...

Resumes firing events (see suspendEvents). If events were suspended using the `queueSuspended` parameter, then all events fired during event suspension will be sent to any listeners now.


### resumeLayouts

...

**Parameters:** flushOptions : Object


### savePropToState

Conditionally saves a single property from this object to the given state object. ...

Conditionally saves a single property from this object to the given state object. The idea is to only save state which has changed from the initial state so that current software settings do not override future software settings. Only those values that are user-changed state should be saved.

**Parameters:** propName : StringThe name of the property to save.


### savePropsToState

Gathers additional named properties of the instance and adds their current values to the passed state object. ...

Gathers additional named properties of the instance and adds their current values to the passed state object.

**Parameters:** propNames : String/String[]The name (or array of names) of the property to save.


### saveScrollPos

...


### saveState

Saves the state of the object to the persistence store. ...

Saves the state of the object to the persistence store.


### scrollBy

Scrolls this Component's target element by the passed delta values, optionally animating. ...

Scrolls this Component's target element by the passed delta values, optionally animating. All of the following are equivalent:

**Parameters:** deltaX : Number/Number[]/ObjectEither the x delta, an Array specifying x and y deltas or an object with "x" and "y" properties.


### scrollByDeltaX

...

**Parameters:** xDelta : Object


### scrollByDeltaY

...

**Parameters:** yDelta : Object


### sequenceFx

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. ...

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. This is the opposite of syncFx.

**Returns:** Objectthis


### setActive

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been moved to th...

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been moved to the top of its zIndex stack, or pushed from the top of its zIndex stack. If a *Window* is superceded by another Window, deactivating it hides its shadow. This method also fires the activate or deactivate event depending on which action occurred.

**Parameters:** active : Boolean (optional)True to activate the Component, false to deactivate it. Defaults to: `false`


### setAutoScroll

autoScroll is never valid for all classes which extend TablePanel. ...

autoScroll is never valid for all classes which extend TablePanel. Overrides: Ext.Component.setAutoScroll


### setBodyStyle

Sets the body style according to the passed parameters. ...

Sets the body style according to the passed parameters.

**Parameters:** style : MixedA full style specification string, or object, or the name of a style property to set.


### setBorder

...

**Parameters:** border : String/NumberThe border, see border. If a falsey value is passed the border will be removed.


### setBorderRegion

This method changes the region config property for this border region. ...

This method changes the `region` config property for this border region. This is only valid if this component is in a `border` layout (`Ext.layout.container.Border`). **Defined in override Ext.layout.container.border.Region.**

**Parameters:** region : StringThe new `region` value (`"north"`, `"south"`, `"east"` or `"west"`).


### setBox

Sets the element's box. ...

Sets the element's box. If animate is true then x, y, width, and height will be animated concurrently.

**Parameters:** box : ObjectThe box to fill {x, y, width, height}


### setComponentLayout

...

**Parameters:** layout : Object


### setConfig

...

**Parameters:** config : Object


### setDisabled

Enable or disable the component. ...

Enable or disable the component.

**Parameters:** disabled : Boolean`true` to disable.


### setDocked

Sets the dock position of this component in its parent panel. ...

Sets the dock position of this component in its parent panel. Note that this only has effect if this item is part of the `dockedItems` collection of a parent that has a DockLayout (note that any Panel has a DockLayout by default)

**Parameters:** dock : ObjectThe dock position.


### setFloatParent

...

**Parameters:** floatParent : Object


### setGlyph

Set the glyph for the panel's header. ...

Set the glyph for the panel's header. See Ext.panel.Header.glyph. It will fire the glyphchange event after completion.

**Parameters:** newGlyph : Number/StringThe new glyph This parameter expects a format consistent with that of glyph


### setHeight

Sets the height of the component. ...

Sets the height of the component. This method fires the resize event.

**Parameters:** - height : NumberThe new height to set. This may be one of: A Number specifying the new height in the Element's Ext.Element.defaultUnits (by default, pixels). - A String used to set the CSS height style. - *undefined* to leave the height unchanged.


### setHiddenDocked

...


### setHiddenState

...

**Parameters:** hidden : Object


### setIcon

Set the icon for the panel's header. ...

Set the icon for the panel's header. See Ext.panel.Header.icon. It will fire the iconchange event after completion.

**Parameters:** newIcon : StringThe new icon path


### setIconCls

Set the iconCls for the panel's header. ...

Set the iconCls for the panel's header. See Ext.panel.Header.iconCls. It will fire the iconclschange event after completion.

**Parameters:** newIconCls : StringThe new CSS class name


### setLayout

...

**Parameters:** layout : Object


### setLoading

This method allows you to show or hide a LoadMask on top of this component. ...

This method allows you to show or hide a LoadMask on top of this component.

**Parameters:** load : Boolean/Object/StringTrue to show the default LoadMask, a config object that will be passed to the LoadMask constructor, or a message String to show. False to hide the current LoadMask.


### setLocalX

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.** Sets the local x coordinate of this element using CSS style. When used on an absolute positioned element this method is symmetrical with getLocalX, but may not be symmetrical when used on a relatively positioned element.

**Parameters:** x : NumberThe x coordinate. A value of `null` sets the left style to 'auto'.


### setLocalXY

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.** Sets the local x and y coordinates of this element using CSS style. When used on an absolute positioned element this method is symmetrical with getLocalXY, but may not be symmetrical when used on a relatively positioned element.

**Parameters:** x : Number/ArrayThe x coordinate or an array containing [x, y]. A value of `null` sets the left style to 'auto'


### setLocalY

Sets the local y coordinate of this element using CSS style. ...

Sets the local y coordinate of this element using CSS style. When used on an absolute positioned element this method is symmetrical with getLocalY, but may not be symmetrical when used on a relatively positioned element.

**Parameters:** y : NumberThe y coordinate. A value of `null` sets the top style to 'auto'.


### setMargin

Sets the margin on the target element. ...

Sets the margin on the target element.

**Parameters:** margin : Number/StringThe margin to set. See the margin config.


### setOverflowXY

Sets the overflow x/y on the content element of the component. ...

Sets the overflow x/y on the content element of the component. The x/y overflow values can be any valid CSS overflow (e.g., 'auto' or 'scroll'). By default, the value is 'hidden'. Passing null for one of the values will erase the inline style. Passing `undefined` will preserve the current value.

**Parameters:** overflowX : StringThe overflow-x value.


### setPagePosition

Sets the page XY position of the component. ...

Sets the page XY position of the component. To set the left and top instead, use setPosition. This method fires the move event.

**Parameters:** x : Number/Number[]The new x position or an array of `[x,y]`.


### setPosition

Sets the left and top of the component. ...

Sets the left and top of the component. To set the page XY position instead, use setPagePosition. This method fires the move event.

**Parameters:** x : Number/Number[]/ObjectThe new left, an array of `[x,y]`, or animation config object containing `x` and `y` properties.


### setRegion

Sets the element's position and size to the specified region. ...

Sets the element's position and size to the specified region. If animation is true then width, height, x and y will be animated concurrently.

**Parameters:** region : Ext.util.RegionThe region to fill


### setRegionWeight

Sets the weight config property for this component. ...

Sets the `weight` config property for this component. This is only valid if this component is in a `border` layout (`Ext.layout.container.Border`). **Defined in override Ext.layout.container.border.Region.**

**Parameters:** weight : NumberThe new `weight` value.


### setSize

Sets the width and height of this Component. ...

Sets the width and height of this Component. This method fires the resize event. This method can accept either width and height as separate arguments, or you can pass a size object like `{width:10, height:20}`.

**Parameters:** - width : Number/String/ObjectThe new width to set. This may be one of: A Number specifying the new width in the Element's Ext.Element.defaultUnits (by default, pixels). - A String used to set the CSS width style. - A size object in the format `{width: widthValue, height: heightValue}`. - `undefined` to leave the width unchanged.


### setTitle

Set a title for the panel's header. ...

Set a title for the panel's header. See Ext.panel.Header.title.

**Parameters:** newTitle : String


### setUI

Sets the UI for the component. ...

Sets the UI for the component. This will remove any existing UIs on the component. It will also loop through any `uiCls` set on the component and rename them so they include the new UI.

**Parameters:** ui : StringThe new UI for the component.


### setVisible

Convenience function to hide or show this component by Boolean. ...

Convenience function to hide or show this component by Boolean. Available since: 1.1.0

**Parameters:** visible : Boolean`true` to show, `false` to hide.


### setWidth

Sets the width of the component. ...

Sets the width of the component. This method fires the resize event.

**Parameters:** - width : NumberThe new width to setThis may be one of: A Number specifying the new width in the Element's Ext.Element.defaultUnits (by default, pixels). - A String used to set the CSS width style.


### setX

Sets the X position of the DOM element based on page coordinates. ...

Sets the X position of the DOM element based on page coordinates.

**Parameters:** The : NumberX position


### setXY

Sets the position of the DOM element in page coordinates. ...

Sets the position of the DOM element in page coordinates.

**Parameters:** pos : Number[]Contains X & Y [x, y] values for new position (coordinates are page-based)


### setY

Sets the Y position of the DOM element based on page coordinates. ...

Sets the Y position of the DOM element based on page coordinates.

**Parameters:** The : NumberY position


### setZIndex

z-index is managed by the zIndexManager and may be overwritten at any time. ...

z-index is managed by the zIndexManager and may be overwritten at any time.

**Parameters:** index : Object

**Returns:** the next z-index to be used. If this is a Container, then it will have rebased any managed floating Components, and so the next available z-index will be approximately 10000 above that.


### setupDockingRenderTpl

...

**Parameters:** renderTpl : Object


### setupFramingTpl

Inject a reference to the function which applies the render template into the framing template. ...

Inject a reference to the function which applies the render template into the framing template. The framing template wraps the content.

**Parameters:** frameTpl : Object


### setupProtoEl

...


### setupRenderTpl

...

**Parameters:** renderTpl : Object


### show

Shows this Component, rendering it first if autoRender or floating are true. ...

Shows this Component, rendering it first if autoRender or floating are `true`. After being shown, a floating Component (such as a Ext.window.Window), is activated it and brought to the front of its z-index stack.

**Parameters:** animateTarget : String/Ext.Element (optional)only valid for floating Components such as Windows or ToolTips, or regular Components which have been configured with `floating: true`. The target from which the Component should animate from while opening. Defaults to: `null`


### showAt

Displays component at specific xy position. ...

Displays component at specific xy position. A floating component (like a menu) is positioned relative to its ownerCt if any. Useful for popping up a context menu:

**Parameters:** x : Number/Number[]The new x position or array of `[x,y]`.


### showBy

Shows this component by the specified Component or Element. ...

Shows this component by the specified Component or Element. Used when this component is floating.

**Parameters:** component : Ext.Component/Ext.dom.ElementThe Ext.Component or Ext.Element to show the component by.


### showMenuBy

...

**Parameters:** t : Object


### slideOutFloatedPanel

...


### slideOutFloatedPanelBegin

This method begins the slide out of the floated panel. ...

This method begins the slide out of the floated panel.


### slideOutFloatedPanelEnd

This method cleans up after the slide out of the floated panel. ...

This method cleans up after the slide out of the floated panel.


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### stopAnimation

Stops any running effects and clears this object's internal effects queue if it contains any additional effects that ...

Stops any running effects and clears this object's internal effects queue if it contains any additional effects that haven't started yet.

**Returns:** Ext.ElementThe Element


### stopFx

Stops any running effects and clears this object's internal effects queue if it contains any additional effects that ...

Stops any running effects and clears this object's internal effects queue if it contains any additional effects that haven't started yet. This method has been **deprecated** since 4.0 Replaced by stopAnimation


### suspendEvent

Suspends firing of the named event(s). ...

Suspends firing of the named event(s). After calling this method to suspend events, the events will no longer fire when requested to fire. Note that if this is called multiple times for a certain event, the converse method resumeEvent will have to be called the same number of times for it to resume firing.

**Parameters:** eventName : String...Multiple event names to suspend.


### suspendEvents

Suspends the firing of all events. ...

Suspends the firing of all events. (see resumeEvents)

**Parameters:** queueSuspended : BooleanPass as true to queue up suspended events to be fired after the resumeEvents call instead of discarding all suspended events.


### suspendLayouts

...


### syncFx

Ensures that all effects queued after syncFx is called on this object are run concurrently. ...

Ensures that all effects queued after syncFx is called on this object are run concurrently. This is the opposite of sequenceFx.

**Returns:** Objectthis


### syncHidden

synchronizes the hidden state of this component with the state of its hierarchy ...

synchronizes the hidden state of this component with the state of its hierarchy


### syncHorizontalScroll

...

**Parameters:** left : Object


### syncLockedWidth

Updates the overall view after columns have been resized, or moved from the locked to unlocked side or vice-versa. ...

Updates the overall view after columns have been resized, or moved from the locked to unlocked side or vice-versa. If all columns are removed from either side, that side must be hidden, and the sole remaining column owning grid then becomes *the* grid. It must flex to occupy the whole of the locking view. And it must also allow scrolling. If columns are shared between the two sides, the *locked* grid shrinkwraps the width of the visible locked columns while the normal grid flexes in what space remains.

**Returns:** Boolean`true` if there are visible locked columns which need refreshing.


### syncRowHeights

Synchronizes the row heights between the locked and non locked portion of the grid for each row. ...

Synchronizes the row heights between the locked and non locked portion of the grid for each row. If one row is smaller than the other, the height will be increased to match the larger one.


### syncShadow

...


### toBack

Sends this Component to the back of (lower z-index than) any other visible windows ...

Sends this Component to the back of (lower z-index than) any other visible windows

**Returns:** Ext.Componentthis


### toFront

Brings this floating Component to the front of any other visible, floating Components managed by the same ZIndexManag...

Brings this floating Component to the front of any other visible, floating Components managed by the same ZIndexManager If this Component is modal, inserts the modal mask just below this Component in the z-index stack.

**Parameters:** preventFocus : Boolean (optional)Specify `true` to prevent the Component from being focused. Defaults to: `false`


### toggleCollapse

Shortcut for performing an expand or collapse based on the current state of the panel. ...

Shortcut for performing an expand or collapse based on the current state of the panel.

**Returns:** Ext.panel.Panelthis


### translatePoints

Translates the passed page coordinates into left/top css values for the element ...

Translates the passed page coordinates into left/top css values for the element

**Parameters:** x : Number/ArrayThe page x or an array containing [x, y]


### translateXY

Translates the passed page coordinates into x and y css values for the element ...

Translates the passed page coordinates into x and y css values for the element

**Parameters:** x : Number/ArrayThe page x or an array containing [x, y]


### un

Shorthand for removeListener. ...

Shorthand for removeListener. Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### unbindStore

...


### unghost

...

**Parameters:** show : Object


### unitizeBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** box : Object


### unlock

Unlocks the activeHeader as determined by which menu is open OR a header as specified. ...

Unlocks the activeHeader as determined by which menu is open OR a header as specified.

**Parameters:** header : Ext.grid.column.Column (optional)Header to unlock from the locked section. Defaults to the header which has the menu open currently.


### unmask

...


### unregisterFloatingItem

...

**Parameters:** cmp : Object


### up

Navigates up the ownership hierarchy searching for an ancestor Container which matches any passed simple selector or ...

Navigates up the ownership hierarchy searching for an ancestor Container which matches any passed simple selector or component. *Important.* There is not a universal upwards navigation pointer. There are several upwards relationships such as the button which activates a menu, or the menu item which activated a submenu, or the column header which activated the column menu. These differences are abstracted away by this method. Example:

**Parameters:** selector : String/Ext.Component (optional)The simple selector component or actual component to test. If not passed the immediate owner/activater is returned.


### update

Update the content area of a component. ...

Update the content area of a component. Available since: 3.4.0

**Parameters:** htmlOrData : String/ObjectIf this component has been configured with a template via the tpl config then it will use this argument as data to populate the template. If this component was not configured with a template, the components content area will be updated via Ext.Element update.


### updateAria

Injected as an override by Ext.Aria.initialize ...

Injected as an override by Ext.Aria.initialize


### updateBox

Sets the current box measurements of the component's underlying element. ...

Sets the current box measurements of the component's underlying element.

**Parameters:** box : ObjectAn object in the format {x, y, width, height}


### updateCollapseTool

...


### updateFrame

...


### updateHeader

Create, hide, or show the header component as appropriate based on the current config. ...

Create, hide, or show the header component as appropriate based on the current config.

**Parameters:** force : BooleanTrue to force the header to be created


### updateLayout

Updates this component's layout. ...

Updates this component's layout. If this update affects this components ownerCt, that component's `updateLayout` method will be called to perform the layout instead. Otherwise, just this component (and its child items) will layout.

**Parameters:** options : Object (optional)An object with layout options. defer : Boolean`true` if this layout should be deferred.


### wrapPrimaryEl

...

**Parameters:** dom : Object


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


### activate

Fires after a Component has been visually activated. ...

Fires after a Component has been visually activated.

**Parameters:** this : Ext.Component


### add

Fires after any Ext.Component is added or inserted into the container. ...

Fires after any Ext.Component is added or inserted into the container. **This event bubbles:** 'add' will also be fired when Component is added to any of the child containers or their childern or ... Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### added

Fires after a Component had been added to a Container. ...

Fires after a Component had been added to a Container. Available since: 3.4.0

**Parameters:** this : Ext.Component


### afterlayout

Fires when the components in this container are arranged by the associated layout manager. ...

Fires when the components in this container are arranged by the associated layout manager. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### afterrender

Fires after the component rendering is finished. ...

Fires after the component rendering is finished. The `afterrender` event is fired after this Component has been rendered, been postprocessed by any `afterRender` method defined for the Component. Available since: 3.4.0

**Parameters:** this : Ext.Component


### beforeactivate

Fires before a Component has been visually activated. ...

Fires before a Component has been visually activated. Returning `false` from an event listener can prevent the activate from occurring.

**Parameters:** this : Ext.Component


### beforeadd

Fires before any Ext.Component is added or inserted into the container. ...

Fires before any Ext.Component is added or inserted into the container. A handler can return false to cancel the add. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### beforecellclick

Fired before the cell click is processed. ...

Fired before the cell click is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellcontextmenu

Fired before the cell right click is processed. ...

Fired before the cell right click is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecelldblclick

Fired before the cell double click is processed. ...

Fired before the cell double click is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellkeydown

Fired before the cell key down is processed. ...

Fired before the cell key down is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellmousedown

Fired before the cell mouse down is processed. ...

Fired before the cell mouse down is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellmouseup

Fired before the cell mouse up is processed. ...

Fired before the cell mouse up is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforeclose

Fires before the user closes the panel. ...

Fires before the user closes the panel. Return false from any listener to stop the close event being fired

**Parameters:** panel : Ext.panel.PanelThe Panel object


### beforecollapse

Fires before this panel is collapsed. ...

Fires before this panel is collapsed. Return false to prevent the collapse.

**Parameters:** p : Ext.panel.PanelThe Panel being collapsed.


### beforecontainerclick

Fires before the click event on the container is processed. ...

Fires before the click event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainercontextmenu

Fires before the contextmenu event on the container is processed. ...

Fires before the contextmenu event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainerdblclick

Fires before the dblclick event on the container is processed. ...

Fires before the dblclick event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermousedown

Fires before the mousedown event on the container is processed. ...

Fires before the mousedown event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermouseout

Fires before the mouseout event on the container is processed. ...

Fires before the mouseout event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermouseover

Fires before the mouseover event on the container is processed. ...

Fires before the mouseover event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermouseup

Fires before the mouseup event on the container is processed. ...

Fires before the mouseup event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforedeactivate

Fires before a Component has been visually deactivated. ...

Fires before a Component has been visually deactivated. Returning `false` from an event listener can prevent the deactivate from occurring.

**Parameters:** this : Ext.Component


### beforedeselect

Fired before a record is deselected. ...

Fired before a record is deselected. If any listener returns false, the deselection is cancelled.

**Parameters:** this : Ext.selection.RowModel


### beforedestroy

Fires before the component is destroyed. ...

Fires before the component is destroyed. Return `false` from an event handler to stop the destroy. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeexpand

Fires before this panel is expanded. ...

Fires before this panel is expanded. Return false to prevent the expand.

**Parameters:** p : Ext.panel.PanelThe Panel being expanded.


### beforehide

Fires before the component is hidden when calling the hide method. ...

Fires before the component is hidden when calling the hide method. Return `false` from an event handler to stop the hide. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeitemclick

Fires before the click event on an item is processed. ...

Fires before the click event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemcontextmenu

Fires before the contextmenu event on an item is processed. ...

Fires before the contextmenu event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemdblclick

Fires before the dblclick event on an item is processed. ...

Fires before the dblclick event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmousedown

Fires before the mousedown event on an item is processed. ...

Fires before the mousedown event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmouseenter

Fires before the mouseenter event on an item is processed. ...

Fires before the mouseenter event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmouseleave

Fires before the mouseleave event on an item is processed. ...

Fires before the mouseleave event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmouseup

Fires before the mouseup event on an item is processed. ...

Fires before the mouseup event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeremove

Fires before any Ext.Component is removed from the container. ...

Fires before any Ext.Component is removed from the container. A handler can return false to cancel the remove. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### beforerender

Fires before the component is rendered. ...

Fires before the component is rendered. Return `false` from an event handler to stop the render. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeselect

Fired before a record is selected. ...

Fired before a record is selected. If any listener returns false, the selection is cancelled.

**Parameters:** this : Ext.selection.RowModel


### beforeshow

Fires before the component is shown when calling the show method. ...

Fires before the component is shown when calling the show method. Return `false` from an event handler to stop the show. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforestaterestore

Fires before the state of the object is restored. ...

Fires before the state of the object is restored. Return false from an event handler to stop the restore.

**Parameters:** this : Ext.state.Stateful


### beforestatesave

Fires before the state of the object is saved to the configured state provider. ...

Fires before the state of the object is saved to the configured state provider. Return false to stop the save.

**Parameters:** this : Ext.state.Stateful


### blur

Fires when this Component loses focus. ...

Fires when this Component loses focus.

**Parameters:** this : Ext.Component


### boxready

Fires one time - after the component has been laid out for the first time at its initial size. ...

Fires *one time* - after the component has been laid out for the first time at its initial size.

**Parameters:** this : Ext.Component


### cellclick

Fired when table cell is clicked. ...

Fired when table cell is clicked.

**Parameters:** this : Ext.view.Table


### cellcontextmenu

Fired when table cell is right clicked. ...

Fired when table cell is right clicked.

**Parameters:** this : Ext.view.Table


### celldblclick

Fired when table cell is double clicked. ...

Fired when table cell is double clicked.

**Parameters:** this : Ext.view.Table


### cellkeydown

Fired when the keydown event is captured on the cell. ...

Fired when the keydown event is captured on the cell.

**Parameters:** this : Ext.view.Table


### cellmousedown

Fired when the mousedown event is captured on the cell. ...

Fired when the mousedown event is captured on the cell.

**Parameters:** this : Ext.view.Table


### cellmouseup

Fired when the mouseup event is captured on the cell. ...

Fired when the mouseup event is captured on the cell.

**Parameters:** this : Ext.view.Table


### close

Fires when the user closes the panel. ...

Fires when the user closes the panel.

**Parameters:** panel : Ext.panel.PanelThe Panel object


### collapse

Fires after this Panel has collapsed. ...

Fires after this Panel has collapsed.

**Parameters:** p : Ext.panel.PanelThe Panel that has been collapsed.


### columnhide

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnmove

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnresize

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnschanged

Fired after the columns change in any way, when a column has been hidden or shown, or when a column is added to or re...

Fired after the columns change in any way, when a column has been hidden or shown, or when a column is added to or removed from this header container.

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnshow

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### containerclick

Fires when the container is clicked. ...

Fires when the container is clicked.

**Parameters:** this : Ext.view.View


### containercontextmenu

Fires when the container is right clicked. ...

Fires when the container is right clicked.

**Parameters:** this : Ext.view.View


### containerdblclick

Fires when the container is double clicked. ...

Fires when the container is double clicked.

**Parameters:** this : Ext.view.View


### containermouseout

Fires when you move the mouse out of the container. ...

Fires when you move the mouse out of the container.

**Parameters:** this : Ext.view.View


### containermouseover

Fires when you move the mouse over the container. ...

Fires when you move the mouse over the container.

**Parameters:** this : Ext.view.View


### containermouseup

Fires when there is a mouse up on the container ...

Fires when there is a mouse up on the container

**Parameters:** this : Ext.view.View


### deactivate

Fires after a Component has been visually deactivated. ...

Fires after a Component has been visually deactivated.

**Parameters:** this : Ext.Component


### deselect

Fired after a record is deselected ...

Fired after a record is deselected

**Parameters:** this : Ext.selection.RowModel


### destroy

Fires after the component is destroyed. ...

Fires after the component is destroyed. Available since: 1.1.0

**Parameters:** this : Ext.Component


### disable

Fires after the component is disabled. ...

Fires after the component is disabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### dockedadd

Fires when any Ext.Component is added or inserted as a docked item. ...

Fires when any Ext.Component is added or inserted as a docked item.

**Parameters:** this : Ext.panel.Panel


### dockedremove

Fires when any Ext.Component is removed from the docked items. ...

Fires when any Ext.Component is removed from the docked items.

**Parameters:** this : Ext.panel.Panel


### enable

Fires after the component is enabled. ...

Fires after the component is enabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### expand

Fires after this Panel has expanded. ...

Fires after this Panel has expanded.

**Parameters:** p : Ext.panel.PanelThe Panel that has been expanded.


### filterchange

Fired whenever the filter set changes. ...

Fired whenever the filter set changes.

**Parameters:** store : Ext.data.StoreThe store.


### float

Fires after a collapsed Panel has been "floated" by clicking on it's header. ...

Fires after a collapsed Panel has been "floated" by clicking on it's header. Only applicable when the Panel is an item in a Border Layout.

**Parameters:** eOpts : ObjectThe options object passed to Ext.util.Observable.addListener.


### focus

Fires when this Component receives focus. ...

Fires when this Component receives focus.

**Parameters:** this : Ext.Component


### glyphchange

Fired when the Panel glyph has been changed by the setGlyph method. ...

Fired when the Panel glyph has been changed by the setGlyph method.

**Parameters:** this : Ext.panel.Panel


### headerclick

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### headercontextmenu

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### headertriggerclick

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### hide

Fires after the component is hidden. ...

Fires after the component is hidden. Fires after the component is hidden when calling the hide method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### iconchange

Fires after the Panel icon has been set or changed. ...

Fires after the Panel icon has been set or changed.

**Parameters:** p : Ext.panel.PanelThe Panel which has the icon changed.


### iconclschange

Fires after the Panel iconCls has been set or changed. ...

Fires after the Panel iconCls has been set or changed.

**Parameters:** p : Ext.panel.PanelThe Panel which has the iconCls changed.


### itemclick

Fires when an item is clicked. ...

Fires when an item is clicked.

**Parameters:** this : Ext.view.View


### itemcontextmenu

Fires when an item is right clicked. ...

Fires when an item is right clicked.

**Parameters:** this : Ext.view.View


### itemdblclick

Fires when an item is double clicked. ...

Fires when an item is double clicked.

**Parameters:** this : Ext.view.View


### itemmousedown

Fires when there is a mouse down on an item ...

Fires when there is a mouse down on an item

**Parameters:** this : Ext.view.View


### itemmouseenter

Fires when the mouse enters an item. ...

Fires when the mouse enters an item.

**Parameters:** this : Ext.view.View


### itemmouseleave

Fires when the mouse leaves an item. ...

Fires when the mouse leaves an item.

**Parameters:** this : Ext.view.View


### itemmouseup

Fires when there is a mouse up on an item ...

Fires when there is a mouse up on an item

**Parameters:** this : Ext.view.View


### lockcolumn

Fires when a column is locked. ...

Fires when a column is locked.

**Parameters:** this : Ext.grid.PanelThe gridpanel.


### move

Fires after the component is moved. ...

Fires after the component is moved.

**Parameters:** this : Ext.Component


### processcolumns

Fires when the configured (or reconfigured) column set is split into two depending on the locked flag. ...

Fires when the configured (or **reconfigured**) column set is split into two depending on the locked flag.

**Parameters:** lockedColumns : Ext.grid.column.Column[]The locked columns.


### remove

Fires after any Ext.Component is removed from the container. ...

Fires after any Ext.Component is removed from the container. **This event bubbles:** 'remove' will also be fired when Component is removed from any of the child containers or their children or ... Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### removed

Fires when a component is removed from an Ext.container.Container ...

Fires when a component is removed from an Ext.container.Container Available since: 3.4.0

**Parameters:** this : Ext.Component


### render

Fires after the component markup is rendered. ...

Fires after the component markup is rendered. Available since: 1.1.0

**Parameters:** this : Ext.Component


### resize

Fires after the component is resized. ...

Fires after the component is resized. Note that this does *not* fire when the component is first laid out at its initial size. To hook that point in the life cycle, use the boxready event.

**Parameters:** this : Ext.Component


### select

Fired after a record is selected ...

Fired after a record is selected

**Parameters:** this : Ext.selection.RowModel


### selectionchange

Fired after a selection change has occurred ...

Fired after a selection change has occurred

**Parameters:** this : Ext.selection.Model


### show

Fires after the component is shown when calling the show method. ...

Fires after the component is shown when calling the show method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### sortchange

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### staterestore

Fires after the state of the object is restored. ...

Fires after the state of the object is restored.

**Parameters:** this : Ext.state.Stateful


### statesave

Fires after the state of the object is saved to the configured state provider. ...

Fires after the state of the object is saved to the configured state provider.

**Parameters:** this : Ext.state.Stateful


### titlechange

Fires after the Panel title has been set or changed. ...

Fires after the Panel title has been set or changed.

**Parameters:** p : Ext.panel.Panelthe Panel which has been resized.


### unfloat

Fires after a "floated" Panel has returned to it's collapsed state as a result of the mouse leaving the Panel. ...

Fires after a "floated" Panel has returned to it's collapsed state as a result of the mouse leaving the Panel. Only applicable when the Panel is an item in a Border Layout.

**Parameters:** eOpts : ObjectThe options object passed to Ext.util.Observable.addListener.


### unlockcolumn

Fires when a column is unlocked. ...

Fires when a column is unlocked.

**Parameters:** this : Ext.grid.PanelThe gridpanel.


### viewready

Fires when the grid view is available (use this for selecting a default row). ...

Fires when the grid view is available (use this for selecting a default row).

**Parameters:** this : Ext.panel.Table


### $border-width-threshold

**Type:** $border-width-threshold

The maximum width a Panel's border can be before resizer handles are embedded into the borders using negative absolut...

The maximum width a Panel's border can be before resizer handles are embedded into the borders using negative absolute positions. This defaults to 2, so that in the classic theme which uses 1 pixel borders, resize handles are in the content area within the border as they always have been. In the Neptune theme, the handles are embedded into the 5 pixel wide borders of any framed panel. Defaults to: `2`


### $grid-body-background-color

**Type:** color

The background-color of the grid body ...

The background-color of the grid body Defaults to: `$panel-body-background-color`


### $grid-body-border-color

**Type:** color

The border-color of the grid body ...

The border-color of the grid body Defaults to: `$panel-body-border-color`


### $grid-body-border-style

**Type:** string

The border-style of the grid body border ...

The border-style of the grid body border Defaults to: `$panel-body-border-style`


### $grid-body-border-width

**Type:** number

The border-width of the grid body border ...

The border-width of the grid body border Defaults to: `$panel-body-border-width`


### $grid-cell-inner-padding

**Type:** number

The amount of padding to apply to the grid cell's inner div element ...

The amount of padding to apply to the grid cell's inner div element Defaults to: `3px 6px`


### $grid-cell-inner-text-overflow

**Type:** string

The type of text-overflow to use on the grid cell's inner div element ...

The type of text-overflow to use on the grid cell's inner div element Defaults to: `ellipsis`


### $grid-cell-selected-background-color

**Type:** color

The background-color of a selected cell when using a Cell Selection Model. ...

The background-color of a selected cell when using a Cell Selection Model. Defaults to: `$grid-row-cell-selected-background-color`


### $grid-cell-selected-color

**Type:** color

The text color of a selected cell when using a Cell Selection Model. ...

The text color of a selected cell when using a Cell Selection Model. Defaults to: `$grid-row-cell-selected-color`


### $grid-cell-special-background-color

**Type:** color

The background-color of "special" cells. ...

The background-color of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `$grid-row-cell-background-color`


### $grid-cell-special-background-gradient

**Type:** string

The background-gradient to use for "special" cells. ...

The background-gradient to use for "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `null`


### $grid-cell-special-border-color

**Type:** color

The border-color of "special" cells. ...

The border-color of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border color is determined by {#$grid-row-cell-border-color}. Defaults to: `$grid-row-cell-border-color`


### $grid-cell-special-border-style

**Type:** string

The border-style of "special" cells. ...

The border-style of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border style is determined by {#$grid-row-cell-border-style}. Defaults to: `$grid-row-cell-border-style`


### $grid-cell-special-border-width

**Type:** number

The border-width of "special" cells. ...

The border-width of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border width is determined by {#$grid-row-cell-border-width}. Defaults to: `$grid-row-cell-border-width`


### $grid-cell-special-over-background-color

**Type:** color

The background-color of "special" cells when the row is hovered. ...

The background-color of "special" cells when the row is hovered. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `$grid-row-cell-over-background-color`


### $grid-cell-special-selected-border-color

**Type:** color

The border-color of "special" cells when the row is selected using a Row Selection Model. ...

The border-color of "special" cells when the row is selected using a Row Selection Model. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the selected row border color is determined by {#$grid-row-cell-selected-border-color}. Defaults to: `$grid-row-cell-border-color`


### $grid-empty-background-color

**Type:** color

The background color of the grid body when the grid contains no data. ...

The background color of the grid body when the grid contains no data. Defaults to: `$panel-body-background-color`


### $grid-empty-color

**Type:** color

The text color of the emptyText in the grid body when the grid contains no data. ...

The text color of the emptyText in the grid body when the grid contains no data. Defaults to: `#808080`


### $grid-empty-font-family

**Type:** number

The font-family of the emptyText in the grid body when the grid contains no data. ...

The font-family of the emptyText in the grid body when the grid contains no data. Defaults to: `$font-family`


### $grid-empty-font-size

**Type:** number

The font-size of the emptyText in the grid body when the grid contains no data. ...

The font-size of the emptyText in the grid body when the grid contains no data. Defaults to: `$grid-row-cell-font-size`


### $grid-empty-font-weight

**Type:** number

The font-weight of the emptyText in the grid body when the grid contains no data. ...

The font-weight of the emptyText in the grid body when the grid contains no data. Defaults to: `normal`


### $grid-empty-padding

**Type:** number

The amount of padding to apply to the grid body when the grid contains no data. ...

The amount of padding to apply to the grid body when the grid contains no data. Defaults to: `10px`


### $grid-lockable-separator-border-style

**Type:** string

The border-style of the border between the locked views ...

The border-style of the border between the locked views Defaults to: `solid`


### $grid-lockable-separator-border-width

**Type:** number

The width of the border between the locked views ...

The width of the border between the locked views Defaults to: `1px`


### $grid-no-row-lines-show-focus-border

**Type:** boolean

True to show the focus border when a row is focused even if the grid has no rowLines. ...

True to show the focus border when a row is focused even if the grid has no rowLines. Defaults to: `false`


### $grid-resize-marker-background-color

**Type:** color

The color of the resize markers that display when dragging a column border to resize the column ...

The color of the resize markers that display when dragging a column border to resize the column Defaults to: `#0f0f0f`


### $grid-row-cell-alt-background-color

**Type:** color

The background-color color of odd-numbered rows when the table view is configured with stripeRows: true. ...

The background-color color of odd-numbered rows when the table view is configured with `stripeRows: true`. Defaults to: `darken ( $grid-row-cell-background-color , 2 )`


### $grid-row-cell-background-color

**Type:** color

The background-color of the grid cells ...

The background-color of the grid cells Defaults to: `#fff`


### $grid-row-cell-border-color

**Type:** color

The border-color of row/column borders. ...

The border-color of row/column borders. Can be specified as a single color, or as a list of colors containing the row border color followed by the column border color. Defaults to: `#ededed`


### $grid-row-cell-border-style

**Type:** string

The border-style of the row/column borders. ...

The border-style of the row/column borders. Defaults to: `solid`


### $grid-row-cell-border-width

**Type:** number

The border-width of the row and column borders. ...

The border-width of the row and column borders. Defaults to: `1px`


### $grid-row-cell-color

**Type:** color

The color of the text in the grid cells ...

The color of the text in the grid cells Defaults to: `null`


### $grid-row-cell-focus-background-color

**Type:** color

The background-color of the focused row ...

The background-color of the focused row Defaults to: `$grid-row-cell-background-color`


### $grid-row-cell-focus-border-color

**Type:** color

The border-color of the focused row ...

The border-color of the focused row Defaults to: `#808080`


### $grid-row-cell-focus-border-style

**Type:** string

The border-style of the focused row ...

The border-style of the focused row Defaults to: `dotted`


### $grid-row-cell-focus-color

**Type:** color

The text color of the focused row ...

The text color of the focused row Defaults to: `$grid-row-cell-color`


### $grid-row-cell-font-family

**Type:** string

The font-family of the text in the grid cells ...

The font-family of the text in the grid cells Defaults to: `$font-family`


### $grid-row-cell-font-size

**Type:** number

The font size of the text in the grid cells ...

The font size of the text in the grid cells Defaults to: `$font-size`


### $grid-row-cell-font-weight

**Type:** string

The font-weight of the text in the grid cells ...

The font-weight of the text in the grid cells Defaults to: `normal`


### $grid-row-cell-line-height

**Type:** Object

var {number} $grid-row-cell-line-height The line-height of the text inside the grid cells. ...

var {number} $grid-row-cell-line-height The line-height of the text inside the grid cells. Defaults to: `round ( $grid-row-cell-font-size * 1.15 )`


### $grid-row-cell-over-background-color

**Type:** color

The background-color of the hovered row ...

The background-color of the hovered row Defaults to: `#ddd`


### $grid-row-cell-over-border-color

**Type:** color

The border-color of the hovered row ...

The border-color of the hovered row Defaults to: `$grid-row-cell-border-color`


### $grid-row-cell-over-border-style

**Type:** string

The border-style of the hovered row ...

The border-style of the hovered row Defaults to: `solid`


### $grid-row-cell-over-color

**Type:** color

The text color of the hovered row ...

The text color of the hovered row Defaults to: `$grid-row-cell-color`


### $grid-row-cell-selected-background-color

**Type:** color

The background-color of the selected row ...

The background-color of the selected row Defaults to: `#ccc`


### $grid-row-cell-selected-border-color

**Type:** color

The border-color of the selected row ...

The border-color of the selected row Defaults to: `$grid-row-cell-border-color`


### $grid-row-cell-selected-border-style

**Type:** string

The border-style of the selected row ...

The border-style of the selected row Defaults to: `solid`


### $grid-row-cell-selected-color

**Type:** color

The text color of the selected row ...

The text color of the selected row Defaults to: `$grid-row-cell-color`


### $include-panel-default-framed-ui

**Type:** boolean

True to include the "default-framed" panel UI ...

True to include the "default-framed" panel UI Defaults to: `$include-default-uis`


### $include-panel-default-ui

**Type:** boolean

True to include the "default" panel UI ...

True to include the "default" panel UI Defaults to: `$include-default-uis`


### $panel-background-stretch-bottom

**Type:** string

The direction to strech the background-gradient of bottom docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of bottom docked Headers when slicing images for IE using Sencha Cmd Defaults to: `top`


### $panel-background-stretch-left

**Type:** string

The direction to strech the background-gradient of left docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of left docked Headers when slicing images for IE using Sencha Cmd Defaults to: `right`


### $panel-background-stretch-right

**Type:** string

The direction to strech the background-gradient of right docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of right docked Headers when slicing images for IE using Sencha Cmd Defaults to: `left`


### $panel-background-stretch-top

**Type:** string

The direction to strech the background-gradient of top docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of top docked Headers when slicing images for IE using Sencha Cmd Defaults to: `bottom`


### $panel-base-color

**Type:** color

The base color of Panels ...

The base color of Panels Defaults to: `$base-color`


### $panel-body-background-color

**Type:** color

The default body background-color of Panels ...

The default body background-color of Panels Defaults to: `#fff`


### $panel-body-border-color

**Type:** color

The default border-color of the Panel body ...

The default border-color of the Panel body Defaults to: `$panel-border-color`


### $panel-body-border-style

**Type:** string

The default border-style of Panels ...

The default border-style of Panels Defaults to: `solid`


### $panel-body-border-width

**Type:** number

The default border-width of the Panel body ...

The default border-width of the Panel body Defaults to: `1px`


### $panel-body-color

**Type:** color

The default color of text inside a Panel's body ...

The default color of text inside a Panel's body Defaults to: `#000`


### $panel-body-font-size

**Type:** number

The default font-size of the Panel body ...

The default font-size of the Panel body Defaults to: `$font-size`


### $panel-body-font-weight

**Type:** string

The default font-weight of the Panel body ...

The default font-weight of the Panel body Defaults to: `normal`


### $panel-border-color

**Type:** color

The default border-color of Panels ...

The default border-color of Panels Defaults to: `$panel-base-color`


### $panel-border-width

**Type:** number

The default border-width of Panels ...

The default border-width of Panels Defaults to: `1px`


### $panel-frame-background-color

**Type:** color

The background-color of framed Panels ...

The background-color of framed Panels Defaults to: `#fff`


### $panel-frame-base-color

**Type:** color

The base color of the framed Panels ...

The base color of the framed Panels Defaults to: `$panel-base-color`


### $panel-frame-body-border-width

**Type:** number

The border-width of the body element of framed Panels ...

The border-width of the body element of framed Panels Defaults to: `1px`


### $panel-frame-border-color

**Type:** color

The border-color of framed Panels ...

The border-color of framed Panels Defaults to: `$panel-border-color`


### $panel-frame-border-radius

**Type:** number

The border-radius of framed Panels ...

The border-radius of framed Panels Defaults to: `4px`


### $panel-frame-border-style

**Type:** string

The border-style of framed Panels ...

The border-style of framed Panels Defaults to: `solid`


### $panel-frame-border-width

**Type:** number

The border-width of framed Panels ...

The border-width of framed Panels Defaults to: `1px`


### $panel-frame-header-border-width

**Type:** number

The border-width of framed Panel Headers ...

The border-width of framed Panel Headers Defaults to: `$panel-header-border-width`


### $panel-frame-header-inner-border-color

**Type:** color

The inner border-color of framed Panel Headers ...

The inner border-color of framed Panel Headers Defaults to: `#fff`


### $panel-frame-header-inner-border-width

**Type:** number

The inner border-width of framed Panel Headers ...

The inner border-width of framed Panel Headers Defaults to: `0`


### $panel-frame-header-padding

**Type:** number/list

The padding of framed Panel Headers ...

The padding of framed Panel Headers Defaults to: `$panel-header-padding`


### $panel-frame-padding

**Type:** number

The padding of framed Panels ...

The padding of framed Panels Defaults to: `4px`


### $panel-ghost-opacity

**Type:** number

The opacity of ghost Panels while dragging ...

The opacity of ghost Panels while dragging Defaults to: `0.50`


### $panel-header-background-color

**Type:** color

The background-color of the Panel Header ...

The background-color of the Panel Header Defaults to: `$panel-base-color`


### $panel-header-background-gradient

**Type:** string/list

The background-gradient of the Panel Header. ...

The background-gradient of the Panel Header. Can be either the name of a predefined gradient or a list of color stops. Used as the `$type` parameter for Global_CSS.background-gradient. Defaults to: `null`


### $panel-header-border-color

**Type:** color

The border-color of the Panel Header ...

The border-color of the Panel Header Defaults to: `$panel-border-color`


### $panel-header-border-style

**Type:** string

The border-style of Panel Headers ...

The border-style of Panel Headers Defaults to: `solid`


### $panel-header-border-width

**Type:** number

The border-width of Panel Headers ...

The border-width of Panel Headers Defaults to: `$panel-border-width`


### $panel-header-color

**Type:** color

The text color of the Panel Header ...

The text color of the Panel Header Defaults to: `$color`


### $panel-header-font-family

**Type:** string

The font-family of Panel Headers ...

The font-family of Panel Headers Defaults to: `$font-family`


### $panel-header-font-size

**Type:** number

The font-size of Panel Headers ...

The font-size of Panel Headers Defaults to: `$font-size`


### $panel-header-font-weight

**Type:** string

The font-weight of Panel Headers ...

The font-weight of Panel Headers Defaults to: `bold`


### $panel-header-glyph-color

**Type:** color

The color of the Panel Header glyph icon ...

The color of the Panel Header glyph icon Defaults to: `$panel-header-color`


### $panel-header-glyph-opacity

**Type:** number

The opacity of the Panel Header glyph icon ...

The opacity of the Panel Header glyph icon Defaults to: `.5`


### $panel-header-icon-background-position

**Type:** list

The background-position of the Panel Header icon ...

The background-position of the Panel Header icon Defaults to: `center center`


### $panel-header-icon-height

**Type:** number

The height of the Panel Header icon ...

The height of the Panel Header icon Defaults to: `16px`


### $panel-header-icon-spacing

**Type:** number

The space between the Panel Header icon and text ...

The space between the Panel Header icon and text Defaults to: `4px`


### $panel-header-icon-width

**Type:** number

The width of the Panel Header icon ...

The width of the Panel Header icon Defaults to: `16px`


### $panel-header-inner-border-color

**Type:** color

The inner border-color of the Panel Header ...

The inner border-color of the Panel Header Defaults to: `#fff`


### $panel-header-inner-border-width

**Type:** number

The inner border-width of the Panel Header ...

The inner border-width of the Panel Header Defaults to: `0`


### $panel-header-line-height

**Type:** number

The line-height of Panel Headers ...

The line-height of Panel Headers Defaults to: `16px`


### $panel-header-padding

**Type:** number/list

The padding of Panel Headers ...

The padding of Panel Headers Defaults to: `4px 5px`


### $panel-header-text-padding

**Type:** number/list

The padding of the Panel Header's text element ...

The padding of the Panel Header's text element Defaults to: `0`


### $panel-header-text-transform

**Type:** string

The text-transform of Panel Headers ...

The text-transform of Panel Headers Defaults to: `none`


### $panel-include-border-management-rules

**Type:** boolean

True to include neptune style border management rules. ...

True to include neptune style border management rules. Defaults to: `false`


### $panel-tool-background-image

**Type:** string

The background sprite to use for Panel Tools ...

The background sprite to use for Panel Tools Defaults to: `'tools/tool-sprites'`


### $panel-tool-spacing

**Type:** number

The space between the Panel Tools ...

The space between the Panel Tools Defaults to: `4px`


### $panel-wrap-border-color

**Type:** color

The color to apply to the border that wraps the body and docked items in a framed panel. ...

The color to apply to the border that wraps the body and docked items in a framed panel. The presence of the wrap border in a framed panel is controlled by the border config. Only applicable when `$panel-include-border-management-rules` is `true`. Defaults to: `$panel-border-color`


### $panel-wrap-border-width

**Type:** number

The width to apply to the border that wraps the body and docked items in a framed panel. ...

The width to apply to the border that wraps the body and docked items in a framed panel. The presence of the wrap border in a framed panel is controlled by the border config. Only applicable when `$panel-include-border-management-rules` is `true`. Defaults to: `1px`


### extjs-panel-ui

Creates a visual theme for a Panel ...

Creates a visual theme for a Panel $ui-label : stringThe name of the UI being created. Can not included spaces or special punctuation (used in CSS class names).


## Properties

### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### _alignRe

**Type:** RegExp

...

Defaults to: `/^([a-z]+)-([a-z]+)(\?)?$/`


### _isLayoutRoot

**Type:** Boolean

Setting this property to true causes the isLayoutRoot method to return true and stop the search for the top-most comp...

Setting this property to `true` causes the isLayoutRoot method to return `true` and stop the search for the top-most component for a layout. Defaults to: `false`


### _positionTopLeft

**Type:** Array

...

Defaults to: `['position', 'top', 'left']`


### allowDomMove

**Type:** Boolean

...

Defaults to: `true`


### autoGenId

**Type:** Boolean

true indicates an id was auto-generated rather than provided by configuration. ...

`true` indicates an `id` was auto-generated rather than provided by configuration. Defaults to: `false`


### body

**Type:** Ext.dom.Element

The Panel's body Element which may be used to contain HTML content. ...

The Panel's body Element which may be used to contain HTML content. The content may be specified in the html config, or it may be loaded using the loader config. Read-only. If this is used to load visible HTML elements in either way, then the Panel may not be used as a Layout for hosting nested Panels. If this Panel is intended to be used as the host of a Layout (See layout then the body Element must not be loaded or changed - it is under the control of the Panel's Layout.


### bodyPosProps

**Type:** Object

...

Defaults to: `{x: 'x', y: 'y'}`


### borderBoxCls

**Type:** String

private ...

private Defaults to: `Ext.baseCSSPrefix + 'border-box'`


### bothCfgCopy

**Type:** Array

Required for the Lockable Mixin. ...

Required for the Lockable Mixin. These are the configurations which will be copied to the normal and locked sub tablepanels Defaults to: `['invalidateScrollerOnRefresh', 'hideHeaders', 'enableColumnHide', 'enableColumnMove', 'enableColumnResize', 'sortableColumns', 'columnLines', 'rowLines']`


### bubbleEvents

**Type:** Array

...

Defaults to: `[]`


### childEls

**Type:** Array

...

Defaults to: `['body']` Overrides: Ext.util.ElementContainer.childEls


### componentLayoutCounter

**Type:** Number

The number of component layout calls made on this object. ...

The number of component layout calls made on this object. Defaults to: `0`


### configMap

**Type:** Object

...

Defaults to: `{}`


### contentPaddingProperty

**Type:** String

The name of the padding property that is used by the layout to manage padding. ...

The name of the padding property that is used by the layout to manage padding. See managePadding Defaults to: `'bodyPadding'` Overrides: Ext.AbstractComponent.contentPaddingProperty


### convertPositionSpec

**Type:** Object

By default this method does nothing but return the position spec passed to it. ...

By default this method does nothing but return the position spec passed to it. In rtl mode it is overridden to convert "l" to "r" and vice versa when required.


### dd

**Type:** Ext.dd.DragSource/Ext.util.ComponentDragger

Only present if this Panel has been configured with draggable true. ...

Only present if this Panel has been configured with draggable `true`. Simple dragging If this Panel is configured simpleDrag `true` (the default is `false`), this property will reference an instance of Ext.util.ComponentDragger (A subclass of DragTracker) which handles moving the Panel's DOM Element, and constraining according to the constrain and constrainHeader . This object fires various events during its lifecycle and during a drag operation. Complex dragging interacting with other DragDrop instances By default, this property in a draggable Panel will contain an instance of Ext.dd.DragSource which handles dragging the Panel. The developer must provide implementations of the abstract methods of Ext.dd.DragSource in order to supply behaviour for each stage of the drag/drop process. See draggable.


### defaultComponentLayoutType

**Type:** String

...

Defaults to: `'autocomponent'`


### deferLayouts

**Type:** Boolean

...

Defaults to: `false`


### dockOrder

**Type:** Object

Values to decide which side of the body element docked items must go This overides any weight. ...

Values to decide which side of the body element docked items must go This overides any weight. A left/top will *always* sort before a right/bottom regardless of any weight value. Weights sort at either side of the "body" dividing point.


### draggable

**Type:** Boolean

Indicates whether or not the component can be dragged. ...

Indicates whether or not the component can be dragged. Defaults to: `false`


### emptyArray

**Type:** Array

...

Defaults to: `[]`


### emptyCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid-empty'`


### eventsSuspended

**Type:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called. Defaults to: `0`


### extraBaseCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid'`


### extraBodyCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid-body'`


### floatParent

**Type:** Ext.Container

Only present for floating Components which were inserted as child items of Containers. ...

**Only present for floating Components which were inserted as child items of Containers.** There are other similar relationships such as the button which activates a menu, or the menu item which activated a submenu, or the column header which activated the column menu. These differences are abstracted away by the up method. Floating Components that are programatically rendered will not have a `floatParent` property. See floating and zIndexManager


### frameCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'frame'`


### frameElNames

**Type:** Array

...

Defaults to: `['TL', 'TC', 'TR', 'ML', 'MC', 'MR', 'BL', 'BC', 'BR']`


### frameElementsArray

**Type:** Array

...

Defaults to: `['tl', 'tc', 'tr', 'ml', 'mc', 'mr', 'bl', 'bc', 'br']`


### frameIdRegex

**Type:** RegExp

...

Defaults to: `/[\-]frame\d+[TMB][LCR]$/`


### frameInfoCache

**Type:** Object

Cache the frame information object so as not to cause style recalculations ...

Cache the frame information object so as not to cause style recalculations Defaults to: `{}`


### frameSize

**Type:** Object

Indicates the width of any framing elements which were added within the encapsulating element to provide graphical, r...

Indicates the width of any framing elements which were added within the encapsulating element to provide graphical, rounded borders. See the frame config. This property is `null` if the component is not framed. This is an object containing the frame width in pixels for all four sides of the Component containing the following properties: top : Number (optional)The width of the top framing element in pixels. Defaults to: `0`


### frameTableTpl

**Type:** Object


### frameTpl

**Type:** Array

...

Defaults to: `['{%this.renderDockedItems(out,values,0);%}', '<tpl if="top">', '<tpl if="left"><div id="{fgid}TL" class="{frameCls}-tl {baseCls}-tl {baseCls}-{ui}-tl<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-tl</tpl>{frameElCls}" role="presentation"></tpl>', '<tpl if="right"><div id="{fgid}TR" class="{frameCls}-tr {baseCls}-tr {baseCls}-{ui}-tr<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-tr</tpl>{frameElCls}" role="presentation"></tpl>', '<div id="{fgid}TC" class="{frameCls}-tc {baseCls}-tc {baseCls}-{ui}-tc<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-tc</tpl>{frameElCls}" role="presentation"></div>', '<tpl if="right"></div></tpl>', '<tpl if="left"></div></tpl>', '</tpl>', '<tpl if="left"><div id="{fgid}ML" class="{frameCls}-ml {baseCls}-ml {baseCls}-{ui}-ml<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-ml</tpl>{frameElCls}" role="presentation"></tpl>', '<tpl if="right"><div id="{fgid}MR" class="{frameCls}-mr {baseCls}-mr {baseCls}-{ui}-mr<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-mr</tpl>{frameElCls}" role="presentation"></tpl>', '<div id="{fgid}MC" class="{frameCls}-mc {baseCls}-mc {baseCls}-{ui}-mc<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-mc</tpl>{frameElCls}" role="presentation">', '{%this.applyRenderTpl(out, values)%}', '</div>', '<tpl if="right"></div></tpl>', '<tpl if="left"></div></tpl>', '<tpl if="bottom">', '<tpl if="left"><div id="{fgid}BL" class="{frameCls}-bl {baseCls}-bl {baseCls}-{ui}-bl<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-bl</tpl>{frameElCls}" role="presentation"></tpl>', '<tpl if="right"><div id="{fgid}BR" class="{frameCls}-br {baseCls}-br {baseCls}-{ui}-br<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-br</tpl>{frameElCls}" role="presentation"></tpl>', '<div id="{fgid}BC" class="{frameCls}-bc {baseCls}-bc {baseCls}-{ui}-bc<tpl for="uiCls"> {parent.baseCls}-{parent.ui}-{.}-bc</tpl>{frameElCls}" role="presentation"></div>', '<tpl if="right"></div></tpl>', '<tpl if="left"></div></tpl>', '</tpl>', '{%this.renderDockedItems(out,values,1);%}']`


### hasListeners

**Type:** Object

This object holds a key for any event that has a listener. ...

This object holds a key for any event that has a listener. The listener may be set directly on the instance, or on its class or a super class (via observe) or on the MVC EventBus. The values of this object are truthy (a non-zero number) and falsy (0 or undefined). They do not represent an exact count of listeners. The value for an event is truthy if the event must be fired and is falsy if there is no need to fire the event. The intended use of this property is to avoid the expense of fireEvent calls when there are no listeners. This can be particularly helpful when one would otherwise have to call fireEvent hundreds or thousands of times. It is used like this:


### hasView

**Type:** Boolean

True to indicate that a view has been injected into the panel. ...

True to indicate that a view has been injected into the panel. Defaults to: `false`


### hiddenHeaderCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid-header-hidden'`


### hiddenHeaderCtCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid-header-ct-hidden'`


### horizontalDocks

**Type:** Number

Number of dock 'left' and 'right' items. ...

Number of dock 'left' and 'right' items. Defaults to: `0`


### horizontalPosProp

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


### isAnimate

**Type:** Boolean

...

Defaults to: `true`


### isComponent

**Type:** Boolean

true in this class to identify an object as an instantiated Component, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Component, or subclass thereof. Defaults to: `true`


### isContainer

**Type:** Boolean

true in this class to identify an object as an instantiated Container, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Container, or subclass thereof. Defaults to: `true`


### isDockingContainer

**Type:** Boolean

End Definitions ...

End Definitions Defaults to: `true`


### isInstance

**Type:** Boolean

...

Defaults to: `true`


### isObservable

**Type:** Boolean

true in this class to identify an object as an instantiated Observable, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Observable, or subclass thereof. Defaults to: `true`


### isPanel

**Type:** Boolean

true in this class to identify an object as an instantiated Panel, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Panel, or subclass thereof. Defaults to: `true`


### isQueryable

**Type:** Boolean

...

Defaults to: `true`


### items

**Type:** Ext.util.AbstractMixedCollection

The MixedCollection containing all the child items of this container.

The MixedCollection containing all the child items of this container. Available since: 2.3.0


### layoutCounter

**Type:** Number

The number of container layout calls made on this object. ...

The number of container layout calls made on this object. Defaults to: `0`


### layoutSuspendCount

**Type:** Number

...

Defaults to: `0`


### lockText

**Type:** String

...

Defaults to: `'Lock'`


### lockedCfgCopy

**Type:** Array

...

Defaults to: `[]`


### maskOnDisable

**Type:** Boolean

This is an internal flag that you use when creating custom components. ...

This is an internal flag that you use when creating custom components. By default this is set to `true` which means that every component gets a mask when it's disabled. Components like FieldContainer, FieldSet, Field, Button, Tab override this property to `false` since they want to implement custom disable logic. Defaults to: `true`


### noRowLinesCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid-no-row-lines'`


### normalCfgCopy

**Type:** Array

...

Defaults to: `['verticalScroller', 'verticalScrollDock', 'verticalScrollerType', 'scroll']`


### offsetsCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'hide-offsets'`


### optimizedColumnMove

**Type:** Boolean

If you are writing a grid plugin or a {Ext.grid.feature.Feature Feature} which creates a column-based structure which...

If you are writing a grid plugin or a {Ext.grid.feature.Feature Feature} which creates a column-based structure which needs a view refresh when columns are moved, then set this property in the grid. An example is the built in Summary Feature. This creates summary rows, and the summary columns must be in the same order as the data columns. This plugin sets the `optimizedColumnMove` to `false.


### ownerCt

**Type:** Ext.Container

This Component's owner Container (is set automatically when this Component is added to a Container). ...

This Component's owner Container (is set automatically when this Component is added to a Container). *Important.* This is not a universal upwards navigation pointer. It indicates the Container which owns and manages this Component if any. There are other similar relationships such as the button which activates a menu, or the menu item which activated a submenu, or the column header which activated the column menu. These differences are abstracted away by the up method. **Note**: to access items within the Container see itemId. Available since: 2.3.0


### rendered

**Type:** Boolean

Indicates whether or not the component has been rendered. ...

Indicates whether or not the component has been rendered. Defaults to: `false` Available since: 1.1.0


### resizeMarkerCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid-resize-marker'`


### rowLinesCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'grid-with-row-lines'`


### scrollFlags

**Type:** Object

An object property which provides unified information as to which dimensions are scrollable based upon the autoScroll...

An object property which provides unified information as to which dimensions are scrollable based upon the autoScroll, overflowX and overflowY settings (And for *views* of trees and grids, the owning panel's scroll setting). Note that if you set overflow styles using the style config or bodyStyle config, this object does not include that information; it is best to use autoScroll, overflowX and overflowY if you need to access these flags. This object has the following properties: x : Boolean`true` if this Component is scrollable horizontally - style setting may be `'auto'` or `'scroll'`.


### scrollerOwner

**Type:** Boolean

private property used to determine where to go down to find views this is here to support locking. ...

private property used to determine where to go down to find views this is here to support locking. Defaults to: `true`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### unlockText

**Type:** String

i8n text ...

i8n text Defaults to: `'Unlock'`


### weight

**Type:** Number

...

Defaults to: `0`


### zIndexManager

**Type:** Ext.ZIndexManager

Only present for floating Components after they have been rendered. ...

Only present for floating Components after they have been rendered. A reference to the ZIndexManager which is managing this Component's z-index. The ZIndexManager maintains a stack of floating Component z-indices, and also provides a single modal mask which is insert just beneath the topmost visible modal floating Component. Floating Components may be brought to the front or sent to the back of the z-index stack. This defaults to the global ZIndexManager for floating Components that are programatically rendered. For floating Components which are added to a Container, the ZIndexManager is acquired from the first ancestor Container found which is floating. If no floating ancestor is found, the global ZIndexManager is used. See floating and zIndexParent


### zIndexParent

**Type:** Ext.Container

Only present for floating Components which were inserted as child items of Containers, and which have a floating Cont...

Only present for floating Components which were inserted as child items of Containers, and which have a floating Container in their containment ancestry. For floating Components which are child items of a Container, the zIndexParent will be a floating ancestor Container which is responsible for the base z-index value of all its floating descendants. It provides a ZIndexManager which provides z-indexing services for all its descendant floating Components. Floating Components that are programatically rendered will not have a `zIndexParent` property. For example, the dropdown BoundList of a ComboBox which is in a Window will have the Window as its `zIndexParent`, and will always show above that Window, wherever the Window is placed in the z-index stack. See floating and zIndexManager


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.panel.Table

Creates new Component. ...

Creates new Component.

**Parameters:** - config : Ext.Element/String/ObjectThe configuration options may be specified as either: **an element** : it is set as the internal element and its id used as the component id - **a string** : it is assumed to be the id of an existing element and is used as the component id - **anything else** : it is assumed to be a standard config object and is applied to the component


### add

Adds Component(s) to this Container. ...

Adds Component(s) to this Container. Description: - Fires the beforeadd event before adding. - The Container's default config values will be applied accordingly (see `defaults` for details). - Fires the `add` event after the component has been added. Notes: If the Container is **already rendered** when `add` is called, it will render the newly added Component into its content area. **If** the Container was configured with a size-managing layout manager, the Container will recalculate its internal layout at this time too. Note that the default layout manager simply renders child Components sequentially into the content area and thereafter performs no sizing. If adding multiple new child Components, pass them as an array to the `add` method, so that only one layout recalculation is performed. To inject components between existing ones, use the insert method. Warning: Components directly managed by the BorderLayout layout manager may not be removed or added. See the Notes for BorderLayout for more details. Available since: 2.3.0

**Parameters:** component : Ext.Component[]|Object[]/Ext.Component.../Object...Either one or more Components to add or an Array of Components to add. See `items` for additional information.


### addBodyCls

Adds a CSS class to the body element. ...

Adds a CSS class to the body element. If not rendered, the class will be added when the panel is rendered.

**Parameters:** cls : StringThe class to add


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### addClass

Adds a CSS class to the top level element representing this component. ...

Adds a CSS class to the top level element representing this component. This method has been **deprecated** since 4.1 Use addCls instead.


### addCls

Adds a CSS class to the top level element representing this component. ...

Adds a CSS class to the top level element representing this component.

**Parameters:** cls : String/String[]The CSS class name to add.


### addClsWithUI

Adds a cls to the uiCls array, which will also call addUIClsToElement and adds to all elements of this component. ...

Adds a `cls` to the `uiCls` array, which will also call addUIClsToElement and adds to all elements of this component.

**Parameters:** classes : String/String[]A string or an array of strings to add to the `uiCls`.


### addDocked

Adds docked item(s) to the container. ...

Adds docked item(s) to the container.

**Parameters:** component : Object/Object[]The Component or array of components to add. The components must include a 'dock' parameter on each component to indicate where it should be docked ('top', 'right', 'bottom', 'left').


### addEvents

Adds the specified events to the list of events which this Observable may fire. ...

Adds the specified events to the list of events which this Observable may fire.

**Parameters:** eventNames : Object/String...Either an object with event names as properties with a value of `true`. For example: Or any number of event names as separate parameters. For example:


### addFocusListener

Sets up the focus listener on this Component's focusEl if it has one. ...

Sets up the focus listener on this Component's focusEl if it has one. Form Components which must implicitly participate in tabbing order usually have a naturally focusable element as their focusEl, and it is the DOM event of that receiving focus which drives the Component's `onFocus` handling, and the DOM event of it being blurred which drives the `onBlur` handling. If the focusEl is **not** naturally focusable, then the listeners are only added if the FocusManager is enabled.


### addListener

Appends an event handler to this object. ...

Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### addManagedListener

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destr...

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### addOverCls

...


### addPlugin

Adds a plugin. ...

Adds a plugin. May be called at any time in the component's lifecycle.

**Parameters:** plugin : Object


### addPropertyToState

Save a property to the given state object if it is not its default or configured value. ...

Save a property to the given state object if it is not its default or configured value.

**Parameters:** state : ObjectThe state object.


### addStateEvents

Add events that will trigger the state to be saved. ...

Add events that will trigger the state to be saved. If the first argument is an array, each element of that array is the name of a state event. Otherwise, each argument passed to this method is the name of a state event.

**Parameters:** events : String/String[]The event name or an array of event names.


### addTool

Add tools to this panel ...

Add tools to this panel

**Parameters:** tools : Object[]/Ext.panel.Tool[]The tools to add


### addTools

Template method to be implemented in subclasses to add their tools after the collapsible tool. ...

Template method to be implemented in subclasses to add their tools after the collapsible tool. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### addUIClsToElement

inherit docs Method which adds a specified UI + uiCls to the components element. ...

inherit docs Method which adds a specified UI + `uiCls` to the components element. Can be overridden to remove the UI from more than just the components element.

**Parameters:** ui : StringThe UI to remove from the element.


### addUIToElement

inherit docs Method which adds a specified UI to the components element. ...

inherit docs Method which adds a specified UI to the components element. Overrides: Ext.AbstractComponent.addUIToElement


### adjustForConstraints

private ==> used outside of core TODO: currently only used by ToolTip. ...

private ==> used outside of core TODO: currently only used by ToolTip. does this method belong here?

**Parameters:** xy : Object


### adjustPosition

...

**Parameters:** x : Object


### afterCollapse

Invoked after the Panel is Collapsed. ...

Invoked after the Panel is Collapsed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterComponentLayout

Called by the layout system after the Component has been laid out. ...

Called by the layout system after the Component has been laid out. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterExpand

Invoked after the Panel is Expanded. ...

Invoked after the Panel is Expanded. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterFirstLayout

...

**Parameters:** width : Object


### afterHide

Invoked after the Component has been hidden. ...

Invoked after the Component has been hidden. Gets passed the same `callback` and `scope` parameters that onHide received. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterLayout

Invoked after the Container has laid out (and rendered if necessary) its child Components. ...

Invoked after the Container has laid out (and rendered if necessary) its child Components. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterLockedViewLayout

Due to automatic component border setting using inline style, to create the scrollbar-replacing bottom border, we hav...

Due to automatic component border setting using inline style, to create the scrollbar-replacing bottom border, we have to postprocess the locked view *after* render. If there are visible normal columns, we do need the fat bottom border.


### afterRender

Allows addition of behavior after rendering is complete. ...

Allows addition of behavior after rendering is complete. At this stage the Component’s Element will have been styled according to the configuration, will have had any configured CSS class names added, and will be in the configured visibility and the configured enable state. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterSetPosition

Template method called after a Component has been positioned. ...

Template method called after a Component has been positioned. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterShow

Invoked after the Component is shown (after onShow is called). ...

Invoked after the Component is shown (after onShow is called). Gets passed the same parameters as show. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### alignTo

Aligns the element with another element relative to the specified anchor points. ...

Aligns the element with another element relative to the specified anchor points. If the other element is the document it aligns it to the viewport. The position parameter is optional, and can be specified in any one of the following formats: - **Blank**: Defaults to aligning the element's top-left corner to the target's bottom-left corner ("tl-bl"). - **One anchor (deprecated)**: The passed anchor position is used as the target element's anchor point. The element being aligned will position its top-left corner (tl) to that point. This method has been deprecated in favor of the newer two anchor syntax below. - **Two anchors**: If two values from the table below are passed separated by a dash, the first value is used as the element's anchor point, and the second value is used as the target's anchor point. In addition to the anchor points, the position parameter also supports the "?" character. If "?" is passed at the end of the position string, the element will attempt to align as specified, but the position will be adjusted to constrain to the viewport if necessary. Note that the element being aligned might be swapped to align to a different position than that specified in order to enforce the viewport constraints. Following are all of the supported anchor positions: Example Usage:

**Parameters:** element : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or id of the element to align to.


### anchorTo

Anchors an element to another element and realigns it when the window is resized. ...

Anchors an element to another element and realigns it when the window is resized.

**Parameters:** element : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or id of the element to align to.


### anim

process the passed fx configuration. ...

- process the passed fx configuration.

**Parameters:** config : Object


### animate

Performs custom animation on this object. ...

Performs custom animation on this object. This method is applicable to both the Component class and the Sprite class. It performs animated transitions of certain properties of this object over a specified timeline. Animating a Component When animating a Component, the following properties may be specified in `from`, `to`, and `keyframe` objects: - `x` - The Component's page X position in pixels. - `y` - The Component's page Y position in pixels - `left` - The Component's `left` value in pixels. - `top` - The Component's `top` value in pixels. - `width` - The Component's `width` value in pixels. - `height` - The Component's `height` value in pixels. - `dynamic` - Specify as true to update the Component's layout (if it is a Container) at every frame of the animation. *Use sparingly as laying out on every intermediate size change is an expensive operation.* For example, to animate a Window to a new size, ensuring that its internal layout and any shadow is correct: For performance reasons, by default, the internal layout is only updated when the Window reaches its final `"to"` size. If dynamic updating of the Window's child Components is required, then configure the animation with `dynamic: true` and the two child items will maintain their proportions during the animation.

**Parameters:** config : ObjectConfiguration for Ext.fx.Anim. Note that the to config is required.


### applyChildEls

Sets references to elements inside the component. ...

Sets references to elements inside the component.

**Parameters:** el : Object


### applyDefaults

...

**Parameters:** config : Object


### applyRenderSelectors

Sets references to elements inside the component. ...

Sets references to elements inside the component. This applies renderSelectors as well as childEls.


### applyState

Applies the state to the object. ...

Applies the state to the object. This should be overridden in subclasses to do more complex state operations. By default it applies the state properties onto the current object.

**Parameters:** state : ObjectThe state


### applyTargetCls

...

**Parameters:** targetCls : Object


### beforeBlur

Template method to do any pre-blur processing. ...

Template method to do any pre-blur processing.

**Parameters:** e : Ext.EventObjectThe event object


### beforeComponentLayout

Occurs before componentLayout is run. ...

Occurs before `componentLayout` is run. Returning `false` from this method will prevent the `componentLayout` from being executed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeDestroy

Invoked before the Component is destroyed. ...

Invoked before the Component is destroyed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeFocus

Template method to do any pre-focus processing. ...

Template method to do any pre-focus processing.

**Parameters:** e : Ext.EventObjectThe event object


### beforeLayout

Occurs before componentLayout is run. ...

Occurs before componentLayout is run. In previous releases, this method could return `false` to prevent its layout but that is not supported in Ext JS 4.1 or higher. This method is simply a notification of the impending layout to give the component a chance to adjust the DOM. Ideally, DOM reads should be avoided at this time to reduce expensive document reflows. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeRender

...

Overrides: Ext.container.AbstractContainer.beforeRender


### beforeSetPosition

Template method called before a Component is positioned. ...

Template method called before a Component is positioned. Ensures that the position is adjusted so that the Component is constrained if so configured.

**Parameters:** x : Object


### beforeShow

Invoked before the Component is shown. ...

Invoked before the Component is shown. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beginCollapse

Called before the change from default, configured state into the collapsed state. ...

Called before the change from default, configured state into the collapsed state. This method may be called at render time to enable rendering in an initially collapsed state, or at runtime when an existing, fully layed out Panel may be collapsed. It basically saves configs which need to be clobbered for the duration of the collapsed state.


### beginDrag

...


### beginExpand

...


### bindStore

...

**Parameters:** store : Object


### blur

...

**Returns:** Ext.Componentthis


### bridgeToolbars

...


### bubble

Bubbles up the component/container heirarchy, calling the specified function with each component. ...

Bubbles up the component/container heirarchy, calling the specified function with each component. The scope (*this*) of function call will be the scope provided or the current component. The arguments to the function will be the args provided or the current component. If the function returns false at any point, the bubble is stopped.

**Parameters:** fn : FunctionThe function to call


### calculateAnchorXY

Calculates x,y coordinates specified by the anchor position on the element, adding extraX and extraY values. ...

Calculates x,y coordinates specified by the anchor position on the element, adding extraX and extraY values.

**Parameters:** anchor : String (optional)The specified anchor position. See alignTo for details on supported anchor positions. Defaults to: `'tl'`


### calculateConstrainedPosition

Calculates the new [x,y] position to move this Positionable into a constrain region. ...

Calculates the new [x,y] position to move this Positionable into a constrain region. By default, this Positionable is constrained to be within the container it was added to, or the element it was rendered to. Priority is given to constraining the top and left within the constraint. An alternative constraint may be passed.

**Parameters:** constrainTo : String/HTMLElement/Ext.Element/Ext.util.Region (optional)The Element or Region into which this Component is to be constrained. Defaults to the element into which this Positionable was rendered, or this Component's {@link Ext.Component.constrainTo.


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


### cancelFocus

Cancel any deferred focus on this component ...

Cancel any deferred focus on this component


### captureArgs

...

**Parameters:** o : Object


### cascade

Cascades down the component/container heirarchy from this component (passed in the first call), calling the specified...

Cascades down the component/container heirarchy from this component (passed in the first call), calling the specified function with each component. The scope (this reference) of the function call will be the scope provided or the current component. The arguments to the function will be the args provided or the current component. If the function returns false at any point, the cascade is stopped on that branch. Available since: 2.3.0

**Parameters:** fn : FunctionThe function to call


### center

Center this Component in its container. ...

Center this Component in its container.

**Returns:** Ext.Componentthis


### child

Retrieves the first direct child of this container which matches the passed selector or component. ...

Retrieves the first direct child of this container which matches the passed selector or component. The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.

**Parameters:** selector : String/Ext.Component (optional)An Ext.ComponentQuery selector. If no selector is specified, the first child will be returned.


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### cloneConfig

Clone the current component using the original config values passed into this instance by default. ...

Clone the current component using the original config values passed into this instance by default.

**Parameters:** overrides : ObjectA new config containing any properties to override in the cloned version. An id property can be passed on this object, otherwise one will be generated to avoid duplicates.


### close

Closes the Panel. ...

Closes the Panel. By default, this method, removes it from the DOM, destroys the Panel object and all its descendant Components. The beforeclose event is fired before the close happens and will cancel the close action if it returns false. **Note:** This method is also affected by the closeAction setting. For more explicit control use destroy and hide methods.


### collapse

Collapses the panel body so that the body becomes hidden. ...

Collapses the panel body so that the body becomes hidden. Docked Components parallel to the border towards which the collapse takes place will remain visible. Fires the beforecollapse event which will cancel the collapse action if it returns false.

**Parameters:** - direction : String (optional)The direction to collapse towards. Must be one of Ext.Component.DIRECTION_TOP - Ext.Component.DIRECTION_RIGHT - Ext.Component.DIRECTION_BOTTOM - Ext.Component.DIRECTION_LEFT Defaults to collapseDirection.


### collapsedHorizontal

...


### collapsedVertical

...


### configClass

...


### constructLockableFeatures

...


### constructLockablePlugins

...


### constructPlugin

...

**Parameters:** ptype : String/Objectstring or config object containing a ptype property. Constructs a plugin according to the passed config object/ptype string. Ensures that the constructed plugin always has a `cmp` reference back to this component. The setting up of this is done in PluginManager. The PluginManager ensures that a reference to this component is passed to the constructor. It also ensures that the plugin's `setCmp` method (if any) is called.


### constructPlugins

Returns an array of fully constructed plugin instances. ...

**Returns:** an array of fully constructed plugin instances. This converts any configs into their appropriate instances. It does not mutate the plugins array. It creates a new array.


### contains

Determines whether the passed Component is either an immediate child of this Container, or whether it is a descendant. ...

Determines whether the passed Component is either an immediate child of this Container, or whether it is a descendant.

**Parameters:** comp : Ext.ComponentThe Component to test.


### continueFireEvent

Continue to fire event. ...

Continue to fire event.

**Parameters:** eventName : String


### convertCollapseDir

converts a collapsdDir into an anchor argument for Element.slideIn overridden in rtl mode to switch "l" and "r" ...

converts a collapsdDir into an anchor argument for Element.slideIn overridden in rtl mode to switch "l" and "r"

**Parameters:** collapseDir : Object


### convertPositionSpec

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**

**Parameters:** posSpec : Object


### createReExpander

...

**Parameters:** direction : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### delayScroll

...


### deleteMembers

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### destroyDockedItems

...


### destroyLockable

...


### detachComponent

Detach a component from the DOM ...

Detach a component from the DOM

**Parameters:** component : Object


### determineScrollbars

This method is obsolete in 4.1. ...

This method is obsolete in 4.1. The closest equivalent in 4.1 is doLayout, but it is also possible that no layout is needed. This method has been **deprecated** since 4.1


### determineXTypeToCreate

...

**Parameters:** lockedSide : Object


### disable

Inherit docs Disable all immediate children that was previously disabled Override disable because onDisable only gets...

Inherit docs Disable all immediate children that was previously disabled Override disable because onDisable only gets called when rendered Disable the component. Available since: 1.1.0

**Parameters:** silent : Boolean (optional)Passing `true` will suppress the `disable` event from being fired. Defaults to: `false`


### doApplyRenderTpl

Called from the selected frame generation template to insert this Component's inner structure inside the framing stru...

Called from the selected frame generation template to insert this Component's inner structure inside the framing structure. When framing is used, a selected frame generation template is used as the primary template of the getElConfig instead of the configured renderTpl. The renderTpl is invoked by this method which is injected into the framing template.

**Parameters:** out : Object


### doAutoRender

Handles autoRender. ...

Handles autoRender. Floating Components may have an ownerCt. If they are asking to be constrained, constrain them within that ownerCt, and have their z-index managed locally. Floating Components are always rendered to document.body


### doClose

...


### doCollapseExpand

...

**Parameters:** flags : Object


### doComponentLayout

This method needs to be called whenever you change something on this component that requires the Component's layout t...

This method needs to be called whenever you change something on this component that requires the Component's layout to be recalculated.

**Returns:** Ext.container.Containerthis


### doConstrain

Moves this floating Component into a constrain region. ...

Moves this floating Component into a constrain region. By default, this Component is constrained to be within the container it was added to, or the element it was rendered to. An alternative constraint may be passed.

**Parameters:** constrainTo : String/HTMLElement/Ext.Element/Ext.util.Region (optional)The Element or Region into which this Component is to be constrained. Defaults to the element into which this floating Component was rendered.


### doLayout

Manually force this container's layout to be recalculated. ...

Manually force this container's layout to be recalculated. The framework uses this internally to refresh layouts form most cases. Available since: 2.3.0

**Returns:** Ext.container.Containerthis


### doRemove

...

**Parameters:** component : Object


### doRenderContent

...

**Parameters:** out : Object


### doRenderDockedItems

...

**Parameters:** out : Object


### doRenderFramingDockedItems

...

**Parameters:** out : Object


### down

Retrieves the first descendant of this container which matches the passed selector. ...

Retrieves the first descendant of this container which matches the passed selector. The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.

**Parameters:** selector : String/Ext.Component (optional)An Ext.ComponentQuery selector or Ext.Component. If no selector is specified, the first child will be returned.


### enable

Enable all immediate children that was previously disabled Override enable because onEnable only gets called when ren...

Enable all immediate children that was previously disabled Override enable because onEnable only gets called when rendered Enable the component Available since: 1.1.0

**Parameters:** silent : Boolean (optional)Passing `true` will suppress the `enable` event from being fired. Defaults to: `false`


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if present. There is no implementation in the Observable base class. This is commonly used by Ext.Components to bubble events to owner Containers. See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the Component's immediate owner. But if a known target is required, this can be overridden to access the required target more quickly. Example:

**Parameters:** eventNames : String/String[]The event name to bubble, or an Array of event names.


### endDrag

...


### ensureAttachedToBody

Ensures that this component is attached to document.body. ...

Ensures that this component is attached to `document.body`. If the component was rendered to Ext.getDetachedBody, then it will be appended to `document.body`. Any configured position is also restored.

**Parameters:** runLayout : Boolean (optional)True to run the component's layout. Defaults to: `false`


### expand

Expands the panel body so that it becomes visible. ...

Expands the panel body so that it becomes visible. Fires the beforeexpand event which will cancel the expand action if it returns false.

**Parameters:** animate : Boolean (optional)True to animate the transition, else false (defaults to the value of the animCollapse panel config). May also be specified as the animation duration in milliseconds.


### findParentBy

Find a container above this component at any level by a custom function. ...

Find a container above this component at any level by a custom function. If the passed function returns true, the container will be returned. See also the up method.

**Parameters:** fn : FunctionThe custom function to call with the arguments (container, this component).


### findParentByType

Find a container above this component at any level by xtype or class See also the up method. ...

Find a container above this component at any level by xtype or class See also the up method.

**Parameters:** xtype : String/Ext.ClassThe xtype string for a component, or the class of the component directly


### findPlugin

Retrieves plugin from this component's collection by its ptype. ...

Retrieves plugin from this component's collection by its `ptype`.

**Parameters:** ptype : StringThe Plugin's ptype as specified by the class's `alias` configuration.


### findReExpander

...

**Parameters:** direction : Object


### finishRender

This method visits the rendered component tree in a "top-down" order. ...

This method visits the rendered component tree in a "top-down" order. That is, this code runs on a parent component before running on a child. This method calls the onRender method of each component.

**Parameters:** containerIdx : NumberThe index into the Container items of this Component.


### finishRenderChildren

...

Overrides: Ext.util.Renderable.finishRenderChildren


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed to addListener). An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list. An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### fireHierarchyEvent

For more information on the hierarchy events, see the note for the hierarchyEventSource observer defined in the onCla...

For more information on the hierarchy events, see the note for the hierarchyEventSource observer defined in the onClassCreated callback. This functionality is contained in Component (as opposed to Container) because a Component can be the ownerCt for a floating component (loadmask), and the loadmask needs to know when its owner is shown/hidden via the hierarchyEventSource so that its hidden state can be synchronized. TODO: merge this functionality with Ext.globalEvents

**Parameters:** ename : Object


### fitContainer

...

**Parameters:** animate : Object


### floatCollapsedPanel

...


### focus

Try to focus this component. ...

Try to focus this component.

**Parameters:** selectText : Boolean (optional)If applicable, true to also select the text in this component


### forceComponentLayout

Forces this component to redo its componentLayout. ...

Forces this component to redo its componentLayout. This method has been **deprecated** since 4.1.0 Use updateLayout instead.


### getActionEl

Deprecate 5.0 ...

Deprecate 5.0


### getActiveAnimation

Returns the current animation if this object has any effects actively running or queued, else returns false. ...

**Returns:** the current animation if this object has any effects actively running or queued, else returns false. ReturnsExt.fx.Anim/BooleanAnim if element has active effects, else false


### getAlignToXY

Gets the x,y coordinates to align this element with another element. ...

Gets the x,y coordinates to align this element with another element. See alignTo for more info on the supported position values.

**Parameters:** element : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or id of the element to align to.


### getAnchor

private ...

private


### getAnchorToXY

Begin Positionable methods Overridden in Ext.rtl.AbstractComponent. ...

Begin Positionable methods **Overridden in Ext.rtl.AbstractComponent.** Gets the x,y coordinates of an element specified by the anchor position on the element.

**Parameters:** el : Ext.dom.ElementThe element


### getAnchorXY

Gets the x,y coordinates specified by the anchor position on the element. ...

Gets the x,y coordinates specified by the anchor position on the element.

**Parameters:** anchor : String (optional)The specified anchor position. See alignTo for details on supported anchor positions. Defaults to: `'tl'`


### getAnimateTarget

...

**Parameters:** target : Object


### getAutoId

...


### getBorderPadding

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Returns:** the size of the element's borders and padding. ReturnsObjectan object with the following numeric properties - beforeX - afterX - beforeY - afterY


### getBox

Return an object defining the area of this Element which can be passed to setBox to set another Element's size/locati...

Return an object defining the area of this Element which can be passed to setBox to set another Element's size/location to match this element.

**Parameters:** contentBox : Boolean (optional)If true a box for the content of the element is returned.


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getBubbleTarget

Implements an upward event bubbling policy. ...

Implements an upward event bubbling policy. By default a Component bubbles events up to its reference owner. Component subclasses may implement a different bubbling strategy by overriding this method. Overrides: Ext.AbstractComponent.getBubbleTarget


### getChildByElement

Return the immediate child Component in which the passed element is located. ...

Return the immediate child Component in which the passed element is located.

**Parameters:** el : Ext.Element/HTMLElement/StringThe element to test (or ID of element).


### getChildEls

...


### getChildItemsToDisable

Gets a list of child components to enable/disable when the container is enabled/disabled ...

Gets a list of child components to enable/disable when the container is enabled/disabled

**Returns:** Ext.Component[]Items to be enabled/disabled


### getClassChildEls

...

**Parameters:** cls : Object


### getCollapsed

Returns the current collapsed state of the panel. ...

**Returns:** the current collapsed state of the panel. ReturnsBoolean/StringFalse when not collapsed, otherwise the value of collapseDirection.


### getCollapsedDockedItems

...


### getColumnWidth

Used when calculating total locked column width in processColumns Use shrinkwrapping of child columns if no top level...

Used when calculating total locked column width in processColumns Use shrinkwrapping of child columns if no top level width.

**Parameters:** column : Object


### getComponent

Attempts a default component lookup (see Ext.container.Container.getComponent). ...

Attempts a default component lookup (see Ext.container.Container.getComponent). If the component is not found in the normal items, the dockedItems are searched and the matched component (if any) returned (see getDockedComponent). Note that docked items will only be matched by component id or itemId -- if you pass a numeric index only non-docked child components will be searched. Available since: 2.3.0

**Parameters:** comp : String/NumberThe component id, itemId or position to find


### getComponentId

used as the key lookup function for the items collection ...

- used as the key lookup function for the items collection

**Parameters:** comp : Object


### getComponentLayout

...


### getConfig

...

**Parameters:** name : Object


### getConstrainVector

Returns the [X, Y] vector by which this Positionable's element must be translated to make a best attempt to constrain...

**Parameters:** constrainTo : Ext.util.Positionable/HTMLElement/String/Ext.util.Region (optional)The Positionable, HTMLElement, element id, or Region into which the element is to be constrained.

**Returns:** the `[X, Y]` vector by which this Positionable's element must be translated to make a best attempt to constrain within the passed constraint. Returns `false` if the element does not need to be moved. Priority is given to constraining the top and left within the constraint. The constraint may either be an existing element into which the element is to be constrained, or a Region into which this element is to be constrained. By default, any extra shadow around the element is **not** included in the constrain calculations - the edges of the element are used as the element bounds. To constrain the shadow within the constrain region, set the `constrainShadow` property on this element to `true`.


### getContentTarget

...

Overrides: Ext.Component.getContentTarget


### getDefaultContentTarget

...

Overrides: Ext.container.AbstractContainer.getDefaultContentTarget


### getDockedComponent

Finds a docked component by id, itemId or position. ...

Finds a docked component by id, itemId or position. Also see getDockedItems

**Parameters:** comp : String/NumberThe id, itemId or position of the docked component (see getComponent for details)


### getDockedItems

Retrieves an array of all currently docked Components. ...

Retrieves an array of all currently docked Components. For example to find a toolbar that has been docked at top:

**Parameters:** selector : StringA ComponentQuery selector string to filter the returned items.


### getDockingRefItems

...

**Parameters:** deep : Object


### getDragEl

...


### getEditorParent

...


### getEl

Retrieves the top level element representing this component. ...

Retrieves the top level element representing this component. Available since: 1.1.0

**Returns:** Ext.dom.Element


### getElConfig

...


### getFocusEl

Returns the focus holder element associated with this Container. ...

**Returns:** the focus holder element associated with this Container. By default, this is the Container's target element. Subclasses which use embedded focusable elements (such as Window and Button) should override this for use by the focus method. ReturnsExt.Elementthe focus holding element.


### getFrameInfo

On render, reads an encoded style attribute, "filter" from the style of this Component's element. ...

On render, reads an encoded style attribute, "filter" from the style of this Component's element. This information is memoized based upon the CSS class name of this Component's element. Because child Components are rendered as textual HTML as part of the topmost Container, a dummy div is inserted into the document to receive the document element's CSS class name, and therefore style attributes.


### getFrameRenderData

...


### getFrameTpl

...

**Parameters:** table : Object


### getFramingInfoCls

...


### getHeader

Gets the Header for this panel. ...

Gets the Header for this panel.


### getHeaderCollapsedClasses

Create the class array to add to the Header when collpsed. ...

Create the class array to add to the Header when collpsed.

**Parameters:** header : Object


### getHeight

Gets the current height of the component's underlying element. ...

Gets the current height of the component's underlying element.

**Returns:** Number


### getHeightAuthority

...


### getHierarchyState

A component's hierarchyState is used to keep track of aspects of a component's state that affect its descendants hier...

A component's hierarchyState is used to keep track of aspects of a component's state that affect its descendants hierarchically like "collapsed" and "hidden". For example, if this.hierarchyState.hidden == true, it means that either this component, or one of its ancestors is hidden. Hierarchical state management is implemented by chaining each component's hierarchyState property to its parent container's hierarchyState property via the prototype. The result is such that if a component's hierarchyState does not have it's own property, it inherits the property from the nearest ancestor that does. To set a hierarchical "hidden" value: It is important to remember when unsetting hierarchyState properties to delete them instead of just setting them to a falsy value. This ensures that the hierarchyState returns to a state of inheriting the value instead of overriding it To unset the hierarchical "hidden" value: IMPORTANT! ALWAYS access hierarchyState using this method, not by accessing this.hierarchyState directly. The hierarchyState property does not exist until the first time getHierarchyState() is called. At that point getHierarchyState() walks up the component tree to establish the hierarchyState prototype chain. Additionally the hierarchyState property should NOT be relied upon even after the initial call to getHierarchyState() because it is possible for the hierarchyState to be invalidated. Invalidation typically happens when a component is moved to a new container. In such a case the hierarchy state remains invalid until the next time getHierarchyState() is called on the component or one of its descendants.

**Parameters:** inner : Object


### getId

Retrieves the id of this component. ...

Retrieves the `id` of this component. Will auto-generate an `id` if one has not already been set.

**Returns:** String


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getInsertPosition

This function takes the position argument passed to onRender and returns a DOM element that you can use in the insert...

This function takes the position argument passed to onRender and returns a DOM element that you can use in the insertBefore.

**Parameters:** position : String/Number/Ext.dom.Element/HTMLElementIndex, element id or element you want to put this component before.


### getItemId

Returns the value of itemId assigned to this component, or when that is not set, returns the value of id. ...

**Returns:** the value of itemId assigned to this component, or when that is not set, returns the value of id. ReturnsString


### getKeyMap

...


### getLayout

Returns the layout instance currently associated with this Container. ...

**Returns:** the layout instance currently associated with this Container. If a layout has not been instantiated yet, that is done first ReturnsExt.layout.container.ContainerThe layout


### getLhsMarker

Gets left hand side marker for header resizing. ...

Gets left hand side marker for header resizing.


### getLoader

Gets the Ext.ComponentLoader for this Component. ...

Gets the Ext.ComponentLoader for this Component.

**Returns:** Ext.ComponentLoaderThe loader instance, null if it doesn't exist.


### getLocalX

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Returns:** the x coordinate of this element reletive to its `offsetParent`. ReturnsNumberThe local x coordinate


### getLocalXY

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Returns:** the x and y coordinates of this element relative to its `offsetParent`. ReturnsNumber[]The local XY position of the element


### getLocalY

Returns the y coordinate of this element reletive to its offsetParent. ...

**Returns:** the y coordinate of this element reletive to its `offsetParent`. ReturnsNumberThe local y coordinate


### getLockingViewConfig

...


### getMaskTarget

...


### getMenuItems

...

**Parameters:** getMenuItems : Object


### getOffsetsTo

Returns the offsets of this element from the passed element. ...

**Parameters:** offsetsTo : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or element id to get get the offsets from.

**Returns:** the offsets of this element from the passed element. The element must both be part of the DOM tree and not have display:none to have page coordinates.


### getOppositeDirection

...

**Parameters:** d : Object


### getOuterSize

Include margins ...

Include margins


### getOverflowEl

Get an el for overflowing, defaults to the target el ...

Get an el for overflowing, defaults to the target el


### getOverflowStyle

Returns the CSS style object which will set the Component's scroll styles. ...

**Returns:** the CSS style object which will set the Component's scroll styles. This must be applied to the target element.


### getOwningBorderContainer

Returns the owning container if that container uses border layout. ...

**Returns:** the owning container if that container uses `border` layout. Otherwise this method returns `null`. **Defined in override Ext.layout.container.border.Region.** ReturnsExt.container.ContainerThe owning border container or `null`.


### getOwningBorderLayout

Returns the owning border (Ext.layout.container.Border) instance if there is one. ...

**Returns:** the owning `border` (`Ext.layout.container.Border`) instance if there is one. Otherwise this method returns `null`. **Defined in override Ext.layout.container.border.Region.** ReturnsExt.layout.container.BorderThe owning border layout or `null`.


### getPlaceholder

...

**Parameters:** direction : Object


### getPlugin

Retrieves a plugin from this component's collection by its pluginId. ...

Retrieves a plugin from this component's collection by its `pluginId`.

**Parameters:** pluginId : String


### getPosition

Gets the current XY position of the component's underlying element. ...

Gets the current XY position of the component's underlying element.

**Parameters:** local : Boolean (optional)If true the element's left and top are returned instead of page XY. Defaults to: `false`


### getPositionEl

Deprecate 5.0 ...

Deprecate 5.0


### getProtoBody

...


### getProxy

...


### getReExpander

...

**Parameters:** direction : Object


### getRefItems

Used by ComponentQuery, child and down to retrieve all of the items which can potentially be considered a child of th...

Used by ComponentQuery, child and down to retrieve all of the items which can potentially be considered a child of this Container. This may be overriden by Components which have ownership of Components that are not contained in the items collection. NOTE: IMPORTANT note for maintainers: Items are returned in tree traversal order. Each item is appended to the result array followed by the results of that child's getRefItems call. Floating child items are appended after internal child items.

**Parameters:** deep : Object


### getRefOwner

Used by ComponentQuery, and the up method to find the owning Component in the linkage hierarchy. ...

Used by ComponentQuery, and the up method to find the owning Component in the linkage hierarchy. By default this returns the Container which contains this Component. This may be overriden by Component authors who implement ownership hierarchies which are not based upon ownerCt, such as BoundLists being owned by Fields or Menus being owned by Buttons.


### getRegion

Returns a region object that defines the area of this element. ...

**Returns:** a region object that defines the area of this element. ReturnsExt.util.RegionA Region containing "top, left, bottom, right" properties.


### getRenderTree

...


### getResizeEl

Deprecate 5.0 ...

Deprecate 5.0


### getRhsMarker

Gets right hand side marker for header resizing. ...

Gets right hand side marker for header resizing.


### getScrollTarget

...


### getScrollerOwner

...


### getSelectionModel

Returns the selection model being used and creates it via the configuration if it has not been created already. ...

**Returns:** the selection model being used and creates it via the configuration if it has not been created already. ReturnsExt.selection.ModelselModel


### getSize

Gets the current size of the component's underlying element. ...

Gets the current size of the component's underlying element.

**Returns:** ObjectAn object containing the element's size `{width: (element width), height: (element height)}`


### getSizeModel

Returns an object that describes how this component's width and height are managed. ...

**Parameters:** ownerCtSizeModel : Object

**Returns:** an object that describes how this component's width and height are managed. All of these objects are shared and should not be modified.


### getState

The supplied default state gathering method for the AbstractComponent class. ...

The supplied default state gathering method for the AbstractComponent class. This method returns dimension settings such as `flex`, `anchor`, `width` and `height` along with `collapsed` state. Subclasses which implement more complex state should call the superclass's implementation, and apply their state to the result if this basic state is to be saved. Note that Component state will only be saved if the Component has a stateId and there as a StateProvider configured for the document.

**Returns:** Object


### getStateId

Gets the state id for this object. ...

Gets the state id for this object.

**Returns:** StringThe 'stateId' or the implicit 'id' specified by component configuration.


### getStore

Returns the store associated with this Panel. ...

**Returns:** the store associated with this Panel. ReturnsExt.data.StoreThe store


### getStyleProxy

Returns an offscreen div with the same class name as the element this is being rendered. ...

**Parameters:** cls : Object

**Returns:** an offscreen div with the same class name as the element this is being rendered. This is because child item rendering takes place in a detached div which, being not part of the document, has no styling.


### getTargetEl

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. ...

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. Overrides: Ext.panel.AbstractPanel.getTargetEl


### getTpl

...

**Parameters:** name : Object


### getView

Gets the view for this panel. ...

Gets the view for this panel.

**Returns:** Ext.view.Table


### getViewRegion

Returns the content region of this element. ...

**Returns:** the **content** region of this element. That is the region within the borders and padding. ReturnsExt.util.RegionA Region containing "top, left, bottom, right" member data.


### getVisibilityEl

Deprecate 5.0 ...

Deprecate 5.0


### getWidth

Gets the current width of the component's underlying element. ...

Gets the current width of the component's underlying element.

**Returns:** Number


### getWidthAuthority

...


### getX

Gets the current X position of the DOM element based on page coordinates. ...

Gets the current X position of the DOM element based on page coordinates.

**Returns:** NumberThe X position of the element


### getXType

Gets the xtype for this component as registered with Ext.ComponentManager. ...

Gets the xtype for this component as registered with Ext.ComponentManager. For a list of all available xtypes, see the Ext.Component header. Example usage:

**Returns:** StringThe xtype


### getXTypes

Returns this Component's xtype hierarchy as a slash-delimited string. ...

**Returns:** this Component's xtype hierarchy as a slash-delimited string. For a list of all available xtypes, see the Ext.Component header. If using your own subclasses, be aware that a Component must register its own xtype to participate in determination of inherited xtypes. Example usage: Available since: 2.3.0 ReturnsStringThe xtype hierarchy string


### getXY

Gets the current position of the DOM element based on page coordinates. ...

Gets the current position of the DOM element based on page coordinates.

**Returns:** Number[]The XY position of the element


### getY

Gets the current Y position of the DOM element based on page coordinates. ...

Gets the current Y position of the DOM element based on page coordinates.

**Returns:** NumberThe Y position of the element


### ghost

used for dragging ...

used for dragging

**Parameters:** cls : Object


### ghostTools

helper function for ghost ...

helper function for ghost


### hasActiveFx

Returns the current animation if this object has any effects actively running or queued, else returns false. ...

**Returns:** the current animation if this object has any effects actively running or queued, else returns false. This method has been **deprecated** since 4.0 Replaced by getActiveAnimation


### hasCls

Checks if the specified CSS class exists on this element's DOM node. ...

Checks if the specified CSS class exists on this element's DOM node.

**Parameters:** className : StringThe CSS class to check for.


### hasConfig

...

**Parameters:** config : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer indicates whether the event needs firing or not.

**Parameters:** eventName : StringThe name of the event to check for


### hasLockedColumns

Private. ...

Private. Determine if there are any columns with a locked configuration option

**Parameters:** columns : Object


### hasUICls

Checks if there is currently a specified uiCls. ...

Checks if there is currently a specified `uiCls`.

**Parameters:** cls : StringThe `cls` to check.


### hide

Hides this Component, setting it to invisible using the configured hideMode. ...

Hides this Component, setting it to invisible using the configured hideMode.

**Parameters:** animateTarget : String/Ext.Element/Ext.Component (optional)only valid for floating Components such as Windows or ToolTips, or regular Components which have been configured with `floating: true`.. The target to which the Component should animate while hiding. Defaults to: `null`


### initAria

...


### initBodyBorder

...


### initBodyStyles

Parses the bodyStyle config if available to create a style string that will be applied to the body element. ...

Parses the bodyStyle config if available to create a style string that will be applied to the body element. This also includes bodyPadding and bodyBorder if available.

**Returns:** StringA CSS style string with body styles, padding and border.


### initBorderProps

...


### initBorderRegion

This method is called by the Ext.layout.container.Border class when instances are added as regions to the layout. ...

This method is called by the `Ext.layout.container.Border` class when instances are added as regions to the layout. Since it is valid to add any component to a border layout as a region, this method must be added to `Ext.Component` but is only ever called when that component is owned by a `border` layout. **Defined in override Ext.layout.container.border.Region.**


### initCls

...


### initComponent

The initComponent template method is an important initialization step for a Component. ...

The initComponent template method is an important initialization step for a Component. It is intended to be implemented by each subclass of Ext.Component to provide any needed constructor logic. The initComponent method of the class being created is called first, with each initComponent method up the hierarchy to Ext.Component being called thereafter. This makes it easy to implement and, if needed, override the constructor logic of the Component at any step in the hierarchy. The initComponent method **must** contain a call to callParent in order to ensure that the parent class' initComponent method is also called. All config options passed to the constructor are applied to `this` before initComponent is called, so you can simply access them with `this.someOption`. The following example demonstrates using a dynamic string for the text of a button at the time of instantiation of the class. Available since: 1.1.0 This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initContainer

...

**Parameters:** container : Object


### initDockingItems

...


### initDraggable

...

Overrides: Ext.Component.initDraggable


### initEvents

Initialize any events on this component ...

Initialize any events on this component


### initFrame

...


### initFramingTpl

Poke in a reference to applyRenderTpl(frameInfo, out) ...

Poke in a reference to applyRenderTpl(frameInfo, out)

**Parameters:** table : Object


### initHeaderAria

...


### initHierarchyEvents

...


### initHierarchyState

Called by getHierarchyState to initialize the hierarchyState the first time it is requested. ...

Called by getHierarchyState to initialize the hierarchyState the first time it is requested. **Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** hierarchyState : Object


### initItems

...

Overrides: Ext.container.AbstractContainer.initItems


### initPadding

Initializes padding by applying it to the target element, or if the layout manages padding ensures that the padding o...

Initializes padding by applying it to the target element, or if the layout manages padding ensures that the padding on the target element is "0".

**Parameters:** targetEl : Object


### initPlugin

...

**Parameters:** plugin : Object


### initRenderData

Initialized the renderData to be used when rendering the renderTpl. ...

Initialized the renderData to be used when rendering the renderTpl.

**Returns:** ObjectObject with keys and values that are going to be applied to the renderTpl


### initRenderTpl

Initializes the renderTpl. ...

Initializes the renderTpl.

**Returns:** Ext.XTemplateThe renderTpl XTemplate instance.


### initResizable

...

Overrides: Ext.Component.initResizable


### initSimpleDraggable

Override Component.initDraggable. ...

Override Component.initDraggable. Panel (and subclasses) use the header element as the delegate.


### initState

Initializes the state of the object upon construction. ...

Initializes the state of the object upon construction.


### initStyles

Applies padding, margin, border, top, left, height, and width configs to the appropriate elements. ...

Applies padding, margin, border, top, left, height, and width configs to the appropriate elements.

**Parameters:** targetEl : Object


### initTools

Tools are a Panel-specific capabilty. ...

Tools are a Panel-specific capabilty. Panel uses initTools. Subclasses may contribute tools by implementing addTools.


### injectLockable

injectLockable will be invoked before initComponent's parent class implementation is called, so throughout this metho...

injectLockable will be invoked before initComponent's parent class implementation is called, so throughout this method this. are configurations


### insert

Inserts a Component into this Container at a specified index. ...

Inserts a Component into this Container at a specified index. Fires the beforeadd event before inserting, then fires the add event after the Component has been inserted. Available since: 2.3.0

**Parameters:** index : NumberThe index at which the Component will be inserted into the Container's items collection


### insertDocked

Inserts docked item(s) to the panel at the indicated position. ...

Inserts docked item(s) to the panel at the indicated position.

**Parameters:** pos : NumberThe index at which the Component will be inserted


### invalidateScroller

This method is obsolete in 4.1. ...

This method is obsolete in 4.1. The closest equivalent in 4.1 is Ext.AbstractComponent.updateLayout, but it is also possible that no layout is needed. This method has been **deprecated** since 4.1


### is

Tests whether this Component matches the selector string. ...

Tests whether this Component matches the selector string.

**Parameters:** selector : StringThe selector string to test against.


### isAncestor

Determines whether this Container is an ancestor of the passed Component. ...

Determines whether **this Container** is an ancestor of the passed Component. This will return `true` if the passed Component is anywhere within the subtree beneath this Container.

**Parameters:** possibleDescendant : Ext.ComponentThe Component to test for presence within this Container's subtree.


### isContainedFloater

Utility method to determine if a Component is floating, and has an owning Container whose coordinate system it must b...

Utility method to determine if a Component is floating, and has an owning Container whose coordinate system it must be positioned in when using setPosition.


### isDescendant

...

**Parameters:** ancestor : Object


### isDescendantOf

Determines whether this component is the descendant of a particular container. ...

Determines whether this component is the descendant of a particular container.

**Parameters:** container : Ext.Container


### isDisabled

Method to determine whether this Component is currently disabled. ...

Method to determine whether this Component is currently disabled.

**Returns:** Booleanthe disabled state of this Component.


### isDraggable

Method to determine whether this Component is draggable. ...

Method to determine whether this Component is draggable.

**Returns:** Booleanthe draggable state of this component.


### isDroppable

Method to determine whether this Component is droppable. ...

Method to determine whether this Component is droppable.

**Returns:** Booleanthe droppable state of this component.


### isFloating

Method to determine whether this Component is floating. ...

Method to determine whether this Component is floating.

**Returns:** Booleanthe floating state of this component.


### isFocusable

...


### isHidden

Method to determine whether this Component is currently set to hidden. ...

Method to determine whether this Component is currently set to hidden.

**Returns:** Booleanthe hidden state of this Component.


### isHierarchicallyHidden

...


### isLayoutRoot

Determines whether this Component is the root of a layout. ...

Determines whether this Component is the root of a layout. This returns `true` if this component can run its layout without assistance from or impact on its owner. If this component cannot run its layout given these restrictions, `false` is returned and its owner will be considered as the next candidate for the layout root. Setting the _isLayoutRoot property to `true` causes this method to always return `true`. This may be useful when updating a layout of a Container which shrink wraps content, and you know that it will not change size, and so can safely be the topmost participant in the layout run. Overrides: Ext.AbstractComponent.isLayoutRoot


### isLayoutSuspended

Returns true if layout is suspended for this component. ...

**Returns:** `true` if layout is suspended for this component. This can come from direct suspension of this component's layout activity (Ext.Container.suspendLayout) or if one of this component's containers is suspended. ReturnsBoolean`true` layout of this component is suspended.


### isLocalRtl

Returns true if this component's local coordinate system is rtl. ...

**Returns:** true if this component's local coordinate system is rtl. For normal components this equates to the value of isParentRtl(). Floaters are a bit different because a floater's element can be a childNode of something other than its parent component's element. For floaters we have to read the dom to see if the component's element's parentNode has a css direction value of "rtl". **Defined in override Ext.rtl.AbstractComponent.** ReturnsBoolean


### isOppositeRootDirection

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**


### isParentRtl

Returns true if this component's parent container is rtl. ...

**Returns:** true if this component's parent container is rtl. Used by rtl positioning methods to determine if the component should be positioned using a right-to-left coordinate system. **Defined in override Ext.rtl.AbstractComponent.** ReturnsBoolean


### isPlaceHolderCollapse

...


### isVisible

Returns true if this component is visible. ...

**Parameters:** deep : Boolean (optional)Pass `true` to interrogate the visibility status of all parent Containers to determine whether this Component is truly visible to the user. Generally, to determine whether a Component is hidden, the no argument form is needed. For example when creating dynamically laid out UIs in a hidden Container before showing them. Defaults to: `false`

**Returns:** `true` if this component is visible. Available since: 1.1.0


### isXType

Tests whether or not this Component is of a specific xtype. ...

Tests whether or not this Component is of a specific xtype. This can test whether this Component is descended from the xtype (default) or whether it is directly of the xtype specified (`shallow = true`). If using your own subclasses, be aware that a Component must register its own xtype to participate in determination of inherited xtypes. For a list of all available xtypes, see the Ext.Component header. Example usage: Available since: 2.3.0

**Parameters:** xtype : StringThe xtype to check for this Component


### lock

Locks the activeHeader as determined by which menu is open OR a header as specified. ...

Locks the activeHeader as determined by which menu is open OR a header as specified.

**Parameters:** header : Ext.grid.column.Column (optional)Header to unlock from the locked section. Defaults to the header which has the menu open currently.


### lookupComponent

...

**Parameters:** comp : Object


### makeFloating

...

**Parameters:** dom : Object


### mask

...


### modifyHeaderCt

inject Lock and Unlock text Hide/show Lock/Unlock options ...

inject Lock and Unlock text Hide/show Lock/Unlock options


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener. Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### move

Moves a Component within the Container ...

Moves a Component within the Container

**Parameters:** fromIdx : Number/Ext.ComponentThe index/component to move.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener. Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### nextChild

...

**Parameters:** child : Object


### nextNode

Returns the next node in the Component tree in tree traversal order. ...

**Parameters:** selector : String (optional)A ComponentQuery selector to filter the following nodes.

**Returns:** the next node in the Component tree in tree traversal order. Note that this is not limited to siblings, and if invoked upon a node with no matching siblings, will walk the tree to attempt to find a match. Contrast with nextSibling.


### nextSibling

Returns the next sibling of this Component. ...

**Parameters:** selector : String (optional)A ComponentQuery selector to filter the following items.

**Returns:** the next sibling of this Component. Optionally selects the next sibling which matches the passed ComponentQuery selector. May also be referred to as **`next()`** Note that this is limited to siblings, and if no siblings of the item match, `null` is returned. Contrast with nextNode


### on

Shorthand for addListener. ...

Shorthand for addListener. Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### onAdd

This method is invoked after a new Component has been added. ...

This method is invoked after a new Component has been added. It is passed the Component which has been added. This method may be used to update any internal structure which may depend upon the state of the child items. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onAdded

Method to manage awareness of when components are added to their respective Container, firing an added event. ...

Method to manage awareness of when components are added to their respective Container, firing an added event. References are established at add time rather than at render time. Allows addition of behavior when a Component is added to a Container. At this stage, the Component is in the parent Container's collection of child items. After calling the superclass's `onAdded`, the `ownerCt` reference will be present, and if configured with a ref, the `refOwner` will be set. Available since: 3.4.0 This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onAfterFloatLayout

...


### onBeforeAdd

This method is invoked before adding a new child Component. ...

This method is invoked before adding a new child Component. It is passed the new Component, and may be used to modify the Component, or prepare the Container in some way. Returning false aborts the add operation. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onBeforeFloatLayout

...


### onBlur

private ...

private

**Parameters:** e : Object


### onBoxReady

...

Overrides: Ext.AbstractComponent.onBoxReady


### onConfigUpdate

...

**Parameters:** names : Object


### onDestroy

Allows addition of behavior to the destroy operation. ...

Allows addition of behavior to the destroy operation. After calling the superclass's onDestroy, the Component will be destroyed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onDisable

Allows addition of behavior to the disable operation. ...

Allows addition of behavior to the disable operation. After calling the superclass's `onDisable`, the Component will be disabled. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onDockedAdd

Invoked after a docked item is added to the Panel. ...

Invoked after a docked item is added to the Panel. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onDockedRemove

Invoked after a docked item is removed from the Panel. ...

Invoked after a docked item is removed from the Panel. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onEnable

Allows addition of behavior to the enable operation. ...

Allows addition of behavior to the enable operation. After calling the superclass's `onEnable`, the Component will be enabled. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onFloatShow

...


### onFocus

private ...

private

**Parameters:** e : Object


### onHeaderHide

Section onHeaderHide is invoked after view. ...

Section onHeaderHide is invoked after view.

**Parameters:** headerCt : Object


### onHeaderMove

Update the view when a header moves ...

Update the view when a header moves

**Parameters:** headerCt : Object


### onHeaderResize

...


### onHeaderShow

...

**Parameters:** headerCt : Object


### onHide

Possibly animates down to a target element. ...

Possibly animates down to a target element. Allows addition of behavior to the hide operation. After calling the superclass’s onHide, the Component will be hidden. Gets passed the same parameters as hide. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onHorizontalScroll

...

**Parameters:** event : Object


### onKeyDown

Listen for TAB events and wrap round if tabbing of either end of the Floater ...

Listen for TAB events and wrap round if tabbing of either end of the Floater

**Parameters:** e : Object


### onLockMenuClick

...


### onLockedHeaderAdd

...


### onLockedHeaderHide

...


### onLockedHeaderResize

...


### onLockedHeaderShow

...


### onLockedHeaderSortChange

...

**Parameters:** headerCt : Object


### onLockedViewMouseWheel

Listen for mousewheel events on the locked section which does not scroll. ...

Listen for mousewheel events on the locked section which does not scroll. Scroll it in response, and the other section will automatically sync.

**Parameters:** e : Object


### onLockedViewScroll

...


### onMouseDown

Mousedown brings to front, and programatically grabs focus unless the mousedown was on a focusable element ...

Mousedown brings to front, and programatically grabs focus *unless the mousedown was on a focusable element*

**Parameters:** e : Object


### onMouseEnterFloated

...

**Parameters:** e : Object


### onMouseLeaveFloated

...

**Parameters:** e : Object


### onMove

...


### onNormalHeaderSortChange

...

**Parameters:** headerCt : Object


### onNormalViewScroll

...


### onPosition

Called after the component is moved, this method is empty by default but can be implemented by any subclass that need...

Called after the component is moved, this method is empty by default but can be implemented by any subclass that needs to perform custom logic after a move occurs. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRemove

This method is invoked after a new Component has been removed. ...

This method is invoked after a new Component has been removed. It is passed the Component which has been removed. This method may be used to update any internal structure which may depend upon the state of the child items. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRemoved

Method to manage awareness of when components are removed from their respective Container, firing a removed event. ...

Method to manage awareness of when components are removed from their respective Container, firing a removed event. References are properly cleaned up after removing a component from its owning container. Allows addition of behavior when a Component is removed from its parent Container. At this stage, the Component has been removed from its parent Container's collection of child items, but has not been destroyed (It will be destroyed if the parent Container's `autoDestroy` is `true`, or if the remove call was passed a truthy second parameter). After calling the superclass's `onRemoved`, the `ownerCt` and the `refOwner` will not be present. Available since: 3.4.0 This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRender

Template method called when this Component's DOM structure is created. ...

Template method called when this Component's DOM structure is created. At this point, this Component's (and all descendants') DOM structure *exists* but it has not been layed out (positioned and sized). Subclasses which override this to gain access to the structure at render time should call the parent class's method before attempting to access any child elements of the Component. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onResize

Allows addition of behavior to the resize operation. ...

Allows addition of behavior to the resize operation. Called when Ext.resizer.Resizer#drag event is fired. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRestoreHorzScroll

Tracks when things happen to the view and preserves the horizontal scroll position. ...

Tracks when things happen to the view and preserves the horizontal scroll position.


### onShow

Allows addition of behavior to the show operation. ...

Allows addition of behavior to the show operation. After calling the superclass's onShow, the Component will be visible. Override in subclasses where more complex behaviour is needed. Gets passed the same parameters as show. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onShowComplete

Invoked after the afterShow method is complete. ...

Invoked after the afterShow method is complete. Gets passed the same `callback` and `scope` parameters that afterShow received. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onShowVeto

...


### onStateChange

This method is called when any of the stateEvents are fired. ...

This method is called when any of the stateEvents are fired.


### onStoreLoad

template method meant to be overriden ...

template method meant to be overriden


### onUnlockMenuClick

...


### onViewReady

Fires the TablePanel's viewready event when the view declares that its internal DOM is ready ...

Fires the TablePanel's viewready event when the view declares that its internal DOM is ready


### parseBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** box : Object


### placeholderCollapse

...

**Parameters:** direction : Object


### placeholderExpand

...

**Parameters:** animate : Object


### postBlur

Template method to do any post-blur processing. ...

Template method to do any post-blur processing.

**Parameters:** e : Ext.EventObjectThe event object


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a class derives from this class or uses this class as a mixin.

**Parameters:** T : FunctionThe class constructor to prepare.


### prepareItems

...

**Parameters:** items : Object


### prevChild

...

**Parameters:** child : Object


### previousNode

Returns the previous node in the Component tree in tree traversal order. ...

**Parameters:** selector : String (optional)A ComponentQuery selector to filter the preceding nodes.

**Returns:** the previous node in the Component tree in tree traversal order. Note that this is not limited to siblings, and if invoked upon a node with no matching siblings, will walk the tree in reverse order to attempt to find a match. Contrast with previousSibling.


### previousSibling

Returns the previous sibling of this Component. ...

**Parameters:** selector : String (optional)A ComponentQuery selector to filter the preceding items.

**Returns:** the previous sibling of this Component. Optionally selects the previous sibling which matches the passed ComponentQuery selector. May also be referred to as **`prev()`** Note that this is limited to siblings, and if no siblings of the item match, `null` is returned. Contrast with previousNode


### processColumns

...

**Parameters:** columns : Object


### processEvent

Processes UI events from the view. ...

Processes UI events from the view. Propagates them to whatever internal Components need to process them.

**Parameters:** type : StringEvent type, eg 'click'


### prune

...

**Parameters:** childEls : Object


### query

Retrieves all descendant components which match the passed selector. ...

Retrieves all descendant components which match the passed selector. Executes an Ext.ComponentQuery.query using this container as its root.

**Parameters:** selector : String (optional)Selector complying to an Ext.ComponentQuery selector. If no selector is specified all items will be returned.


### queryBy

Retrieves all descendant components which match the passed function. ...

Retrieves all descendant components which match the passed function. The function should return false for components that are to be excluded from the selection.

**Parameters:** fn : FunctionThe matcher function. It will be called with a single argument, the component being tested.


### queryById

Finds a component at any level under this container matching the id/itemId. ...

Finds a component at any level under this container matching the id/itemId. This is a shorthand for calling ct.down('#' + id);

**Parameters:** id : StringThe id to find


### reconfigure

documented on GridPanel ...

documented on GridPanel

**Parameters:** store : Object


### reconfigureLockable

we want to totally override the reconfigure behaviour here, since we're creating 2 sub-grids ...

we want to totally override the reconfigure behaviour here, since we're creating 2 sub-grids

**Parameters:** store : Object


### registerFloatingItem

Called by Component#doAutoRender Register a Container configured floating: true with this Component's ZIndexManager. ...

Called by Component#doAutoRender Register a Container configured `floating: true` with this Component's ZIndexManager. Components added in this way will not participate in any layout, but will be rendered upon first show in the way that Windows are.

**Parameters:** cmp : Object


### registerWithOwnerCt

...


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`. For example if you are extending Grid, you might decide to forward some events from store. So you can do this inside your initComponent: The grid instance will then have an observable 'load' event which will be passed the parameters of the store's load event and any function fired with the grid's load event would have access to the grid using the `this` keyword.

**Parameters:** origin : ObjectThe Observable whose events this object is to relay.


### relayHeaderCtEvents

...

**Parameters:** headerCt : Object


### remove

Removes a component from this container. ...

Removes a component from this container. Fires the beforeremove event before removing, then fires the remove event after the component has been removed. Available since: 2.3.0

**Parameters:** component : Ext.Component/StringThe component reference or id to remove.


### removeAll

Removes all components from this container. ...

Removes all components from this container. Available since: 2.3.0

**Parameters:** autoDestroy : Boolean (optional)True to automatically invoke the removed Component's Ext.Component.destroy function. Defaults to the value of this Container's autoDestroy config.


### removeAnchor

Remove any anchor to this element. ...

Remove any anchor to this element. See anchorTo.

**Returns:** Ext.util.Positionablethis


### removeBodyCls

Removes a CSS class from the body element. ...

Removes a CSS class from the body element.

**Parameters:** cls : StringThe class to remove


### removeChildEls

Removes items in the childEls array based on the return value of a supplied test function. ...

Removes items in the childEls array based on the return value of a supplied test function. The function is called with a entry in childEls and if the test function return true, that entry is removed. If false, that entry is kept.

**Parameters:** testFn : FunctionThe test function.


### removeClass

...

Available since: 2.3.0


### removeCls

Removes a CSS class from the top level element representing this component. ...

Removes a CSS class from the top level element representing this component.

**Parameters:** cls : String/String[]The CSS class name to remove.


### removeClsWithUI

Removes a cls to the uiCls array, which will also call removeUIClsFromElement and removes it from all elements of thi...

Removes a `cls` to the `uiCls` array, which will also call removeUIClsFromElement and removes it from all elements of this component.

**Parameters:** cls : String/String[]A string or an array of strings to remove to the `uiCls`.


### removeDocked

Removes the docked item from the panel. ...

Removes the docked item from the panel.

**Parameters:** item : Ext.ComponentThe Component to remove.


### removeListener

Removes an event handler. ...

Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### removeManagedListener

Removes listeners that were added by the mon method. ...

Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### removeManagedListenerItem

inherit docs Remove a single managed listener item ...

inherit docs Remove a single managed listener item

**Parameters:** isClear : BooleanTrue if this is being called during a clear


### removeOverCls

...


### removePlugin

...

**Parameters:** plugin : Object


### removeUIClsFromElement

inherit docs Method which removes a specified UI + uiCls from the components element. ...

inherit docs Method which removes a specified UI + `uiCls` from the components element. The `cls` which is added to the element will be: `this.baseCls + '-' + ui`.

**Parameters:** ui : StringThe UI to add to the element.


### removeUIFromElement

inherit docs Method which removes a specified UI from the components element. ...

inherit docs Method which removes a specified UI from the components element. Overrides: Ext.AbstractComponent.removeUIFromElement


### render

Renders the Component into the passed HTML element. ...

Renders the Component into the passed HTML element. If you are using a Container object to house this Component, then do not use the render method. A Container's child Components are rendered by that Container's layout manager when the Container is first rendered. If the Container is already rendered when a new child Component is added, you may need to call the Container's doLayout to refresh the view which causes any unrendered child Components to be rendered. This is required so that you can add multiple child components if needed while only refreshing the layout once. When creating complex UIs, it is important to remember that sizing and positioning of child items is the responsibility of the Container's layout manager. If you expect child items to be sized in response to user interactions, you must configure the Container with a layout manager which creates and manages the type of layout you have in mind. Omitting the Container's layout config means that a basic layout manager is used which does nothing but render child components sequentially into the Container. No sizing or positioning will be performed in this situation.

**Parameters:** container : Ext.Element/HTMLElement/String (optional)The element this Component should be rendered into. If it is being created from existing markup, this should be omitted.


### repositionFloatingItems

...


### restoreDimension

...


### restoreHiddenDocked

...


### restoreScrollPos

...


### resumeEvent

Resumes firing of the named event(s). ...

Resumes firing of the named event(s). After calling this method to resume events, the events will fire when requested to fire. Note that if the suspendEvent method is called multiple times for a certain event, this converse method will have to be called the same number of times for it to resume firing.

**Parameters:** eventName : String...Multiple event names to resume.


### resumeEvents

Resumes firing events (see suspendEvents). ...

Resumes firing events (see suspendEvents). If events were suspended using the `queueSuspended` parameter, then all events fired during event suspension will be sent to any listeners now.


### resumeLayouts

...

**Parameters:** flushOptions : Object


### savePropToState

Conditionally saves a single property from this object to the given state object. ...

Conditionally saves a single property from this object to the given state object. The idea is to only save state which has changed from the initial state so that current software settings do not override future software settings. Only those values that are user-changed state should be saved.

**Parameters:** propName : StringThe name of the property to save.


### savePropsToState

Gathers additional named properties of the instance and adds their current values to the passed state object. ...

Gathers additional named properties of the instance and adds their current values to the passed state object.

**Parameters:** propNames : String/String[]The name (or array of names) of the property to save.


### saveScrollPos

...


### saveState

Saves the state of the object to the persistence store. ...

Saves the state of the object to the persistence store.


### scrollBy

Scrolls this Component's target element by the passed delta values, optionally animating. ...

Scrolls this Component's target element by the passed delta values, optionally animating. All of the following are equivalent:

**Parameters:** deltaX : Number/Number[]/ObjectEither the x delta, an Array specifying x and y deltas or an object with "x" and "y" properties.


### scrollByDeltaX

...

**Parameters:** xDelta : Object


### scrollByDeltaY

...

**Parameters:** yDelta : Object


### sequenceFx

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. ...

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. This is the opposite of syncFx.

**Returns:** Objectthis


### setActive

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been moved to th...

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been moved to the top of its zIndex stack, or pushed from the top of its zIndex stack. If a *Window* is superceded by another Window, deactivating it hides its shadow. This method also fires the activate or deactivate event depending on which action occurred.

**Parameters:** active : Boolean (optional)True to activate the Component, false to deactivate it. Defaults to: `false`


### setAutoScroll

autoScroll is never valid for all classes which extend TablePanel. ...

autoScroll is never valid for all classes which extend TablePanel. Overrides: Ext.Component.setAutoScroll


### setBodyStyle

Sets the body style according to the passed parameters. ...

Sets the body style according to the passed parameters.

**Parameters:** style : MixedA full style specification string, or object, or the name of a style property to set.


### setBorder

...

**Parameters:** border : String/NumberThe border, see border. If a falsey value is passed the border will be removed.


### setBorderRegion

This method changes the region config property for this border region. ...

This method changes the `region` config property for this border region. This is only valid if this component is in a `border` layout (`Ext.layout.container.Border`). **Defined in override Ext.layout.container.border.Region.**

**Parameters:** region : StringThe new `region` value (`"north"`, `"south"`, `"east"` or `"west"`).


### setBox

Sets the element's box. ...

Sets the element's box. If animate is true then x, y, width, and height will be animated concurrently.

**Parameters:** box : ObjectThe box to fill {x, y, width, height}


### setComponentLayout

...

**Parameters:** layout : Object


### setConfig

...

**Parameters:** config : Object


### setDisabled

Enable or disable the component. ...

Enable or disable the component.

**Parameters:** disabled : Boolean`true` to disable.


### setDocked

Sets the dock position of this component in its parent panel. ...

Sets the dock position of this component in its parent panel. Note that this only has effect if this item is part of the `dockedItems` collection of a parent that has a DockLayout (note that any Panel has a DockLayout by default)

**Parameters:** dock : ObjectThe dock position.


### setFloatParent

...

**Parameters:** floatParent : Object


### setGlyph

Set the glyph for the panel's header. ...

Set the glyph for the panel's header. See Ext.panel.Header.glyph. It will fire the glyphchange event after completion.

**Parameters:** newGlyph : Number/StringThe new glyph This parameter expects a format consistent with that of glyph


### setHeight

Sets the height of the component. ...

Sets the height of the component. This method fires the resize event.

**Parameters:** - height : NumberThe new height to set. This may be one of: A Number specifying the new height in the Element's Ext.Element.defaultUnits (by default, pixels). - A String used to set the CSS height style. - *undefined* to leave the height unchanged.


### setHiddenDocked

...


### setHiddenState

...

**Parameters:** hidden : Object


### setIcon

Set the icon for the panel's header. ...

Set the icon for the panel's header. See Ext.panel.Header.icon. It will fire the iconchange event after completion.

**Parameters:** newIcon : StringThe new icon path


### setIconCls

Set the iconCls for the panel's header. ...

Set the iconCls for the panel's header. See Ext.panel.Header.iconCls. It will fire the iconclschange event after completion.

**Parameters:** newIconCls : StringThe new CSS class name


### setLayout

...

**Parameters:** layout : Object


### setLoading

This method allows you to show or hide a LoadMask on top of this component. ...

This method allows you to show or hide a LoadMask on top of this component.

**Parameters:** load : Boolean/Object/StringTrue to show the default LoadMask, a config object that will be passed to the LoadMask constructor, or a message String to show. False to hide the current LoadMask.


### setLocalX

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.** Sets the local x coordinate of this element using CSS style. When used on an absolute positioned element this method is symmetrical with getLocalX, but may not be symmetrical when used on a relatively positioned element.

**Parameters:** x : NumberThe x coordinate. A value of `null` sets the left style to 'auto'.


### setLocalXY

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.** Sets the local x and y coordinates of this element using CSS style. When used on an absolute positioned element this method is symmetrical with getLocalXY, but may not be symmetrical when used on a relatively positioned element.

**Parameters:** x : Number/ArrayThe x coordinate or an array containing [x, y]. A value of `null` sets the left style to 'auto'


### setLocalY

Sets the local y coordinate of this element using CSS style. ...

Sets the local y coordinate of this element using CSS style. When used on an absolute positioned element this method is symmetrical with getLocalY, but may not be symmetrical when used on a relatively positioned element.

**Parameters:** y : NumberThe y coordinate. A value of `null` sets the top style to 'auto'.


### setMargin

Sets the margin on the target element. ...

Sets the margin on the target element.

**Parameters:** margin : Number/StringThe margin to set. See the margin config.


### setOverflowXY

Sets the overflow x/y on the content element of the component. ...

Sets the overflow x/y on the content element of the component. The x/y overflow values can be any valid CSS overflow (e.g., 'auto' or 'scroll'). By default, the value is 'hidden'. Passing null for one of the values will erase the inline style. Passing `undefined` will preserve the current value.

**Parameters:** overflowX : StringThe overflow-x value.


### setPagePosition

Sets the page XY position of the component. ...

Sets the page XY position of the component. To set the left and top instead, use setPosition. This method fires the move event.

**Parameters:** x : Number/Number[]The new x position or an array of `[x,y]`.


### setPosition

Sets the left and top of the component. ...

Sets the left and top of the component. To set the page XY position instead, use setPagePosition. This method fires the move event.

**Parameters:** x : Number/Number[]/ObjectThe new left, an array of `[x,y]`, or animation config object containing `x` and `y` properties.


### setRegion

Sets the element's position and size to the specified region. ...

Sets the element's position and size to the specified region. If animation is true then width, height, x and y will be animated concurrently.

**Parameters:** region : Ext.util.RegionThe region to fill


### setRegionWeight

Sets the weight config property for this component. ...

Sets the `weight` config property for this component. This is only valid if this component is in a `border` layout (`Ext.layout.container.Border`). **Defined in override Ext.layout.container.border.Region.**

**Parameters:** weight : NumberThe new `weight` value.


### setSize

Sets the width and height of this Component. ...

Sets the width and height of this Component. This method fires the resize event. This method can accept either width and height as separate arguments, or you can pass a size object like `{width:10, height:20}`.

**Parameters:** - width : Number/String/ObjectThe new width to set. This may be one of: A Number specifying the new width in the Element's Ext.Element.defaultUnits (by default, pixels). - A String used to set the CSS width style. - A size object in the format `{width: widthValue, height: heightValue}`. - `undefined` to leave the width unchanged.


### setTitle

Set a title for the panel's header. ...

Set a title for the panel's header. See Ext.panel.Header.title.

**Parameters:** newTitle : String


### setUI

Sets the UI for the component. ...

Sets the UI for the component. This will remove any existing UIs on the component. It will also loop through any `uiCls` set on the component and rename them so they include the new UI.

**Parameters:** ui : StringThe new UI for the component.


### setVisible

Convenience function to hide or show this component by Boolean. ...

Convenience function to hide or show this component by Boolean. Available since: 1.1.0

**Parameters:** visible : Boolean`true` to show, `false` to hide.


### setWidth

Sets the width of the component. ...

Sets the width of the component. This method fires the resize event.

**Parameters:** - width : NumberThe new width to setThis may be one of: A Number specifying the new width in the Element's Ext.Element.defaultUnits (by default, pixels). - A String used to set the CSS width style.


### setX

Sets the X position of the DOM element based on page coordinates. ...

Sets the X position of the DOM element based on page coordinates.

**Parameters:** The : NumberX position


### setXY

Sets the position of the DOM element in page coordinates. ...

Sets the position of the DOM element in page coordinates.

**Parameters:** pos : Number[]Contains X & Y [x, y] values for new position (coordinates are page-based)


### setY

Sets the Y position of the DOM element based on page coordinates. ...

Sets the Y position of the DOM element based on page coordinates.

**Parameters:** The : NumberY position


### setZIndex

z-index is managed by the zIndexManager and may be overwritten at any time. ...

z-index is managed by the zIndexManager and may be overwritten at any time.

**Parameters:** index : Object

**Returns:** the next z-index to be used. If this is a Container, then it will have rebased any managed floating Components, and so the next available z-index will be approximately 10000 above that.


### setupDockingRenderTpl

...

**Parameters:** renderTpl : Object


### setupFramingTpl

Inject a reference to the function which applies the render template into the framing template. ...

Inject a reference to the function which applies the render template into the framing template. The framing template wraps the content.

**Parameters:** frameTpl : Object


### setupProtoEl

...


### setupRenderTpl

...

**Parameters:** renderTpl : Object


### show

Shows this Component, rendering it first if autoRender or floating are true. ...

Shows this Component, rendering it first if autoRender or floating are `true`. After being shown, a floating Component (such as a Ext.window.Window), is activated it and brought to the front of its z-index stack.

**Parameters:** animateTarget : String/Ext.Element (optional)only valid for floating Components such as Windows or ToolTips, or regular Components which have been configured with `floating: true`. The target from which the Component should animate from while opening. Defaults to: `null`


### showAt

Displays component at specific xy position. ...

Displays component at specific xy position. A floating component (like a menu) is positioned relative to its ownerCt if any. Useful for popping up a context menu:

**Parameters:** x : Number/Number[]The new x position or array of `[x,y]`.


### showBy

Shows this component by the specified Component or Element. ...

Shows this component by the specified Component or Element. Used when this component is floating.

**Parameters:** component : Ext.Component/Ext.dom.ElementThe Ext.Component or Ext.Element to show the component by.


### showMenuBy

...

**Parameters:** t : Object


### slideOutFloatedPanel

...


### slideOutFloatedPanelBegin

This method begins the slide out of the floated panel. ...

This method begins the slide out of the floated panel.


### slideOutFloatedPanelEnd

This method cleans up after the slide out of the floated panel. ...

This method cleans up after the slide out of the floated panel.


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### stopAnimation

Stops any running effects and clears this object's internal effects queue if it contains any additional effects that ...

Stops any running effects and clears this object's internal effects queue if it contains any additional effects that haven't started yet.

**Returns:** Ext.ElementThe Element


### stopFx

Stops any running effects and clears this object's internal effects queue if it contains any additional effects that ...

Stops any running effects and clears this object's internal effects queue if it contains any additional effects that haven't started yet. This method has been **deprecated** since 4.0 Replaced by stopAnimation


### suspendEvent

Suspends firing of the named event(s). ...

Suspends firing of the named event(s). After calling this method to suspend events, the events will no longer fire when requested to fire. Note that if this is called multiple times for a certain event, the converse method resumeEvent will have to be called the same number of times for it to resume firing.

**Parameters:** eventName : String...Multiple event names to suspend.


### suspendEvents

Suspends the firing of all events. ...

Suspends the firing of all events. (see resumeEvents)

**Parameters:** queueSuspended : BooleanPass as true to queue up suspended events to be fired after the resumeEvents call instead of discarding all suspended events.


### suspendLayouts

...


### syncFx

Ensures that all effects queued after syncFx is called on this object are run concurrently. ...

Ensures that all effects queued after syncFx is called on this object are run concurrently. This is the opposite of sequenceFx.

**Returns:** Objectthis


### syncHidden

synchronizes the hidden state of this component with the state of its hierarchy ...

synchronizes the hidden state of this component with the state of its hierarchy


### syncHorizontalScroll

...

**Parameters:** left : Object


### syncLockedWidth

Updates the overall view after columns have been resized, or moved from the locked to unlocked side or vice-versa. ...

Updates the overall view after columns have been resized, or moved from the locked to unlocked side or vice-versa. If all columns are removed from either side, that side must be hidden, and the sole remaining column owning grid then becomes *the* grid. It must flex to occupy the whole of the locking view. And it must also allow scrolling. If columns are shared between the two sides, the *locked* grid shrinkwraps the width of the visible locked columns while the normal grid flexes in what space remains.

**Returns:** Boolean`true` if there are visible locked columns which need refreshing.


### syncRowHeights

Synchronizes the row heights between the locked and non locked portion of the grid for each row. ...

Synchronizes the row heights between the locked and non locked portion of the grid for each row. If one row is smaller than the other, the height will be increased to match the larger one.


### syncShadow

...


### toBack

Sends this Component to the back of (lower z-index than) any other visible windows ...

Sends this Component to the back of (lower z-index than) any other visible windows

**Returns:** Ext.Componentthis


### toFront

Brings this floating Component to the front of any other visible, floating Components managed by the same ZIndexManag...

Brings this floating Component to the front of any other visible, floating Components managed by the same ZIndexManager If this Component is modal, inserts the modal mask just below this Component in the z-index stack.

**Parameters:** preventFocus : Boolean (optional)Specify `true` to prevent the Component from being focused. Defaults to: `false`


### toggleCollapse

Shortcut for performing an expand or collapse based on the current state of the panel. ...

Shortcut for performing an expand or collapse based on the current state of the panel.

**Returns:** Ext.panel.Panelthis


### translatePoints

Translates the passed page coordinates into left/top css values for the element ...

Translates the passed page coordinates into left/top css values for the element

**Parameters:** x : Number/ArrayThe page x or an array containing [x, y]


### translateXY

Translates the passed page coordinates into x and y css values for the element ...

Translates the passed page coordinates into x and y css values for the element

**Parameters:** x : Number/ArrayThe page x or an array containing [x, y]


### un

Shorthand for removeListener. ...

Shorthand for removeListener. Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### unbindStore

...


### unghost

...

**Parameters:** show : Object


### unitizeBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** box : Object


### unlock

Unlocks the activeHeader as determined by which menu is open OR a header as specified. ...

Unlocks the activeHeader as determined by which menu is open OR a header as specified.

**Parameters:** header : Ext.grid.column.Column (optional)Header to unlock from the locked section. Defaults to the header which has the menu open currently.


### unmask

...


### unregisterFloatingItem

...

**Parameters:** cmp : Object


### up

Navigates up the ownership hierarchy searching for an ancestor Container which matches any passed simple selector or ...

Navigates up the ownership hierarchy searching for an ancestor Container which matches any passed simple selector or component. *Important.* There is not a universal upwards navigation pointer. There are several upwards relationships such as the button which activates a menu, or the menu item which activated a submenu, or the column header which activated the column menu. These differences are abstracted away by this method. Example:

**Parameters:** selector : String/Ext.Component (optional)The simple selector component or actual component to test. If not passed the immediate owner/activater is returned.


### update

Update the content area of a component. ...

Update the content area of a component. Available since: 3.4.0

**Parameters:** htmlOrData : String/ObjectIf this component has been configured with a template via the tpl config then it will use this argument as data to populate the template. If this component was not configured with a template, the components content area will be updated via Ext.Element update.


### updateAria

Injected as an override by Ext.Aria.initialize ...

Injected as an override by Ext.Aria.initialize


### updateBox

Sets the current box measurements of the component's underlying element. ...

Sets the current box measurements of the component's underlying element.

**Parameters:** box : ObjectAn object in the format {x, y, width, height}


### updateCollapseTool

...


### updateFrame

...


### updateHeader

Create, hide, or show the header component as appropriate based on the current config. ...

Create, hide, or show the header component as appropriate based on the current config.

**Parameters:** force : BooleanTrue to force the header to be created


### updateLayout

Updates this component's layout. ...

Updates this component's layout. If this update affects this components ownerCt, that component's `updateLayout` method will be called to perform the layout instead. Otherwise, just this component (and its child items) will layout.

**Parameters:** options : Object (optional)An object with layout options. defer : Boolean`true` if this layout should be deferred.


### wrapPrimaryEl

...

**Parameters:** dom : Object


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


### activate

Fires after a Component has been visually activated. ...

Fires after a Component has been visually activated.

**Parameters:** this : Ext.Component


### add

Fires after any Ext.Component is added or inserted into the container. ...

Fires after any Ext.Component is added or inserted into the container. **This event bubbles:** 'add' will also be fired when Component is added to any of the child containers or their childern or ... Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### added

Fires after a Component had been added to a Container. ...

Fires after a Component had been added to a Container. Available since: 3.4.0

**Parameters:** this : Ext.Component


### afterlayout

Fires when the components in this container are arranged by the associated layout manager. ...

Fires when the components in this container are arranged by the associated layout manager. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### afterrender

Fires after the component rendering is finished. ...

Fires after the component rendering is finished. The `afterrender` event is fired after this Component has been rendered, been postprocessed by any `afterRender` method defined for the Component. Available since: 3.4.0

**Parameters:** this : Ext.Component


### beforeactivate

Fires before a Component has been visually activated. ...

Fires before a Component has been visually activated. Returning `false` from an event listener can prevent the activate from occurring.

**Parameters:** this : Ext.Component


### beforeadd

Fires before any Ext.Component is added or inserted into the container. ...

Fires before any Ext.Component is added or inserted into the container. A handler can return false to cancel the add. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### beforecellclick

Fired before the cell click is processed. ...

Fired before the cell click is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellcontextmenu

Fired before the cell right click is processed. ...

Fired before the cell right click is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecelldblclick

Fired before the cell double click is processed. ...

Fired before the cell double click is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellkeydown

Fired before the cell key down is processed. ...

Fired before the cell key down is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellmousedown

Fired before the cell mouse down is processed. ...

Fired before the cell mouse down is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellmouseup

Fired before the cell mouse up is processed. ...

Fired before the cell mouse up is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforeclose

Fires before the user closes the panel. ...

Fires before the user closes the panel. Return false from any listener to stop the close event being fired

**Parameters:** panel : Ext.panel.PanelThe Panel object


### beforecollapse

Fires before this panel is collapsed. ...

Fires before this panel is collapsed. Return false to prevent the collapse.

**Parameters:** p : Ext.panel.PanelThe Panel being collapsed.


### beforecontainerclick

Fires before the click event on the container is processed. ...

Fires before the click event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainercontextmenu

Fires before the contextmenu event on the container is processed. ...

Fires before the contextmenu event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainerdblclick

Fires before the dblclick event on the container is processed. ...

Fires before the dblclick event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermousedown

Fires before the mousedown event on the container is processed. ...

Fires before the mousedown event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermouseout

Fires before the mouseout event on the container is processed. ...

Fires before the mouseout event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermouseover

Fires before the mouseover event on the container is processed. ...

Fires before the mouseover event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermouseup

Fires before the mouseup event on the container is processed. ...

Fires before the mouseup event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforedeactivate

Fires before a Component has been visually deactivated. ...

Fires before a Component has been visually deactivated. Returning `false` from an event listener can prevent the deactivate from occurring.

**Parameters:** this : Ext.Component


### beforedeselect

Fired before a record is deselected. ...

Fired before a record is deselected. If any listener returns false, the deselection is cancelled.

**Parameters:** this : Ext.selection.RowModel


### beforedestroy

Fires before the component is destroyed. ...

Fires before the component is destroyed. Return `false` from an event handler to stop the destroy. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeexpand

Fires before this panel is expanded. ...

Fires before this panel is expanded. Return false to prevent the expand.

**Parameters:** p : Ext.panel.PanelThe Panel being expanded.


### beforehide

Fires before the component is hidden when calling the hide method. ...

Fires before the component is hidden when calling the hide method. Return `false` from an event handler to stop the hide. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeitemclick

Fires before the click event on an item is processed. ...

Fires before the click event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemcontextmenu

Fires before the contextmenu event on an item is processed. ...

Fires before the contextmenu event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemdblclick

Fires before the dblclick event on an item is processed. ...

Fires before the dblclick event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmousedown

Fires before the mousedown event on an item is processed. ...

Fires before the mousedown event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmouseenter

Fires before the mouseenter event on an item is processed. ...

Fires before the mouseenter event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmouseleave

Fires before the mouseleave event on an item is processed. ...

Fires before the mouseleave event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmouseup

Fires before the mouseup event on an item is processed. ...

Fires before the mouseup event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeremove

Fires before any Ext.Component is removed from the container. ...

Fires before any Ext.Component is removed from the container. A handler can return false to cancel the remove. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### beforerender

Fires before the component is rendered. ...

Fires before the component is rendered. Return `false` from an event handler to stop the render. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeselect

Fired before a record is selected. ...

Fired before a record is selected. If any listener returns false, the selection is cancelled.

**Parameters:** this : Ext.selection.RowModel


### beforeshow

Fires before the component is shown when calling the show method. ...

Fires before the component is shown when calling the show method. Return `false` from an event handler to stop the show. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforestaterestore

Fires before the state of the object is restored. ...

Fires before the state of the object is restored. Return false from an event handler to stop the restore.

**Parameters:** this : Ext.state.Stateful


### beforestatesave

Fires before the state of the object is saved to the configured state provider. ...

Fires before the state of the object is saved to the configured state provider. Return false to stop the save.

**Parameters:** this : Ext.state.Stateful


### blur

Fires when this Component loses focus. ...

Fires when this Component loses focus.

**Parameters:** this : Ext.Component


### boxready

Fires one time - after the component has been laid out for the first time at its initial size. ...

Fires *one time* - after the component has been laid out for the first time at its initial size.

**Parameters:** this : Ext.Component


### cellclick

Fired when table cell is clicked. ...

Fired when table cell is clicked.

**Parameters:** this : Ext.view.Table


### cellcontextmenu

Fired when table cell is right clicked. ...

Fired when table cell is right clicked.

**Parameters:** this : Ext.view.Table


### celldblclick

Fired when table cell is double clicked. ...

Fired when table cell is double clicked.

**Parameters:** this : Ext.view.Table


### cellkeydown

Fired when the keydown event is captured on the cell. ...

Fired when the keydown event is captured on the cell.

**Parameters:** this : Ext.view.Table


### cellmousedown

Fired when the mousedown event is captured on the cell. ...

Fired when the mousedown event is captured on the cell.

**Parameters:** this : Ext.view.Table


### cellmouseup

Fired when the mouseup event is captured on the cell. ...

Fired when the mouseup event is captured on the cell.

**Parameters:** this : Ext.view.Table


### close

Fires when the user closes the panel. ...

Fires when the user closes the panel.

**Parameters:** panel : Ext.panel.PanelThe Panel object


### collapse

Fires after this Panel has collapsed. ...

Fires after this Panel has collapsed.

**Parameters:** p : Ext.panel.PanelThe Panel that has been collapsed.


### columnhide

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnmove

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnresize

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnschanged

Fired after the columns change in any way, when a column has been hidden or shown, or when a column is added to or re...

Fired after the columns change in any way, when a column has been hidden or shown, or when a column is added to or removed from this header container.

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnshow

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### containerclick

Fires when the container is clicked. ...

Fires when the container is clicked.

**Parameters:** this : Ext.view.View


### containercontextmenu

Fires when the container is right clicked. ...

Fires when the container is right clicked.

**Parameters:** this : Ext.view.View


### containerdblclick

Fires when the container is double clicked. ...

Fires when the container is double clicked.

**Parameters:** this : Ext.view.View


### containermouseout

Fires when you move the mouse out of the container. ...

Fires when you move the mouse out of the container.

**Parameters:** this : Ext.view.View


### containermouseover

Fires when you move the mouse over the container. ...

Fires when you move the mouse over the container.

**Parameters:** this : Ext.view.View


### containermouseup

Fires when there is a mouse up on the container ...

Fires when there is a mouse up on the container

**Parameters:** this : Ext.view.View


### deactivate

Fires after a Component has been visually deactivated. ...

Fires after a Component has been visually deactivated.

**Parameters:** this : Ext.Component


### deselect

Fired after a record is deselected ...

Fired after a record is deselected

**Parameters:** this : Ext.selection.RowModel


### destroy

Fires after the component is destroyed. ...

Fires after the component is destroyed. Available since: 1.1.0

**Parameters:** this : Ext.Component


### disable

Fires after the component is disabled. ...

Fires after the component is disabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### dockedadd

Fires when any Ext.Component is added or inserted as a docked item. ...

Fires when any Ext.Component is added or inserted as a docked item.

**Parameters:** this : Ext.panel.Panel


### dockedremove

Fires when any Ext.Component is removed from the docked items. ...

Fires when any Ext.Component is removed from the docked items.

**Parameters:** this : Ext.panel.Panel


### enable

Fires after the component is enabled. ...

Fires after the component is enabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### expand

Fires after this Panel has expanded. ...

Fires after this Panel has expanded.

**Parameters:** p : Ext.panel.PanelThe Panel that has been expanded.


### filterchange

Fired whenever the filter set changes. ...

Fired whenever the filter set changes.

**Parameters:** store : Ext.data.StoreThe store.


### float

Fires after a collapsed Panel has been "floated" by clicking on it's header. ...

Fires after a collapsed Panel has been "floated" by clicking on it's header. Only applicable when the Panel is an item in a Border Layout.

**Parameters:** eOpts : ObjectThe options object passed to Ext.util.Observable.addListener.


### focus

Fires when this Component receives focus. ...

Fires when this Component receives focus.

**Parameters:** this : Ext.Component


### glyphchange

Fired when the Panel glyph has been changed by the setGlyph method. ...

Fired when the Panel glyph has been changed by the setGlyph method.

**Parameters:** this : Ext.panel.Panel


### headerclick

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### headercontextmenu

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### headertriggerclick

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### hide

Fires after the component is hidden. ...

Fires after the component is hidden. Fires after the component is hidden when calling the hide method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### iconchange

Fires after the Panel icon has been set or changed. ...

Fires after the Panel icon has been set or changed.

**Parameters:** p : Ext.panel.PanelThe Panel which has the icon changed.


### iconclschange

Fires after the Panel iconCls has been set or changed. ...

Fires after the Panel iconCls has been set or changed.

**Parameters:** p : Ext.panel.PanelThe Panel which has the iconCls changed.


### itemclick

Fires when an item is clicked. ...

Fires when an item is clicked.

**Parameters:** this : Ext.view.View


### itemcontextmenu

Fires when an item is right clicked. ...

Fires when an item is right clicked.

**Parameters:** this : Ext.view.View


### itemdblclick

Fires when an item is double clicked. ...

Fires when an item is double clicked.

**Parameters:** this : Ext.view.View


### itemmousedown

Fires when there is a mouse down on an item ...

Fires when there is a mouse down on an item

**Parameters:** this : Ext.view.View


### itemmouseenter

Fires when the mouse enters an item. ...

Fires when the mouse enters an item.

**Parameters:** this : Ext.view.View


### itemmouseleave

Fires when the mouse leaves an item. ...

Fires when the mouse leaves an item.

**Parameters:** this : Ext.view.View


### itemmouseup

Fires when there is a mouse up on an item ...

Fires when there is a mouse up on an item

**Parameters:** this : Ext.view.View


### lockcolumn

Fires when a column is locked. ...

Fires when a column is locked.

**Parameters:** this : Ext.grid.PanelThe gridpanel.


### move

Fires after the component is moved. ...

Fires after the component is moved.

**Parameters:** this : Ext.Component


### processcolumns

Fires when the configured (or reconfigured) column set is split into two depending on the locked flag. ...

Fires when the configured (or **reconfigured**) column set is split into two depending on the locked flag.

**Parameters:** lockedColumns : Ext.grid.column.Column[]The locked columns.


### remove

Fires after any Ext.Component is removed from the container. ...

Fires after any Ext.Component is removed from the container. **This event bubbles:** 'remove' will also be fired when Component is removed from any of the child containers or their children or ... Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### removed

Fires when a component is removed from an Ext.container.Container ...

Fires when a component is removed from an Ext.container.Container Available since: 3.4.0

**Parameters:** this : Ext.Component


### render

Fires after the component markup is rendered. ...

Fires after the component markup is rendered. Available since: 1.1.0

**Parameters:** this : Ext.Component


### resize

Fires after the component is resized. ...

Fires after the component is resized. Note that this does *not* fire when the component is first laid out at its initial size. To hook that point in the life cycle, use the boxready event.

**Parameters:** this : Ext.Component


### select

Fired after a record is selected ...

Fired after a record is selected

**Parameters:** this : Ext.selection.RowModel


### selectionchange

Fired after a selection change has occurred ...

Fired after a selection change has occurred

**Parameters:** this : Ext.selection.Model


### show

Fires after the component is shown when calling the show method. ...

Fires after the component is shown when calling the show method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### sortchange

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### staterestore

Fires after the state of the object is restored. ...

Fires after the state of the object is restored.

**Parameters:** this : Ext.state.Stateful


### statesave

Fires after the state of the object is saved to the configured state provider. ...

Fires after the state of the object is saved to the configured state provider.

**Parameters:** this : Ext.state.Stateful


### titlechange

Fires after the Panel title has been set or changed. ...

Fires after the Panel title has been set or changed.

**Parameters:** p : Ext.panel.Panelthe Panel which has been resized.


### unfloat

Fires after a "floated" Panel has returned to it's collapsed state as a result of the mouse leaving the Panel. ...

Fires after a "floated" Panel has returned to it's collapsed state as a result of the mouse leaving the Panel. Only applicable when the Panel is an item in a Border Layout.

**Parameters:** eOpts : ObjectThe options object passed to Ext.util.Observable.addListener.


### unlockcolumn

Fires when a column is unlocked. ...

Fires when a column is unlocked.

**Parameters:** this : Ext.grid.PanelThe gridpanel.


### viewready

Fires when the grid view is available (use this for selecting a default row). ...

Fires when the grid view is available (use this for selecting a default row).

**Parameters:** this : Ext.panel.Table


### $border-width-threshold

**Type:** $border-width-threshold

The maximum width a Panel's border can be before resizer handles are embedded into the borders using negative absolut...

The maximum width a Panel's border can be before resizer handles are embedded into the borders using negative absolute positions. This defaults to 2, so that in the classic theme which uses 1 pixel borders, resize handles are in the content area within the border as they always have been. In the Neptune theme, the handles are embedded into the 5 pixel wide borders of any framed panel. Defaults to: `2`


### $grid-body-background-color

**Type:** color

The background-color of the grid body ...

The background-color of the grid body Defaults to: `$panel-body-background-color`


### $grid-body-border-color

**Type:** color

The border-color of the grid body ...

The border-color of the grid body Defaults to: `$panel-body-border-color`


### $grid-body-border-style

**Type:** string

The border-style of the grid body border ...

The border-style of the grid body border Defaults to: `$panel-body-border-style`


### $grid-body-border-width

**Type:** number

The border-width of the grid body border ...

The border-width of the grid body border Defaults to: `$panel-body-border-width`


### $grid-cell-inner-padding

**Type:** number

The amount of padding to apply to the grid cell's inner div element ...

The amount of padding to apply to the grid cell's inner div element Defaults to: `3px 6px`


### $grid-cell-inner-text-overflow

**Type:** string

The type of text-overflow to use on the grid cell's inner div element ...

The type of text-overflow to use on the grid cell's inner div element Defaults to: `ellipsis`


### $grid-cell-selected-background-color

**Type:** color

The background-color of a selected cell when using a Cell Selection Model. ...

The background-color of a selected cell when using a Cell Selection Model. Defaults to: `$grid-row-cell-selected-background-color`


### $grid-cell-selected-color

**Type:** color

The text color of a selected cell when using a Cell Selection Model. ...

The text color of a selected cell when using a Cell Selection Model. Defaults to: `$grid-row-cell-selected-color`


### $grid-cell-special-background-color

**Type:** color

The background-color of "special" cells. ...

The background-color of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `$grid-row-cell-background-color`


### $grid-cell-special-background-gradient

**Type:** string

The background-gradient to use for "special" cells. ...

The background-gradient to use for "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `null`


### $grid-cell-special-border-color

**Type:** color

The border-color of "special" cells. ...

The border-color of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border color is determined by {#$grid-row-cell-border-color}. Defaults to: `$grid-row-cell-border-color`


### $grid-cell-special-border-style

**Type:** string

The border-style of "special" cells. ...

The border-style of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border style is determined by {#$grid-row-cell-border-style}. Defaults to: `$grid-row-cell-border-style`


### $grid-cell-special-border-width

**Type:** number

The border-width of "special" cells. ...

The border-width of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border width is determined by {#$grid-row-cell-border-width}. Defaults to: `$grid-row-cell-border-width`


### $grid-cell-special-over-background-color

**Type:** color

The background-color of "special" cells when the row is hovered. ...

The background-color of "special" cells when the row is hovered. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `$grid-row-cell-over-background-color`


### $grid-cell-special-selected-border-color

**Type:** color

The border-color of "special" cells when the row is selected using a Row Selection Model. ...

The border-color of "special" cells when the row is selected using a Row Selection Model. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the selected row border color is determined by {#$grid-row-cell-selected-border-color}. Defaults to: `$grid-row-cell-border-color`


### $grid-empty-background-color

**Type:** color

The background color of the grid body when the grid contains no data. ...

The background color of the grid body when the grid contains no data. Defaults to: `$panel-body-background-color`


### $grid-empty-color

**Type:** color

The text color of the emptyText in the grid body when the grid contains no data. ...

The text color of the emptyText in the grid body when the grid contains no data. Defaults to: `#808080`


### $grid-empty-font-family

**Type:** number

The font-family of the emptyText in the grid body when the grid contains no data. ...

The font-family of the emptyText in the grid body when the grid contains no data. Defaults to: `$font-family`


### $grid-empty-font-size

**Type:** number

The font-size of the emptyText in the grid body when the grid contains no data. ...

The font-size of the emptyText in the grid body when the grid contains no data. Defaults to: `$grid-row-cell-font-size`


### $grid-empty-font-weight

**Type:** number

The font-weight of the emptyText in the grid body when the grid contains no data. ...

The font-weight of the emptyText in the grid body when the grid contains no data. Defaults to: `normal`


### $grid-empty-padding

**Type:** number

The amount of padding to apply to the grid body when the grid contains no data. ...

The amount of padding to apply to the grid body when the grid contains no data. Defaults to: `10px`


### $grid-lockable-separator-border-style

**Type:** string

The border-style of the border between the locked views ...

The border-style of the border between the locked views Defaults to: `solid`


### $grid-lockable-separator-border-width

**Type:** number

The width of the border between the locked views ...

The width of the border between the locked views Defaults to: `1px`


### $grid-no-row-lines-show-focus-border

**Type:** boolean

True to show the focus border when a row is focused even if the grid has no rowLines. ...

True to show the focus border when a row is focused even if the grid has no rowLines. Defaults to: `false`


### $grid-resize-marker-background-color

**Type:** color

The color of the resize markers that display when dragging a column border to resize the column ...

The color of the resize markers that display when dragging a column border to resize the column Defaults to: `#0f0f0f`


### $grid-row-cell-alt-background-color

**Type:** color

The background-color color of odd-numbered rows when the table view is configured with stripeRows: true. ...

The background-color color of odd-numbered rows when the table view is configured with `stripeRows: true`. Defaults to: `darken ( $grid-row-cell-background-color , 2 )`


### $grid-row-cell-background-color

**Type:** color

The background-color of the grid cells ...

The background-color of the grid cells Defaults to: `#fff`


### $grid-row-cell-border-color

**Type:** color

The border-color of row/column borders. ...

The border-color of row/column borders. Can be specified as a single color, or as a list of colors containing the row border color followed by the column border color. Defaults to: `#ededed`


### $grid-row-cell-border-style

**Type:** string

The border-style of the row/column borders. ...

The border-style of the row/column borders. Defaults to: `solid`


### $grid-row-cell-border-width

**Type:** number

The border-width of the row and column borders. ...

The border-width of the row and column borders. Defaults to: `1px`


### $grid-row-cell-color

**Type:** color

The color of the text in the grid cells ...

The color of the text in the grid cells Defaults to: `null`


### $grid-row-cell-focus-background-color

**Type:** color

The background-color of the focused row ...

The background-color of the focused row Defaults to: `$grid-row-cell-background-color`


### $grid-row-cell-focus-border-color

**Type:** color

The border-color of the focused row ...

The border-color of the focused row Defaults to: `#808080`


### $grid-row-cell-focus-border-style

**Type:** string

The border-style of the focused row ...

The border-style of the focused row Defaults to: `dotted`


### $grid-row-cell-focus-color

**Type:** color

The text color of the focused row ...

The text color of the focused row Defaults to: `$grid-row-cell-color`


### $grid-row-cell-font-family

**Type:** string

The font-family of the text in the grid cells ...

The font-family of the text in the grid cells Defaults to: `$font-family`


### $grid-row-cell-font-size

**Type:** number

The font size of the text in the grid cells ...

The font size of the text in the grid cells Defaults to: `$font-size`


### $grid-row-cell-font-weight

**Type:** string

The font-weight of the text in the grid cells ...

The font-weight of the text in the grid cells Defaults to: `normal`


### $grid-row-cell-line-height

**Type:** Object

var {number} $grid-row-cell-line-height The line-height of the text inside the grid cells. ...

var {number} $grid-row-cell-line-height The line-height of the text inside the grid cells. Defaults to: `round ( $grid-row-cell-font-size * 1.15 )`


### $grid-row-cell-over-background-color

**Type:** color

The background-color of the hovered row ...

The background-color of the hovered row Defaults to: `#ddd`


### $grid-row-cell-over-border-color

**Type:** color

The border-color of the hovered row ...

The border-color of the hovered row Defaults to: `$grid-row-cell-border-color`


### $grid-row-cell-over-border-style

**Type:** string

The border-style of the hovered row ...

The border-style of the hovered row Defaults to: `solid`


### $grid-row-cell-over-color

**Type:** color

The text color of the hovered row ...

The text color of the hovered row Defaults to: `$grid-row-cell-color`


### $grid-row-cell-selected-background-color

**Type:** color

The background-color of the selected row ...

The background-color of the selected row Defaults to: `#ccc`


### $grid-row-cell-selected-border-color

**Type:** color

The border-color of the selected row ...

The border-color of the selected row Defaults to: `$grid-row-cell-border-color`


### $grid-row-cell-selected-border-style

**Type:** string

The border-style of the selected row ...

The border-style of the selected row Defaults to: `solid`


### $grid-row-cell-selected-color

**Type:** color

The text color of the selected row ...

The text color of the selected row Defaults to: `$grid-row-cell-color`


### $include-panel-default-framed-ui

**Type:** boolean

True to include the "default-framed" panel UI ...

True to include the "default-framed" panel UI Defaults to: `$include-default-uis`


### $include-panel-default-ui

**Type:** boolean

True to include the "default" panel UI ...

True to include the "default" panel UI Defaults to: `$include-default-uis`


### $panel-background-stretch-bottom

**Type:** string

The direction to strech the background-gradient of bottom docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of bottom docked Headers when slicing images for IE using Sencha Cmd Defaults to: `top`


### $panel-background-stretch-left

**Type:** string

The direction to strech the background-gradient of left docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of left docked Headers when slicing images for IE using Sencha Cmd Defaults to: `right`


### $panel-background-stretch-right

**Type:** string

The direction to strech the background-gradient of right docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of right docked Headers when slicing images for IE using Sencha Cmd Defaults to: `left`


### $panel-background-stretch-top

**Type:** string

The direction to strech the background-gradient of top docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of top docked Headers when slicing images for IE using Sencha Cmd Defaults to: `bottom`


### $panel-base-color

**Type:** color

The base color of Panels ...

The base color of Panels Defaults to: `$base-color`


### $panel-body-background-color

**Type:** color

The default body background-color of Panels ...

The default body background-color of Panels Defaults to: `#fff`


### $panel-body-border-color

**Type:** color

The default border-color of the Panel body ...

The default border-color of the Panel body Defaults to: `$panel-border-color`


### $panel-body-border-style

**Type:** string

The default border-style of Panels ...

The default border-style of Panels Defaults to: `solid`


### $panel-body-border-width

**Type:** number

The default border-width of the Panel body ...

The default border-width of the Panel body Defaults to: `1px`


### $panel-body-color

**Type:** color

The default color of text inside a Panel's body ...

The default color of text inside a Panel's body Defaults to: `#000`


### $panel-body-font-size

**Type:** number

The default font-size of the Panel body ...

The default font-size of the Panel body Defaults to: `$font-size`


### $panel-body-font-weight

**Type:** string

The default font-weight of the Panel body ...

The default font-weight of the Panel body Defaults to: `normal`


### $panel-border-color

**Type:** color

The default border-color of Panels ...

The default border-color of Panels Defaults to: `$panel-base-color`


### $panel-border-width

**Type:** number

The default border-width of Panels ...

The default border-width of Panels Defaults to: `1px`


### $panel-frame-background-color

**Type:** color

The background-color of framed Panels ...

The background-color of framed Panels Defaults to: `#fff`


### $panel-frame-base-color

**Type:** color

The base color of the framed Panels ...

The base color of the framed Panels Defaults to: `$panel-base-color`


### $panel-frame-body-border-width

**Type:** number

The border-width of the body element of framed Panels ...

The border-width of the body element of framed Panels Defaults to: `1px`


### $panel-frame-border-color

**Type:** color

The border-color of framed Panels ...

The border-color of framed Panels Defaults to: `$panel-border-color`


### $panel-frame-border-radius

**Type:** number

The border-radius of framed Panels ...

The border-radius of framed Panels Defaults to: `4px`


### $panel-frame-border-style

**Type:** string

The border-style of framed Panels ...

The border-style of framed Panels Defaults to: `solid`


### $panel-frame-border-width

**Type:** number

The border-width of framed Panels ...

The border-width of framed Panels Defaults to: `1px`


### $panel-frame-header-border-width

**Type:** number

The border-width of framed Panel Headers ...

The border-width of framed Panel Headers Defaults to: `$panel-header-border-width`


### $panel-frame-header-inner-border-color

**Type:** color

The inner border-color of framed Panel Headers ...

The inner border-color of framed Panel Headers Defaults to: `#fff`


### $panel-frame-header-inner-border-width

**Type:** number

The inner border-width of framed Panel Headers ...

The inner border-width of framed Panel Headers Defaults to: `0`


### $panel-frame-header-padding

**Type:** number/list

The padding of framed Panel Headers ...

The padding of framed Panel Headers Defaults to: `$panel-header-padding`


### $panel-frame-padding

**Type:** number

The padding of framed Panels ...

The padding of framed Panels Defaults to: `4px`


### $panel-ghost-opacity

**Type:** number

The opacity of ghost Panels while dragging ...

The opacity of ghost Panels while dragging Defaults to: `0.50`


### $panel-header-background-color

**Type:** color

The background-color of the Panel Header ...

The background-color of the Panel Header Defaults to: `$panel-base-color`


### $panel-header-background-gradient

**Type:** string/list

The background-gradient of the Panel Header. ...

The background-gradient of the Panel Header. Can be either the name of a predefined gradient or a list of color stops. Used as the `$type` parameter for Global_CSS.background-gradient. Defaults to: `null`


### $panel-header-border-color

**Type:** color

The border-color of the Panel Header ...

The border-color of the Panel Header Defaults to: `$panel-border-color`


### $panel-header-border-style

**Type:** string

The border-style of Panel Headers ...

The border-style of Panel Headers Defaults to: `solid`


### $panel-header-border-width

**Type:** number

The border-width of Panel Headers ...

The border-width of Panel Headers Defaults to: `$panel-border-width`


### $panel-header-color

**Type:** color

The text color of the Panel Header ...

The text color of the Panel Header Defaults to: `$color`


### $panel-header-font-family

**Type:** string

The font-family of Panel Headers ...

The font-family of Panel Headers Defaults to: `$font-family`


### $panel-header-font-size

**Type:** number

The font-size of Panel Headers ...

The font-size of Panel Headers Defaults to: `$font-size`


### $panel-header-font-weight

**Type:** string

The font-weight of Panel Headers ...

The font-weight of Panel Headers Defaults to: `bold`


### $panel-header-glyph-color

**Type:** color

The color of the Panel Header glyph icon ...

The color of the Panel Header glyph icon Defaults to: `$panel-header-color`


### $panel-header-glyph-opacity

**Type:** number

The opacity of the Panel Header glyph icon ...

The opacity of the Panel Header glyph icon Defaults to: `.5`


### $panel-header-icon-background-position

**Type:** list

The background-position of the Panel Header icon ...

The background-position of the Panel Header icon Defaults to: `center center`


### $panel-header-icon-height

**Type:** number

The height of the Panel Header icon ...

The height of the Panel Header icon Defaults to: `16px`


### $panel-header-icon-spacing

**Type:** number

The space between the Panel Header icon and text ...

The space between the Panel Header icon and text Defaults to: `4px`


### $panel-header-icon-width

**Type:** number

The width of the Panel Header icon ...

The width of the Panel Header icon Defaults to: `16px`


### $panel-header-inner-border-color

**Type:** color

The inner border-color of the Panel Header ...

The inner border-color of the Panel Header Defaults to: `#fff`


### $panel-header-inner-border-width

**Type:** number

The inner border-width of the Panel Header ...

The inner border-width of the Panel Header Defaults to: `0`


### $panel-header-line-height

**Type:** number

The line-height of Panel Headers ...

The line-height of Panel Headers Defaults to: `16px`


### $panel-header-padding

**Type:** number/list

The padding of Panel Headers ...

The padding of Panel Headers Defaults to: `4px 5px`


### $panel-header-text-padding

**Type:** number/list

The padding of the Panel Header's text element ...

The padding of the Panel Header's text element Defaults to: `0`


### $panel-header-text-transform

**Type:** string

The text-transform of Panel Headers ...

The text-transform of Panel Headers Defaults to: `none`


### $panel-include-border-management-rules

**Type:** boolean

True to include neptune style border management rules. ...

True to include neptune style border management rules. Defaults to: `false`


### $panel-tool-background-image

**Type:** string

The background sprite to use for Panel Tools ...

The background sprite to use for Panel Tools Defaults to: `'tools/tool-sprites'`


### $panel-tool-spacing

**Type:** number

The space between the Panel Tools ...

The space between the Panel Tools Defaults to: `4px`


### $panel-wrap-border-color

**Type:** color

The color to apply to the border that wraps the body and docked items in a framed panel. ...

The color to apply to the border that wraps the body and docked items in a framed panel. The presence of the wrap border in a framed panel is controlled by the border config. Only applicable when `$panel-include-border-management-rules` is `true`. Defaults to: `$panel-border-color`


### $panel-wrap-border-width

**Type:** number

The width to apply to the border that wraps the body and docked items in a framed panel. ...

The width to apply to the border that wraps the body and docked items in a framed panel. The presence of the wrap border in a framed panel is controlled by the border config. Only applicable when `$panel-include-border-management-rules` is `true`. Defaults to: `1px`


### extjs-panel-ui

Creates a visual theme for a Panel ...

Creates a visual theme for a Panel $ui-label : stringThe name of the UI being created. Can not included spaces or special punctuation (used in CSS class names).


## Methods

### Ext.panel.Table

Creates new Component. ...

Creates new Component.

**Parameters:** - config : Ext.Element/String/ObjectThe configuration options may be specified as either: **an element** : it is set as the internal element and its id used as the component id - **a string** : it is assumed to be the id of an existing element and is used as the component id - **anything else** : it is assumed to be a standard config object and is applied to the component


### add

Adds Component(s) to this Container. ...

Adds Component(s) to this Container. Description: - Fires the beforeadd event before adding. - The Container's default config values will be applied accordingly (see `defaults` for details). - Fires the `add` event after the component has been added. Notes: If the Container is **already rendered** when `add` is called, it will render the newly added Component into its content area. **If** the Container was configured with a size-managing layout manager, the Container will recalculate its internal layout at this time too. Note that the default layout manager simply renders child Components sequentially into the content area and thereafter performs no sizing. If adding multiple new child Components, pass them as an array to the `add` method, so that only one layout recalculation is performed. To inject components between existing ones, use the insert method. Warning: Components directly managed by the BorderLayout layout manager may not be removed or added. See the Notes for BorderLayout for more details. Available since: 2.3.0

**Parameters:** component : Ext.Component[]|Object[]/Ext.Component.../Object...Either one or more Components to add or an Array of Components to add. See `items` for additional information.


### addBodyCls

Adds a CSS class to the body element. ...

Adds a CSS class to the body element. If not rendered, the class will be added when the panel is rendered.

**Parameters:** cls : StringThe class to add


### addChildEls

Adds each argument passed to this method to the childEls array. ...

Adds each argument passed to this method to the childEls array.


### addClass

Adds a CSS class to the top level element representing this component. ...

Adds a CSS class to the top level element representing this component. This method has been **deprecated** since 4.1 Use addCls instead.


### addCls

Adds a CSS class to the top level element representing this component. ...

Adds a CSS class to the top level element representing this component.

**Parameters:** cls : String/String[]The CSS class name to add.


### addClsWithUI

Adds a cls to the uiCls array, which will also call addUIClsToElement and adds to all elements of this component. ...

Adds a `cls` to the `uiCls` array, which will also call addUIClsToElement and adds to all elements of this component.

**Parameters:** classes : String/String[]A string or an array of strings to add to the `uiCls`.


### addDocked

Adds docked item(s) to the container. ...

Adds docked item(s) to the container.

**Parameters:** component : Object/Object[]The Component or array of components to add. The components must include a 'dock' parameter on each component to indicate where it should be docked ('top', 'right', 'bottom', 'left').


### addEvents

Adds the specified events to the list of events which this Observable may fire. ...

Adds the specified events to the list of events which this Observable may fire.

**Parameters:** eventNames : Object/String...Either an object with event names as properties with a value of `true`. For example: Or any number of event names as separate parameters. For example:


### addFocusListener

Sets up the focus listener on this Component's focusEl if it has one. ...

Sets up the focus listener on this Component's focusEl if it has one. Form Components which must implicitly participate in tabbing order usually have a naturally focusable element as their focusEl, and it is the DOM event of that receiving focus which drives the Component's `onFocus` handling, and the DOM event of it being blurred which drives the `onBlur` handling. If the focusEl is **not** naturally focusable, then the listeners are only added if the FocusManager is enabled.


### addListener

Appends an event handler to this object. ...

Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### addManagedListener

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destr...

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### addOverCls

...


### addPlugin

Adds a plugin. ...

Adds a plugin. May be called at any time in the component's lifecycle.

**Parameters:** plugin : Object


### addPropertyToState

Save a property to the given state object if it is not its default or configured value. ...

Save a property to the given state object if it is not its default or configured value.

**Parameters:** state : ObjectThe state object.


### addStateEvents

Add events that will trigger the state to be saved. ...

Add events that will trigger the state to be saved. If the first argument is an array, each element of that array is the name of a state event. Otherwise, each argument passed to this method is the name of a state event.

**Parameters:** events : String/String[]The event name or an array of event names.


### addTool

Add tools to this panel ...

Add tools to this panel

**Parameters:** tools : Object[]/Ext.panel.Tool[]The tools to add


### addTools

Template method to be implemented in subclasses to add their tools after the collapsible tool. ...

Template method to be implemented in subclasses to add their tools after the collapsible tool. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### addUIClsToElement

inherit docs Method which adds a specified UI + uiCls to the components element. ...

inherit docs Method which adds a specified UI + `uiCls` to the components element. Can be overridden to remove the UI from more than just the components element.

**Parameters:** ui : StringThe UI to remove from the element.


### addUIToElement

inherit docs Method which adds a specified UI to the components element. ...

inherit docs Method which adds a specified UI to the components element. Overrides: Ext.AbstractComponent.addUIToElement


### adjustForConstraints

private ==> used outside of core TODO: currently only used by ToolTip. ...

private ==> used outside of core TODO: currently only used by ToolTip. does this method belong here?

**Parameters:** xy : Object


### adjustPosition

...

**Parameters:** x : Object


### afterCollapse

Invoked after the Panel is Collapsed. ...

Invoked after the Panel is Collapsed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterComponentLayout

Called by the layout system after the Component has been laid out. ...

Called by the layout system after the Component has been laid out. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterExpand

Invoked after the Panel is Expanded. ...

Invoked after the Panel is Expanded. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterFirstLayout

...

**Parameters:** width : Object


### afterHide

Invoked after the Component has been hidden. ...

Invoked after the Component has been hidden. Gets passed the same `callback` and `scope` parameters that onHide received. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterLayout

Invoked after the Container has laid out (and rendered if necessary) its child Components. ...

Invoked after the Container has laid out (and rendered if necessary) its child Components. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterLockedViewLayout

Due to automatic component border setting using inline style, to create the scrollbar-replacing bottom border, we hav...

Due to automatic component border setting using inline style, to create the scrollbar-replacing bottom border, we have to postprocess the locked view *after* render. If there are visible normal columns, we do need the fat bottom border.


### afterRender

Allows addition of behavior after rendering is complete. ...

Allows addition of behavior after rendering is complete. At this stage the Component’s Element will have been styled according to the configuration, will have had any configured CSS class names added, and will be in the configured visibility and the configured enable state. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterSetPosition

Template method called after a Component has been positioned. ...

Template method called after a Component has been positioned. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterShow

Invoked after the Component is shown (after onShow is called). ...

Invoked after the Component is shown (after onShow is called). Gets passed the same parameters as show. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### alignTo

Aligns the element with another element relative to the specified anchor points. ...

Aligns the element with another element relative to the specified anchor points. If the other element is the document it aligns it to the viewport. The position parameter is optional, and can be specified in any one of the following formats: - **Blank**: Defaults to aligning the element's top-left corner to the target's bottom-left corner ("tl-bl"). - **One anchor (deprecated)**: The passed anchor position is used as the target element's anchor point. The element being aligned will position its top-left corner (tl) to that point. This method has been deprecated in favor of the newer two anchor syntax below. - **Two anchors**: If two values from the table below are passed separated by a dash, the first value is used as the element's anchor point, and the second value is used as the target's anchor point. In addition to the anchor points, the position parameter also supports the "?" character. If "?" is passed at the end of the position string, the element will attempt to align as specified, but the position will be adjusted to constrain to the viewport if necessary. Note that the element being aligned might be swapped to align to a different position than that specified in order to enforce the viewport constraints. Following are all of the supported anchor positions: Example Usage:

**Parameters:** element : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or id of the element to align to.


### anchorTo

Anchors an element to another element and realigns it when the window is resized. ...

Anchors an element to another element and realigns it when the window is resized.

**Parameters:** element : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or id of the element to align to.


### anim

process the passed fx configuration. ...

- process the passed fx configuration.

**Parameters:** config : Object


### animate

Performs custom animation on this object. ...

Performs custom animation on this object. This method is applicable to both the Component class and the Sprite class. It performs animated transitions of certain properties of this object over a specified timeline. Animating a Component When animating a Component, the following properties may be specified in `from`, `to`, and `keyframe` objects: - `x` - The Component's page X position in pixels. - `y` - The Component's page Y position in pixels - `left` - The Component's `left` value in pixels. - `top` - The Component's `top` value in pixels. - `width` - The Component's `width` value in pixels. - `height` - The Component's `height` value in pixels. - `dynamic` - Specify as true to update the Component's layout (if it is a Container) at every frame of the animation. *Use sparingly as laying out on every intermediate size change is an expensive operation.* For example, to animate a Window to a new size, ensuring that its internal layout and any shadow is correct: For performance reasons, by default, the internal layout is only updated when the Window reaches its final `"to"` size. If dynamic updating of the Window's child Components is required, then configure the animation with `dynamic: true` and the two child items will maintain their proportions during the animation.

**Parameters:** config : ObjectConfiguration for Ext.fx.Anim. Note that the to config is required.


### applyChildEls

Sets references to elements inside the component. ...

Sets references to elements inside the component.

**Parameters:** el : Object


### applyDefaults

...

**Parameters:** config : Object


### applyRenderSelectors

Sets references to elements inside the component. ...

Sets references to elements inside the component. This applies renderSelectors as well as childEls.


### applyState

Applies the state to the object. ...

Applies the state to the object. This should be overridden in subclasses to do more complex state operations. By default it applies the state properties onto the current object.

**Parameters:** state : ObjectThe state


### applyTargetCls

...

**Parameters:** targetCls : Object


### beforeBlur

Template method to do any pre-blur processing. ...

Template method to do any pre-blur processing.

**Parameters:** e : Ext.EventObjectThe event object


### beforeComponentLayout

Occurs before componentLayout is run. ...

Occurs before `componentLayout` is run. Returning `false` from this method will prevent the `componentLayout` from being executed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeDestroy

Invoked before the Component is destroyed. ...

Invoked before the Component is destroyed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeFocus

Template method to do any pre-focus processing. ...

Template method to do any pre-focus processing.

**Parameters:** e : Ext.EventObjectThe event object


### beforeLayout

Occurs before componentLayout is run. ...

Occurs before componentLayout is run. In previous releases, this method could return `false` to prevent its layout but that is not supported in Ext JS 4.1 or higher. This method is simply a notification of the impending layout to give the component a chance to adjust the DOM. Ideally, DOM reads should be avoided at this time to reduce expensive document reflows. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeRender

...

Overrides: Ext.container.AbstractContainer.beforeRender


### beforeSetPosition

Template method called before a Component is positioned. ...

Template method called before a Component is positioned. Ensures that the position is adjusted so that the Component is constrained if so configured.

**Parameters:** x : Object


### beforeShow

Invoked before the Component is shown. ...

Invoked before the Component is shown. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beginCollapse

Called before the change from default, configured state into the collapsed state. ...

Called before the change from default, configured state into the collapsed state. This method may be called at render time to enable rendering in an initially collapsed state, or at runtime when an existing, fully layed out Panel may be collapsed. It basically saves configs which need to be clobbered for the duration of the collapsed state.


### beginDrag

...


### beginExpand

...


### bindStore

...

**Parameters:** store : Object


### blur

...

**Returns:** Ext.Componentthis


### bridgeToolbars

...


### bubble

Bubbles up the component/container heirarchy, calling the specified function with each component. ...

Bubbles up the component/container heirarchy, calling the specified function with each component. The scope (*this*) of function call will be the scope provided or the current component. The arguments to the function will be the args provided or the current component. If the function returns false at any point, the bubble is stopped.

**Parameters:** fn : FunctionThe function to call


### calculateAnchorXY

Calculates x,y coordinates specified by the anchor position on the element, adding extraX and extraY values. ...

Calculates x,y coordinates specified by the anchor position on the element, adding extraX and extraY values.

**Parameters:** anchor : String (optional)The specified anchor position. See alignTo for details on supported anchor positions. Defaults to: `'tl'`


### calculateConstrainedPosition

Calculates the new [x,y] position to move this Positionable into a constrain region. ...

Calculates the new [x,y] position to move this Positionable into a constrain region. By default, this Positionable is constrained to be within the container it was added to, or the element it was rendered to. Priority is given to constraining the top and left within the constraint. An alternative constraint may be passed.

**Parameters:** constrainTo : String/HTMLElement/Ext.Element/Ext.util.Region (optional)The Element or Region into which this Component is to be constrained. Defaults to the element into which this Positionable was rendered, or this Component's {@link Ext.Component.constrainTo.


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


### cancelFocus

Cancel any deferred focus on this component ...

Cancel any deferred focus on this component


### captureArgs

...

**Parameters:** o : Object


### cascade

Cascades down the component/container heirarchy from this component (passed in the first call), calling the specified...

Cascades down the component/container heirarchy from this component (passed in the first call), calling the specified function with each component. The scope (this reference) of the function call will be the scope provided or the current component. The arguments to the function will be the args provided or the current component. If the function returns false at any point, the cascade is stopped on that branch. Available since: 2.3.0

**Parameters:** fn : FunctionThe function to call


### center

Center this Component in its container. ...

Center this Component in its container.

**Returns:** Ext.Componentthis


### child

Retrieves the first direct child of this container which matches the passed selector or component. ...

Retrieves the first direct child of this container which matches the passed selector or component. The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.

**Parameters:** selector : String/Ext.Component (optional)An Ext.ComponentQuery selector. If no selector is specified, the first child will be returned.


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### cloneConfig

Clone the current component using the original config values passed into this instance by default. ...

Clone the current component using the original config values passed into this instance by default.

**Parameters:** overrides : ObjectA new config containing any properties to override in the cloned version. An id property can be passed on this object, otherwise one will be generated to avoid duplicates.


### close

Closes the Panel. ...

Closes the Panel. By default, this method, removes it from the DOM, destroys the Panel object and all its descendant Components. The beforeclose event is fired before the close happens and will cancel the close action if it returns false. **Note:** This method is also affected by the closeAction setting. For more explicit control use destroy and hide methods.


### collapse

Collapses the panel body so that the body becomes hidden. ...

Collapses the panel body so that the body becomes hidden. Docked Components parallel to the border towards which the collapse takes place will remain visible. Fires the beforecollapse event which will cancel the collapse action if it returns false.

**Parameters:** - direction : String (optional)The direction to collapse towards. Must be one of Ext.Component.DIRECTION_TOP - Ext.Component.DIRECTION_RIGHT - Ext.Component.DIRECTION_BOTTOM - Ext.Component.DIRECTION_LEFT Defaults to collapseDirection.


### collapsedHorizontal

...


### collapsedVertical

...


### configClass

...


### constructLockableFeatures

...


### constructLockablePlugins

...


### constructPlugin

...

**Parameters:** ptype : String/Objectstring or config object containing a ptype property. Constructs a plugin according to the passed config object/ptype string. Ensures that the constructed plugin always has a `cmp` reference back to this component. The setting up of this is done in PluginManager. The PluginManager ensures that a reference to this component is passed to the constructor. It also ensures that the plugin's `setCmp` method (if any) is called.


### constructPlugins

Returns an array of fully constructed plugin instances. ...

**Returns:** an array of fully constructed plugin instances. This converts any configs into their appropriate instances. It does not mutate the plugins array. It creates a new array.


### contains

Determines whether the passed Component is either an immediate child of this Container, or whether it is a descendant. ...

Determines whether the passed Component is either an immediate child of this Container, or whether it is a descendant.

**Parameters:** comp : Ext.ComponentThe Component to test.


### continueFireEvent

Continue to fire event. ...

Continue to fire event.

**Parameters:** eventName : String


### convertCollapseDir

converts a collapsdDir into an anchor argument for Element.slideIn overridden in rtl mode to switch "l" and "r" ...

converts a collapsdDir into an anchor argument for Element.slideIn overridden in rtl mode to switch "l" and "r"

**Parameters:** collapseDir : Object


### convertPositionSpec

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**

**Parameters:** posSpec : Object


### createReExpander

...

**Parameters:** direction : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### delayScroll

...


### deleteMembers

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### destroyDockedItems

...


### destroyLockable

...


### detachComponent

Detach a component from the DOM ...

Detach a component from the DOM

**Parameters:** component : Object


### determineScrollbars

This method is obsolete in 4.1. ...

This method is obsolete in 4.1. The closest equivalent in 4.1 is doLayout, but it is also possible that no layout is needed. This method has been **deprecated** since 4.1


### determineXTypeToCreate

...

**Parameters:** lockedSide : Object


### disable

Inherit docs Disable all immediate children that was previously disabled Override disable because onDisable only gets...

Inherit docs Disable all immediate children that was previously disabled Override disable because onDisable only gets called when rendered Disable the component. Available since: 1.1.0

**Parameters:** silent : Boolean (optional)Passing `true` will suppress the `disable` event from being fired. Defaults to: `false`


### doApplyRenderTpl

Called from the selected frame generation template to insert this Component's inner structure inside the framing stru...

Called from the selected frame generation template to insert this Component's inner structure inside the framing structure. When framing is used, a selected frame generation template is used as the primary template of the getElConfig instead of the configured renderTpl. The renderTpl is invoked by this method which is injected into the framing template.

**Parameters:** out : Object


### doAutoRender

Handles autoRender. ...

Handles autoRender. Floating Components may have an ownerCt. If they are asking to be constrained, constrain them within that ownerCt, and have their z-index managed locally. Floating Components are always rendered to document.body


### doClose

...


### doCollapseExpand

...

**Parameters:** flags : Object


### doComponentLayout

This method needs to be called whenever you change something on this component that requires the Component's layout t...

This method needs to be called whenever you change something on this component that requires the Component's layout to be recalculated.

**Returns:** Ext.container.Containerthis


### doConstrain

Moves this floating Component into a constrain region. ...

Moves this floating Component into a constrain region. By default, this Component is constrained to be within the container it was added to, or the element it was rendered to. An alternative constraint may be passed.

**Parameters:** constrainTo : String/HTMLElement/Ext.Element/Ext.util.Region (optional)The Element or Region into which this Component is to be constrained. Defaults to the element into which this floating Component was rendered.


### doLayout

Manually force this container's layout to be recalculated. ...

Manually force this container's layout to be recalculated. The framework uses this internally to refresh layouts form most cases. Available since: 2.3.0

**Returns:** Ext.container.Containerthis


### doRemove

...

**Parameters:** component : Object


### doRenderContent

...

**Parameters:** out : Object


### doRenderDockedItems

...

**Parameters:** out : Object


### doRenderFramingDockedItems

...

**Parameters:** out : Object


### down

Retrieves the first descendant of this container which matches the passed selector. ...

Retrieves the first descendant of this container which matches the passed selector. The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.

**Parameters:** selector : String/Ext.Component (optional)An Ext.ComponentQuery selector or Ext.Component. If no selector is specified, the first child will be returned.


### enable

Enable all immediate children that was previously disabled Override enable because onEnable only gets called when ren...

Enable all immediate children that was previously disabled Override enable because onEnable only gets called when rendered Enable the component Available since: 1.1.0

**Parameters:** silent : Boolean (optional)Passing `true` will suppress the `enable` event from being fired. Defaults to: `false`


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if present. There is no implementation in the Observable base class. This is commonly used by Ext.Components to bubble events to owner Containers. See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the Component's immediate owner. But if a known target is required, this can be overridden to access the required target more quickly. Example:

**Parameters:** eventNames : String/String[]The event name to bubble, or an Array of event names.


### endDrag

...


### ensureAttachedToBody

Ensures that this component is attached to document.body. ...

Ensures that this component is attached to `document.body`. If the component was rendered to Ext.getDetachedBody, then it will be appended to `document.body`. Any configured position is also restored.

**Parameters:** runLayout : Boolean (optional)True to run the component's layout. Defaults to: `false`


### expand

Expands the panel body so that it becomes visible. ...

Expands the panel body so that it becomes visible. Fires the beforeexpand event which will cancel the expand action if it returns false.

**Parameters:** animate : Boolean (optional)True to animate the transition, else false (defaults to the value of the animCollapse panel config). May also be specified as the animation duration in milliseconds.


### findParentBy

Find a container above this component at any level by a custom function. ...

Find a container above this component at any level by a custom function. If the passed function returns true, the container will be returned. See also the up method.

**Parameters:** fn : FunctionThe custom function to call with the arguments (container, this component).


### findParentByType

Find a container above this component at any level by xtype or class See also the up method. ...

Find a container above this component at any level by xtype or class See also the up method.

**Parameters:** xtype : String/Ext.ClassThe xtype string for a component, or the class of the component directly


### findPlugin

Retrieves plugin from this component's collection by its ptype. ...

Retrieves plugin from this component's collection by its `ptype`.

**Parameters:** ptype : StringThe Plugin's ptype as specified by the class's `alias` configuration.


### findReExpander

...

**Parameters:** direction : Object


### finishRender

This method visits the rendered component tree in a "top-down" order. ...

This method visits the rendered component tree in a "top-down" order. That is, this code runs on a parent component before running on a child. This method calls the onRender method of each component.

**Parameters:** containerIdx : NumberThe index into the Container items of this Component.


### finishRenderChildren

...

Overrides: Ext.util.Renderable.finishRenderChildren


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed to addListener). An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list. An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by calling enableBubble.

**Parameters:** eventName : StringThe name of the event to fire.


### fireHierarchyEvent

For more information on the hierarchy events, see the note for the hierarchyEventSource observer defined in the onCla...

For more information on the hierarchy events, see the note for the hierarchyEventSource observer defined in the onClassCreated callback. This functionality is contained in Component (as opposed to Container) because a Component can be the ownerCt for a floating component (loadmask), and the loadmask needs to know when its owner is shown/hidden via the hierarchyEventSource so that its hidden state can be synchronized. TODO: merge this functionality with Ext.globalEvents

**Parameters:** ename : Object


### fitContainer

...

**Parameters:** animate : Object


### floatCollapsedPanel

...


### focus

Try to focus this component. ...

Try to focus this component.

**Parameters:** selectText : Boolean (optional)If applicable, true to also select the text in this component


### forceComponentLayout

Forces this component to redo its componentLayout. ...

Forces this component to redo its componentLayout. This method has been **deprecated** since 4.1.0 Use updateLayout instead.


### getActionEl

Deprecate 5.0 ...

Deprecate 5.0


### getActiveAnimation

Returns the current animation if this object has any effects actively running or queued, else returns false. ...

**Returns:** the current animation if this object has any effects actively running or queued, else returns false. ReturnsExt.fx.Anim/BooleanAnim if element has active effects, else false


### getAlignToXY

Gets the x,y coordinates to align this element with another element. ...

Gets the x,y coordinates to align this element with another element. See alignTo for more info on the supported position values.

**Parameters:** element : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or id of the element to align to.


### getAnchor

private ...

private


### getAnchorToXY

Begin Positionable methods Overridden in Ext.rtl.AbstractComponent. ...

Begin Positionable methods **Overridden in Ext.rtl.AbstractComponent.** Gets the x,y coordinates of an element specified by the anchor position on the element.

**Parameters:** el : Ext.dom.ElementThe element


### getAnchorXY

Gets the x,y coordinates specified by the anchor position on the element. ...

Gets the x,y coordinates specified by the anchor position on the element.

**Parameters:** anchor : String (optional)The specified anchor position. See alignTo for details on supported anchor positions. Defaults to: `'tl'`


### getAnimateTarget

...

**Parameters:** target : Object


### getAutoId

...


### getBorderPadding

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Returns:** the size of the element's borders and padding. ReturnsObjectan object with the following numeric properties - beforeX - afterX - beforeY - afterY


### getBox

Return an object defining the area of this Element which can be passed to setBox to set another Element's size/locati...

Return an object defining the area of this Element which can be passed to setBox to set another Element's size/location to match this element.

**Parameters:** contentBox : Boolean (optional)If true a box for the content of the element is returned.


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getBubbleTarget

Implements an upward event bubbling policy. ...

Implements an upward event bubbling policy. By default a Component bubbles events up to its reference owner. Component subclasses may implement a different bubbling strategy by overriding this method. Overrides: Ext.AbstractComponent.getBubbleTarget


### getChildByElement

Return the immediate child Component in which the passed element is located. ...

Return the immediate child Component in which the passed element is located.

**Parameters:** el : Ext.Element/HTMLElement/StringThe element to test (or ID of element).


### getChildEls

...


### getChildItemsToDisable

Gets a list of child components to enable/disable when the container is enabled/disabled ...

Gets a list of child components to enable/disable when the container is enabled/disabled

**Returns:** Ext.Component[]Items to be enabled/disabled


### getClassChildEls

...

**Parameters:** cls : Object


### getCollapsed

Returns the current collapsed state of the panel. ...

**Returns:** the current collapsed state of the panel. ReturnsBoolean/StringFalse when not collapsed, otherwise the value of collapseDirection.


### getCollapsedDockedItems

...


### getColumnWidth

Used when calculating total locked column width in processColumns Use shrinkwrapping of child columns if no top level...

Used when calculating total locked column width in processColumns Use shrinkwrapping of child columns if no top level width.

**Parameters:** column : Object


### getComponent

Attempts a default component lookup (see Ext.container.Container.getComponent). ...

Attempts a default component lookup (see Ext.container.Container.getComponent). If the component is not found in the normal items, the dockedItems are searched and the matched component (if any) returned (see getDockedComponent). Note that docked items will only be matched by component id or itemId -- if you pass a numeric index only non-docked child components will be searched. Available since: 2.3.0

**Parameters:** comp : String/NumberThe component id, itemId or position to find


### getComponentId

used as the key lookup function for the items collection ...

- used as the key lookup function for the items collection

**Parameters:** comp : Object


### getComponentLayout

...


### getConfig

...

**Parameters:** name : Object


### getConstrainVector

Returns the [X, Y] vector by which this Positionable's element must be translated to make a best attempt to constrain...

**Parameters:** constrainTo : Ext.util.Positionable/HTMLElement/String/Ext.util.Region (optional)The Positionable, HTMLElement, element id, or Region into which the element is to be constrained.

**Returns:** the `[X, Y]` vector by which this Positionable's element must be translated to make a best attempt to constrain within the passed constraint. Returns `false` if the element does not need to be moved. Priority is given to constraining the top and left within the constraint. The constraint may either be an existing element into which the element is to be constrained, or a Region into which this element is to be constrained. By default, any extra shadow around the element is **not** included in the constrain calculations - the edges of the element are used as the element bounds. To constrain the shadow within the constrain region, set the `constrainShadow` property on this element to `true`.


### getContentTarget

...

Overrides: Ext.Component.getContentTarget


### getDefaultContentTarget

...

Overrides: Ext.container.AbstractContainer.getDefaultContentTarget


### getDockedComponent

Finds a docked component by id, itemId or position. ...

Finds a docked component by id, itemId or position. Also see getDockedItems

**Parameters:** comp : String/NumberThe id, itemId or position of the docked component (see getComponent for details)


### getDockedItems

Retrieves an array of all currently docked Components. ...

Retrieves an array of all currently docked Components. For example to find a toolbar that has been docked at top:

**Parameters:** selector : StringA ComponentQuery selector string to filter the returned items.


### getDockingRefItems

...

**Parameters:** deep : Object


### getDragEl

...


### getEditorParent

...


### getEl

Retrieves the top level element representing this component. ...

Retrieves the top level element representing this component. Available since: 1.1.0

**Returns:** Ext.dom.Element


### getElConfig

...


### getFocusEl

Returns the focus holder element associated with this Container. ...

**Returns:** the focus holder element associated with this Container. By default, this is the Container's target element. Subclasses which use embedded focusable elements (such as Window and Button) should override this for use by the focus method. ReturnsExt.Elementthe focus holding element.


### getFrameInfo

On render, reads an encoded style attribute, "filter" from the style of this Component's element. ...

On render, reads an encoded style attribute, "filter" from the style of this Component's element. This information is memoized based upon the CSS class name of this Component's element. Because child Components are rendered as textual HTML as part of the topmost Container, a dummy div is inserted into the document to receive the document element's CSS class name, and therefore style attributes.


### getFrameRenderData

...


### getFrameTpl

...

**Parameters:** table : Object


### getFramingInfoCls

...


### getHeader

Gets the Header for this panel. ...

Gets the Header for this panel.


### getHeaderCollapsedClasses

Create the class array to add to the Header when collpsed. ...

Create the class array to add to the Header when collpsed.

**Parameters:** header : Object


### getHeight

Gets the current height of the component's underlying element. ...

Gets the current height of the component's underlying element.

**Returns:** Number


### getHeightAuthority

...


### getHierarchyState

A component's hierarchyState is used to keep track of aspects of a component's state that affect its descendants hier...

A component's hierarchyState is used to keep track of aspects of a component's state that affect its descendants hierarchically like "collapsed" and "hidden". For example, if this.hierarchyState.hidden == true, it means that either this component, or one of its ancestors is hidden. Hierarchical state management is implemented by chaining each component's hierarchyState property to its parent container's hierarchyState property via the prototype. The result is such that if a component's hierarchyState does not have it's own property, it inherits the property from the nearest ancestor that does. To set a hierarchical "hidden" value: It is important to remember when unsetting hierarchyState properties to delete them instead of just setting them to a falsy value. This ensures that the hierarchyState returns to a state of inheriting the value instead of overriding it To unset the hierarchical "hidden" value: IMPORTANT! ALWAYS access hierarchyState using this method, not by accessing this.hierarchyState directly. The hierarchyState property does not exist until the first time getHierarchyState() is called. At that point getHierarchyState() walks up the component tree to establish the hierarchyState prototype chain. Additionally the hierarchyState property should NOT be relied upon even after the initial call to getHierarchyState() because it is possible for the hierarchyState to be invalidated. Invalidation typically happens when a component is moved to a new container. In such a case the hierarchy state remains invalid until the next time getHierarchyState() is called on the component or one of its descendants.

**Parameters:** inner : Object


### getId

Retrieves the id of this component. ...

Retrieves the `id` of this component. Will auto-generate an `id` if one has not already been set.

**Returns:** String


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getInsertPosition

This function takes the position argument passed to onRender and returns a DOM element that you can use in the insert...

This function takes the position argument passed to onRender and returns a DOM element that you can use in the insertBefore.

**Parameters:** position : String/Number/Ext.dom.Element/HTMLElementIndex, element id or element you want to put this component before.


### getItemId

Returns the value of itemId assigned to this component, or when that is not set, returns the value of id. ...

**Returns:** the value of itemId assigned to this component, or when that is not set, returns the value of id. ReturnsString


### getKeyMap

...


### getLayout

Returns the layout instance currently associated with this Container. ...

**Returns:** the layout instance currently associated with this Container. If a layout has not been instantiated yet, that is done first ReturnsExt.layout.container.ContainerThe layout


### getLhsMarker

Gets left hand side marker for header resizing. ...

Gets left hand side marker for header resizing.


### getLoader

Gets the Ext.ComponentLoader for this Component. ...

Gets the Ext.ComponentLoader for this Component.

**Returns:** Ext.ComponentLoaderThe loader instance, null if it doesn't exist.


### getLocalX

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Returns:** the x coordinate of this element reletive to its `offsetParent`. ReturnsNumberThe local x coordinate


### getLocalXY

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Returns:** the x and y coordinates of this element relative to its `offsetParent`. ReturnsNumber[]The local XY position of the element


### getLocalY

Returns the y coordinate of this element reletive to its offsetParent. ...

**Returns:** the y coordinate of this element reletive to its `offsetParent`. ReturnsNumberThe local y coordinate


### getLockingViewConfig

...


### getMaskTarget

...


### getMenuItems

...

**Parameters:** getMenuItems : Object


### getOffsetsTo

Returns the offsets of this element from the passed element. ...

**Parameters:** offsetsTo : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or element id to get get the offsets from.

**Returns:** the offsets of this element from the passed element. The element must both be part of the DOM tree and not have display:none to have page coordinates.


### getOppositeDirection

...

**Parameters:** d : Object


### getOuterSize

Include margins ...

Include margins


### getOverflowEl

Get an el for overflowing, defaults to the target el ...

Get an el for overflowing, defaults to the target el


### getOverflowStyle

Returns the CSS style object which will set the Component's scroll styles. ...

**Returns:** the CSS style object which will set the Component's scroll styles. This must be applied to the target element.


### getOwningBorderContainer

Returns the owning container if that container uses border layout. ...

**Returns:** the owning container if that container uses `border` layout. Otherwise this method returns `null`. **Defined in override Ext.layout.container.border.Region.** ReturnsExt.container.ContainerThe owning border container or `null`.


### getOwningBorderLayout

Returns the owning border (Ext.layout.container.Border) instance if there is one. ...

**Returns:** the owning `border` (`Ext.layout.container.Border`) instance if there is one. Otherwise this method returns `null`. **Defined in override Ext.layout.container.border.Region.** ReturnsExt.layout.container.BorderThe owning border layout or `null`.


### getPlaceholder

...

**Parameters:** direction : Object


### getPlugin

Retrieves a plugin from this component's collection by its pluginId. ...

Retrieves a plugin from this component's collection by its `pluginId`.

**Parameters:** pluginId : String


### getPosition

Gets the current XY position of the component's underlying element. ...

Gets the current XY position of the component's underlying element.

**Parameters:** local : Boolean (optional)If true the element's left and top are returned instead of page XY. Defaults to: `false`


### getPositionEl

Deprecate 5.0 ...

Deprecate 5.0


### getProtoBody

...


### getProxy

...


### getReExpander

...

**Parameters:** direction : Object


### getRefItems

Used by ComponentQuery, child and down to retrieve all of the items which can potentially be considered a child of th...

Used by ComponentQuery, child and down to retrieve all of the items which can potentially be considered a child of this Container. This may be overriden by Components which have ownership of Components that are not contained in the items collection. NOTE: IMPORTANT note for maintainers: Items are returned in tree traversal order. Each item is appended to the result array followed by the results of that child's getRefItems call. Floating child items are appended after internal child items.

**Parameters:** deep : Object


### getRefOwner

Used by ComponentQuery, and the up method to find the owning Component in the linkage hierarchy. ...

Used by ComponentQuery, and the up method to find the owning Component in the linkage hierarchy. By default this returns the Container which contains this Component. This may be overriden by Component authors who implement ownership hierarchies which are not based upon ownerCt, such as BoundLists being owned by Fields or Menus being owned by Buttons.


### getRegion

Returns a region object that defines the area of this element. ...

**Returns:** a region object that defines the area of this element. ReturnsExt.util.RegionA Region containing "top, left, bottom, right" properties.


### getRenderTree

...


### getResizeEl

Deprecate 5.0 ...

Deprecate 5.0


### getRhsMarker

Gets right hand side marker for header resizing. ...

Gets right hand side marker for header resizing.


### getScrollTarget

...


### getScrollerOwner

...


### getSelectionModel

Returns the selection model being used and creates it via the configuration if it has not been created already. ...

**Returns:** the selection model being used and creates it via the configuration if it has not been created already. ReturnsExt.selection.ModelselModel


### getSize

Gets the current size of the component's underlying element. ...

Gets the current size of the component's underlying element.

**Returns:** ObjectAn object containing the element's size `{width: (element width), height: (element height)}`


### getSizeModel

Returns an object that describes how this component's width and height are managed. ...

**Parameters:** ownerCtSizeModel : Object

**Returns:** an object that describes how this component's width and height are managed. All of these objects are shared and should not be modified.


### getState

The supplied default state gathering method for the AbstractComponent class. ...

The supplied default state gathering method for the AbstractComponent class. This method returns dimension settings such as `flex`, `anchor`, `width` and `height` along with `collapsed` state. Subclasses which implement more complex state should call the superclass's implementation, and apply their state to the result if this basic state is to be saved. Note that Component state will only be saved if the Component has a stateId and there as a StateProvider configured for the document.

**Returns:** Object


### getStateId

Gets the state id for this object. ...

Gets the state id for this object.

**Returns:** StringThe 'stateId' or the implicit 'id' specified by component configuration.


### getStore

Returns the store associated with this Panel. ...

**Returns:** the store associated with this Panel. ReturnsExt.data.StoreThe store


### getStyleProxy

Returns an offscreen div with the same class name as the element this is being rendered. ...

**Parameters:** cls : Object

**Returns:** an offscreen div with the same class name as the element this is being rendered. This is because child item rendering takes place in a detached div which, being not part of the document, has no styling.


### getTargetEl

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. ...

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. Overrides: Ext.panel.AbstractPanel.getTargetEl


### getTpl

...

**Parameters:** name : Object


### getView

Gets the view for this panel. ...

Gets the view for this panel.

**Returns:** Ext.view.Table


### getViewRegion

Returns the content region of this element. ...

**Returns:** the **content** region of this element. That is the region within the borders and padding. ReturnsExt.util.RegionA Region containing "top, left, bottom, right" member data.


### getVisibilityEl

Deprecate 5.0 ...

Deprecate 5.0


### getWidth

Gets the current width of the component's underlying element. ...

Gets the current width of the component's underlying element.

**Returns:** Number


### getWidthAuthority

...


### getX

Gets the current X position of the DOM element based on page coordinates. ...

Gets the current X position of the DOM element based on page coordinates.

**Returns:** NumberThe X position of the element


### getXType

Gets the xtype for this component as registered with Ext.ComponentManager. ...

Gets the xtype for this component as registered with Ext.ComponentManager. For a list of all available xtypes, see the Ext.Component header. Example usage:

**Returns:** StringThe xtype


### getXTypes

Returns this Component's xtype hierarchy as a slash-delimited string. ...

**Returns:** this Component's xtype hierarchy as a slash-delimited string. For a list of all available xtypes, see the Ext.Component header. If using your own subclasses, be aware that a Component must register its own xtype to participate in determination of inherited xtypes. Example usage: Available since: 2.3.0 ReturnsStringThe xtype hierarchy string


### getXY

Gets the current position of the DOM element based on page coordinates. ...

Gets the current position of the DOM element based on page coordinates.

**Returns:** Number[]The XY position of the element


### getY

Gets the current Y position of the DOM element based on page coordinates. ...

Gets the current Y position of the DOM element based on page coordinates.

**Returns:** NumberThe Y position of the element


### ghost

used for dragging ...

used for dragging

**Parameters:** cls : Object


### ghostTools

helper function for ghost ...

helper function for ghost


### hasActiveFx

Returns the current animation if this object has any effects actively running or queued, else returns false. ...

**Returns:** the current animation if this object has any effects actively running or queued, else returns false. This method has been **deprecated** since 4.0 Replaced by getActiveAnimation


### hasCls

Checks if the specified CSS class exists on this element's DOM node. ...

Checks if the specified CSS class exists on this element's DOM node.

**Parameters:** className : StringThe CSS class to check for.


### hasConfig

...

**Parameters:** config : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer indicates whether the event needs firing or not.

**Parameters:** eventName : StringThe name of the event to check for


### hasLockedColumns

Private. ...

Private. Determine if there are any columns with a locked configuration option

**Parameters:** columns : Object


### hasUICls

Checks if there is currently a specified uiCls. ...

Checks if there is currently a specified `uiCls`.

**Parameters:** cls : StringThe `cls` to check.


### hide

Hides this Component, setting it to invisible using the configured hideMode. ...

Hides this Component, setting it to invisible using the configured hideMode.

**Parameters:** animateTarget : String/Ext.Element/Ext.Component (optional)only valid for floating Components such as Windows or ToolTips, or regular Components which have been configured with `floating: true`.. The target to which the Component should animate while hiding. Defaults to: `null`


### initAria

...


### initBodyBorder

...


### initBodyStyles

Parses the bodyStyle config if available to create a style string that will be applied to the body element. ...

Parses the bodyStyle config if available to create a style string that will be applied to the body element. This also includes bodyPadding and bodyBorder if available.

**Returns:** StringA CSS style string with body styles, padding and border.


### initBorderProps

...


### initBorderRegion

This method is called by the Ext.layout.container.Border class when instances are added as regions to the layout. ...

This method is called by the `Ext.layout.container.Border` class when instances are added as regions to the layout. Since it is valid to add any component to a border layout as a region, this method must be added to `Ext.Component` but is only ever called when that component is owned by a `border` layout. **Defined in override Ext.layout.container.border.Region.**


### initCls

...


### initComponent

The initComponent template method is an important initialization step for a Component. ...

The initComponent template method is an important initialization step for a Component. It is intended to be implemented by each subclass of Ext.Component to provide any needed constructor logic. The initComponent method of the class being created is called first, with each initComponent method up the hierarchy to Ext.Component being called thereafter. This makes it easy to implement and, if needed, override the constructor logic of the Component at any step in the hierarchy. The initComponent method **must** contain a call to callParent in order to ensure that the parent class' initComponent method is also called. All config options passed to the constructor are applied to `this` before initComponent is called, so you can simply access them with `this.someOption`. The following example demonstrates using a dynamic string for the text of a button at the time of instantiation of the class. Available since: 1.1.0 This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initContainer

...

**Parameters:** container : Object


### initDockingItems

...


### initDraggable

...

Overrides: Ext.Component.initDraggable


### initEvents

Initialize any events on this component ...

Initialize any events on this component


### initFrame

...


### initFramingTpl

Poke in a reference to applyRenderTpl(frameInfo, out) ...

Poke in a reference to applyRenderTpl(frameInfo, out)

**Parameters:** table : Object


### initHeaderAria

...


### initHierarchyEvents

...


### initHierarchyState

Called by getHierarchyState to initialize the hierarchyState the first time it is requested. ...

Called by getHierarchyState to initialize the hierarchyState the first time it is requested. **Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** hierarchyState : Object


### initItems

...

Overrides: Ext.container.AbstractContainer.initItems


### initPadding

Initializes padding by applying it to the target element, or if the layout manages padding ensures that the padding o...

Initializes padding by applying it to the target element, or if the layout manages padding ensures that the padding on the target element is "0".

**Parameters:** targetEl : Object


### initPlugin

...

**Parameters:** plugin : Object


### initRenderData

Initialized the renderData to be used when rendering the renderTpl. ...

Initialized the renderData to be used when rendering the renderTpl.

**Returns:** ObjectObject with keys and values that are going to be applied to the renderTpl


### initRenderTpl

Initializes the renderTpl. ...

Initializes the renderTpl.

**Returns:** Ext.XTemplateThe renderTpl XTemplate instance.


### initResizable

...

Overrides: Ext.Component.initResizable


### initSimpleDraggable

Override Component.initDraggable. ...

Override Component.initDraggable. Panel (and subclasses) use the header element as the delegate.


### initState

Initializes the state of the object upon construction. ...

Initializes the state of the object upon construction.


### initStyles

Applies padding, margin, border, top, left, height, and width configs to the appropriate elements. ...

Applies padding, margin, border, top, left, height, and width configs to the appropriate elements.

**Parameters:** targetEl : Object


### initTools

Tools are a Panel-specific capabilty. ...

Tools are a Panel-specific capabilty. Panel uses initTools. Subclasses may contribute tools by implementing addTools.


### injectLockable

injectLockable will be invoked before initComponent's parent class implementation is called, so throughout this metho...

injectLockable will be invoked before initComponent's parent class implementation is called, so throughout this method this. are configurations


### insert

Inserts a Component into this Container at a specified index. ...

Inserts a Component into this Container at a specified index. Fires the beforeadd event before inserting, then fires the add event after the Component has been inserted. Available since: 2.3.0

**Parameters:** index : NumberThe index at which the Component will be inserted into the Container's items collection


### insertDocked

Inserts docked item(s) to the panel at the indicated position. ...

Inserts docked item(s) to the panel at the indicated position.

**Parameters:** pos : NumberThe index at which the Component will be inserted


### invalidateScroller

This method is obsolete in 4.1. ...

This method is obsolete in 4.1. The closest equivalent in 4.1 is Ext.AbstractComponent.updateLayout, but it is also possible that no layout is needed. This method has been **deprecated** since 4.1


### is

Tests whether this Component matches the selector string. ...

Tests whether this Component matches the selector string.

**Parameters:** selector : StringThe selector string to test against.


### isAncestor

Determines whether this Container is an ancestor of the passed Component. ...

Determines whether **this Container** is an ancestor of the passed Component. This will return `true` if the passed Component is anywhere within the subtree beneath this Container.

**Parameters:** possibleDescendant : Ext.ComponentThe Component to test for presence within this Container's subtree.


### isContainedFloater

Utility method to determine if a Component is floating, and has an owning Container whose coordinate system it must b...

Utility method to determine if a Component is floating, and has an owning Container whose coordinate system it must be positioned in when using setPosition.


### isDescendant

...

**Parameters:** ancestor : Object


### isDescendantOf

Determines whether this component is the descendant of a particular container. ...

Determines whether this component is the descendant of a particular container.

**Parameters:** container : Ext.Container


### isDisabled

Method to determine whether this Component is currently disabled. ...

Method to determine whether this Component is currently disabled.

**Returns:** Booleanthe disabled state of this Component.


### isDraggable

Method to determine whether this Component is draggable. ...

Method to determine whether this Component is draggable.

**Returns:** Booleanthe draggable state of this component.


### isDroppable

Method to determine whether this Component is droppable. ...

Method to determine whether this Component is droppable.

**Returns:** Booleanthe droppable state of this component.


### isFloating

Method to determine whether this Component is floating. ...

Method to determine whether this Component is floating.

**Returns:** Booleanthe floating state of this component.


### isFocusable

...


### isHidden

Method to determine whether this Component is currently set to hidden. ...

Method to determine whether this Component is currently set to hidden.

**Returns:** Booleanthe hidden state of this Component.


### isHierarchicallyHidden

...


### isLayoutRoot

Determines whether this Component is the root of a layout. ...

Determines whether this Component is the root of a layout. This returns `true` if this component can run its layout without assistance from or impact on its owner. If this component cannot run its layout given these restrictions, `false` is returned and its owner will be considered as the next candidate for the layout root. Setting the _isLayoutRoot property to `true` causes this method to always return `true`. This may be useful when updating a layout of a Container which shrink wraps content, and you know that it will not change size, and so can safely be the topmost participant in the layout run. Overrides: Ext.AbstractComponent.isLayoutRoot


### isLayoutSuspended

Returns true if layout is suspended for this component. ...

**Returns:** `true` if layout is suspended for this component. This can come from direct suspension of this component's layout activity (Ext.Container.suspendLayout) or if one of this component's containers is suspended. ReturnsBoolean`true` layout of this component is suspended.


### isLocalRtl

Returns true if this component's local coordinate system is rtl. ...

**Returns:** true if this component's local coordinate system is rtl. For normal components this equates to the value of isParentRtl(). Floaters are a bit different because a floater's element can be a childNode of something other than its parent component's element. For floaters we have to read the dom to see if the component's element's parentNode has a css direction value of "rtl". **Defined in override Ext.rtl.AbstractComponent.** ReturnsBoolean


### isOppositeRootDirection

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**


### isParentRtl

Returns true if this component's parent container is rtl. ...

**Returns:** true if this component's parent container is rtl. Used by rtl positioning methods to determine if the component should be positioned using a right-to-left coordinate system. **Defined in override Ext.rtl.AbstractComponent.** ReturnsBoolean


### isPlaceHolderCollapse

...


### isVisible

Returns true if this component is visible. ...

**Parameters:** deep : Boolean (optional)Pass `true` to interrogate the visibility status of all parent Containers to determine whether this Component is truly visible to the user. Generally, to determine whether a Component is hidden, the no argument form is needed. For example when creating dynamically laid out UIs in a hidden Container before showing them. Defaults to: `false`

**Returns:** `true` if this component is visible. Available since: 1.1.0


### isXType

Tests whether or not this Component is of a specific xtype. ...

Tests whether or not this Component is of a specific xtype. This can test whether this Component is descended from the xtype (default) or whether it is directly of the xtype specified (`shallow = true`). If using your own subclasses, be aware that a Component must register its own xtype to participate in determination of inherited xtypes. For a list of all available xtypes, see the Ext.Component header. Example usage: Available since: 2.3.0

**Parameters:** xtype : StringThe xtype to check for this Component


### lock

Locks the activeHeader as determined by which menu is open OR a header as specified. ...

Locks the activeHeader as determined by which menu is open OR a header as specified.

**Parameters:** header : Ext.grid.column.Column (optional)Header to unlock from the locked section. Defaults to the header which has the menu open currently.


### lookupComponent

...

**Parameters:** comp : Object


### makeFloating

...

**Parameters:** dom : Object


### mask

...


### modifyHeaderCt

inject Lock and Unlock text Hide/show Lock/Unlock options ...

inject Lock and Unlock text Hide/show Lock/Unlock options


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener. Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is destroyed.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### move

Moves a Component within the Container ...

Moves a Component within the Container

**Parameters:** fromIdx : Number/Ext.ComponentThe index/component to move.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener. Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### nextChild

...

**Parameters:** child : Object


### nextNode

Returns the next node in the Component tree in tree traversal order. ...

**Parameters:** selector : String (optional)A ComponentQuery selector to filter the following nodes.

**Returns:** the next node in the Component tree in tree traversal order. Note that this is not limited to siblings, and if invoked upon a node with no matching siblings, will walk the tree to attempt to find a match. Contrast with nextSibling.


### nextSibling

Returns the next sibling of this Component. ...

**Parameters:** selector : String (optional)A ComponentQuery selector to filter the following items.

**Returns:** the next sibling of this Component. Optionally selects the next sibling which matches the passed ComponentQuery selector. May also be referred to as **`next()`** Note that this is limited to siblings, and if no siblings of the item match, `null` is returned. Contrast with nextNode


### on

Shorthand for addListener. ...

Shorthand for addListener. Appends an event handler to this object. For example: The method also allows for a single argument to be passed which is a config object containing properties which specify multiple events. For example: One can also specify options for each event handler separately: *Names* of methods in a specified scope may also be used. Note that `scope` MUST be specified to use this option:

**Parameters:** eventName : String/ObjectThe name of the event to listen for. May also be an object who's property names are event names.


### onAdd

This method is invoked after a new Component has been added. ...

This method is invoked after a new Component has been added. It is passed the Component which has been added. This method may be used to update any internal structure which may depend upon the state of the child items. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onAdded

Method to manage awareness of when components are added to their respective Container, firing an added event. ...

Method to manage awareness of when components are added to their respective Container, firing an added event. References are established at add time rather than at render time. Allows addition of behavior when a Component is added to a Container. At this stage, the Component is in the parent Container's collection of child items. After calling the superclass's `onAdded`, the `ownerCt` reference will be present, and if configured with a ref, the `refOwner` will be set. Available since: 3.4.0 This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onAfterFloatLayout

...


### onBeforeAdd

This method is invoked before adding a new child Component. ...

This method is invoked before adding a new child Component. It is passed the new Component, and may be used to modify the Component, or prepare the Container in some way. Returning false aborts the add operation. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onBeforeFloatLayout

...


### onBlur

private ...

private

**Parameters:** e : Object


### onBoxReady

...

Overrides: Ext.AbstractComponent.onBoxReady


### onConfigUpdate

...

**Parameters:** names : Object


### onDestroy

Allows addition of behavior to the destroy operation. ...

Allows addition of behavior to the destroy operation. After calling the superclass's onDestroy, the Component will be destroyed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onDisable

Allows addition of behavior to the disable operation. ...

Allows addition of behavior to the disable operation. After calling the superclass's `onDisable`, the Component will be disabled. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onDockedAdd

Invoked after a docked item is added to the Panel. ...

Invoked after a docked item is added to the Panel. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onDockedRemove

Invoked after a docked item is removed from the Panel. ...

Invoked after a docked item is removed from the Panel. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onEnable

Allows addition of behavior to the enable operation. ...

Allows addition of behavior to the enable operation. After calling the superclass's `onEnable`, the Component will be enabled. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onFloatShow

...


### onFocus

private ...

private

**Parameters:** e : Object


### onHeaderHide

Section onHeaderHide is invoked after view. ...

Section onHeaderHide is invoked after view.

**Parameters:** headerCt : Object


### onHeaderMove

Update the view when a header moves ...

Update the view when a header moves

**Parameters:** headerCt : Object


### onHeaderResize

...


### onHeaderShow

...

**Parameters:** headerCt : Object


### onHide

Possibly animates down to a target element. ...

Possibly animates down to a target element. Allows addition of behavior to the hide operation. After calling the superclass’s onHide, the Component will be hidden. Gets passed the same parameters as hide. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onHorizontalScroll

...

**Parameters:** event : Object


### onKeyDown

Listen for TAB events and wrap round if tabbing of either end of the Floater ...

Listen for TAB events and wrap round if tabbing of either end of the Floater

**Parameters:** e : Object


### onLockMenuClick

...


### onLockedHeaderAdd

...


### onLockedHeaderHide

...


### onLockedHeaderResize

...


### onLockedHeaderShow

...


### onLockedHeaderSortChange

...

**Parameters:** headerCt : Object


### onLockedViewMouseWheel

Listen for mousewheel events on the locked section which does not scroll. ...

Listen for mousewheel events on the locked section which does not scroll. Scroll it in response, and the other section will automatically sync.

**Parameters:** e : Object


### onLockedViewScroll

...


### onMouseDown

Mousedown brings to front, and programatically grabs focus unless the mousedown was on a focusable element ...

Mousedown brings to front, and programatically grabs focus *unless the mousedown was on a focusable element*

**Parameters:** e : Object


### onMouseEnterFloated

...

**Parameters:** e : Object


### onMouseLeaveFloated

...

**Parameters:** e : Object


### onMove

...


### onNormalHeaderSortChange

...

**Parameters:** headerCt : Object


### onNormalViewScroll

...


### onPosition

Called after the component is moved, this method is empty by default but can be implemented by any subclass that need...

Called after the component is moved, this method is empty by default but can be implemented by any subclass that needs to perform custom logic after a move occurs. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRemove

This method is invoked after a new Component has been removed. ...

This method is invoked after a new Component has been removed. It is passed the Component which has been removed. This method may be used to update any internal structure which may depend upon the state of the child items. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRemoved

Method to manage awareness of when components are removed from their respective Container, firing a removed event. ...

Method to manage awareness of when components are removed from their respective Container, firing a removed event. References are properly cleaned up after removing a component from its owning container. Allows addition of behavior when a Component is removed from its parent Container. At this stage, the Component has been removed from its parent Container's collection of child items, but has not been destroyed (It will be destroyed if the parent Container's `autoDestroy` is `true`, or if the remove call was passed a truthy second parameter). After calling the superclass's `onRemoved`, the `ownerCt` and the `refOwner` will not be present. Available since: 3.4.0 This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRender

Template method called when this Component's DOM structure is created. ...

Template method called when this Component's DOM structure is created. At this point, this Component's (and all descendants') DOM structure *exists* but it has not been layed out (positioned and sized). Subclasses which override this to gain access to the structure at render time should call the parent class's method before attempting to access any child elements of the Component. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onResize

Allows addition of behavior to the resize operation. ...

Allows addition of behavior to the resize operation. Called when Ext.resizer.Resizer#drag event is fired. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRestoreHorzScroll

Tracks when things happen to the view and preserves the horizontal scroll position. ...

Tracks when things happen to the view and preserves the horizontal scroll position.


### onShow

Allows addition of behavior to the show operation. ...

Allows addition of behavior to the show operation. After calling the superclass's onShow, the Component will be visible. Override in subclasses where more complex behaviour is needed. Gets passed the same parameters as show. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onShowComplete

Invoked after the afterShow method is complete. ...

Invoked after the afterShow method is complete. Gets passed the same `callback` and `scope` parameters that afterShow received. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onShowVeto

...


### onStateChange

This method is called when any of the stateEvents are fired. ...

This method is called when any of the stateEvents are fired.


### onStoreLoad

template method meant to be overriden ...

template method meant to be overriden


### onUnlockMenuClick

...


### onViewReady

Fires the TablePanel's viewready event when the view declares that its internal DOM is ready ...

Fires the TablePanel's viewready event when the view declares that its internal DOM is ready


### parseBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** box : Object


### placeholderCollapse

...

**Parameters:** direction : Object


### placeholderExpand

...

**Parameters:** animate : Object


### postBlur

Template method to do any post-blur processing. ...

Template method to do any post-blur processing.

**Parameters:** e : Ext.EventObjectThe event object


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a class derives from this class or uses this class as a mixin.

**Parameters:** T : FunctionThe class constructor to prepare.


### prepareItems

...

**Parameters:** items : Object


### prevChild

...

**Parameters:** child : Object


### previousNode

Returns the previous node in the Component tree in tree traversal order. ...

**Parameters:** selector : String (optional)A ComponentQuery selector to filter the preceding nodes.

**Returns:** the previous node in the Component tree in tree traversal order. Note that this is not limited to siblings, and if invoked upon a node with no matching siblings, will walk the tree in reverse order to attempt to find a match. Contrast with previousSibling.


### previousSibling

Returns the previous sibling of this Component. ...

**Parameters:** selector : String (optional)A ComponentQuery selector to filter the preceding items.

**Returns:** the previous sibling of this Component. Optionally selects the previous sibling which matches the passed ComponentQuery selector. May also be referred to as **`prev()`** Note that this is limited to siblings, and if no siblings of the item match, `null` is returned. Contrast with previousNode


### processColumns

...

**Parameters:** columns : Object


### processEvent

Processes UI events from the view. ...

Processes UI events from the view. Propagates them to whatever internal Components need to process them.

**Parameters:** type : StringEvent type, eg 'click'


### prune

...

**Parameters:** childEls : Object


### query

Retrieves all descendant components which match the passed selector. ...

Retrieves all descendant components which match the passed selector. Executes an Ext.ComponentQuery.query using this container as its root.

**Parameters:** selector : String (optional)Selector complying to an Ext.ComponentQuery selector. If no selector is specified all items will be returned.


### queryBy

Retrieves all descendant components which match the passed function. ...

Retrieves all descendant components which match the passed function. The function should return false for components that are to be excluded from the selection.

**Parameters:** fn : FunctionThe matcher function. It will be called with a single argument, the component being tested.


### queryById

Finds a component at any level under this container matching the id/itemId. ...

Finds a component at any level under this container matching the id/itemId. This is a shorthand for calling ct.down('#' + id);

**Parameters:** id : StringThe id to find


### reconfigure

documented on GridPanel ...

documented on GridPanel

**Parameters:** store : Object


### reconfigureLockable

we want to totally override the reconfigure behaviour here, since we're creating 2 sub-grids ...

we want to totally override the reconfigure behaviour here, since we're creating 2 sub-grids

**Parameters:** store : Object


### registerFloatingItem

Called by Component#doAutoRender Register a Container configured floating: true with this Component's ZIndexManager. ...

Called by Component#doAutoRender Register a Container configured `floating: true` with this Component's ZIndexManager. Components added in this way will not participate in any layout, but will be rendered upon first show in the way that Windows are.

**Parameters:** cmp : Object


### registerWithOwnerCt

...


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`. For example if you are extending Grid, you might decide to forward some events from store. So you can do this inside your initComponent: The grid instance will then have an observable 'load' event which will be passed the parameters of the store's load event and any function fired with the grid's load event would have access to the grid using the `this` keyword.

**Parameters:** origin : ObjectThe Observable whose events this object is to relay.


### relayHeaderCtEvents

...

**Parameters:** headerCt : Object


### remove

Removes a component from this container. ...

Removes a component from this container. Fires the beforeremove event before removing, then fires the remove event after the component has been removed. Available since: 2.3.0

**Parameters:** component : Ext.Component/StringThe component reference or id to remove.


### removeAll

Removes all components from this container. ...

Removes all components from this container. Available since: 2.3.0

**Parameters:** autoDestroy : Boolean (optional)True to automatically invoke the removed Component's Ext.Component.destroy function. Defaults to the value of this Container's autoDestroy config.


### removeAnchor

Remove any anchor to this element. ...

Remove any anchor to this element. See anchorTo.

**Returns:** Ext.util.Positionablethis


### removeBodyCls

Removes a CSS class from the body element. ...

Removes a CSS class from the body element.

**Parameters:** cls : StringThe class to remove


### removeChildEls

Removes items in the childEls array based on the return value of a supplied test function. ...

Removes items in the childEls array based on the return value of a supplied test function. The function is called with a entry in childEls and if the test function return true, that entry is removed. If false, that entry is kept.

**Parameters:** testFn : FunctionThe test function.


### removeClass

...

Available since: 2.3.0


### removeCls

Removes a CSS class from the top level element representing this component. ...

Removes a CSS class from the top level element representing this component.

**Parameters:** cls : String/String[]The CSS class name to remove.


### removeClsWithUI

Removes a cls to the uiCls array, which will also call removeUIClsFromElement and removes it from all elements of thi...

Removes a `cls` to the `uiCls` array, which will also call removeUIClsFromElement and removes it from all elements of this component.

**Parameters:** cls : String/String[]A string or an array of strings to remove to the `uiCls`.


### removeDocked

Removes the docked item from the panel. ...

Removes the docked item from the panel.

**Parameters:** item : Ext.ComponentThe Component to remove.


### removeListener

Removes an event handler. ...

Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### removeManagedListener

Removes listeners that were added by the mon method. ...

Removes listeners that were added by the mon method.

**Parameters:** item : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### removeManagedListenerItem

inherit docs Remove a single managed listener item ...

inherit docs Remove a single managed listener item

**Parameters:** isClear : BooleanTrue if this is being called during a clear


### removeOverCls

...


### removePlugin

...

**Parameters:** plugin : Object


### removeUIClsFromElement

inherit docs Method which removes a specified UI + uiCls from the components element. ...

inherit docs Method which removes a specified UI + `uiCls` from the components element. The `cls` which is added to the element will be: `this.baseCls + '-' + ui`.

**Parameters:** ui : StringThe UI to add to the element.


### removeUIFromElement

inherit docs Method which removes a specified UI from the components element. ...

inherit docs Method which removes a specified UI from the components element. Overrides: Ext.AbstractComponent.removeUIFromElement


### render

Renders the Component into the passed HTML element. ...

Renders the Component into the passed HTML element. If you are using a Container object to house this Component, then do not use the render method. A Container's child Components are rendered by that Container's layout manager when the Container is first rendered. If the Container is already rendered when a new child Component is added, you may need to call the Container's doLayout to refresh the view which causes any unrendered child Components to be rendered. This is required so that you can add multiple child components if needed while only refreshing the layout once. When creating complex UIs, it is important to remember that sizing and positioning of child items is the responsibility of the Container's layout manager. If you expect child items to be sized in response to user interactions, you must configure the Container with a layout manager which creates and manages the type of layout you have in mind. Omitting the Container's layout config means that a basic layout manager is used which does nothing but render child components sequentially into the Container. No sizing or positioning will be performed in this situation.

**Parameters:** container : Ext.Element/HTMLElement/String (optional)The element this Component should be rendered into. If it is being created from existing markup, this should be omitted.


### repositionFloatingItems

...


### restoreDimension

...


### restoreHiddenDocked

...


### restoreScrollPos

...


### resumeEvent

Resumes firing of the named event(s). ...

Resumes firing of the named event(s). After calling this method to resume events, the events will fire when requested to fire. Note that if the suspendEvent method is called multiple times for a certain event, this converse method will have to be called the same number of times for it to resume firing.

**Parameters:** eventName : String...Multiple event names to resume.


### resumeEvents

Resumes firing events (see suspendEvents). ...

Resumes firing events (see suspendEvents). If events were suspended using the `queueSuspended` parameter, then all events fired during event suspension will be sent to any listeners now.


### resumeLayouts

...

**Parameters:** flushOptions : Object


### savePropToState

Conditionally saves a single property from this object to the given state object. ...

Conditionally saves a single property from this object to the given state object. The idea is to only save state which has changed from the initial state so that current software settings do not override future software settings. Only those values that are user-changed state should be saved.

**Parameters:** propName : StringThe name of the property to save.


### savePropsToState

Gathers additional named properties of the instance and adds their current values to the passed state object. ...

Gathers additional named properties of the instance and adds their current values to the passed state object.

**Parameters:** propNames : String/String[]The name (or array of names) of the property to save.


### saveScrollPos

...


### saveState

Saves the state of the object to the persistence store. ...

Saves the state of the object to the persistence store.


### scrollBy

Scrolls this Component's target element by the passed delta values, optionally animating. ...

Scrolls this Component's target element by the passed delta values, optionally animating. All of the following are equivalent:

**Parameters:** deltaX : Number/Number[]/ObjectEither the x delta, an Array specifying x and y deltas or an object with "x" and "y" properties.


### scrollByDeltaX

...

**Parameters:** xDelta : Object


### scrollByDeltaY

...

**Parameters:** yDelta : Object


### sequenceFx

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. ...

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. This is the opposite of syncFx.

**Returns:** Objectthis


### setActive

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been moved to th...

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been moved to the top of its zIndex stack, or pushed from the top of its zIndex stack. If a *Window* is superceded by another Window, deactivating it hides its shadow. This method also fires the activate or deactivate event depending on which action occurred.

**Parameters:** active : Boolean (optional)True to activate the Component, false to deactivate it. Defaults to: `false`


### setAutoScroll

autoScroll is never valid for all classes which extend TablePanel. ...

autoScroll is never valid for all classes which extend TablePanel. Overrides: Ext.Component.setAutoScroll


### setBodyStyle

Sets the body style according to the passed parameters. ...

Sets the body style according to the passed parameters.

**Parameters:** style : MixedA full style specification string, or object, or the name of a style property to set.


### setBorder

...

**Parameters:** border : String/NumberThe border, see border. If a falsey value is passed the border will be removed.


### setBorderRegion

This method changes the region config property for this border region. ...

This method changes the `region` config property for this border region. This is only valid if this component is in a `border` layout (`Ext.layout.container.Border`). **Defined in override Ext.layout.container.border.Region.**

**Parameters:** region : StringThe new `region` value (`"north"`, `"south"`, `"east"` or `"west"`).


### setBox

Sets the element's box. ...

Sets the element's box. If animate is true then x, y, width, and height will be animated concurrently.

**Parameters:** box : ObjectThe box to fill {x, y, width, height}


### setComponentLayout

...

**Parameters:** layout : Object


### setConfig

...

**Parameters:** config : Object


### setDisabled

Enable or disable the component. ...

Enable or disable the component.

**Parameters:** disabled : Boolean`true` to disable.


### setDocked

Sets the dock position of this component in its parent panel. ...

Sets the dock position of this component in its parent panel. Note that this only has effect if this item is part of the `dockedItems` collection of a parent that has a DockLayout (note that any Panel has a DockLayout by default)

**Parameters:** dock : ObjectThe dock position.


### setFloatParent

...

**Parameters:** floatParent : Object


### setGlyph

Set the glyph for the panel's header. ...

Set the glyph for the panel's header. See Ext.panel.Header.glyph. It will fire the glyphchange event after completion.

**Parameters:** newGlyph : Number/StringThe new glyph This parameter expects a format consistent with that of glyph


### setHeight

Sets the height of the component. ...

Sets the height of the component. This method fires the resize event.

**Parameters:** - height : NumberThe new height to set. This may be one of: A Number specifying the new height in the Element's Ext.Element.defaultUnits (by default, pixels). - A String used to set the CSS height style. - *undefined* to leave the height unchanged.


### setHiddenDocked

...


### setHiddenState

...

**Parameters:** hidden : Object


### setIcon

Set the icon for the panel's header. ...

Set the icon for the panel's header. See Ext.panel.Header.icon. It will fire the iconchange event after completion.

**Parameters:** newIcon : StringThe new icon path


### setIconCls

Set the iconCls for the panel's header. ...

Set the iconCls for the panel's header. See Ext.panel.Header.iconCls. It will fire the iconclschange event after completion.

**Parameters:** newIconCls : StringThe new CSS class name


### setLayout

...

**Parameters:** layout : Object


### setLoading

This method allows you to show or hide a LoadMask on top of this component. ...

This method allows you to show or hide a LoadMask on top of this component.

**Parameters:** load : Boolean/Object/StringTrue to show the default LoadMask, a config object that will be passed to the LoadMask constructor, or a message String to show. False to hide the current LoadMask.


### setLocalX

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.** Sets the local x coordinate of this element using CSS style. When used on an absolute positioned element this method is symmetrical with getLocalX, but may not be symmetrical when used on a relatively positioned element.

**Parameters:** x : NumberThe x coordinate. A value of `null` sets the left style to 'auto'.


### setLocalXY

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.** Sets the local x and y coordinates of this element using CSS style. When used on an absolute positioned element this method is symmetrical with getLocalXY, but may not be symmetrical when used on a relatively positioned element.

**Parameters:** x : Number/ArrayThe x coordinate or an array containing [x, y]. A value of `null` sets the left style to 'auto'


### setLocalY

Sets the local y coordinate of this element using CSS style. ...

Sets the local y coordinate of this element using CSS style. When used on an absolute positioned element this method is symmetrical with getLocalY, but may not be symmetrical when used on a relatively positioned element.

**Parameters:** y : NumberThe y coordinate. A value of `null` sets the top style to 'auto'.


### setMargin

Sets the margin on the target element. ...

Sets the margin on the target element.

**Parameters:** margin : Number/StringThe margin to set. See the margin config.


### setOverflowXY

Sets the overflow x/y on the content element of the component. ...

Sets the overflow x/y on the content element of the component. The x/y overflow values can be any valid CSS overflow (e.g., 'auto' or 'scroll'). By default, the value is 'hidden'. Passing null for one of the values will erase the inline style. Passing `undefined` will preserve the current value.

**Parameters:** overflowX : StringThe overflow-x value.


### setPagePosition

Sets the page XY position of the component. ...

Sets the page XY position of the component. To set the left and top instead, use setPosition. This method fires the move event.

**Parameters:** x : Number/Number[]The new x position or an array of `[x,y]`.


### setPosition

Sets the left and top of the component. ...

Sets the left and top of the component. To set the page XY position instead, use setPagePosition. This method fires the move event.

**Parameters:** x : Number/Number[]/ObjectThe new left, an array of `[x,y]`, or animation config object containing `x` and `y` properties.


### setRegion

Sets the element's position and size to the specified region. ...

Sets the element's position and size to the specified region. If animation is true then width, height, x and y will be animated concurrently.

**Parameters:** region : Ext.util.RegionThe region to fill


### setRegionWeight

Sets the weight config property for this component. ...

Sets the `weight` config property for this component. This is only valid if this component is in a `border` layout (`Ext.layout.container.Border`). **Defined in override Ext.layout.container.border.Region.**

**Parameters:** weight : NumberThe new `weight` value.


### setSize

Sets the width and height of this Component. ...

Sets the width and height of this Component. This method fires the resize event. This method can accept either width and height as separate arguments, or you can pass a size object like `{width:10, height:20}`.

**Parameters:** - width : Number/String/ObjectThe new width to set. This may be one of: A Number specifying the new width in the Element's Ext.Element.defaultUnits (by default, pixels). - A String used to set the CSS width style. - A size object in the format `{width: widthValue, height: heightValue}`. - `undefined` to leave the width unchanged.


### setTitle

Set a title for the panel's header. ...

Set a title for the panel's header. See Ext.panel.Header.title.

**Parameters:** newTitle : String


### setUI

Sets the UI for the component. ...

Sets the UI for the component. This will remove any existing UIs on the component. It will also loop through any `uiCls` set on the component and rename them so they include the new UI.

**Parameters:** ui : StringThe new UI for the component.


### setVisible

Convenience function to hide or show this component by Boolean. ...

Convenience function to hide or show this component by Boolean. Available since: 1.1.0

**Parameters:** visible : Boolean`true` to show, `false` to hide.


### setWidth

Sets the width of the component. ...

Sets the width of the component. This method fires the resize event.

**Parameters:** - width : NumberThe new width to setThis may be one of: A Number specifying the new width in the Element's Ext.Element.defaultUnits (by default, pixels). - A String used to set the CSS width style.


### setX

Sets the X position of the DOM element based on page coordinates. ...

Sets the X position of the DOM element based on page coordinates.

**Parameters:** The : NumberX position


### setXY

Sets the position of the DOM element in page coordinates. ...

Sets the position of the DOM element in page coordinates.

**Parameters:** pos : Number[]Contains X & Y [x, y] values for new position (coordinates are page-based)


### setY

Sets the Y position of the DOM element based on page coordinates. ...

Sets the Y position of the DOM element based on page coordinates.

**Parameters:** The : NumberY position


### setZIndex

z-index is managed by the zIndexManager and may be overwritten at any time. ...

z-index is managed by the zIndexManager and may be overwritten at any time.

**Parameters:** index : Object

**Returns:** the next z-index to be used. If this is a Container, then it will have rebased any managed floating Components, and so the next available z-index will be approximately 10000 above that.


### setupDockingRenderTpl

...

**Parameters:** renderTpl : Object


### setupFramingTpl

Inject a reference to the function which applies the render template into the framing template. ...

Inject a reference to the function which applies the render template into the framing template. The framing template wraps the content.

**Parameters:** frameTpl : Object


### setupProtoEl

...


### setupRenderTpl

...

**Parameters:** renderTpl : Object


### show

Shows this Component, rendering it first if autoRender or floating are true. ...

Shows this Component, rendering it first if autoRender or floating are `true`. After being shown, a floating Component (such as a Ext.window.Window), is activated it and brought to the front of its z-index stack.

**Parameters:** animateTarget : String/Ext.Element (optional)only valid for floating Components such as Windows or ToolTips, or regular Components which have been configured with `floating: true`. The target from which the Component should animate from while opening. Defaults to: `null`


### showAt

Displays component at specific xy position. ...

Displays component at specific xy position. A floating component (like a menu) is positioned relative to its ownerCt if any. Useful for popping up a context menu:

**Parameters:** x : Number/Number[]The new x position or array of `[x,y]`.


### showBy

Shows this component by the specified Component or Element. ...

Shows this component by the specified Component or Element. Used when this component is floating.

**Parameters:** component : Ext.Component/Ext.dom.ElementThe Ext.Component or Ext.Element to show the component by.


### showMenuBy

...

**Parameters:** t : Object


### slideOutFloatedPanel

...


### slideOutFloatedPanelBegin

This method begins the slide out of the floated panel. ...

This method begins the slide out of the floated panel.


### slideOutFloatedPanelEnd

This method cleans up after the slide out of the floated panel. ...

This method cleans up after the slide out of the floated panel.


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### stopAnimation

Stops any running effects and clears this object's internal effects queue if it contains any additional effects that ...

Stops any running effects and clears this object's internal effects queue if it contains any additional effects that haven't started yet.

**Returns:** Ext.ElementThe Element


### stopFx

Stops any running effects and clears this object's internal effects queue if it contains any additional effects that ...

Stops any running effects and clears this object's internal effects queue if it contains any additional effects that haven't started yet. This method has been **deprecated** since 4.0 Replaced by stopAnimation


### suspendEvent

Suspends firing of the named event(s). ...

Suspends firing of the named event(s). After calling this method to suspend events, the events will no longer fire when requested to fire. Note that if this is called multiple times for a certain event, the converse method resumeEvent will have to be called the same number of times for it to resume firing.

**Parameters:** eventName : String...Multiple event names to suspend.


### suspendEvents

Suspends the firing of all events. ...

Suspends the firing of all events. (see resumeEvents)

**Parameters:** queueSuspended : BooleanPass as true to queue up suspended events to be fired after the resumeEvents call instead of discarding all suspended events.


### suspendLayouts

...


### syncFx

Ensures that all effects queued after syncFx is called on this object are run concurrently. ...

Ensures that all effects queued after syncFx is called on this object are run concurrently. This is the opposite of sequenceFx.

**Returns:** Objectthis


### syncHidden

synchronizes the hidden state of this component with the state of its hierarchy ...

synchronizes the hidden state of this component with the state of its hierarchy


### syncHorizontalScroll

...

**Parameters:** left : Object


### syncLockedWidth

Updates the overall view after columns have been resized, or moved from the locked to unlocked side or vice-versa. ...

Updates the overall view after columns have been resized, or moved from the locked to unlocked side or vice-versa. If all columns are removed from either side, that side must be hidden, and the sole remaining column owning grid then becomes *the* grid. It must flex to occupy the whole of the locking view. And it must also allow scrolling. If columns are shared between the two sides, the *locked* grid shrinkwraps the width of the visible locked columns while the normal grid flexes in what space remains.

**Returns:** Boolean`true` if there are visible locked columns which need refreshing.


### syncRowHeights

Synchronizes the row heights between the locked and non locked portion of the grid for each row. ...

Synchronizes the row heights between the locked and non locked portion of the grid for each row. If one row is smaller than the other, the height will be increased to match the larger one.


### syncShadow

...


### toBack

Sends this Component to the back of (lower z-index than) any other visible windows ...

Sends this Component to the back of (lower z-index than) any other visible windows

**Returns:** Ext.Componentthis


### toFront

Brings this floating Component to the front of any other visible, floating Components managed by the same ZIndexManag...

Brings this floating Component to the front of any other visible, floating Components managed by the same ZIndexManager If this Component is modal, inserts the modal mask just below this Component in the z-index stack.

**Parameters:** preventFocus : Boolean (optional)Specify `true` to prevent the Component from being focused. Defaults to: `false`


### toggleCollapse

Shortcut for performing an expand or collapse based on the current state of the panel. ...

Shortcut for performing an expand or collapse based on the current state of the panel.

**Returns:** Ext.panel.Panelthis


### translatePoints

Translates the passed page coordinates into left/top css values for the element ...

Translates the passed page coordinates into left/top css values for the element

**Parameters:** x : Number/ArrayThe page x or an array containing [x, y]


### translateXY

Translates the passed page coordinates into x and y css values for the element ...

Translates the passed page coordinates into x and y css values for the element

**Parameters:** x : Number/ArrayThe page x or an array containing [x, y]


### un

Shorthand for removeListener. ...

Shorthand for removeListener. Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### unbindStore

...


### unghost

...

**Parameters:** show : Object


### unitizeBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** box : Object


### unlock

Unlocks the activeHeader as determined by which menu is open OR a header as specified. ...

Unlocks the activeHeader as determined by which menu is open OR a header as specified.

**Parameters:** header : Ext.grid.column.Column (optional)Header to unlock from the locked section. Defaults to the header which has the menu open currently.


### unmask

...


### unregisterFloatingItem

...

**Parameters:** cmp : Object


### up

Navigates up the ownership hierarchy searching for an ancestor Container which matches any passed simple selector or ...

Navigates up the ownership hierarchy searching for an ancestor Container which matches any passed simple selector or component. *Important.* There is not a universal upwards navigation pointer. There are several upwards relationships such as the button which activates a menu, or the menu item which activated a submenu, or the column header which activated the column menu. These differences are abstracted away by this method. Example:

**Parameters:** selector : String/Ext.Component (optional)The simple selector component or actual component to test. If not passed the immediate owner/activater is returned.


### update

Update the content area of a component. ...

Update the content area of a component. Available since: 3.4.0

**Parameters:** htmlOrData : String/ObjectIf this component has been configured with a template via the tpl config then it will use this argument as data to populate the template. If this component was not configured with a template, the components content area will be updated via Ext.Element update.


### updateAria

Injected as an override by Ext.Aria.initialize ...

Injected as an override by Ext.Aria.initialize


### updateBox

Sets the current box measurements of the component's underlying element. ...

Sets the current box measurements of the component's underlying element.

**Parameters:** box : ObjectAn object in the format {x, y, width, height}


### updateCollapseTool

...


### updateFrame

...


### updateHeader

Create, hide, or show the header component as appropriate based on the current config. ...

Create, hide, or show the header component as appropriate based on the current config.

**Parameters:** force : BooleanTrue to force the header to be created


### updateLayout

Updates this component's layout. ...

Updates this component's layout. If this update affects this components ownerCt, that component's `updateLayout` method will be called to perform the layout instead. Otherwise, just this component (and its child items) will layout.

**Parameters:** options : Object (optional)An object with layout options. defer : Boolean`true` if this layout should be deferred.


### wrapPrimaryEl

...

**Parameters:** dom : Object


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


### activate

Fires after a Component has been visually activated. ...

Fires after a Component has been visually activated.

**Parameters:** this : Ext.Component


### add

Fires after any Ext.Component is added or inserted into the container. ...

Fires after any Ext.Component is added or inserted into the container. **This event bubbles:** 'add' will also be fired when Component is added to any of the child containers or their childern or ... Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### added

Fires after a Component had been added to a Container. ...

Fires after a Component had been added to a Container. Available since: 3.4.0

**Parameters:** this : Ext.Component


### afterlayout

Fires when the components in this container are arranged by the associated layout manager. ...

Fires when the components in this container are arranged by the associated layout manager. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### afterrender

Fires after the component rendering is finished. ...

Fires after the component rendering is finished. The `afterrender` event is fired after this Component has been rendered, been postprocessed by any `afterRender` method defined for the Component. Available since: 3.4.0

**Parameters:** this : Ext.Component


### beforeactivate

Fires before a Component has been visually activated. ...

Fires before a Component has been visually activated. Returning `false` from an event listener can prevent the activate from occurring.

**Parameters:** this : Ext.Component


### beforeadd

Fires before any Ext.Component is added or inserted into the container. ...

Fires before any Ext.Component is added or inserted into the container. A handler can return false to cancel the add. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### beforecellclick

Fired before the cell click is processed. ...

Fired before the cell click is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellcontextmenu

Fired before the cell right click is processed. ...

Fired before the cell right click is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecelldblclick

Fired before the cell double click is processed. ...

Fired before the cell double click is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellkeydown

Fired before the cell key down is processed. ...

Fired before the cell key down is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellmousedown

Fired before the cell mouse down is processed. ...

Fired before the cell mouse down is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellmouseup

Fired before the cell mouse up is processed. ...

Fired before the cell mouse up is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforeclose

Fires before the user closes the panel. ...

Fires before the user closes the panel. Return false from any listener to stop the close event being fired

**Parameters:** panel : Ext.panel.PanelThe Panel object


### beforecollapse

Fires before this panel is collapsed. ...

Fires before this panel is collapsed. Return false to prevent the collapse.

**Parameters:** p : Ext.panel.PanelThe Panel being collapsed.


### beforecontainerclick

Fires before the click event on the container is processed. ...

Fires before the click event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainercontextmenu

Fires before the contextmenu event on the container is processed. ...

Fires before the contextmenu event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainerdblclick

Fires before the dblclick event on the container is processed. ...

Fires before the dblclick event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermousedown

Fires before the mousedown event on the container is processed. ...

Fires before the mousedown event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermouseout

Fires before the mouseout event on the container is processed. ...

Fires before the mouseout event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermouseover

Fires before the mouseover event on the container is processed. ...

Fires before the mouseover event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermouseup

Fires before the mouseup event on the container is processed. ...

Fires before the mouseup event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforedeactivate

Fires before a Component has been visually deactivated. ...

Fires before a Component has been visually deactivated. Returning `false` from an event listener can prevent the deactivate from occurring.

**Parameters:** this : Ext.Component


### beforedeselect

Fired before a record is deselected. ...

Fired before a record is deselected. If any listener returns false, the deselection is cancelled.

**Parameters:** this : Ext.selection.RowModel


### beforedestroy

Fires before the component is destroyed. ...

Fires before the component is destroyed. Return `false` from an event handler to stop the destroy. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeexpand

Fires before this panel is expanded. ...

Fires before this panel is expanded. Return false to prevent the expand.

**Parameters:** p : Ext.panel.PanelThe Panel being expanded.


### beforehide

Fires before the component is hidden when calling the hide method. ...

Fires before the component is hidden when calling the hide method. Return `false` from an event handler to stop the hide. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeitemclick

Fires before the click event on an item is processed. ...

Fires before the click event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemcontextmenu

Fires before the contextmenu event on an item is processed. ...

Fires before the contextmenu event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemdblclick

Fires before the dblclick event on an item is processed. ...

Fires before the dblclick event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmousedown

Fires before the mousedown event on an item is processed. ...

Fires before the mousedown event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmouseenter

Fires before the mouseenter event on an item is processed. ...

Fires before the mouseenter event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmouseleave

Fires before the mouseleave event on an item is processed. ...

Fires before the mouseleave event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmouseup

Fires before the mouseup event on an item is processed. ...

Fires before the mouseup event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeremove

Fires before any Ext.Component is removed from the container. ...

Fires before any Ext.Component is removed from the container. A handler can return false to cancel the remove. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### beforerender

Fires before the component is rendered. ...

Fires before the component is rendered. Return `false` from an event handler to stop the render. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeselect

Fired before a record is selected. ...

Fired before a record is selected. If any listener returns false, the selection is cancelled.

**Parameters:** this : Ext.selection.RowModel


### beforeshow

Fires before the component is shown when calling the show method. ...

Fires before the component is shown when calling the show method. Return `false` from an event handler to stop the show. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforestaterestore

Fires before the state of the object is restored. ...

Fires before the state of the object is restored. Return false from an event handler to stop the restore.

**Parameters:** this : Ext.state.Stateful


### beforestatesave

Fires before the state of the object is saved to the configured state provider. ...

Fires before the state of the object is saved to the configured state provider. Return false to stop the save.

**Parameters:** this : Ext.state.Stateful


### blur

Fires when this Component loses focus. ...

Fires when this Component loses focus.

**Parameters:** this : Ext.Component


### boxready

Fires one time - after the component has been laid out for the first time at its initial size. ...

Fires *one time* - after the component has been laid out for the first time at its initial size.

**Parameters:** this : Ext.Component


### cellclick

Fired when table cell is clicked. ...

Fired when table cell is clicked.

**Parameters:** this : Ext.view.Table


### cellcontextmenu

Fired when table cell is right clicked. ...

Fired when table cell is right clicked.

**Parameters:** this : Ext.view.Table


### celldblclick

Fired when table cell is double clicked. ...

Fired when table cell is double clicked.

**Parameters:** this : Ext.view.Table


### cellkeydown

Fired when the keydown event is captured on the cell. ...

Fired when the keydown event is captured on the cell.

**Parameters:** this : Ext.view.Table


### cellmousedown

Fired when the mousedown event is captured on the cell. ...

Fired when the mousedown event is captured on the cell.

**Parameters:** this : Ext.view.Table


### cellmouseup

Fired when the mouseup event is captured on the cell. ...

Fired when the mouseup event is captured on the cell.

**Parameters:** this : Ext.view.Table


### close

Fires when the user closes the panel. ...

Fires when the user closes the panel.

**Parameters:** panel : Ext.panel.PanelThe Panel object


### collapse

Fires after this Panel has collapsed. ...

Fires after this Panel has collapsed.

**Parameters:** p : Ext.panel.PanelThe Panel that has been collapsed.


### columnhide

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnmove

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnresize

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnschanged

Fired after the columns change in any way, when a column has been hidden or shown, or when a column is added to or re...

Fired after the columns change in any way, when a column has been hidden or shown, or when a column is added to or removed from this header container.

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnshow

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### containerclick

Fires when the container is clicked. ...

Fires when the container is clicked.

**Parameters:** this : Ext.view.View


### containercontextmenu

Fires when the container is right clicked. ...

Fires when the container is right clicked.

**Parameters:** this : Ext.view.View


### containerdblclick

Fires when the container is double clicked. ...

Fires when the container is double clicked.

**Parameters:** this : Ext.view.View


### containermouseout

Fires when you move the mouse out of the container. ...

Fires when you move the mouse out of the container.

**Parameters:** this : Ext.view.View


### containermouseover

Fires when you move the mouse over the container. ...

Fires when you move the mouse over the container.

**Parameters:** this : Ext.view.View


### containermouseup

Fires when there is a mouse up on the container ...

Fires when there is a mouse up on the container

**Parameters:** this : Ext.view.View


### deactivate

Fires after a Component has been visually deactivated. ...

Fires after a Component has been visually deactivated.

**Parameters:** this : Ext.Component


### deselect

Fired after a record is deselected ...

Fired after a record is deselected

**Parameters:** this : Ext.selection.RowModel


### destroy

Fires after the component is destroyed. ...

Fires after the component is destroyed. Available since: 1.1.0

**Parameters:** this : Ext.Component


### disable

Fires after the component is disabled. ...

Fires after the component is disabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### dockedadd

Fires when any Ext.Component is added or inserted as a docked item. ...

Fires when any Ext.Component is added or inserted as a docked item.

**Parameters:** this : Ext.panel.Panel


### dockedremove

Fires when any Ext.Component is removed from the docked items. ...

Fires when any Ext.Component is removed from the docked items.

**Parameters:** this : Ext.panel.Panel


### enable

Fires after the component is enabled. ...

Fires after the component is enabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### expand

Fires after this Panel has expanded. ...

Fires after this Panel has expanded.

**Parameters:** p : Ext.panel.PanelThe Panel that has been expanded.


### filterchange

Fired whenever the filter set changes. ...

Fired whenever the filter set changes.

**Parameters:** store : Ext.data.StoreThe store.


### float

Fires after a collapsed Panel has been "floated" by clicking on it's header. ...

Fires after a collapsed Panel has been "floated" by clicking on it's header. Only applicable when the Panel is an item in a Border Layout.

**Parameters:** eOpts : ObjectThe options object passed to Ext.util.Observable.addListener.


### focus

Fires when this Component receives focus. ...

Fires when this Component receives focus.

**Parameters:** this : Ext.Component


### glyphchange

Fired when the Panel glyph has been changed by the setGlyph method. ...

Fired when the Panel glyph has been changed by the setGlyph method.

**Parameters:** this : Ext.panel.Panel


### headerclick

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### headercontextmenu

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### headertriggerclick

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### hide

Fires after the component is hidden. ...

Fires after the component is hidden. Fires after the component is hidden when calling the hide method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### iconchange

Fires after the Panel icon has been set or changed. ...

Fires after the Panel icon has been set or changed.

**Parameters:** p : Ext.panel.PanelThe Panel which has the icon changed.


### iconclschange

Fires after the Panel iconCls has been set or changed. ...

Fires after the Panel iconCls has been set or changed.

**Parameters:** p : Ext.panel.PanelThe Panel which has the iconCls changed.


### itemclick

Fires when an item is clicked. ...

Fires when an item is clicked.

**Parameters:** this : Ext.view.View


### itemcontextmenu

Fires when an item is right clicked. ...

Fires when an item is right clicked.

**Parameters:** this : Ext.view.View


### itemdblclick

Fires when an item is double clicked. ...

Fires when an item is double clicked.

**Parameters:** this : Ext.view.View


### itemmousedown

Fires when there is a mouse down on an item ...

Fires when there is a mouse down on an item

**Parameters:** this : Ext.view.View


### itemmouseenter

Fires when the mouse enters an item. ...

Fires when the mouse enters an item.

**Parameters:** this : Ext.view.View


### itemmouseleave

Fires when the mouse leaves an item. ...

Fires when the mouse leaves an item.

**Parameters:** this : Ext.view.View


### itemmouseup

Fires when there is a mouse up on an item ...

Fires when there is a mouse up on an item

**Parameters:** this : Ext.view.View


### lockcolumn

Fires when a column is locked. ...

Fires when a column is locked.

**Parameters:** this : Ext.grid.PanelThe gridpanel.


### move

Fires after the component is moved. ...

Fires after the component is moved.

**Parameters:** this : Ext.Component


### processcolumns

Fires when the configured (or reconfigured) column set is split into two depending on the locked flag. ...

Fires when the configured (or **reconfigured**) column set is split into two depending on the locked flag.

**Parameters:** lockedColumns : Ext.grid.column.Column[]The locked columns.


### remove

Fires after any Ext.Component is removed from the container. ...

Fires after any Ext.Component is removed from the container. **This event bubbles:** 'remove' will also be fired when Component is removed from any of the child containers or their children or ... Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### removed

Fires when a component is removed from an Ext.container.Container ...

Fires when a component is removed from an Ext.container.Container Available since: 3.4.0

**Parameters:** this : Ext.Component


### render

Fires after the component markup is rendered. ...

Fires after the component markup is rendered. Available since: 1.1.0

**Parameters:** this : Ext.Component


### resize

Fires after the component is resized. ...

Fires after the component is resized. Note that this does *not* fire when the component is first laid out at its initial size. To hook that point in the life cycle, use the boxready event.

**Parameters:** this : Ext.Component


### select

Fired after a record is selected ...

Fired after a record is selected

**Parameters:** this : Ext.selection.RowModel


### selectionchange

Fired after a selection change has occurred ...

Fired after a selection change has occurred

**Parameters:** this : Ext.selection.Model


### show

Fires after the component is shown when calling the show method. ...

Fires after the component is shown when calling the show method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### sortchange

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### staterestore

Fires after the state of the object is restored. ...

Fires after the state of the object is restored.

**Parameters:** this : Ext.state.Stateful


### statesave

Fires after the state of the object is saved to the configured state provider. ...

Fires after the state of the object is saved to the configured state provider.

**Parameters:** this : Ext.state.Stateful


### titlechange

Fires after the Panel title has been set or changed. ...

Fires after the Panel title has been set or changed.

**Parameters:** p : Ext.panel.Panelthe Panel which has been resized.


### unfloat

Fires after a "floated" Panel has returned to it's collapsed state as a result of the mouse leaving the Panel. ...

Fires after a "floated" Panel has returned to it's collapsed state as a result of the mouse leaving the Panel. Only applicable when the Panel is an item in a Border Layout.

**Parameters:** eOpts : ObjectThe options object passed to Ext.util.Observable.addListener.


### unlockcolumn

Fires when a column is unlocked. ...

Fires when a column is unlocked.

**Parameters:** this : Ext.grid.PanelThe gridpanel.


### viewready

Fires when the grid view is available (use this for selecting a default row). ...

Fires when the grid view is available (use this for selecting a default row).

**Parameters:** this : Ext.panel.Table


### $border-width-threshold

**Type:** $border-width-threshold

The maximum width a Panel's border can be before resizer handles are embedded into the borders using negative absolut...

The maximum width a Panel's border can be before resizer handles are embedded into the borders using negative absolute positions. This defaults to 2, so that in the classic theme which uses 1 pixel borders, resize handles are in the content area within the border as they always have been. In the Neptune theme, the handles are embedded into the 5 pixel wide borders of any framed panel. Defaults to: `2`


### $grid-body-background-color

**Type:** color

The background-color of the grid body ...

The background-color of the grid body Defaults to: `$panel-body-background-color`


### $grid-body-border-color

**Type:** color

The border-color of the grid body ...

The border-color of the grid body Defaults to: `$panel-body-border-color`


### $grid-body-border-style

**Type:** string

The border-style of the grid body border ...

The border-style of the grid body border Defaults to: `$panel-body-border-style`


### $grid-body-border-width

**Type:** number

The border-width of the grid body border ...

The border-width of the grid body border Defaults to: `$panel-body-border-width`


### $grid-cell-inner-padding

**Type:** number

The amount of padding to apply to the grid cell's inner div element ...

The amount of padding to apply to the grid cell's inner div element Defaults to: `3px 6px`


### $grid-cell-inner-text-overflow

**Type:** string

The type of text-overflow to use on the grid cell's inner div element ...

The type of text-overflow to use on the grid cell's inner div element Defaults to: `ellipsis`


### $grid-cell-selected-background-color

**Type:** color

The background-color of a selected cell when using a Cell Selection Model. ...

The background-color of a selected cell when using a Cell Selection Model. Defaults to: `$grid-row-cell-selected-background-color`


### $grid-cell-selected-color

**Type:** color

The text color of a selected cell when using a Cell Selection Model. ...

The text color of a selected cell when using a Cell Selection Model. Defaults to: `$grid-row-cell-selected-color`


### $grid-cell-special-background-color

**Type:** color

The background-color of "special" cells. ...

The background-color of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `$grid-row-cell-background-color`


### $grid-cell-special-background-gradient

**Type:** string

The background-gradient to use for "special" cells. ...

The background-gradient to use for "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `null`


### $grid-cell-special-border-color

**Type:** color

The border-color of "special" cells. ...

The border-color of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border color is determined by {#$grid-row-cell-border-color}. Defaults to: `$grid-row-cell-border-color`


### $grid-cell-special-border-style

**Type:** string

The border-style of "special" cells. ...

The border-style of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border style is determined by {#$grid-row-cell-border-style}. Defaults to: `$grid-row-cell-border-style`


### $grid-cell-special-border-width

**Type:** number

The border-width of "special" cells. ...

The border-width of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border width is determined by {#$grid-row-cell-border-width}. Defaults to: `$grid-row-cell-border-width`


### $grid-cell-special-over-background-color

**Type:** color

The background-color of "special" cells when the row is hovered. ...

The background-color of "special" cells when the row is hovered. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `$grid-row-cell-over-background-color`


### $grid-cell-special-selected-border-color

**Type:** color

The border-color of "special" cells when the row is selected using a Row Selection Model. ...

The border-color of "special" cells when the row is selected using a Row Selection Model. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the selected row border color is determined by {#$grid-row-cell-selected-border-color}. Defaults to: `$grid-row-cell-border-color`


### $grid-empty-background-color

**Type:** color

The background color of the grid body when the grid contains no data. ...

The background color of the grid body when the grid contains no data. Defaults to: `$panel-body-background-color`


### $grid-empty-color

**Type:** color

The text color of the emptyText in the grid body when the grid contains no data. ...

The text color of the emptyText in the grid body when the grid contains no data. Defaults to: `#808080`


### $grid-empty-font-family

**Type:** number

The font-family of the emptyText in the grid body when the grid contains no data. ...

The font-family of the emptyText in the grid body when the grid contains no data. Defaults to: `$font-family`


### $grid-empty-font-size

**Type:** number

The font-size of the emptyText in the grid body when the grid contains no data. ...

The font-size of the emptyText in the grid body when the grid contains no data. Defaults to: `$grid-row-cell-font-size`


### $grid-empty-font-weight

**Type:** number

The font-weight of the emptyText in the grid body when the grid contains no data. ...

The font-weight of the emptyText in the grid body when the grid contains no data. Defaults to: `normal`


### $grid-empty-padding

**Type:** number

The amount of padding to apply to the grid body when the grid contains no data. ...

The amount of padding to apply to the grid body when the grid contains no data. Defaults to: `10px`


### $grid-lockable-separator-border-style

**Type:** string

The border-style of the border between the locked views ...

The border-style of the border between the locked views Defaults to: `solid`


### $grid-lockable-separator-border-width

**Type:** number

The width of the border between the locked views ...

The width of the border between the locked views Defaults to: `1px`


### $grid-no-row-lines-show-focus-border

**Type:** boolean

True to show the focus border when a row is focused even if the grid has no rowLines. ...

True to show the focus border when a row is focused even if the grid has no rowLines. Defaults to: `false`


### $grid-resize-marker-background-color

**Type:** color

The color of the resize markers that display when dragging a column border to resize the column ...

The color of the resize markers that display when dragging a column border to resize the column Defaults to: `#0f0f0f`


### $grid-row-cell-alt-background-color

**Type:** color

The background-color color of odd-numbered rows when the table view is configured with stripeRows: true. ...

The background-color color of odd-numbered rows when the table view is configured with `stripeRows: true`. Defaults to: `darken ( $grid-row-cell-background-color , 2 )`


### $grid-row-cell-background-color

**Type:** color

The background-color of the grid cells ...

The background-color of the grid cells Defaults to: `#fff`


### $grid-row-cell-border-color

**Type:** color

The border-color of row/column borders. ...

The border-color of row/column borders. Can be specified as a single color, or as a list of colors containing the row border color followed by the column border color. Defaults to: `#ededed`


### $grid-row-cell-border-style

**Type:** string

The border-style of the row/column borders. ...

The border-style of the row/column borders. Defaults to: `solid`


### $grid-row-cell-border-width

**Type:** number

The border-width of the row and column borders. ...

The border-width of the row and column borders. Defaults to: `1px`


### $grid-row-cell-color

**Type:** color

The color of the text in the grid cells ...

The color of the text in the grid cells Defaults to: `null`


### $grid-row-cell-focus-background-color

**Type:** color

The background-color of the focused row ...

The background-color of the focused row Defaults to: `$grid-row-cell-background-color`


### $grid-row-cell-focus-border-color

**Type:** color

The border-color of the focused row ...

The border-color of the focused row Defaults to: `#808080`


### $grid-row-cell-focus-border-style

**Type:** string

The border-style of the focused row ...

The border-style of the focused row Defaults to: `dotted`


### $grid-row-cell-focus-color

**Type:** color

The text color of the focused row ...

The text color of the focused row Defaults to: `$grid-row-cell-color`


### $grid-row-cell-font-family

**Type:** string

The font-family of the text in the grid cells ...

The font-family of the text in the grid cells Defaults to: `$font-family`


### $grid-row-cell-font-size

**Type:** number

The font size of the text in the grid cells ...

The font size of the text in the grid cells Defaults to: `$font-size`


### $grid-row-cell-font-weight

**Type:** string

The font-weight of the text in the grid cells ...

The font-weight of the text in the grid cells Defaults to: `normal`


### $grid-row-cell-line-height

**Type:** Object

var {number} $grid-row-cell-line-height The line-height of the text inside the grid cells. ...

var {number} $grid-row-cell-line-height The line-height of the text inside the grid cells. Defaults to: `round ( $grid-row-cell-font-size * 1.15 )`


### $grid-row-cell-over-background-color

**Type:** color

The background-color of the hovered row ...

The background-color of the hovered row Defaults to: `#ddd`


### $grid-row-cell-over-border-color

**Type:** color

The border-color of the hovered row ...

The border-color of the hovered row Defaults to: `$grid-row-cell-border-color`


### $grid-row-cell-over-border-style

**Type:** string

The border-style of the hovered row ...

The border-style of the hovered row Defaults to: `solid`


### $grid-row-cell-over-color

**Type:** color

The text color of the hovered row ...

The text color of the hovered row Defaults to: `$grid-row-cell-color`


### $grid-row-cell-selected-background-color

**Type:** color

The background-color of the selected row ...

The background-color of the selected row Defaults to: `#ccc`


### $grid-row-cell-selected-border-color

**Type:** color

The border-color of the selected row ...

The border-color of the selected row Defaults to: `$grid-row-cell-border-color`


### $grid-row-cell-selected-border-style

**Type:** string

The border-style of the selected row ...

The border-style of the selected row Defaults to: `solid`


### $grid-row-cell-selected-color

**Type:** color

The text color of the selected row ...

The text color of the selected row Defaults to: `$grid-row-cell-color`


### $include-panel-default-framed-ui

**Type:** boolean

True to include the "default-framed" panel UI ...

True to include the "default-framed" panel UI Defaults to: `$include-default-uis`


### $include-panel-default-ui

**Type:** boolean

True to include the "default" panel UI ...

True to include the "default" panel UI Defaults to: `$include-default-uis`


### $panel-background-stretch-bottom

**Type:** string

The direction to strech the background-gradient of bottom docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of bottom docked Headers when slicing images for IE using Sencha Cmd Defaults to: `top`


### $panel-background-stretch-left

**Type:** string

The direction to strech the background-gradient of left docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of left docked Headers when slicing images for IE using Sencha Cmd Defaults to: `right`


### $panel-background-stretch-right

**Type:** string

The direction to strech the background-gradient of right docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of right docked Headers when slicing images for IE using Sencha Cmd Defaults to: `left`


### $panel-background-stretch-top

**Type:** string

The direction to strech the background-gradient of top docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of top docked Headers when slicing images for IE using Sencha Cmd Defaults to: `bottom`


### $panel-base-color

**Type:** color

The base color of Panels ...

The base color of Panels Defaults to: `$base-color`


### $panel-body-background-color

**Type:** color

The default body background-color of Panels ...

The default body background-color of Panels Defaults to: `#fff`


### $panel-body-border-color

**Type:** color

The default border-color of the Panel body ...

The default border-color of the Panel body Defaults to: `$panel-border-color`


### $panel-body-border-style

**Type:** string

The default border-style of Panels ...

The default border-style of Panels Defaults to: `solid`


### $panel-body-border-width

**Type:** number

The default border-width of the Panel body ...

The default border-width of the Panel body Defaults to: `1px`


### $panel-body-color

**Type:** color

The default color of text inside a Panel's body ...

The default color of text inside a Panel's body Defaults to: `#000`


### $panel-body-font-size

**Type:** number

The default font-size of the Panel body ...

The default font-size of the Panel body Defaults to: `$font-size`


### $panel-body-font-weight

**Type:** string

The default font-weight of the Panel body ...

The default font-weight of the Panel body Defaults to: `normal`


### $panel-border-color

**Type:** color

The default border-color of Panels ...

The default border-color of Panels Defaults to: `$panel-base-color`


### $panel-border-width

**Type:** number

The default border-width of Panels ...

The default border-width of Panels Defaults to: `1px`


### $panel-frame-background-color

**Type:** color

The background-color of framed Panels ...

The background-color of framed Panels Defaults to: `#fff`


### $panel-frame-base-color

**Type:** color

The base color of the framed Panels ...

The base color of the framed Panels Defaults to: `$panel-base-color`


### $panel-frame-body-border-width

**Type:** number

The border-width of the body element of framed Panels ...

The border-width of the body element of framed Panels Defaults to: `1px`


### $panel-frame-border-color

**Type:** color

The border-color of framed Panels ...

The border-color of framed Panels Defaults to: `$panel-border-color`


### $panel-frame-border-radius

**Type:** number

The border-radius of framed Panels ...

The border-radius of framed Panels Defaults to: `4px`


### $panel-frame-border-style

**Type:** string

The border-style of framed Panels ...

The border-style of framed Panels Defaults to: `solid`


### $panel-frame-border-width

**Type:** number

The border-width of framed Panels ...

The border-width of framed Panels Defaults to: `1px`


### $panel-frame-header-border-width

**Type:** number

The border-width of framed Panel Headers ...

The border-width of framed Panel Headers Defaults to: `$panel-header-border-width`


### $panel-frame-header-inner-border-color

**Type:** color

The inner border-color of framed Panel Headers ...

The inner border-color of framed Panel Headers Defaults to: `#fff`


### $panel-frame-header-inner-border-width

**Type:** number

The inner border-width of framed Panel Headers ...

The inner border-width of framed Panel Headers Defaults to: `0`


### $panel-frame-header-padding

**Type:** number/list

The padding of framed Panel Headers ...

The padding of framed Panel Headers Defaults to: `$panel-header-padding`


### $panel-frame-padding

**Type:** number

The padding of framed Panels ...

The padding of framed Panels Defaults to: `4px`


### $panel-ghost-opacity

**Type:** number

The opacity of ghost Panels while dragging ...

The opacity of ghost Panels while dragging Defaults to: `0.50`


### $panel-header-background-color

**Type:** color

The background-color of the Panel Header ...

The background-color of the Panel Header Defaults to: `$panel-base-color`


### $panel-header-background-gradient

**Type:** string/list

The background-gradient of the Panel Header. ...

The background-gradient of the Panel Header. Can be either the name of a predefined gradient or a list of color stops. Used as the `$type` parameter for Global_CSS.background-gradient. Defaults to: `null`


### $panel-header-border-color

**Type:** color

The border-color of the Panel Header ...

The border-color of the Panel Header Defaults to: `$panel-border-color`


### $panel-header-border-style

**Type:** string

The border-style of Panel Headers ...

The border-style of Panel Headers Defaults to: `solid`


### $panel-header-border-width

**Type:** number

The border-width of Panel Headers ...

The border-width of Panel Headers Defaults to: `$panel-border-width`


### $panel-header-color

**Type:** color

The text color of the Panel Header ...

The text color of the Panel Header Defaults to: `$color`


### $panel-header-font-family

**Type:** string

The font-family of Panel Headers ...

The font-family of Panel Headers Defaults to: `$font-family`


### $panel-header-font-size

**Type:** number

The font-size of Panel Headers ...

The font-size of Panel Headers Defaults to: `$font-size`


### $panel-header-font-weight

**Type:** string

The font-weight of Panel Headers ...

The font-weight of Panel Headers Defaults to: `bold`


### $panel-header-glyph-color

**Type:** color

The color of the Panel Header glyph icon ...

The color of the Panel Header glyph icon Defaults to: `$panel-header-color`


### $panel-header-glyph-opacity

**Type:** number

The opacity of the Panel Header glyph icon ...

The opacity of the Panel Header glyph icon Defaults to: `.5`


### $panel-header-icon-background-position

**Type:** list

The background-position of the Panel Header icon ...

The background-position of the Panel Header icon Defaults to: `center center`


### $panel-header-icon-height

**Type:** number

The height of the Panel Header icon ...

The height of the Panel Header icon Defaults to: `16px`


### $panel-header-icon-spacing

**Type:** number

The space between the Panel Header icon and text ...

The space between the Panel Header icon and text Defaults to: `4px`


### $panel-header-icon-width

**Type:** number

The width of the Panel Header icon ...

The width of the Panel Header icon Defaults to: `16px`


### $panel-header-inner-border-color

**Type:** color

The inner border-color of the Panel Header ...

The inner border-color of the Panel Header Defaults to: `#fff`


### $panel-header-inner-border-width

**Type:** number

The inner border-width of the Panel Header ...

The inner border-width of the Panel Header Defaults to: `0`


### $panel-header-line-height

**Type:** number

The line-height of Panel Headers ...

The line-height of Panel Headers Defaults to: `16px`


### $panel-header-padding

**Type:** number/list

The padding of Panel Headers ...

The padding of Panel Headers Defaults to: `4px 5px`


### $panel-header-text-padding

**Type:** number/list

The padding of the Panel Header's text element ...

The padding of the Panel Header's text element Defaults to: `0`


### $panel-header-text-transform

**Type:** string

The text-transform of Panel Headers ...

The text-transform of Panel Headers Defaults to: `none`


### $panel-include-border-management-rules

**Type:** boolean

True to include neptune style border management rules. ...

True to include neptune style border management rules. Defaults to: `false`


### $panel-tool-background-image

**Type:** string

The background sprite to use for Panel Tools ...

The background sprite to use for Panel Tools Defaults to: `'tools/tool-sprites'`


### $panel-tool-spacing

**Type:** number

The space between the Panel Tools ...

The space between the Panel Tools Defaults to: `4px`


### $panel-wrap-border-color

**Type:** color

The color to apply to the border that wraps the body and docked items in a framed panel. ...

The color to apply to the border that wraps the body and docked items in a framed panel. The presence of the wrap border in a framed panel is controlled by the border config. Only applicable when `$panel-include-border-management-rules` is `true`. Defaults to: `$panel-border-color`


### $panel-wrap-border-width

**Type:** number

The width to apply to the border that wraps the body and docked items in a framed panel. ...

The width to apply to the border that wraps the body and docked items in a framed panel. The presence of the wrap border in a framed panel is controlled by the border config. Only applicable when `$panel-include-border-management-rules` is `true`. Defaults to: `1px`


### extjs-panel-ui

Creates a visual theme for a Panel ...

Creates a visual theme for a Panel $ui-label : stringThe name of the UI being created. Can not included spaces or special punctuation (used in CSS class names).


## Events

### activate

Fires after a Component has been visually activated. ...

Fires after a Component has been visually activated.

**Parameters:** this : Ext.Component


### add

Fires after any Ext.Component is added or inserted into the container. ...

Fires after any Ext.Component is added or inserted into the container. **This event bubbles:** 'add' will also be fired when Component is added to any of the child containers or their childern or ... Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### added

Fires after a Component had been added to a Container. ...

Fires after a Component had been added to a Container. Available since: 3.4.0

**Parameters:** this : Ext.Component


### afterlayout

Fires when the components in this container are arranged by the associated layout manager. ...

Fires when the components in this container are arranged by the associated layout manager. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### afterrender

Fires after the component rendering is finished. ...

Fires after the component rendering is finished. The `afterrender` event is fired after this Component has been rendered, been postprocessed by any `afterRender` method defined for the Component. Available since: 3.4.0

**Parameters:** this : Ext.Component


### beforeactivate

Fires before a Component has been visually activated. ...

Fires before a Component has been visually activated. Returning `false` from an event listener can prevent the activate from occurring.

**Parameters:** this : Ext.Component


### beforeadd

Fires before any Ext.Component is added or inserted into the container. ...

Fires before any Ext.Component is added or inserted into the container. A handler can return false to cancel the add. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### beforecellclick

Fired before the cell click is processed. ...

Fired before the cell click is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellcontextmenu

Fired before the cell right click is processed. ...

Fired before the cell right click is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecelldblclick

Fired before the cell double click is processed. ...

Fired before the cell double click is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellkeydown

Fired before the cell key down is processed. ...

Fired before the cell key down is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellmousedown

Fired before the cell mouse down is processed. ...

Fired before the cell mouse down is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforecellmouseup

Fired before the cell mouse up is processed. ...

Fired before the cell mouse up is processed. Return false to cancel the default action.

**Parameters:** this : Ext.view.Table


### beforeclose

Fires before the user closes the panel. ...

Fires before the user closes the panel. Return false from any listener to stop the close event being fired

**Parameters:** panel : Ext.panel.PanelThe Panel object


### beforecollapse

Fires before this panel is collapsed. ...

Fires before this panel is collapsed. Return false to prevent the collapse.

**Parameters:** p : Ext.panel.PanelThe Panel being collapsed.


### beforecontainerclick

Fires before the click event on the container is processed. ...

Fires before the click event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainercontextmenu

Fires before the contextmenu event on the container is processed. ...

Fires before the contextmenu event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainerdblclick

Fires before the dblclick event on the container is processed. ...

Fires before the dblclick event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermousedown

Fires before the mousedown event on the container is processed. ...

Fires before the mousedown event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermouseout

Fires before the mouseout event on the container is processed. ...

Fires before the mouseout event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermouseover

Fires before the mouseover event on the container is processed. ...

Fires before the mouseover event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforecontainermouseup

Fires before the mouseup event on the container is processed. ...

Fires before the mouseup event on the container is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforedeactivate

Fires before a Component has been visually deactivated. ...

Fires before a Component has been visually deactivated. Returning `false` from an event listener can prevent the deactivate from occurring.

**Parameters:** this : Ext.Component


### beforedeselect

Fired before a record is deselected. ...

Fired before a record is deselected. If any listener returns false, the deselection is cancelled.

**Parameters:** this : Ext.selection.RowModel


### beforedestroy

Fires before the component is destroyed. ...

Fires before the component is destroyed. Return `false` from an event handler to stop the destroy. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeexpand

Fires before this panel is expanded. ...

Fires before this panel is expanded. Return false to prevent the expand.

**Parameters:** p : Ext.panel.PanelThe Panel being expanded.


### beforehide

Fires before the component is hidden when calling the hide method. ...

Fires before the component is hidden when calling the hide method. Return `false` from an event handler to stop the hide. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeitemclick

Fires before the click event on an item is processed. ...

Fires before the click event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemcontextmenu

Fires before the contextmenu event on an item is processed. ...

Fires before the contextmenu event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemdblclick

Fires before the dblclick event on an item is processed. ...

Fires before the dblclick event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmousedown

Fires before the mousedown event on an item is processed. ...

Fires before the mousedown event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmouseenter

Fires before the mouseenter event on an item is processed. ...

Fires before the mouseenter event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmouseleave

Fires before the mouseleave event on an item is processed. ...

Fires before the mouseleave event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeitemmouseup

Fires before the mouseup event on an item is processed. ...

Fires before the mouseup event on an item is processed.

**Parameters:** this : Ext.view.View

**Returns:** false to cancel the default action.


### beforeremove

Fires before any Ext.Component is removed from the container. ...

Fires before any Ext.Component is removed from the container. A handler can return false to cancel the remove. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### beforerender

Fires before the component is rendered. ...

Fires before the component is rendered. Return `false` from an event handler to stop the render. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeselect

Fired before a record is selected. ...

Fired before a record is selected. If any listener returns false, the selection is cancelled.

**Parameters:** this : Ext.selection.RowModel


### beforeshow

Fires before the component is shown when calling the show method. ...

Fires before the component is shown when calling the show method. Return `false` from an event handler to stop the show. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforestaterestore

Fires before the state of the object is restored. ...

Fires before the state of the object is restored. Return false from an event handler to stop the restore.

**Parameters:** this : Ext.state.Stateful


### beforestatesave

Fires before the state of the object is saved to the configured state provider. ...

Fires before the state of the object is saved to the configured state provider. Return false to stop the save.

**Parameters:** this : Ext.state.Stateful


### blur

Fires when this Component loses focus. ...

Fires when this Component loses focus.

**Parameters:** this : Ext.Component


### boxready

Fires one time - after the component has been laid out for the first time at its initial size. ...

Fires *one time* - after the component has been laid out for the first time at its initial size.

**Parameters:** this : Ext.Component


### cellclick

Fired when table cell is clicked. ...

Fired when table cell is clicked.

**Parameters:** this : Ext.view.Table


### cellcontextmenu

Fired when table cell is right clicked. ...

Fired when table cell is right clicked.

**Parameters:** this : Ext.view.Table


### celldblclick

Fired when table cell is double clicked. ...

Fired when table cell is double clicked.

**Parameters:** this : Ext.view.Table


### cellkeydown

Fired when the keydown event is captured on the cell. ...

Fired when the keydown event is captured on the cell.

**Parameters:** this : Ext.view.Table


### cellmousedown

Fired when the mousedown event is captured on the cell. ...

Fired when the mousedown event is captured on the cell.

**Parameters:** this : Ext.view.Table


### cellmouseup

Fired when the mouseup event is captured on the cell. ...

Fired when the mouseup event is captured on the cell.

**Parameters:** this : Ext.view.Table


### close

Fires when the user closes the panel. ...

Fires when the user closes the panel.

**Parameters:** panel : Ext.panel.PanelThe Panel object


### collapse

Fires after this Panel has collapsed. ...

Fires after this Panel has collapsed.

**Parameters:** p : Ext.panel.PanelThe Panel that has been collapsed.


### columnhide

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnmove

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnresize

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnschanged

Fired after the columns change in any way, when a column has been hidden or shown, or when a column is added to or re...

Fired after the columns change in any way, when a column has been hidden or shown, or when a column is added to or removed from this header container.

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### columnshow

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### containerclick

Fires when the container is clicked. ...

Fires when the container is clicked.

**Parameters:** this : Ext.view.View


### containercontextmenu

Fires when the container is right clicked. ...

Fires when the container is right clicked.

**Parameters:** this : Ext.view.View


### containerdblclick

Fires when the container is double clicked. ...

Fires when the container is double clicked.

**Parameters:** this : Ext.view.View


### containermouseout

Fires when you move the mouse out of the container. ...

Fires when you move the mouse out of the container.

**Parameters:** this : Ext.view.View


### containermouseover

Fires when you move the mouse over the container. ...

Fires when you move the mouse over the container.

**Parameters:** this : Ext.view.View


### containermouseup

Fires when there is a mouse up on the container ...

Fires when there is a mouse up on the container

**Parameters:** this : Ext.view.View


### deactivate

Fires after a Component has been visually deactivated. ...

Fires after a Component has been visually deactivated.

**Parameters:** this : Ext.Component


### deselect

Fired after a record is deselected ...

Fired after a record is deselected

**Parameters:** this : Ext.selection.RowModel


### destroy

Fires after the component is destroyed. ...

Fires after the component is destroyed. Available since: 1.1.0

**Parameters:** this : Ext.Component


### disable

Fires after the component is disabled. ...

Fires after the component is disabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### dockedadd

Fires when any Ext.Component is added or inserted as a docked item. ...

Fires when any Ext.Component is added or inserted as a docked item.

**Parameters:** this : Ext.panel.Panel


### dockedremove

Fires when any Ext.Component is removed from the docked items. ...

Fires when any Ext.Component is removed from the docked items.

**Parameters:** this : Ext.panel.Panel


### enable

Fires after the component is enabled. ...

Fires after the component is enabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### expand

Fires after this Panel has expanded. ...

Fires after this Panel has expanded.

**Parameters:** p : Ext.panel.PanelThe Panel that has been expanded.


### filterchange

Fired whenever the filter set changes. ...

Fired whenever the filter set changes.

**Parameters:** store : Ext.data.StoreThe store.


### float

Fires after a collapsed Panel has been "floated" by clicking on it's header. ...

Fires after a collapsed Panel has been "floated" by clicking on it's header. Only applicable when the Panel is an item in a Border Layout.

**Parameters:** eOpts : ObjectThe options object passed to Ext.util.Observable.addListener.


### focus

Fires when this Component receives focus. ...

Fires when this Component receives focus.

**Parameters:** this : Ext.Component


### glyphchange

Fired when the Panel glyph has been changed by the setGlyph method. ...

Fired when the Panel glyph has been changed by the setGlyph method.

**Parameters:** this : Ext.panel.Panel


### headerclick

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### headercontextmenu

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### headertriggerclick

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### hide

Fires after the component is hidden. ...

Fires after the component is hidden. Fires after the component is hidden when calling the hide method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### iconchange

Fires after the Panel icon has been set or changed. ...

Fires after the Panel icon has been set or changed.

**Parameters:** p : Ext.panel.PanelThe Panel which has the icon changed.


### iconclschange

Fires after the Panel iconCls has been set or changed. ...

Fires after the Panel iconCls has been set or changed.

**Parameters:** p : Ext.panel.PanelThe Panel which has the iconCls changed.


### itemclick

Fires when an item is clicked. ...

Fires when an item is clicked.

**Parameters:** this : Ext.view.View


### itemcontextmenu

Fires when an item is right clicked. ...

Fires when an item is right clicked.

**Parameters:** this : Ext.view.View


### itemdblclick

Fires when an item is double clicked. ...

Fires when an item is double clicked.

**Parameters:** this : Ext.view.View


### itemmousedown

Fires when there is a mouse down on an item ...

Fires when there is a mouse down on an item

**Parameters:** this : Ext.view.View


### itemmouseenter

Fires when the mouse enters an item. ...

Fires when the mouse enters an item.

**Parameters:** this : Ext.view.View


### itemmouseleave

Fires when the mouse leaves an item. ...

Fires when the mouse leaves an item.

**Parameters:** this : Ext.view.View


### itemmouseup

Fires when there is a mouse up on an item ...

Fires when there is a mouse up on an item

**Parameters:** this : Ext.view.View


### lockcolumn

Fires when a column is locked. ...

Fires when a column is locked.

**Parameters:** this : Ext.grid.PanelThe gridpanel.


### move

Fires after the component is moved. ...

Fires after the component is moved.

**Parameters:** this : Ext.Component


### processcolumns

Fires when the configured (or reconfigured) column set is split into two depending on the locked flag. ...

Fires when the configured (or **reconfigured**) column set is split into two depending on the locked flag.

**Parameters:** lockedColumns : Ext.grid.column.Column[]The locked columns.


### remove

Fires after any Ext.Component is removed from the container. ...

Fires after any Ext.Component is removed from the container. **This event bubbles:** 'remove' will also be fired when Component is removed from any of the child containers or their children or ... Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### removed

Fires when a component is removed from an Ext.container.Container ...

Fires when a component is removed from an Ext.container.Container Available since: 3.4.0

**Parameters:** this : Ext.Component


### render

Fires after the component markup is rendered. ...

Fires after the component markup is rendered. Available since: 1.1.0

**Parameters:** this : Ext.Component


### resize

Fires after the component is resized. ...

Fires after the component is resized. Note that this does *not* fire when the component is first laid out at its initial size. To hook that point in the life cycle, use the boxready event.

**Parameters:** this : Ext.Component


### select

Fired after a record is selected ...

Fired after a record is selected

**Parameters:** this : Ext.selection.RowModel


### selectionchange

Fired after a selection change has occurred ...

Fired after a selection change has occurred

**Parameters:** this : Ext.selection.Model


### show

Fires after the component is shown when calling the show method. ...

Fires after the component is shown when calling the show method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### sortchange

...

**Parameters:** ct : Ext.grid.header.ContainerThe grid's header Container which encapsulates all column headers.


### staterestore

Fires after the state of the object is restored. ...

Fires after the state of the object is restored.

**Parameters:** this : Ext.state.Stateful


### statesave

Fires after the state of the object is saved to the configured state provider. ...

Fires after the state of the object is saved to the configured state provider.

**Parameters:** this : Ext.state.Stateful


### titlechange

Fires after the Panel title has been set or changed. ...

Fires after the Panel title has been set or changed.

**Parameters:** p : Ext.panel.Panelthe Panel which has been resized.


### unfloat

Fires after a "floated" Panel has returned to it's collapsed state as a result of the mouse leaving the Panel. ...

Fires after a "floated" Panel has returned to it's collapsed state as a result of the mouse leaving the Panel. Only applicable when the Panel is an item in a Border Layout.

**Parameters:** eOpts : ObjectThe options object passed to Ext.util.Observable.addListener.


### unlockcolumn

Fires when a column is unlocked. ...

Fires when a column is unlocked.

**Parameters:** this : Ext.grid.PanelThe gridpanel.


### viewready

Fires when the grid view is available (use this for selecting a default row). ...

Fires when the grid view is available (use this for selecting a default row).

**Parameters:** this : Ext.panel.Table


### $border-width-threshold

**Type:** $border-width-threshold

The maximum width a Panel's border can be before resizer handles are embedded into the borders using negative absolut...

The maximum width a Panel's border can be before resizer handles are embedded into the borders using negative absolute positions. This defaults to 2, so that in the classic theme which uses 1 pixel borders, resize handles are in the content area within the border as they always have been. In the Neptune theme, the handles are embedded into the 5 pixel wide borders of any framed panel. Defaults to: `2`


### $grid-body-background-color

**Type:** color

The background-color of the grid body ...

The background-color of the grid body Defaults to: `$panel-body-background-color`


### $grid-body-border-color

**Type:** color

The border-color of the grid body ...

The border-color of the grid body Defaults to: `$panel-body-border-color`


### $grid-body-border-style

**Type:** string

The border-style of the grid body border ...

The border-style of the grid body border Defaults to: `$panel-body-border-style`


### $grid-body-border-width

**Type:** number

The border-width of the grid body border ...

The border-width of the grid body border Defaults to: `$panel-body-border-width`


### $grid-cell-inner-padding

**Type:** number

The amount of padding to apply to the grid cell's inner div element ...

The amount of padding to apply to the grid cell's inner div element Defaults to: `3px 6px`


### $grid-cell-inner-text-overflow

**Type:** string

The type of text-overflow to use on the grid cell's inner div element ...

The type of text-overflow to use on the grid cell's inner div element Defaults to: `ellipsis`


### $grid-cell-selected-background-color

**Type:** color

The background-color of a selected cell when using a Cell Selection Model. ...

The background-color of a selected cell when using a Cell Selection Model. Defaults to: `$grid-row-cell-selected-background-color`


### $grid-cell-selected-color

**Type:** color

The text color of a selected cell when using a Cell Selection Model. ...

The text color of a selected cell when using a Cell Selection Model. Defaults to: `$grid-row-cell-selected-color`


### $grid-cell-special-background-color

**Type:** color

The background-color of "special" cells. ...

The background-color of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `$grid-row-cell-background-color`


### $grid-cell-special-background-gradient

**Type:** string

The background-gradient to use for "special" cells. ...

The background-gradient to use for "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `null`


### $grid-cell-special-border-color

**Type:** color

The border-color of "special" cells. ...

The border-color of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border color is determined by {#$grid-row-cell-border-color}. Defaults to: `$grid-row-cell-border-color`


### $grid-cell-special-border-style

**Type:** string

The border-style of "special" cells. ...

The border-style of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border style is determined by {#$grid-row-cell-border-style}. Defaults to: `$grid-row-cell-border-style`


### $grid-cell-special-border-width

**Type:** number

The border-width of "special" cells. ...

The border-width of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border width is determined by {#$grid-row-cell-border-width}. Defaults to: `$grid-row-cell-border-width`


### $grid-cell-special-over-background-color

**Type:** color

The background-color of "special" cells when the row is hovered. ...

The background-color of "special" cells when the row is hovered. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `$grid-row-cell-over-background-color`


### $grid-cell-special-selected-border-color

**Type:** color

The border-color of "special" cells when the row is selected using a Row Selection Model. ...

The border-color of "special" cells when the row is selected using a Row Selection Model. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the selected row border color is determined by {#$grid-row-cell-selected-border-color}. Defaults to: `$grid-row-cell-border-color`


### $grid-empty-background-color

**Type:** color

The background color of the grid body when the grid contains no data. ...

The background color of the grid body when the grid contains no data. Defaults to: `$panel-body-background-color`


### $grid-empty-color

**Type:** color

The text color of the emptyText in the grid body when the grid contains no data. ...

The text color of the emptyText in the grid body when the grid contains no data. Defaults to: `#808080`


### $grid-empty-font-family

**Type:** number

The font-family of the emptyText in the grid body when the grid contains no data. ...

The font-family of the emptyText in the grid body when the grid contains no data. Defaults to: `$font-family`


### $grid-empty-font-size

**Type:** number

The font-size of the emptyText in the grid body when the grid contains no data. ...

The font-size of the emptyText in the grid body when the grid contains no data. Defaults to: `$grid-row-cell-font-size`


### $grid-empty-font-weight

**Type:** number

The font-weight of the emptyText in the grid body when the grid contains no data. ...

The font-weight of the emptyText in the grid body when the grid contains no data. Defaults to: `normal`


### $grid-empty-padding

**Type:** number

The amount of padding to apply to the grid body when the grid contains no data. ...

The amount of padding to apply to the grid body when the grid contains no data. Defaults to: `10px`


### $grid-lockable-separator-border-style

**Type:** string

The border-style of the border between the locked views ...

The border-style of the border between the locked views Defaults to: `solid`


### $grid-lockable-separator-border-width

**Type:** number

The width of the border between the locked views ...

The width of the border between the locked views Defaults to: `1px`


### $grid-no-row-lines-show-focus-border

**Type:** boolean

True to show the focus border when a row is focused even if the grid has no rowLines. ...

True to show the focus border when a row is focused even if the grid has no rowLines. Defaults to: `false`


### $grid-resize-marker-background-color

**Type:** color

The color of the resize markers that display when dragging a column border to resize the column ...

The color of the resize markers that display when dragging a column border to resize the column Defaults to: `#0f0f0f`


### $grid-row-cell-alt-background-color

**Type:** color

The background-color color of odd-numbered rows when the table view is configured with stripeRows: true. ...

The background-color color of odd-numbered rows when the table view is configured with `stripeRows: true`. Defaults to: `darken ( $grid-row-cell-background-color , 2 )`


### $grid-row-cell-background-color

**Type:** color

The background-color of the grid cells ...

The background-color of the grid cells Defaults to: `#fff`


### $grid-row-cell-border-color

**Type:** color

The border-color of row/column borders. ...

The border-color of row/column borders. Can be specified as a single color, or as a list of colors containing the row border color followed by the column border color. Defaults to: `#ededed`


### $grid-row-cell-border-style

**Type:** string

The border-style of the row/column borders. ...

The border-style of the row/column borders. Defaults to: `solid`


### $grid-row-cell-border-width

**Type:** number

The border-width of the row and column borders. ...

The border-width of the row and column borders. Defaults to: `1px`


### $grid-row-cell-color

**Type:** color

The color of the text in the grid cells ...

The color of the text in the grid cells Defaults to: `null`


### $grid-row-cell-focus-background-color

**Type:** color

The background-color of the focused row ...

The background-color of the focused row Defaults to: `$grid-row-cell-background-color`


### $grid-row-cell-focus-border-color

**Type:** color

The border-color of the focused row ...

The border-color of the focused row Defaults to: `#808080`


### $grid-row-cell-focus-border-style

**Type:** string

The border-style of the focused row ...

The border-style of the focused row Defaults to: `dotted`


### $grid-row-cell-focus-color

**Type:** color

The text color of the focused row ...

The text color of the focused row Defaults to: `$grid-row-cell-color`


### $grid-row-cell-font-family

**Type:** string

The font-family of the text in the grid cells ...

The font-family of the text in the grid cells Defaults to: `$font-family`


### $grid-row-cell-font-size

**Type:** number

The font size of the text in the grid cells ...

The font size of the text in the grid cells Defaults to: `$font-size`


### $grid-row-cell-font-weight

**Type:** string

The font-weight of the text in the grid cells ...

The font-weight of the text in the grid cells Defaults to: `normal`


### $grid-row-cell-line-height

**Type:** Object

var {number} $grid-row-cell-line-height The line-height of the text inside the grid cells. ...

var {number} $grid-row-cell-line-height The line-height of the text inside the grid cells. Defaults to: `round ( $grid-row-cell-font-size * 1.15 )`


### $grid-row-cell-over-background-color

**Type:** color

The background-color of the hovered row ...

The background-color of the hovered row Defaults to: `#ddd`


### $grid-row-cell-over-border-color

**Type:** color

The border-color of the hovered row ...

The border-color of the hovered row Defaults to: `$grid-row-cell-border-color`


### $grid-row-cell-over-border-style

**Type:** string

The border-style of the hovered row ...

The border-style of the hovered row Defaults to: `solid`


### $grid-row-cell-over-color

**Type:** color

The text color of the hovered row ...

The text color of the hovered row Defaults to: `$grid-row-cell-color`


### $grid-row-cell-selected-background-color

**Type:** color

The background-color of the selected row ...

The background-color of the selected row Defaults to: `#ccc`


### $grid-row-cell-selected-border-color

**Type:** color

The border-color of the selected row ...

The border-color of the selected row Defaults to: `$grid-row-cell-border-color`


### $grid-row-cell-selected-border-style

**Type:** string

The border-style of the selected row ...

The border-style of the selected row Defaults to: `solid`


### $grid-row-cell-selected-color

**Type:** color

The text color of the selected row ...

The text color of the selected row Defaults to: `$grid-row-cell-color`


### $include-panel-default-framed-ui

**Type:** boolean

True to include the "default-framed" panel UI ...

True to include the "default-framed" panel UI Defaults to: `$include-default-uis`


### $include-panel-default-ui

**Type:** boolean

True to include the "default" panel UI ...

True to include the "default" panel UI Defaults to: `$include-default-uis`


### $panel-background-stretch-bottom

**Type:** string

The direction to strech the background-gradient of bottom docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of bottom docked Headers when slicing images for IE using Sencha Cmd Defaults to: `top`


### $panel-background-stretch-left

**Type:** string

The direction to strech the background-gradient of left docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of left docked Headers when slicing images for IE using Sencha Cmd Defaults to: `right`


### $panel-background-stretch-right

**Type:** string

The direction to strech the background-gradient of right docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of right docked Headers when slicing images for IE using Sencha Cmd Defaults to: `left`


### $panel-background-stretch-top

**Type:** string

The direction to strech the background-gradient of top docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of top docked Headers when slicing images for IE using Sencha Cmd Defaults to: `bottom`


### $panel-base-color

**Type:** color

The base color of Panels ...

The base color of Panels Defaults to: `$base-color`


### $panel-body-background-color

**Type:** color

The default body background-color of Panels ...

The default body background-color of Panels Defaults to: `#fff`


### $panel-body-border-color

**Type:** color

The default border-color of the Panel body ...

The default border-color of the Panel body Defaults to: `$panel-border-color`


### $panel-body-border-style

**Type:** string

The default border-style of Panels ...

The default border-style of Panels Defaults to: `solid`


### $panel-body-border-width

**Type:** number

The default border-width of the Panel body ...

The default border-width of the Panel body Defaults to: `1px`


### $panel-body-color

**Type:** color

The default color of text inside a Panel's body ...

The default color of text inside a Panel's body Defaults to: `#000`


### $panel-body-font-size

**Type:** number

The default font-size of the Panel body ...

The default font-size of the Panel body Defaults to: `$font-size`


### $panel-body-font-weight

**Type:** string

The default font-weight of the Panel body ...

The default font-weight of the Panel body Defaults to: `normal`


### $panel-border-color

**Type:** color

The default border-color of Panels ...

The default border-color of Panels Defaults to: `$panel-base-color`


### $panel-border-width

**Type:** number

The default border-width of Panels ...

The default border-width of Panels Defaults to: `1px`


### $panel-frame-background-color

**Type:** color

The background-color of framed Panels ...

The background-color of framed Panels Defaults to: `#fff`


### $panel-frame-base-color

**Type:** color

The base color of the framed Panels ...

The base color of the framed Panels Defaults to: `$panel-base-color`


### $panel-frame-body-border-width

**Type:** number

The border-width of the body element of framed Panels ...

The border-width of the body element of framed Panels Defaults to: `1px`


### $panel-frame-border-color

**Type:** color

The border-color of framed Panels ...

The border-color of framed Panels Defaults to: `$panel-border-color`


### $panel-frame-border-radius

**Type:** number

The border-radius of framed Panels ...

The border-radius of framed Panels Defaults to: `4px`


### $panel-frame-border-style

**Type:** string

The border-style of framed Panels ...

The border-style of framed Panels Defaults to: `solid`


### $panel-frame-border-width

**Type:** number

The border-width of framed Panels ...

The border-width of framed Panels Defaults to: `1px`


### $panel-frame-header-border-width

**Type:** number

The border-width of framed Panel Headers ...

The border-width of framed Panel Headers Defaults to: `$panel-header-border-width`


### $panel-frame-header-inner-border-color

**Type:** color

The inner border-color of framed Panel Headers ...

The inner border-color of framed Panel Headers Defaults to: `#fff`


### $panel-frame-header-inner-border-width

**Type:** number

The inner border-width of framed Panel Headers ...

The inner border-width of framed Panel Headers Defaults to: `0`


### $panel-frame-header-padding

**Type:** number/list

The padding of framed Panel Headers ...

The padding of framed Panel Headers Defaults to: `$panel-header-padding`


### $panel-frame-padding

**Type:** number

The padding of framed Panels ...

The padding of framed Panels Defaults to: `4px`


### $panel-ghost-opacity

**Type:** number

The opacity of ghost Panels while dragging ...

The opacity of ghost Panels while dragging Defaults to: `0.50`


### $panel-header-background-color

**Type:** color

The background-color of the Panel Header ...

The background-color of the Panel Header Defaults to: `$panel-base-color`


### $panel-header-background-gradient

**Type:** string/list

The background-gradient of the Panel Header. ...

The background-gradient of the Panel Header. Can be either the name of a predefined gradient or a list of color stops. Used as the `$type` parameter for Global_CSS.background-gradient. Defaults to: `null`


### $panel-header-border-color

**Type:** color

The border-color of the Panel Header ...

The border-color of the Panel Header Defaults to: `$panel-border-color`


### $panel-header-border-style

**Type:** string

The border-style of Panel Headers ...

The border-style of Panel Headers Defaults to: `solid`


### $panel-header-border-width

**Type:** number

The border-width of Panel Headers ...

The border-width of Panel Headers Defaults to: `$panel-border-width`


### $panel-header-color

**Type:** color

The text color of the Panel Header ...

The text color of the Panel Header Defaults to: `$color`


### $panel-header-font-family

**Type:** string

The font-family of Panel Headers ...

The font-family of Panel Headers Defaults to: `$font-family`


### $panel-header-font-size

**Type:** number

The font-size of Panel Headers ...

The font-size of Panel Headers Defaults to: `$font-size`


### $panel-header-font-weight

**Type:** string

The font-weight of Panel Headers ...

The font-weight of Panel Headers Defaults to: `bold`


### $panel-header-glyph-color

**Type:** color

The color of the Panel Header glyph icon ...

The color of the Panel Header glyph icon Defaults to: `$panel-header-color`


### $panel-header-glyph-opacity

**Type:** number

The opacity of the Panel Header glyph icon ...

The opacity of the Panel Header glyph icon Defaults to: `.5`


### $panel-header-icon-background-position

**Type:** list

The background-position of the Panel Header icon ...

The background-position of the Panel Header icon Defaults to: `center center`


### $panel-header-icon-height

**Type:** number

The height of the Panel Header icon ...

The height of the Panel Header icon Defaults to: `16px`


### $panel-header-icon-spacing

**Type:** number

The space between the Panel Header icon and text ...

The space between the Panel Header icon and text Defaults to: `4px`


### $panel-header-icon-width

**Type:** number

The width of the Panel Header icon ...

The width of the Panel Header icon Defaults to: `16px`


### $panel-header-inner-border-color

**Type:** color

The inner border-color of the Panel Header ...

The inner border-color of the Panel Header Defaults to: `#fff`


### $panel-header-inner-border-width

**Type:** number

The inner border-width of the Panel Header ...

The inner border-width of the Panel Header Defaults to: `0`


### $panel-header-line-height

**Type:** number

The line-height of Panel Headers ...

The line-height of Panel Headers Defaults to: `16px`


### $panel-header-padding

**Type:** number/list

The padding of Panel Headers ...

The padding of Panel Headers Defaults to: `4px 5px`


### $panel-header-text-padding

**Type:** number/list

The padding of the Panel Header's text element ...

The padding of the Panel Header's text element Defaults to: `0`


### $panel-header-text-transform

**Type:** string

The text-transform of Panel Headers ...

The text-transform of Panel Headers Defaults to: `none`


### $panel-include-border-management-rules

**Type:** boolean

True to include neptune style border management rules. ...

True to include neptune style border management rules. Defaults to: `false`


### $panel-tool-background-image

**Type:** string

The background sprite to use for Panel Tools ...

The background sprite to use for Panel Tools Defaults to: `'tools/tool-sprites'`


### $panel-tool-spacing

**Type:** number

The space between the Panel Tools ...

The space between the Panel Tools Defaults to: `4px`


### $panel-wrap-border-color

**Type:** color

The color to apply to the border that wraps the body and docked items in a framed panel. ...

The color to apply to the border that wraps the body and docked items in a framed panel. The presence of the wrap border in a framed panel is controlled by the border config. Only applicable when `$panel-include-border-management-rules` is `true`. Defaults to: `$panel-border-color`


### $panel-wrap-border-width

**Type:** number

The width to apply to the border that wraps the body and docked items in a framed panel. ...

The width to apply to the border that wraps the body and docked items in a framed panel. The presence of the wrap border in a framed panel is controlled by the border config. Only applicable when `$panel-include-border-management-rules` is `true`. Defaults to: `1px`


### extjs-panel-ui

Creates a visual theme for a Panel ...

Creates a visual theme for a Panel $ui-label : stringThe name of the UI being created. Can not included spaces or special punctuation (used in CSS class names).


## CSS Variables

### $border-width-threshold

**Type:** $border-width-threshold

The maximum width a Panel's border can be before resizer handles are embedded into the borders using negative absolut...

The maximum width a Panel's border can be before resizer handles are embedded into the borders using negative absolute positions. This defaults to 2, so that in the classic theme which uses 1 pixel borders, resize handles are in the content area within the border as they always have been. In the Neptune theme, the handles are embedded into the 5 pixel wide borders of any framed panel. Defaults to: `2`


### $grid-body-background-color

**Type:** color

The background-color of the grid body ...

The background-color of the grid body Defaults to: `$panel-body-background-color`


### $grid-body-border-color

**Type:** color

The border-color of the grid body ...

The border-color of the grid body Defaults to: `$panel-body-border-color`


### $grid-body-border-style

**Type:** string

The border-style of the grid body border ...

The border-style of the grid body border Defaults to: `$panel-body-border-style`


### $grid-body-border-width

**Type:** number

The border-width of the grid body border ...

The border-width of the grid body border Defaults to: `$panel-body-border-width`


### $grid-cell-inner-padding

**Type:** number

The amount of padding to apply to the grid cell's inner div element ...

The amount of padding to apply to the grid cell's inner div element Defaults to: `3px 6px`


### $grid-cell-inner-text-overflow

**Type:** string

The type of text-overflow to use on the grid cell's inner div element ...

The type of text-overflow to use on the grid cell's inner div element Defaults to: `ellipsis`


### $grid-cell-selected-background-color

**Type:** color

The background-color of a selected cell when using a Cell Selection Model. ...

The background-color of a selected cell when using a Cell Selection Model. Defaults to: `$grid-row-cell-selected-background-color`


### $grid-cell-selected-color

**Type:** color

The text color of a selected cell when using a Cell Selection Model. ...

The text color of a selected cell when using a Cell Selection Model. Defaults to: `$grid-row-cell-selected-color`


### $grid-cell-special-background-color

**Type:** color

The background-color of "special" cells. ...

The background-color of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `$grid-row-cell-background-color`


### $grid-cell-special-background-gradient

**Type:** string

The background-gradient to use for "special" cells. ...

The background-gradient to use for "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `null`


### $grid-cell-special-border-color

**Type:** color

The border-color of "special" cells. ...

The border-color of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border color is determined by {#$grid-row-cell-border-color}. Defaults to: `$grid-row-cell-border-color`


### $grid-cell-special-border-style

**Type:** string

The border-style of "special" cells. ...

The border-style of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border style is determined by {#$grid-row-cell-border-style}. Defaults to: `$grid-row-cell-border-style`


### $grid-cell-special-border-width

**Type:** number

The border-width of "special" cells. ...

The border-width of "special" cells. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the row border width is determined by {#$grid-row-cell-border-width}. Defaults to: `$grid-row-cell-border-width`


### $grid-cell-special-over-background-color

**Type:** color

The background-color of "special" cells when the row is hovered. ...

The background-color of "special" cells when the row is hovered. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Defaults to: `$grid-row-cell-over-background-color`


### $grid-cell-special-selected-border-color

**Type:** color

The border-color of "special" cells when the row is selected using a Row Selection Model. ...

The border-color of "special" cells when the row is selected using a Row Selection Model. Special cells are created by RowNumberer, Checkbox Selection Model and RowExpander. Only applies to the vertical border, since the selected row border color is determined by {#$grid-row-cell-selected-border-color}. Defaults to: `$grid-row-cell-border-color`


### $grid-empty-background-color

**Type:** color

The background color of the grid body when the grid contains no data. ...

The background color of the grid body when the grid contains no data. Defaults to: `$panel-body-background-color`


### $grid-empty-color

**Type:** color

The text color of the emptyText in the grid body when the grid contains no data. ...

The text color of the emptyText in the grid body when the grid contains no data. Defaults to: `#808080`


### $grid-empty-font-family

**Type:** number

The font-family of the emptyText in the grid body when the grid contains no data. ...

The font-family of the emptyText in the grid body when the grid contains no data. Defaults to: `$font-family`


### $grid-empty-font-size

**Type:** number

The font-size of the emptyText in the grid body when the grid contains no data. ...

The font-size of the emptyText in the grid body when the grid contains no data. Defaults to: `$grid-row-cell-font-size`


### $grid-empty-font-weight

**Type:** number

The font-weight of the emptyText in the grid body when the grid contains no data. ...

The font-weight of the emptyText in the grid body when the grid contains no data. Defaults to: `normal`


### $grid-empty-padding

**Type:** number

The amount of padding to apply to the grid body when the grid contains no data. ...

The amount of padding to apply to the grid body when the grid contains no data. Defaults to: `10px`


### $grid-lockable-separator-border-style

**Type:** string

The border-style of the border between the locked views ...

The border-style of the border between the locked views Defaults to: `solid`


### $grid-lockable-separator-border-width

**Type:** number

The width of the border between the locked views ...

The width of the border between the locked views Defaults to: `1px`


### $grid-no-row-lines-show-focus-border

**Type:** boolean

True to show the focus border when a row is focused even if the grid has no rowLines. ...

True to show the focus border when a row is focused even if the grid has no rowLines. Defaults to: `false`


### $grid-resize-marker-background-color

**Type:** color

The color of the resize markers that display when dragging a column border to resize the column ...

The color of the resize markers that display when dragging a column border to resize the column Defaults to: `#0f0f0f`


### $grid-row-cell-alt-background-color

**Type:** color

The background-color color of odd-numbered rows when the table view is configured with stripeRows: true. ...

The background-color color of odd-numbered rows when the table view is configured with `stripeRows: true`. Defaults to: `darken ( $grid-row-cell-background-color , 2 )`


### $grid-row-cell-background-color

**Type:** color

The background-color of the grid cells ...

The background-color of the grid cells Defaults to: `#fff`


### $grid-row-cell-border-color

**Type:** color

The border-color of row/column borders. ...

The border-color of row/column borders. Can be specified as a single color, or as a list of colors containing the row border color followed by the column border color. Defaults to: `#ededed`


### $grid-row-cell-border-style

**Type:** string

The border-style of the row/column borders. ...

The border-style of the row/column borders. Defaults to: `solid`


### $grid-row-cell-border-width

**Type:** number

The border-width of the row and column borders. ...

The border-width of the row and column borders. Defaults to: `1px`


### $grid-row-cell-color

**Type:** color

The color of the text in the grid cells ...

The color of the text in the grid cells Defaults to: `null`


### $grid-row-cell-focus-background-color

**Type:** color

The background-color of the focused row ...

The background-color of the focused row Defaults to: `$grid-row-cell-background-color`


### $grid-row-cell-focus-border-color

**Type:** color

The border-color of the focused row ...

The border-color of the focused row Defaults to: `#808080`


### $grid-row-cell-focus-border-style

**Type:** string

The border-style of the focused row ...

The border-style of the focused row Defaults to: `dotted`


### $grid-row-cell-focus-color

**Type:** color

The text color of the focused row ...

The text color of the focused row Defaults to: `$grid-row-cell-color`


### $grid-row-cell-font-family

**Type:** string

The font-family of the text in the grid cells ...

The font-family of the text in the grid cells Defaults to: `$font-family`


### $grid-row-cell-font-size

**Type:** number

The font size of the text in the grid cells ...

The font size of the text in the grid cells Defaults to: `$font-size`


### $grid-row-cell-font-weight

**Type:** string

The font-weight of the text in the grid cells ...

The font-weight of the text in the grid cells Defaults to: `normal`


### $grid-row-cell-line-height

**Type:** Object

var {number} $grid-row-cell-line-height The line-height of the text inside the grid cells. ...

var {number} $grid-row-cell-line-height The line-height of the text inside the grid cells. Defaults to: `round ( $grid-row-cell-font-size * 1.15 )`


### $grid-row-cell-over-background-color

**Type:** color

The background-color of the hovered row ...

The background-color of the hovered row Defaults to: `#ddd`


### $grid-row-cell-over-border-color

**Type:** color

The border-color of the hovered row ...

The border-color of the hovered row Defaults to: `$grid-row-cell-border-color`


### $grid-row-cell-over-border-style

**Type:** string

The border-style of the hovered row ...

The border-style of the hovered row Defaults to: `solid`


### $grid-row-cell-over-color

**Type:** color

The text color of the hovered row ...

The text color of the hovered row Defaults to: `$grid-row-cell-color`


### $grid-row-cell-selected-background-color

**Type:** color

The background-color of the selected row ...

The background-color of the selected row Defaults to: `#ccc`


### $grid-row-cell-selected-border-color

**Type:** color

The border-color of the selected row ...

The border-color of the selected row Defaults to: `$grid-row-cell-border-color`


### $grid-row-cell-selected-border-style

**Type:** string

The border-style of the selected row ...

The border-style of the selected row Defaults to: `solid`


### $grid-row-cell-selected-color

**Type:** color

The text color of the selected row ...

The text color of the selected row Defaults to: `$grid-row-cell-color`


### $include-panel-default-framed-ui

**Type:** boolean

True to include the "default-framed" panel UI ...

True to include the "default-framed" panel UI Defaults to: `$include-default-uis`


### $include-panel-default-ui

**Type:** boolean

True to include the "default" panel UI ...

True to include the "default" panel UI Defaults to: `$include-default-uis`


### $panel-background-stretch-bottom

**Type:** string

The direction to strech the background-gradient of bottom docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of bottom docked Headers when slicing images for IE using Sencha Cmd Defaults to: `top`


### $panel-background-stretch-left

**Type:** string

The direction to strech the background-gradient of left docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of left docked Headers when slicing images for IE using Sencha Cmd Defaults to: `right`


### $panel-background-stretch-right

**Type:** string

The direction to strech the background-gradient of right docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of right docked Headers when slicing images for IE using Sencha Cmd Defaults to: `left`


### $panel-background-stretch-top

**Type:** string

The direction to strech the background-gradient of top docked Headers when slicing images for IE using Sencha Cmd ...

The direction to strech the background-gradient of top docked Headers when slicing images for IE using Sencha Cmd Defaults to: `bottom`


### $panel-base-color

**Type:** color

The base color of Panels ...

The base color of Panels Defaults to: `$base-color`


### $panel-body-background-color

**Type:** color

The default body background-color of Panels ...

The default body background-color of Panels Defaults to: `#fff`


### $panel-body-border-color

**Type:** color

The default border-color of the Panel body ...

The default border-color of the Panel body Defaults to: `$panel-border-color`


### $panel-body-border-style

**Type:** string

The default border-style of Panels ...

The default border-style of Panels Defaults to: `solid`


### $panel-body-border-width

**Type:** number

The default border-width of the Panel body ...

The default border-width of the Panel body Defaults to: `1px`


### $panel-body-color

**Type:** color

The default color of text inside a Panel's body ...

The default color of text inside a Panel's body Defaults to: `#000`


### $panel-body-font-size

**Type:** number

The default font-size of the Panel body ...

The default font-size of the Panel body Defaults to: `$font-size`


### $panel-body-font-weight

**Type:** string

The default font-weight of the Panel body ...

The default font-weight of the Panel body Defaults to: `normal`


### $panel-border-color

**Type:** color

The default border-color of Panels ...

The default border-color of Panels Defaults to: `$panel-base-color`


### $panel-border-width

**Type:** number

The default border-width of Panels ...

The default border-width of Panels Defaults to: `1px`


### $panel-frame-background-color

**Type:** color

The background-color of framed Panels ...

The background-color of framed Panels Defaults to: `#fff`


### $panel-frame-base-color

**Type:** color

The base color of the framed Panels ...

The base color of the framed Panels Defaults to: `$panel-base-color`


### $panel-frame-body-border-width

**Type:** number

The border-width of the body element of framed Panels ...

The border-width of the body element of framed Panels Defaults to: `1px`


### $panel-frame-border-color

**Type:** color

The border-color of framed Panels ...

The border-color of framed Panels Defaults to: `$panel-border-color`


### $panel-frame-border-radius

**Type:** number

The border-radius of framed Panels ...

The border-radius of framed Panels Defaults to: `4px`


### $panel-frame-border-style

**Type:** string

The border-style of framed Panels ...

The border-style of framed Panels Defaults to: `solid`


### $panel-frame-border-width

**Type:** number

The border-width of framed Panels ...

The border-width of framed Panels Defaults to: `1px`


### $panel-frame-header-border-width

**Type:** number

The border-width of framed Panel Headers ...

The border-width of framed Panel Headers Defaults to: `$panel-header-border-width`


### $panel-frame-header-inner-border-color

**Type:** color

The inner border-color of framed Panel Headers ...

The inner border-color of framed Panel Headers Defaults to: `#fff`


### $panel-frame-header-inner-border-width

**Type:** number

The inner border-width of framed Panel Headers ...

The inner border-width of framed Panel Headers Defaults to: `0`


### $panel-frame-header-padding

**Type:** number/list

The padding of framed Panel Headers ...

The padding of framed Panel Headers Defaults to: `$panel-header-padding`


### $panel-frame-padding

**Type:** number

The padding of framed Panels ...

The padding of framed Panels Defaults to: `4px`


### $panel-ghost-opacity

**Type:** number

The opacity of ghost Panels while dragging ...

The opacity of ghost Panels while dragging Defaults to: `0.50`


### $panel-header-background-color

**Type:** color

The background-color of the Panel Header ...

The background-color of the Panel Header Defaults to: `$panel-base-color`


### $panel-header-background-gradient

**Type:** string/list

The background-gradient of the Panel Header. ...

The background-gradient of the Panel Header. Can be either the name of a predefined gradient or a list of color stops. Used as the `$type` parameter for Global_CSS.background-gradient. Defaults to: `null`


### $panel-header-border-color

**Type:** color

The border-color of the Panel Header ...

The border-color of the Panel Header Defaults to: `$panel-border-color`


### $panel-header-border-style

**Type:** string

The border-style of Panel Headers ...

The border-style of Panel Headers Defaults to: `solid`


### $panel-header-border-width

**Type:** number

The border-width of Panel Headers ...

The border-width of Panel Headers Defaults to: `$panel-border-width`


### $panel-header-color

**Type:** color

The text color of the Panel Header ...

The text color of the Panel Header Defaults to: `$color`


### $panel-header-font-family

**Type:** string

The font-family of Panel Headers ...

The font-family of Panel Headers Defaults to: `$font-family`


### $panel-header-font-size

**Type:** number

The font-size of Panel Headers ...

The font-size of Panel Headers Defaults to: `$font-size`


### $panel-header-font-weight

**Type:** string

The font-weight of Panel Headers ...

The font-weight of Panel Headers Defaults to: `bold`


### $panel-header-glyph-color

**Type:** color

The color of the Panel Header glyph icon ...

The color of the Panel Header glyph icon Defaults to: `$panel-header-color`


### $panel-header-glyph-opacity

**Type:** number

The opacity of the Panel Header glyph icon ...

The opacity of the Panel Header glyph icon Defaults to: `.5`


### $panel-header-icon-background-position

**Type:** list

The background-position of the Panel Header icon ...

The background-position of the Panel Header icon Defaults to: `center center`


### $panel-header-icon-height

**Type:** number

The height of the Panel Header icon ...

The height of the Panel Header icon Defaults to: `16px`


### $panel-header-icon-spacing

**Type:** number

The space between the Panel Header icon and text ...

The space between the Panel Header icon and text Defaults to: `4px`


### $panel-header-icon-width

**Type:** number

The width of the Panel Header icon ...

The width of the Panel Header icon Defaults to: `16px`


### $panel-header-inner-border-color

**Type:** color

The inner border-color of the Panel Header ...

The inner border-color of the Panel Header Defaults to: `#fff`


### $panel-header-inner-border-width

**Type:** number

The inner border-width of the Panel Header ...

The inner border-width of the Panel Header Defaults to: `0`


### $panel-header-line-height

**Type:** number

The line-height of Panel Headers ...

The line-height of Panel Headers Defaults to: `16px`


### $panel-header-padding

**Type:** number/list

The padding of Panel Headers ...

The padding of Panel Headers Defaults to: `4px 5px`


### $panel-header-text-padding

**Type:** number/list

The padding of the Panel Header's text element ...

The padding of the Panel Header's text element Defaults to: `0`


### $panel-header-text-transform

**Type:** string

The text-transform of Panel Headers ...

The text-transform of Panel Headers Defaults to: `none`


### $panel-include-border-management-rules

**Type:** boolean

True to include neptune style border management rules. ...

True to include neptune style border management rules. Defaults to: `false`


### $panel-tool-background-image

**Type:** string

The background sprite to use for Panel Tools ...

The background sprite to use for Panel Tools Defaults to: `'tools/tool-sprites'`


### $panel-tool-spacing

**Type:** number

The space between the Panel Tools ...

The space between the Panel Tools Defaults to: `4px`


### $panel-wrap-border-color

**Type:** color

The color to apply to the border that wraps the body and docked items in a framed panel. ...

The color to apply to the border that wraps the body and docked items in a framed panel. The presence of the wrap border in a framed panel is controlled by the border config. Only applicable when `$panel-include-border-management-rules` is `true`. Defaults to: `$panel-border-color`


### $panel-wrap-border-width

**Type:** number

The width to apply to the border that wraps the body and docked items in a framed panel. ...

The width to apply to the border that wraps the body and docked items in a framed panel. The presence of the wrap border in a framed panel is controlled by the border config. Only applicable when `$panel-include-border-management-rules` is `true`. Defaults to: `1px`


### extjs-panel-ui

Creates a visual theme for a Panel ...

Creates a visual theme for a Panel $ui-label : stringThe name of the UI being created. Can not included spaces or special punctuation (used in CSS class names).


## CSS Mixins

### extjs-panel-ui

Creates a visual theme for a Panel ...

Creates a visual theme for a Panel $ui-label : stringThe name of the UI being created. Can not included spaces or special punctuation (used in CSS class names).


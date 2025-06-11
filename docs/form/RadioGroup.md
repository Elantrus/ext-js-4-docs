# Ext.form.RadioGroup

**Extends:** Ext.form.CheckboxGroup

**Widget Alias:** radiogroup

## Description

A field container which has a specialized layout for arranging Ext.form.field.Radio controls into columns, and provides convenience Ext.form.field.Field methods for getting, setting, and validating the group of radio buttons as a whole.

Individual radio buttons themselves have no default validation behavior, but sometimes you want to require a user to select one of a group of radios. RadioGroup allows this by setting the config `allowBlank:false`; when the user does not check at one of the radio buttons, the entire group will be highlighted as invalid and the error message will be displayed according to the msgTarget config.

The default layout for RadioGroup makes it easy to arrange the radio buttons into columns; see the columns and vertical config documentation for details. You may also use a completely different layout by setting the layout to one of the other supported layout types; for instance you may wish to use a custom arrangement of hbox and vbox containers. In that case the Radio components at any depth will still be managed by the RadioGroup's validation.

## Examples

### Example 1

```javascript
Ext.create('Ext.form.Panel', { title: 'RadioGroup Example', width: 300, height: 125, bodyPadding: 10, renderTo: Ext.getBody(), items:[{ xtype: 'radiogroup', fieldLabel: 'Two Columns', // Arrange radio buttons into two columns, distributed vertically columns: 2, vertical: true, items: [ { boxLabel: 'Item 1', name: 'rb', inputValue: '1' }, { boxLabel: 'Item 2', name: 'rb', inputValue: '2', checked: true}, { boxLabel: 'Item 3', name: 'rb', inputValue: '3' }, { boxLabel: 'Item 4', name: 'rb', inputValue: '4' }, { boxLabel: 'Item 5', name: 'rb', inputValue: '5' }, { boxLabel: 'Item 6', name: 'rb', inputValue: '6' } ] }] });
```

## Config options

### activeError

**Type:** String

If specified, then the component will be displayed with this value as its active error when first rendered. ...

If specified, then the component will be displayed with this value as its active error when first rendered. Use setActiveError or unsetActiveError to change it after component creation.


### activeErrorsTpl

**Type:** String/String[]/Ext.XTemplate

The template used to format the Array of error messages passed to setActiveErrors into a single HTML string. ...

The template used to format the Array of error messages passed to setActiveErrors into a single HTML string. if the msgTarget is title, it defaults to a list separated by new lines. Otherwise, it renders each message as an item in an unordered list.


### activeItem

**Type:** String/Number

A string component id or the numeric index of the component that should be initially activated within the container's...

A string component id or the numeric index of the component that should be initially activated within the container's layout on render. For example, activeItem: 'item-1' or activeItem: 0 (index 0 = the first item in the container's collection). activeItem only applies to layout styles that can display items one at a time (like Ext.layout.container.Card and Ext.layout.container.Fit). Available since: 2.3.0


### afterBodyEl

**Type:** String/Array/Ext.XTemplate

An optional string or XTemplate configuration to insert in the field markup at the end of the input containing element. ...

An optional string or `XTemplate` configuration to insert in the field markup at the end of the input containing element. If an `XTemplate` is used, the component's render data serves as the context.


### afterLabelTextTpl

**Type:** String/Array/Ext.XTemplate

An optional string or XTemplate configuration to insert in the field markup after the label text. ...

An optional string or `XTemplate` configuration to insert in the field markup after the label text. If an `XTemplate` is used, the component's render data serves as the context.


### afterLabelTpl

**Type:** String/Array/Ext.XTemplate

An optional string or XTemplate configuration to insert in the field markup after the label element. ...

An optional string or `XTemplate` configuration to insert in the field markup after the label element. If an `XTemplate` is used, the component's render data serves as the context.


### afterSubTpl

**Type:** String/Array/Ext.XTemplate

An optional string or XTemplate configuration to insert in the field markup after the subTpl markup. ...

An optional string or `XTemplate` configuration to insert in the field markup after the subTpl markup. If an `XTemplate` is used, the component's render data serves as the context.


### allowBlank

**Type:** Boolean

True to allow every item in the group to be blank. ...

True to allow every item in the group to be blank. If allowBlank = false and no items are selected at validation time, blankText will be used as the error text. Defaults to: `true` Overrides: Ext.form.CheckboxGroup.allowBlank


### anchorSize

**Type:** Number/Object

Defines the anchoring size of container. ...

Defines the anchoring size of container. Either a number to define the width of the container or an object with `width` and `height` fields.


### autoDestroy

**Type:** Boolean

If true the container will automatically destroy any contained component that is removed from it, else destruction mu...

If true the container will automatically destroy any contained component that is removed from it, else destruction must be handled manually. Defaults to: `true` Available since: 2.3.0


### autoEl

**Type:** String/Object

A tag name or DomHelper spec used to create the Element which will encapsulate this Component. ...

A tag name or DomHelper spec used to create the Element which will encapsulate this Component. You do not normally need to specify this. For the base classes Ext.Component and Ext.container.Container, this defaults to **'div'**. The more complex Sencha classes use a more complex DOM structure specified by their own renderTpls. This is intended to allow the developer to create application-specific utility Components encapsulated by different DOM elements. Example usage: Available since: 2.3.0


### autoFitErrors

**Type:** Boolean

Whether to adjust the component's body area to make room for 'side' or 'under' error messages. ...

Whether to adjust the component's body area to make room for 'side' or 'under' error messages. Defaults to: `true`


### autoLoad

**Type:** Ext.ComponentLoader/Object/String/Boolean

An alias for loader config which also allows to specify just a string which will be used as the url that's automatica...

An alias for loader config which also allows to specify just a string which will be used as the url that's automatically loaded: The above is the same as: Don't use it together with loader config. This cfg has been **deprecated** since 4.1.1 Use loader config instead.


### autoRender

**Type:** Boolean/String/HTMLElement/Ext.Element

This config is intended mainly for non-floating Components which may or may not be shown. ...

This config is intended mainly for non-floating Components which may or may not be shown. Instead of using renderTo in the configuration, and rendering upon construction, this allows a Component to render itself upon first *show*. If floating is `true`, the value of this config is omitted as if it is `true`. Specify as `true` to have this Component render to the document body upon first show. Specify as an element, or the ID of an element to have this Component render to a specific element upon first show. Defaults to: `false`


### autoShow

**Type:** Boolean

true to automatically show the component upon creation. ...

`true` to automatically show the component upon creation. This config option may only be used for floating components or components that use autoRender. Defaults to: `false` Available since: 2.3.0


### baseBodyCls

**Type:** String

The CSS class to be applied to the body content element. ...

The CSS class to be applied to the body content element. Defaults to: `Ext.baseCSSPrefix + 'form-item-body'`


### baseCls

**Type:** String

The base CSS class to apply to this component's element. ...

The base CSS class to apply to this component's element. This will also be prepended to elements within this component like Panel's body will get a class `x-panel-body`. This means that if you create a subclass of Panel, and you want it to get all the Panels styling for the element and the body, you leave the `baseCls` `x-panel` and use `componentCls` to add specific styling for this component. Defaults to: `Ext.baseCSSPrefix + 'container'` Overrides: Ext.AbstractComponent.baseCls


### beforeBodyEl

**Type:** String/Array/Ext.XTemplate

An optional string or XTemplate configuration to insert in the field markup at the beginning of the input containing ...

An optional string or `XTemplate` configuration to insert in the field markup at the beginning of the input containing element. If an `XTemplate` is used, the component's render data serves as the context.


### beforeLabelTextTpl

**Type:** String/Array/Ext.XTemplate

An optional string or XTemplate configuration to insert in the field markup before the label text. ...

An optional string or `XTemplate` configuration to insert in the field markup before the label text. If an `XTemplate` is used, the component's render data serves as the context.


### beforeLabelTpl

**Type:** String/Array/Ext.XTemplate

An optional string or XTemplate configuration to insert in the field markup before the label element. ...

An optional string or `XTemplate` configuration to insert in the field markup before the label element. If an `XTemplate` is used, the component's render data serves as the context.


### beforeSubTpl

**Type:** String/Array/Ext.XTemplate

An optional string or XTemplate configuration to insert in the field markup before the subTpl markup. ...

An optional string or `XTemplate` configuration to insert in the field markup before the subTpl markup. If an `XTemplate` is used, the component's render data serves as the context.


### blankText

**Type:** String

Error text to display if the allowBlank validation fails ...

Error text to display if the allowBlank validation fails Defaults to: `'You must select one item in this group'` Overrides: Ext.form.CheckboxGroup.blankText


### border

**Type:** Number/String/Boolean

Specifies the border size for this component. ...

Specifies the border size for this component. The border can be a single numeric value to apply to all sides or it can be a CSS style specification for each style, for example: '10 5 3 10' (top, right, bottom, left). For components that have no border by default, setting this won't make the border appear by itself. You also need to specify border color and style: To turn off the border, use `border: false`.


### bubbleEvents

**Type:** String[]

An array of events that, when fired, should be bubbled to any parent container. ...

An array of events that, when fired, should be bubbled to any parent container. See Ext.util.Observable.enableBubble. Available since: 3.4.0


### childEls

**Type:** Object[]

An array describing the child elements of the Component. ...

An array describing the child elements of the Component. Each member of the array is an object with these properties: - `name` - The property name on the Component for the child element. - `itemId` - The id to combine with the Component's id that is the id of the child element. - `id` - The id of the child element. If the array member is a string, it is equivalent to `{ name: m, itemId: m }`. For example, a Component which renders a title and body text: A more flexible, but somewhat slower, approach is renderSelectors.


### clearCls

**Type:** String

The CSS class to be applied to the special clearing div rendered directly after the field contents wrapper to provide...

The CSS class to be applied to the special clearing div rendered directly after the field contents wrapper to provide field clearing. Defaults to: `Ext.baseCSSPrefix + 'clear'`


### cls

**Type:** String

An optional extra CSS class that will be added to this component's Element. ...

An optional extra CSS class that will be added to this component's Element. This can be useful for adding customized styles to the component or any of its children using standard CSS rules. Defaults to: `''` Available since: 1.1.0


### columnWidth

**Type:** Number/String

Defines the column width inside column layout. ...

Defines the column width inside column layout. Can be specified as a number or as a percentage.


### columns

**Type:** String/Number/Number[]

Specifies the number of columns to use when displaying grouped checkbox/radio controls using automatic layout. ...

Specifies the number of columns to use when displaying grouped checkbox/radio controls using automatic layout. This config can take several types of values: - 'auto' - The controls will be rendered one per column on one row and the width of each column will be evenly distributed based on the width of the overall field container. This is the default. - Number - If you specific a number (e.g., 3) that number of columns will be created and the contained controls will be automatically distributed based on the value of vertical. - Array - You can also specify an array of column widths, mixing integer (fixed width) and float (percentage width) values as needed (e.g., [100, .25, .75]). Any integer values will be rendered first, then any float values will be calculated as a percentage of the remaining space. Float values do not have to add up to 1 (100%) although if you want the controls to take up the entire field container you should do so. Defaults to: `'auto'`


### combineErrors

**Type:** Boolean

If set to true, the field container will automatically combine and display the validation errors from all the fields ...

If set to true, the field container will automatically combine and display the validation errors from all the fields it contains as a single error on the container, according to the configured msgTarget. Defaults to false. Defaults to: `false`


### combineLabels

**Type:** Boolean

If set to true, and there is no defined fieldLabel, the field container will automatically generate its label by comb...

If set to true, and there is no defined fieldLabel, the field container will automatically generate its label by combining the labels of all the fields it contains. Defaults to false. Defaults to: `false`


### componentCls

**Type:** String

CSS Class to be added to a components root level element to give distinction to it via styling. ...

CSS Class to be added to a components root level element to give distinction to it via styling. Defaults to: `Ext.baseCSSPrefix + 'form-checkboxgroup'` Overrides: Ext.form.FieldContainer.componentCls


### componentLayout

**Type:** String/Object

The sizing and positioning of a Component's internal Elements is the responsibility of the Component's layout manager...

The sizing and positioning of a Component's internal Elements is the responsibility of the Component's layout manager which sizes a Component's internal structure in response to the Component being sized. Generally, developers will not use this configuration as all provided Components which need their internal elements sizing (Such as input fields) come with their own componentLayout managers. The default layout manager will be used on instances of the base Ext.Component class which simply sizes the Component's encapsulating element to the height and width specified in the setSize method. Defaults to: `'fieldcontainer'` Overrides: Ext.AbstractComponent.componentLayout


### constrain

**Type:** Boolean

True to constrain this Components within its containing element, false to allow it to fall outside of its containing ...

True to constrain this Components within its containing element, false to allow it to fall outside of its containing element. By default this Component will be rendered to `document.body`. To render and constrain this Component within another element specify renderTo. Defaults to: `false`


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


### defaultType

**Type:** String

private The default xtype of child Components to create in this Container when a child item is specified as a raw co...

private The default xtype of child Components to create in this Container when a child item is specified as a raw configuration object, rather than as an instantiated Component. Defaults to: `'radiofield'` Available since: 2.3.0 Overrides: Ext.form.CheckboxGroup.defaultType


### defaults

**Type:** Object/Function

This option is a means of applying default settings to all added items whether added through the items config or via ...

This option is a means of applying default settings to all added items whether added through the items config or via the add or insert methods. Defaults are applied to both config objects and instantiated components conditionally so as not to override existing properties in the item (see Ext.applyIf). If the defaults option is specified as a function, then the function will be called using this Container as the scope (`this` reference) and passing the added item as the first parameter. Any resulting object from that call is then applied to the item as default properties. For example, to automatically apply padding to the body of each of a set of contained Ext.panel.Panel items, you could pass: `defaults: {bodyStyle:'padding:15px'}`. Usage: Available since: 2.3.0


### detachOnRemove

**Type:** Boolean

True to move any component to the detachedBody when the component is removed from this container. ...

True to move any component to the detachedBody when the component is removed from this container. This option is only applicable when the component is not destroyed while being removed, see autoDestroy and remove. If this option is set to false, the DOM of the component will remain in the current place until it is explicitly moved. Defaults to: `true`


### disabled

**Type:** Boolean

True to disable the field. ...

True to disable the field. Disabled Fields will not be submitted. Defaults to: `false` Overrides: Ext.AbstractComponent.disabled


### disabledCls

**Type:** String

CSS class to add when the Component is disabled. ...

CSS class to add when the Component is disabled. Defaults to: `'x-item-disabled'`


### draggable

**Type:** Boolean/Object

Specify as true to make a floating Component draggable using the Component's encapsulating element as the drag handle. ...

Specify as true to make a floating Component draggable using the Component's encapsulating element as the drag handle. This may also be specified as a config object for the ComponentDragger which is instantiated to perform dragging. For example to create a Component which may only be dragged around using a certain internal element as the drag handle, use the delegate option: Defaults to: `false` Overrides: Ext.AbstractComponent.draggable


### errorMsgCls

**Type:** String

The CSS class to be applied to the error message element. ...

The CSS class to be applied to the error message element. Defaults to: `Ext.baseCSSPrefix + 'form-error-msg'`


### fieldBodyCls

**Type:** String

An extra CSS class to be applied to the body content element in addition to baseBodyCls. ...

An extra CSS class to be applied to the body content element in addition to baseBodyCls. Defaults to: `''`


### fieldDefaults

**Type:** Object

If specified, the properties in this object are used as default config values for each Ext.form.Labelable instance (e.g. ...

If specified, the properties in this object are used as default config values for each Ext.form.Labelable instance (e.g. Ext.form.field.Base or Ext.form.FieldContainer) that is added as a descendant of this container. Corresponding values specified in an individual field's own configuration, or from the defaults config of its parent container, will take precedence. See the documentation for Ext.form.Labelable to see what config options may be specified in the fieldDefaults. Example: In this example, field1 and field2 will get labelAlign:'top' (from the fieldset's defaults) and labelWidth:100 (from fieldDefaults), field3 and field4 will both get labelAlign:'left' (from fieldDefaults and field3 will use the labelWidth:150 from its own config.


### fieldLabel

**Type:** String

The label for the field. ...

The label for the field. It gets appended with the labelSeparator, and its position and sizing is determined by the labelAlign, labelWidth, and labelPad configs.


### fixed

**Type:** Boolean

Configure as true to have this Component fixed at its X, Y coordinates in the browser viewport, immune to scrolling t...

Configure as `true` to have this Component fixed at its `X, Y` coordinates in the browser viewport, immune to scrolling the document. *Only in browsers that support `position:fixed`* *IE6 and IE7, 8 and 9 quirks do not support `position: fixed`* Defaults to: `false`


### floating

**Type:** Boolean

Specify as true to float the Component outside of the document flow using CSS absolute positioning. ...

Specify as true to float the Component outside of the document flow using CSS absolute positioning. Components such as Windows and Menus are floating by default. Floating Components that are programatically rendered will register themselves with the global ZIndexManager Floating Components as child items of a Container A floating Component may be used as a child item of a Container. This just allows the floating Component to seek a ZIndexManager by examining the ownerCt chain. When configured as floating, Components acquire, at render time, a ZIndexManager which manages a stack of related floating Components. The ZIndexManager brings a single floating Component to the top of its stack when the Component's toFront method is called. The ZIndexManager is found by traversing up the ownerCt chain to find an ancestor which itself is floating. This is so that descendant floating Components of floating *Containers* (Such as a ComboBox dropdown within a Window) can have its zIndex managed relative to any siblings, but always **above** that floating ancestor Container. If no floating ancestor is found, a floating Component registers itself with the default ZIndexManager. Floating components *do not participate in the Container's layout*. Because of this, they are not rendered until you explicitly show them. After rendering, the ownerCt reference is deleted, and the floatParent property is set to the found floating ancestor Container. If no floating ancestor Container was found the floatParent property will not be set. Defaults to: `false` Overrides: Ext.AbstractComponent.floating


### focusOnToFront

**Type:** Boolean

Specifies whether the floated component should be automatically focused when it is brought to the front. ...

Specifies whether the floated component should be automatically focused when it is brought to the front. Defaults to: `true`


### formBind

**Type:** Boolean

When inside FormPanel, any component configured with formBind: true will be enabled/disabled depending on the validit...

When inside FormPanel, any component configured with `formBind: true` will be enabled/disabled depending on the validity state of the form. See Ext.form.Panel for more information and example. Defaults to: `false`


### formItemCls

**Type:** String

A CSS class to be applied to the outermost element to denote that it is participating in the form field layout. ...

A CSS class to be applied to the outermost element to denote that it is participating in the form field layout. Defaults to: `Ext.baseCSSPrefix + 'form-item'`


### frame

**Type:** Boolean

Specify as true to have the Component inject framing elements within the Component at render time to provide a graphi...

Specify as `true` to have the Component inject framing elements within the Component at render time to provide a graphical rounded frame around the Component content. This is only necessary when running on outdated, or non standard-compliant browsers such as Microsoft's Internet Explorer prior to version 9 which do not support rounded corners natively. The extra space taken up by this framing is available from the read only property frameSize.


### height

**Type:** Number

The height of this component in pixels.


### hidden

**Type:** Boolean

true to hide the component. ...

`true` to hide the component. Defaults to: `false` Available since: 2.3.0


### hideEmptyLabel

**Type:** Boolean

When set to true, the label element (fieldLabel and labelSeparator) will be automatically hidden if the fieldLabel is...

When set to true, the label element (fieldLabel and labelSeparator) will be automatically hidden if the fieldLabel is empty. Setting this to false will cause the empty label element to be rendered and space to be reserved for it; this is useful if you want a field without a label to line up with other labeled fields in the same form. If you wish to unconditionall hide the label even if a non-empty fieldLabel is configured, then set the hideLabel config to true. Defaults to: `true`


### hideLabel

**Type:** Boolean

Set to true to completely hide the label element (fieldLabel and labelSeparator). ...

Set to true to completely hide the label element (fieldLabel and labelSeparator). Also see hideEmptyLabel, which controls whether space will be reserved for an empty fieldLabel. Defaults to: `false`


### hideMode

**Type:** String

A String which specifies how this Component's encapsulating DOM element will be hidden. ...

A String which specifies how this Component's encapsulating DOM element will be hidden. Values may be: - `'display'` : The Component will be hidden using the `display: none` style. - `'visibility'` : The Component will be hidden using the `visibility: hidden` style. - `'offsets'` : The Component will be hidden by absolutely positioning it out of the visible area of the document. This is useful when a hidden Component must maintain measurable dimensions. Hiding using `display` results in a Component having zero dimensions. Defaults to: `'display'` Available since: 1.1.0


### html

**Type:** String/Object

An HTML fragment, or a DomHelper specification to use as the layout element content. ...

An HTML fragment, or a DomHelper specification to use as the layout element content. The HTML content is added after the component is rendered, so the document will not contain this HTML at the time the render event is fired. This content is inserted into the body *before* any configured contentEl is appended. Defaults to: `''` Available since: 3.4.0


### id

**Type:** String

The unique id of this component instance. ...

The **unique id of this component instance.** It should not be necessary to use this configuration except for singleton objects in your application. Components created with an `id` may be accessed globally using Ext.getCmp. Instead of using assigned ids, use the itemId config, and ComponentQuery which provides selector-based searching for Sencha Components analogous to DOM querying. The Container class contains shortcut methods to query its descendant Components by selector. Note that this `id` will also be used as the element id for the containing HTML element that is rendered to the page for this component. This allows you to write id-based CSS rules to style the specific instance of this component uniquely, and also to select sub-elements using this component's `id` as the parent. **Note:** To avoid complications imposed by a unique `id` also see `itemId`. **Note:** To access the container of a Component see `ownerCt`. Defaults to an auto-assigned id. Available since: 1.1.0


### invalidCls

**Type:** String

If we allow this to mark with the invalidCls it will cascade to all child fields, let them handle themselves The CSS...

If we allow this to mark with the invalidCls it will cascade to all child fields, let them handle themselves The CSS class to use when marking the component invalid. Defaults to: `''` Overrides: Ext.form.Labelable.invalidCls


### itemId

**Type:** String

An itemId can be used as an alternative way to get a reference to a component when no object reference is available. ...

An `itemId` can be used as an alternative way to get a reference to a component when no object reference is available. Instead of using an `id` with Ext.getCmp, use `itemId` with Ext.container.Container.getComponent which will retrieve `itemId`'s or id's. Since `itemId`'s are an index to the container's internal MixedCollection, the `itemId` is scoped locally to the container -- avoiding potential conflicts with Ext.ComponentManager which requires a **unique** `id`. Also see id, `Ext.container.Container.query`, `Ext.container.Container.down` and `Ext.container.Container.child`. **Note**: to access the container of an item see ownerCt. Available since: 3.4.0


### items

**Type:** Ext.form.field.Radio[]/Object[]

An Array of Radios or Radio config objects to arrange in the group.

An Array of Radios or Radio config objects to arrange in the group. Overrides: Ext.form.CheckboxGroup.items


### labelAlign

**Type:** String

Controls the position and alignment of the fieldLabel. ...

Controls the position and alignment of the fieldLabel. Valid values are: - "left" (the default) - The label is positioned to the left of the field, with its text aligned to the left. Its width is determined by the labelWidth config. - "top" - The label is positioned above the field. - "right" - The label is positioned to the left of the field, with its text aligned to the right. Its width is determined by the labelWidth config. Defaults to: `'left'`


### labelAttrTpl

**Type:** String/Array/Ext.XTemplate

An optional string or XTemplate configuration to insert in the field markup inside the label element (as attributes). ...

An optional string or `XTemplate` configuration to insert in the field markup inside the label element (as attributes). If an `XTemplate` is used, the component's render data serves as the context.


### labelCls

**Type:** String

The CSS class to be applied to the label element. ...

The CSS class to be applied to the label element. This (single) CSS class is used to formulate the renderSelector and drives the field layout where it is concatenated with a hyphen ('-') and labelAlign. To add additional classes, use labelClsExtra. Defaults to: `Ext.baseCSSPrefix + 'form-item-label'`


### labelClsExtra

**Type:** String

An optional string of one or more additional CSS classes to add to the label element. ...

An optional string of one or more additional CSS classes to add to the label element. Defaults to empty.


### labelConnector

**Type:** String

The string to use when joining the labels of individual sub-fields, when combineLabels is set to true. ...

The string to use when joining the labels of individual sub-fields, when combineLabels is set to true. Defaults to ', '. Defaults to: `', '`


### labelPad

**Type:** Number

The amount of space in pixels between the fieldLabel and the input field. ...

The amount of space in pixels between the fieldLabel and the input field. Defaults to: `5`


### labelSeparator

**Type:** String

Character(s) to be inserted at the end of the label text. ...

Character(s) to be inserted at the end of the label text. Set to empty string to hide the separator completely. Defaults to: `':'`


### labelStyle

**Type:** String

A CSS style specification string to apply directly to this field's label.


### labelWidth

**Type:** Number

The width of the fieldLabel in pixels. ...

The width of the fieldLabel in pixels. Only applicable if the labelAlign is set to "left" or "right". Defaults to: `100`


### labelableRenderTpl

**Type:** String/String[]/Ext.XTemplate

The rendering template for the field decorations. ...

The rendering template for the field decorations. Component classes using this mixin should include logic to use this as their renderTpl, and implement the getSubTplMarkup method to generate the field body content. The structure of a field is a table as follows: If `labelAlign: 'left',`msgTarget: 'side'` If `labelAlign: 'left',`msgTarget: 'under'` If `labelAlign: 'top',`msgTarget: 'side'` If `labelAlign: 'top',`msgTarget: 'under'` The total columns always the same for fields with each setting of labelAlign because when rendered into a Ext.layout.container.Form layout, just the `TR` of the table will be placed into the form's main `TABLE`, and the columns of all the siblings must match so that they all line up. In a Ext.layout.container.Form layout, different settings of labelAlign are not supported because of the incompatible column structure. When the triggerCell or side error cell are hidden or shown, the input cell's colspan is recalculated to maintain the correct 3 visible column count. Defaults to: `['<tr role="presentation" id="{id}-inputRow" <tpl if="inFormLayout">id="{id}"</tpl> class="{inputRowCls}">', '<tpl if="labelOnLeft">', '<td role="presentation" id="{id}-labelCell" style="{labelCellStyle}" {labelCellAttrs}>', '{beforeLabelTpl}', '<label id="{id}-labelEl" {labelAttrTpl}<tpl if="inputId"> for="{inputId}"</tpl> class="{labelCls}"', '<tpl if="labelStyle"> style="{labelStyle}"</tpl>', ' unselectable="on"', '>', '{beforeLabelTextTpl}', '<tpl if="fieldLabel">{fieldLabel}{labelSeparator}</tpl>', '{afterLabelTextTpl}', '</label>', '{afterLabelTpl}', '</td>', '</tpl>', '<td role="presentation" class="{baseBodyCls} {fieldBodyCls} {extraFieldBodyCls}" id="{id}-bodyEl" colspan="{bodyColspan}" role="presentation">', '{beforeBodyEl}', '<tpl if="labelAlign==\'top\'">', '{beforeLabelTpl}', '<div role="presentation" id="{id}-labelCell" style="{labelCellStyle}">', '<label id="{id}-labelEl" {labelAttrTpl}<tpl if="inputId"> for="{inputId}"</tpl> class="{labelCls}"', '<tpl if="labelStyle"> style="{labelStyle}"</tpl>', ' unselectable="on"', '>', '{beforeLabelTextTpl}', '<tpl if="fieldLabel">{fieldLabel}{labelSeparator}</tpl>', '{afterLabelTextTpl}', '</label>', '</div>', '{afterLabelTpl}', '</tpl>', '{beforeSubTpl}', '{[values.$comp.getSubTplMarkup(values)]}', '{afterSubTpl}', '<tpl if="msgTarget===\'side\'">', '{afterBodyEl}', '</td>', '<td role="presentation" id="{id}-sideErrorCell" vAlign="{[values.labelAlign===\'top\' && !values.hideLabel ? \'bottom\' : \'middle\']}" style="{[values.autoFitErrors ? \'display:none\' : \'\']}" width="{errorIconWidth}">', '<div role="presentation" id="{id}-errorEl" class="{errorMsgCls}" style="display:none"></div>', '</td>', '<tpl elseif="msgTarget==\'under\'">', '<div role="presentation" id="{id}-errorEl" class="{errorMsgClass}" colspan="2" style="display:none"></div>', '{afterBodyEl}', '</td>', '</tpl>', '</tr>', {disableFormats: true}]`


### layout

**Type:** Ext.enums.Layout/Object

private Important: In order for child items to be correctly sized and positioned, typically a layout manager must be...

private **Important**: In order for child items to be correctly sized and positioned, typically a layout manager **must** be specified through the `layout` configuration option. The sizing and positioning of child items is the responsibility of the Container's layout manager which creates and manages the type of layout you have in mind. For example: If the layout configuration is not explicitly specified for a general purpose container (e.g. Container or Panel) the default layout manager will be used which does nothing but render child components sequentially into the Container (no sizing or positioning will be performed in this situation). **layout** may be specified as either as an Object or as a String: Specify as an Object Example usage: - **type** The layout type to be used for this container. If not specified, a default Ext.layout.container.Auto will be created and used. Valid layout `type` values are listed in Ext.enums.Layout. - Layout specific configuration properties Additional layout specific configuration properties may also be specified. For complete details regarding the valid config options for each layout type, see the layout class corresponding to the `type` specified. Specify as a String Example usage: - **layout** The layout `type` to be used for this container (see Ext.enums.Layout for list of valid values). Additional layout specific configuration properties. For complete details regarding the valid config options for each layout type, see the layout class corresponding to the `layout` specified. Configuring the default layout type If a certain Container class has a default layout (For example a Toolbar with a default `Box` layout), then to simply configure the default layout, use an object, but without the `type` property: Defaults to: `'checkboxgroup'` Available since: 2.3.0 Overrides: Ext.container.AbstractContainer.layout


### listeners

**Type:** Object

A config object containing one or more event handlers to be added to this object during initialization. ...

A config object containing one or more event handlers to be added to this object during initialization. This should be a valid listeners config object as specified in the addListener example for attaching multiple handlers at once. **DOM events from Ext JS Components** While *some* Ext JS Component classes export selected DOM events (e.g. "click", "mouseover" etc), this is usually only done when extra value can be added. For example the DataView's **`itemclick`** event passing the node clicked on. To access DOM events directly from a child element of a Component, we need to specify the `element` option to identify the Component property to add a DOM listener to:


### loader

**Type:** Ext.ComponentLoader/Object

A configuration object or an instance of a Ext.ComponentLoader to load remote content for this Component. ...

A configuration object or an instance of a Ext.ComponentLoader to load remote content for this Component.


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


### minHeight

**Type:** Number

The minimum value in pixels which this Component will set its height to. ...

The minimum value in pixels which this Component will set its height to. **Warning:** This will override any size management applied by layout managers.


### minWidth

**Type:** Number

The minimum value in pixels which this Component will set its width to. ...

The minimum value in pixels which this Component will set its width to. **Warning:** This will override any size management applied by layout managers.


### msgTarget

**Type:** String

The location where the error message text should display. ...

The location where the error message text should display. Must be one of the following values: - `qtip` Display a quick tip containing the message when the user hovers over the field. This is the default. **Ext.tip.QuickTipManager.init must have been called for this setting to work.** - `title` Display the message in a default browser title attribute popup. - `under` Add a block div beneath the field containing the error message. - `side` Add an error icon to the right of the field, displaying the message in a popup on hover. - `none` Don't display any error message. This might be useful if you are implementing custom error display. - `[element id]` Add the error message directly to the innerHTML of the specified element. Defaults to: `'qtip'`


### name

**Type:** String

Overrides: Ext.form.field.Field.name


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


### padding

**Type:** Number/String

Specifies the padding for this component. ...

Specifies the padding for this component. The padding can be a single numeric value to apply to all sides or it can be a CSS style specification for each style, for example: '10 5 3 10' (top, right, bottom, left).


### plugins

**Type:** Ext.AbstractPlugin[]/Ext.AbstractPlugin/Object[]/Object/Ext.enums.Plugin[]/Ext.enums.Plugin

An array of plugins to be added to this component. ...

An array of plugins to be added to this component. Can also be just a single plugin instead of array. Plugins provide custom functionality for a component. The only requirement for a valid plugin is that it contain an `init` method that accepts a reference of type Ext.Component. When a component is created, if any plugins are available, the component will call the init method on each plugin, passing a reference to itself. Each plugin can then call methods or respond to events on the component as needed to provide its functionality. Plugins can be added to component by either directly referencing the plugin instance: By using config object with ptype: Or with just a ptype: See Ext.enums.Plugin for list of all ptypes. Available since: 2.3.0


### preventMark

**Type:** Boolean

true to disable displaying any error message set on this object. ...

true to disable displaying any error message set on this object. Defaults to: `false`


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

End Definitions An XTemplate used to create the internal structure inside this Component's encapsulating Element. ...

End Definitions An XTemplate used to create the internal structure inside this Component's encapsulating Element. You do not normally need to specify this. For the base classes Ext.Component and Ext.container.Container, this defaults to **`null`** which means that they will be initially rendered with no internal structure; they render their Element empty. The more specialized Ext JS and Sencha Touch classes which use a more complex DOM structure, provide their own template definitions. This is intended to allow the developer to create application-specific utility Components with customized internal structure. Upon rendering, any created child elements may be automatically imported into object properties using the renderSelectors and childEls options. Defaults to: `'{%this.renderContainer(out,values)%}'` Overrides: Ext.AbstractComponent.renderTpl


### resizable

**Type:** Boolean/Object

Specify as true to apply a Resizer to this Component after rendering. ...

Specify as `true` to apply a Resizer to this Component after rendering. May also be specified as a config object to be passed to the constructor of Resizer to override any defaults. By default the Component passes its minimum and maximum size, and uses `Ext.resizer.Resizer.dynamic: false`


### resizeHandles

**Type:** String

A valid Ext.resizer.Resizer handles config string. ...

A valid Ext.resizer.Resizer handles config string. Only applies when resizable = true. Defaults to: `'all'`


### rtl

**Type:** Boolean

True to layout this component and its descendants in "rtl" (right-to-left) mode. ...

True to layout this component and its descendants in "rtl" (right-to-left) mode. Can be explicitly set to false to override a true value inherited from an ancestor. **Defined in override Ext.rtl.AbstractComponent.**


### saveDelay

**Type:** Number

A buffer to be applied if many state events are fired within a short period. ...

A buffer to be applied if many state events are fired within a short period. Defaults to: `100`


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


### submitValue

**Type:** Boolean

Setting this to false will prevent the field from being submitted even when it is not disabled. ...

Setting this to false will prevent the field from being submitted even when it is not disabled. Defaults to: `true`


### suspendLayout

**Type:** Boolean

If true, suspend calls to doLayout. ...

If true, suspend calls to doLayout. Useful when batching multiple adds to a container and not passing them as multiple arguments or an array. Defaults to: `false`


### toFrontOnShow

**Type:** Boolean

True to automatically call toFront when the show method is called on an already visible, floating component. ...

True to automatically call toFront when the show method is called on an already visible, floating component. Defaults to: `true`


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


### validateOnChange

**Type:** Boolean

Specifies whether this field should be validated immediately whenever a change in its value is detected. ...

Specifies whether this field should be validated immediately whenever a change in its value is detected. If the validation results in a change in the field's validity, a validitychange event will be fired. This allows the field to show feedback about the validity of its contents immediately as the user is typing. When set to false, feedback will not be immediate. However the form will still be validated before submitting if the clientValidation option to Ext.form.Basic.doAction is enabled, or if the field or form are validated manually. See also Ext.form.field.Base.checkChangeEvents for controlling how changes to the field's value are detected. Defaults to: `true`


### value

**Type:** Object

A value to initialize this field with.


### vertical

**Type:** Boolean

True to distribute contained controls across columns, completely filling each column top to bottom before starting on...

True to distribute contained controls across columns, completely filling each column top to bottom before starting on the next column. The number of controls in each column will be automatically calculated to keep columns as even as possible. The default value is false, so that controls will be added to columns one at a time, completely filling each row left to right before starting on the next row. Defaults to: `false`


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


### autoEl

**Type:** Object

...

Defaults to: `{tag: 'table', cellpadding: 0}`


### autoGenId

**Type:** Boolean

true indicates an id was auto-generated rather than provided by configuration. ...

`true` indicates an `id` was auto-generated rather than provided by configuration. Defaults to: `false`


### bodyEl

**Type:** Ext.Element

The div Element wrapping the component's contents. ...

The div Element wrapping the component's contents. Only available after the component has been rendered.


### borderBoxCls

**Type:** String

private ...

private Defaults to: `Ext.baseCSSPrefix + 'border-box'`


### bubbleEvents

**Type:** Array

...

Defaults to: `[]`


### childEls

**Type:** Array

...

Defaults to: `['containerEl']` Overrides: Ext.form.Labelable.childEls


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

The name of the padding property that is used by the layout to manage padding. See managePadding Defaults to: `'padding'`


### convertPositionSpec

**Type:** Object

By default this method does nothing but return the position spec passed to it. ...

By default this method does nothing but return the position spec passed to it. In rtl mode it is overridden to convert "l" to "r" and vice versa when required.


### customOverflowEl

**Type:** String

Used by the layout system, typically the scrolling el is the targetEl, however we need to let it know we're using som...

Used by the layout system, typically the scrolling el is the targetEl, however we need to let it know we're using something different Defaults to: `'containerEl'`


### defaultComponentLayoutType

**Type:** String

...

Defaults to: `'autocomponent'`


### deferLayouts

**Type:** Boolean

...

Defaults to: `false`


### draggable

**Type:** Boolean

Indicates whether or not the component can be dragged. ...

Indicates whether or not the component can be dragged. Defaults to: `false`


### errorEl

**Type:** Ext.Element

The div Element that will contain the component's error message(s). ...

The div Element that will contain the component's error message(s). Note that depending on the configured msgTarget, this element may be hidden in favor of some other form of presentation, but will always be present in the DOM for use by assistive technologies.


### eventsSuspended

**Type:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called. Defaults to: `0`


### extraFieldBodyCls

**Type:** String

private ...

private Defaults to: `Ext.baseCSSPrefix + 'form-checkboxgroup-body'`


### fieldSubTpl

**Type:** String

...

Defaults to: `'<div id="{id}-containerEl" class="{containerElCls}">{%this.renderContainer(out,values)%}</div>'`


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


### groupCls

**Type:** String

private ...

private Defaults to: `Ext.baseCSSPrefix + 'form-radio-group'` Overrides: Ext.form.CheckboxGroup.groupCls


### hasListeners

**Type:** Object

This object holds a key for any event that has a listener. ...

This object holds a key for any event that has a listener. The listener may be set directly on the instance, or on its class or a super class (via observe) or on the MVC EventBus. The values of this object are truthy (a non-zero number) and falsy (0 or undefined). They do not represent an exact count of listeners. The value for an event is truthy if the event must be fired and is falsy if there is no need to fire the event. The intended use of this property is to avoid the expense of fireEvent calls when there are no listeners. This can be particularly helpful when one would otherwise have to call fireEvent hundreds or thousands of times. It is used like this:


### horizontalPosProp

**Type:** String

...

Defaults to: `'left'`


### htmlActiveErrorsTpl

**Type:** Array

...

Defaults to: `['<tpl if="errors && errors.length">', '<ul class="{listCls}"><tpl for="errors"><li role="alert">{.}</li></tpl></ul>', '</tpl>']`


### initConfigList

**Type:** Array

...

Defaults to: `[]`


### initConfigMap

**Type:** Object

...

Defaults to: `{}`


### inputRowCls

**Type:** String

private ...

private Defaults to: `Ext.baseCSSPrefix + 'form-item-input-row'`


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


### isFieldLabelable

**Type:** Boolean

Flag denoting that this object is labelable as a field. ...

Flag denoting that this object is labelable as a field. Always true. Defaults to: `true`


### isFormField

**Type:** Boolean

Flag denoting that this component is a Field. ...

Flag denoting that this component is a Field. Always true. Defaults to: `true`


### isInstance

**Type:** Boolean

...

Defaults to: `true`


### isObservable

**Type:** Boolean

true in this class to identify an object as an instantiated Observable, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Observable, or subclass thereof. Defaults to: `true`


### isQueryable

**Type:** Boolean

...

Defaults to: `true`


### items

**Type:** Ext.util.AbstractMixedCollection

The MixedCollection containing all the child items of this container.

The MixedCollection containing all the child items of this container. Available since: 2.3.0


### labelCell

**Type:** Ext.Element

The <TD> Element which contains the label Element for this component. ...

The `<TD>` Element which contains the label Element for this component. Only available after the component has been rendered.


### labelEl

**Type:** Ext.Element

The label Element for this component. ...

The label Element for this component. Only available after the component has been rendered.


### labelableInsertions

**Type:** Array

...

Defaults to: `['beforeBodyEl', 'afterBodyEl', 'beforeLabelTpl', 'afterLabelTpl', 'beforeSubTpl', 'afterSubTpl', 'beforeLabelTextTpl', 'afterLabelTextTpl', 'labelAttrTpl']`


### labelableRenderProps

**Type:** Array

This is an array to avoid a split on every call to Ext.copyTo ...

This is an array to avoid a split on every call to Ext.copyTo Defaults to: `['allowBlank', 'id', 'labelAlign', 'fieldBodyCls', 'extraFieldBodyCls', 'baseBodyCls', 'clearCls', 'labelSeparator', 'msgTarget', 'inputRowCls']`


### layoutCounter

**Type:** Number

The number of container layout calls made on this object. ...

The number of container layout calls made on this object. Defaults to: `0`


### layoutSuspendCount

**Type:** Number

...

Defaults to: `0`


### maskOnDisable

**Type:** Boolean

This is an internal flag that you use when creating custom components. ...

This is an internal flag that you use when creating custom components. By default this is set to `true` which means that every component gets a mask when it's disabled. Components like FieldContainer, FieldSet, Field, Button, Tab override this property to `false` since they want to implement custom disable logic. Defaults to: `false` Overrides: Ext.AbstractComponent.maskOnDisable


### noWrap

**Type:** Boolean

Tells the layout system that the height can be measured immediately because the width does not need setting. ...

Tells the layout system that the height can be measured immediately because the width does not need setting. Defaults to: `true`


### offsetsCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'hide-offsets'`


### originalValue

**Type:** Object

The original value of the field as configured in the value configuration, or as loaded by the last form load operatio...

The original value of the field as configured in the value configuration, or as loaded by the last form load operation if the form's trackResetOnLoad setting is `true`.


### ownerCt

**Type:** Ext.Container

This Component's owner Container (is set automatically when this Component is added to a Container). ...

This Component's owner Container (is set automatically when this Component is added to a Container). *Important.* This is not a universal upwards navigation pointer. It indicates the Container which owns and manages this Component if any. There are other similar relationships such as the button which activates a menu, or the menu item which activated a submenu, or the column header which activated the column menu. These differences are abstracted away by the up method. **Note**: to access items within the Container see itemId. Available since: 2.3.0


### plaintextActiveErrorsTpl

**Type:** Array

...

Defaults to: `['<tpl if="errors && errors.length">', '<tpl for="errors"><tpl if="xindex &gt; 1">\n</tpl>{.}</tpl>', '</tpl>']`


### rendered

**Type:** Boolean

Indicates whether or not the component has been rendered. ...

Indicates whether or not the component has been rendered. Defaults to: `false` Available since: 1.1.0


### scrollFlags

**Type:** Object

An object property which provides unified information as to which dimensions are scrollable based upon the autoScroll...

An object property which provides unified information as to which dimensions are scrollable based upon the autoScroll, overflowX and overflowY settings (And for *views* of trees and grids, the owning panel's scroll setting). Note that if you set overflow styles using the style config or bodyStyle config, this object does not include that information; it is best to use autoScroll, overflowX and overflowY if you need to access these flags. This object has the following properties: x : Boolean`true` if this Component is scrollable horizontally - style setting may be `'auto'` or `'scroll'`.


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### suspendCheckChange

**Type:** Number

...

Defaults to: `0`


### weight

**Type:** Number

...

Defaults to: `0`


### xhooks

**Type:** Object


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


### Ext.form.RadioGroup

Creates new Component. ...

Creates new Component.

**Parameters:** - config : Ext.Element/String/ObjectThe configuration options may be specified as either: **an element** : it is set as the internal element and its id used as the component id - **a string** : it is assumed to be the id of an existing element and is used as the component id - **anything else** : it is assumed to be a standard config object and is applied to the component


### add

Adds Component(s) to this Container. ...

Adds Component(s) to this Container. Description: - Fires the beforeadd event before adding. - The Container's default config values will be applied accordingly (see `defaults` for details). - Fires the `add` event after the component has been added. Notes: If the Container is **already rendered** when `add` is called, it will render the newly added Component into its content area. **If** the Container was configured with a size-managing layout manager, the Container will recalculate its internal layout at this time too. Note that the default layout manager simply renders child Components sequentially into the content area and thereafter performs no sizing. If adding multiple new child Components, pass them as an array to the `add` method, so that only one layout recalculation is performed. To inject components between existing ones, use the insert method. Warning: Components directly managed by the BorderLayout layout manager may not be removed or added. See the Notes for BorderLayout for more details. Available since: 2.3.0

**Parameters:** component : Ext.Component[]|Object[]/Ext.Component.../Object...Either one or more Components to add or an Array of Components to add. See `items` for additional information.


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


### addUIClsToElement

Method which adds a specified UI + uiCls to the components element. ...

Method which adds a specified UI + `uiCls` to the components element. Can be overridden to remove the UI from more than just the components element.

**Parameters:** ui : StringThe UI to remove from the element.


### addUIToElement

Method which adds a specified UI to the components element. ...

Method which adds a specified UI to the components element.


### adjustForConstraints

private ==> used outside of core TODO: currently only used by ToolTip. ...

private ==> used outside of core TODO: currently only used by ToolTip. does this method belong here?

**Parameters:** xy : Object


### adjustPosition

...

**Parameters:** x : Object


### afterComponentLayout

Called by the layout system after the Component has been laid out. ...

Called by the layout system after the Component has been laid out. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterFirstLayout

...

**Parameters:** width : Object


### afterHide

Invoked after the Component has been hidden. ...

Invoked after the Component has been hidden. Gets passed the same `callback` and `scope` parameters that onHide received. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterLayout

Invoked after the Container has laid out (and rendered if necessary) its child Components. ...

Invoked after the Container has laid out (and rendered if necessary) its child Components. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


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


### batchChanges

A utility for grouping a set of modifications which may trigger value changes into a single transaction, to prevent e...

A utility for grouping a set of modifications which may trigger value changes into a single transaction, to prevent excessive firing of change events. This is useful for instance if the field has sub-fields which are being updated as a group; you don't want the container field to check its own changed state for each subfield change.

**Parameters:** fn : ObjectA function containing the transaction code


### beforeBlur

Template method to do any pre-blur processing. ...

Template method to do any pre-blur processing.

**Parameters:** e : Ext.EventObjectThe event object


### beforeComponentLayout

Occurs before componentLayout is run. ...

Occurs before `componentLayout` is run. Returning `false` from this method will prevent the `componentLayout` from being executed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeDestroy

...

Overrides: Ext.container.AbstractContainer.beforeDestroy, Ext.panel.Panel.beforeDestroy


### beforeFocus

Template method to do any pre-focus processing. ...

Template method to do any pre-focus processing.

**Parameters:** e : Ext.EventObjectThe event object


### beforeLayout

Occurs before componentLayout is run. ...

Occurs before componentLayout is run. In previous releases, this method could return `false` to prevent its layout but that is not supported in Ext JS 4.1 or higher. This method is simply a notification of the impending layout to give the component a chance to adjust the DOM. Ideally, DOM reads should be avoided at this time to reduce expensive document reflows. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeRender

...

Overrides: Ext.Component.beforeRender


### beforeReset

Template method before a field is reset. ...

Template method before a field is reset.


### beforeSetPosition

Template method called before a Component is positioned. ...

Template method called before a Component is positioned. Ensures that the position is adjusted so that the Component is constrained if so configured.

**Parameters:** x : Object


### beforeShow

Invoked before the Component is shown. ...

Invoked before the Component is shown. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### blur

...

**Returns:** Ext.Componentthis


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


### checkChange

Checks whether the value of the field has changed since the last time it was checked. ...

Checks whether the value of the field has changed since the last time it was checked. If the value has changed, it: - Fires the change event, - Performs validation if the validateOnChange config is enabled, firing the validitychange event if the validity has changed, and - Checks the dirty state of the field and fires the dirtychange event if it has changed. Overrides: Ext.form.field.Field.checkChange


### checkDirty

Checks the isDirty state of the field and if it has changed since the last time it was checked, fires the dirtychange...

Checks the isDirty state of the field and if it has changed since the last time it was checked, fires the dirtychange event.


### child

Retrieves the first direct child of this container which matches the passed selector or component. ...

Retrieves the first direct child of this container which matches the passed selector or component. The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.

**Parameters:** selector : String/Ext.Component (optional)An Ext.ComponentQuery selector. If no selector is specified, the first child will be returned.


### clearInvalid

Clear any invalid styles/messages for this field. ...

Clear any invalid styles/messages for this field. Components using this mixin should implement this method to update the components rendering to clear any existing messages. **Note**: this method does not cause the Field's validate or isValid methods to return `true` if the value does not *pass* validation. So simply clearing a field's errors will not necessarily allow submission of forms submitted with the Ext.form.action.Submit.clientValidation option set.


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


### configClass

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


### convertPositionSpec

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**

**Parameters:** posSpec : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### deleteMembers

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### detachComponent

Detach a component from the DOM ...

Detach a component from the DOM

**Parameters:** component : Object


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


### doRenderFramingDockedItems

...

**Parameters:** out : Object


### down

Retrieves the first descendant of this container which matches the passed selector. ...

Retrieves the first descendant of this container which matches the passed selector. The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.

**Parameters:** selector : String/Ext.Component (optional)An Ext.ComponentQuery selector or Ext.Component. If no selector is specified, the first child will be returned.


### eachBox

Convenience function which calls the given function for every checkbox in the group ...

Convenience function which calls the given function for every checkbox in the group

**Parameters:** fn : FunctionThe function to call


### enable

Enable all immediate children that was previously disabled Override enable because onEnable only gets called when ren...

Enable all immediate children that was previously disabled Override enable because onEnable only gets called when rendered Enable the component Available since: 1.1.0

**Parameters:** silent : Boolean (optional)Passing `true` will suppress the `enable` event from being fired. Defaults to: `false`


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if present. There is no implementation in the Observable base class. This is commonly used by Ext.Components to bubble events to owner Containers. See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the Component's immediate owner. But if a known target is required, this can be overridden to access the required target more quickly. Example:

**Parameters:** eventNames : String/String[]The event name to bubble, or an Array of event names.


### ensureAttachedToBody

Ensures that this component is attached to document.body. ...

Ensures that this component is attached to `document.body`. If the component was rendered to Ext.getDetachedBody, then it will be appended to `document.body`. Any configured position is also restored.

**Parameters:** runLayout : Boolean (optional)True to run the component's layout. Defaults to: `false`


### extractFileInput

Only relevant if the instance's isFileUpload method returns true. ...

Only relevant if the instance's isFileUpload method returns true.

**Returns:** a reference to the file input DOM element holding the user's selected file. The input will be appended into the submission form and will not be returned, so this method should also create a replacement. ReturnsHTMLElement


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


### getActiveError

Gets the active error message for this component, if any. ...

Gets the active error message for this component, if any. This does not trigger validation on its own, it merely returns any message that the component may already hold.

**Returns:** StringThe active error message on the component; if there is no error, an empty string is returned.


### getActiveErrors

Gets an Array of any active error messages currently applied to the field. ...

Gets an Array of any active error messages currently applied to the field. This does not trigger validation on its own, it merely returns any messages that the component may already hold.

**Returns:** String[]The active error messages on the component; if there are no errors, an empty Array is returned.


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


### getBodyColspan

Calculates the colspan value for the body cell - the cell which contains the input field. ...

Calculates the colspan value for the body cell - the cell which contains the input field. The field table structure contains 4 columns:


### getBorderPadding

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Returns:** the size of the element's borders and padding. ReturnsObjectan object with the following numeric properties - beforeX - afterX - beforeY - afterY


### getBox

Return an object defining the area of this Element which can be passed to setBox to set another Element's size/locati...

Return an object defining the area of this Element which can be passed to setBox to set another Element's size/location to match this element.

**Parameters:** contentBox : Boolean (optional)If true a box for the content of the element is returned.


### getBoxes

Returns all checkbox components within the container ...

**Parameters:** query : String (optional)An additional query to add to the selector.

**Returns:** all checkbox components within the container


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getBubbleTarget

Implements an upward event bubbling policy. ...

Implements an upward event bubbling policy. By default a Component bubbles events up to its reference owner. Component subclasses may implement a different bubbling strategy by overriding this method. Overrides: Ext.AbstractComponent.getBubbleTarget


### getChecked

Returns an Array of all checkboxes in the container which are currently checked ...

**Returns:** an Array of all checkboxes in the container which are currently checked ReturnsExt.form.field.Checkbox[]Array of Ext.form.field.Checkbox components


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


### getCombinedErrors

Takes an Array of invalid Ext.form.field.Field objects and builds a combined list of error messages from them. ...

Takes an Array of invalid Ext.form.field.Field objects and builds a combined list of error messages from them. Defaults to prepending each message by the field name and a colon. This can be overridden to provide custom combined error message handling, for instance changing the format of each message or sorting the array (it is sorted in order of appearance by default).

**Parameters:** invalidFields : Ext.form.field.Field[]An Array of the sub-fields which are currently invalid.


### getComponent

Examines this container's items property and gets a direct child component of this container. ...

Examines this container's items **property** and gets a direct child component of this container. Available since: 2.3.0

**Parameters:** - comp : String/NumberThis parameter may be any of the following: a **String** : representing the itemId or id of the child component. - a **Number** : representing the position of the child component within the items **property** For additional information see Ext.util.MixedCollection.get.


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


### getDragEl

...


### getEl

Retrieves the top level element representing this component. ...

Retrieves the top level element representing this component. Available since: 1.1.0

**Returns:** Ext.dom.Element


### getElConfig

...


### getErrorMsgCls

...


### getErrors

Runs CheckboxGroup's validations and returns an array of any errors. ...

Runs CheckboxGroup's validations and returns an array of any errors. The only error by default is if allowBlank is set to true and no items are checked.

**Returns:** String[]Array of all validation errors


### getFieldLabel

Returns the combined field label if combineLabels is set to true and if there is no set fieldLabel. ...

**Returns:** the combined field label if combineLabels is set to true and if there is no set fieldLabel. Otherwise returns the fieldLabel like normal. You can also override this method to provide a custom generated label. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


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


### getHeight

Gets the current height of the component's underlying element. ...

Gets the current height of the component's underlying element.

**Returns:** Number


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


### getInputId

Get the input id, if any, for this component. ...

Get the input id, if any, for this component. This is used as the "for" attribute on the label element. Implementing subclasses may also use this as e.g. the id for their own input element.

**Returns:** StringThe input id


### getInsertPosition

This function takes the position argument passed to onRender and returns a DOM element that you can use in the insert...

This function takes the position argument passed to onRender and returns a DOM element that you can use in the insertBefore.

**Parameters:** position : String/Number/Ext.dom.Element/HTMLElementIndex, element id or element you want to put this component before.


### getInsertionRenderData

...

**Parameters:** data : Object


### getItemId

Returns the value of itemId assigned to this component, or when that is not set, returns the value of id. ...

**Returns:** the value of itemId assigned to this component, or when that is not set, returns the value of id. ReturnsString


### getLabelCellAttrs

...


### getLabelCellStyle

...


### getLabelCls

...


### getLabelStyle

Gets any label styling for the labelEl ...

Gets any label styling for the labelEl

**Returns:** StringThe label styling


### getLabelWidth

Gets the width of the label (if visible) ...

Gets the width of the label (if visible)

**Returns:** NumberThe label width


### getLabelableRenderData

Generates the arguments for the field decorations rendering template. ...

Generates the arguments for the field decorations rendering template.

**Returns:** ObjectThe template arguments


### getLayout

Returns the layout instance currently associated with this Container. ...

**Returns:** the layout instance currently associated with this Container. If a layout has not been instantiated yet, that is done first ReturnsExt.layout.container.ContainerThe layout


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


### getMaskTarget

...


### getModelData

Don't return any data for the model; the form will get the info from the individual checkboxes themselves. ...

Don't return any data for the model; the form will get the info from the individual checkboxes themselves.

**Returns:** the value(s) that should be saved to the Ext.data.Model instance for this field, when Ext.form.Basic.updateRecord is called. Typically this will be an object with a single name-value pair, the name being this field's name and the value being its current data value. More advanced field implementations may return more than one name-value pair. The returned values will be saved to the corresponding field names in the Model. Note that the values returned from this method are not guaranteed to have been successfully validated. ReturnsObjectA mapping of submit parameter names to values; each value should be a string, or an array of strings if that particular name has multiple values. It can also return null if there are no parameters to be submitted.


### getName

Returns the name attribute of the field. ...

**Returns:** the name attribute of the field. This is used as the parameter name when including the field value in a form submit(). ReturnsStringname The field name


### getOffsetsTo

Returns the offsets of this element from the passed element. ...

**Parameters:** offsetsTo : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or element id to get get the offsets from.

**Returns:** the offsets of this element from the passed element. The element must both be part of the DOM tree and not have display:none to have page coordinates.


### getOuterSize

Include margins ...

Include margins


### getOverflowEl

Get an el for overflowing, defaults to the target el ...

Get an el for overflowing, defaults to the target el Overrides: Ext.AbstractComponent.getOverflowEl


### getOverflowStyle

Returns the CSS style object which will set the Component's scroll styles. ...

**Returns:** the CSS style object which will set the Component's scroll styles. This must be applied to the target element.


### getOwningBorderContainer

Returns the owning container if that container uses border layout. ...

**Returns:** the owning container if that container uses `border` layout. Otherwise this method returns `null`. **Defined in override Ext.layout.container.border.Region.** ReturnsExt.container.ContainerThe owning border container or `null`.


### getOwningBorderLayout

Returns the owning border (Ext.layout.container.Border) instance if there is one. ...

**Returns:** the owning `border` (`Ext.layout.container.Border`) instance if there is one. Otherwise this method returns `null`. **Defined in override Ext.layout.container.border.Region.** ReturnsExt.layout.container.BorderThe owning border layout or `null`.


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


### getProxy

...


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


### getStyleProxy

Returns an offscreen div with the same class name as the element this is being rendered. ...

**Parameters:** cls : Object

**Returns:** an offscreen div with the same class name as the element this is being rendered. This is because child item rendering takes place in a detached div which, being not part of the document, has no styling.


### getSubTplData

...


### getSubTplMarkup

Gets the markup to be inserted into the outer template's bodyEl. ...

Gets the markup to be inserted into the outer template's bodyEl. Defaults to empty string, should be implemented by classes including this mixin as needed.

**Returns:** StringThe markup to be inserted


### getSubmitData

Don't return any data for submit; the form will get the info from the individual checkboxes themselves. ...

Don't return any data for submit; the form will get the info from the individual checkboxes themselves.

**Returns:** the parameter(s) that would be included in a standard form submit for this field. Typically this will be an object with a single name-value pair, the name being this field's name and the value being its current stringified value. More advanced field implementations may return more than one name-value pair. Note that the values returned from this method are not guaranteed to have been successfully validated. ReturnsObjectA mapping of submit parameter names to values; each value should be a string, or an array of strings if that particular name has multiple values. It can also return null if there are no parameters to be submitted.


### getTargetEl

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. ...

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. Overrides: Ext.AbstractComponent.getTargetEl


### getTpl

...

**Parameters:** name : Object


### getValue

Returns an object containing the values of all checked checkboxes within the group. ...

**Returns:** an object containing the values of all checked checkboxes within the group. Each key-value pair in the object corresponds to a checkbox name. If there is only one checked checkbox with a particular name, the value of that pair will be the String inputValue of that checkbox. If there are multiple checked checkboxes with that name, the value of that pair will be an Array of the selected inputValues. The object format returned from this method can also be passed directly to the setValue method. NOTE: In Ext 3, this method returned an array of Checkbox components; this was changed to make it more consistent with other field components and with the setValue argument signature. If you need the old behavior in Ext 4+, use the getChecked method instead. Overrides: Ext.form.field.Field.getValue


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


### handleFieldErrorChange

Handle bubbled errorchange events from descendants; invoke the aggregated event and method ...

Handle bubbled errorchange events from descendants; invoke the aggregated event and method

**Parameters:** labelable : Object


### handleFieldValidityChange

Handle bubbled validitychange events from descendants; invoke the aggregated event and method ...

Handle bubbled validitychange events from descendants; invoke the aggregated event and method

**Parameters:** field : Object


### hasActiveError

Tells whether the field currently has an active error message. ...

Tells whether the field currently has an active error message. This does not trigger validation on its own, it merely looks for any message that the component may already hold.

**Returns:** Boolean


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


### hasUICls

Checks if there is currently a specified uiCls. ...

Checks if there is currently a specified `uiCls`.

**Parameters:** cls : StringThe `cls` to check.


### hasVisibleLabel

Checks if the field has a visible label ...

Checks if the field has a visible label

**Returns:** BooleanTrue if the field has a visible label


### hide

Hides this Component, setting it to invisible using the configured hideMode. ...

Hides this Component, setting it to invisible using the configured hideMode.

**Parameters:** animateTarget : String/Ext.Element/Ext.Component (optional)only valid for floating Components such as Windows or ToolTips, or regular Components which have been configured with `floating: true`.. The target to which the Component should animate while hiding. Defaults to: `null`


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


### initDraggable

...


### initEvents

Initialize any events on this component ...

Initialize any events on this component


### initField

Initializes this Field mixin on the current instance. ...

Initializes this Field mixin on the current instance. Components using this mixin should call this method during their own initialization process.


### initFieldAncestor

Initializes the FieldAncestor's state; this must be called from the initComponent method of any components importing ...

Initializes the FieldAncestor's state; this must be called from the initComponent method of any components importing this mixin.


### initFieldDefaults

Initialize the fieldDefaults object ...

Initialize the fieldDefaults object


### initFrame

...


### initFramingTpl

Poke in a reference to applyRenderTpl(frameInfo, out) ...

Poke in a reference to applyRenderTpl(frameInfo, out)

**Parameters:** table : Object


### initHierarchyEvents

...


### initHierarchyState

Called by getHierarchyState to initialize the hierarchyState the first time it is requested. ...

Called by getHierarchyState to initialize the hierarchyState the first time it is requested. **Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** hierarchyState : Object


### initItems

...


### initLabelable

Performs initialization of this mixin. ...

Performs initialization of this mixin. Component classes using this mixin should call this method during their own initialization.


### initMonitor

...


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

**Parameters:** resizable : Object


### initState

Initializes the state of the object upon construction. ...

Initializes the state of the object upon construction.


### initStyles

Applies padding, margin, border, top, left, height, and width configs to the appropriate elements. ...

Applies padding, margin, border, top, left, height, and width configs to the appropriate elements.

**Parameters:** targetEl : Object


### initValue

Initializes the field's value based on the initial config. ...

Initializes the field's value based on the initial config. If the value config is specified then we use that to set the value; otherwise we initialize the originalValue by querying the values of all sub-checkboxes after they have been initialized. Overrides: Ext.form.field.Field.initValue


### insert

Inserts a Component into this Container at a specified index. ...

Inserts a Component into this Container at a specified index. Fires the beforeadd event before inserting, then fires the add event after the Component has been inserted. Available since: 2.3.0

**Parameters:** index : NumberThe index at which the Component will be inserted into the Container's items collection


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


### isDirty

private override Returns true if the value of this Field has been changed from its originalValue. ...

private override

**Returns:** true if the value of this Field has been changed from its originalValue. Will always return false if the field is disabled. Note that if the owning form was configured with trackResetOnLoad then the originalValue is updated when the values are loaded by Ext.form.Basic.setValues. ReturnsBooleanTrue if this field has been changed from its original value (and is not disabled), false otherwise.


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


### isEqual

private override - the group value is a complex object, compare using object serialization Returns whether two field...

private override - the group value is a complex object, compare using object serialization

**Parameters:** value1 : ObjectThe first value to compare

**Returns:** whether two field values are logically equal. Field implementations may override this to provide custom comparison logic appropriate for the particular field's data type.


### isEqualAsString

Returns whether two values are logically equal. ...

**Parameters:** value1 : ObjectThe first value to compare

**Returns:** whether two values are logically equal. Similar to isEqual, however null or undefined values will be treated as empty strings.


### isFileUpload

Returns whether this Field is a file upload field; if it returns true, forms will use special techniques for submitti...

**Returns:** whether this Field is a file upload field; if it returns true, forms will use special techniques for submitting the form via AJAX. See Ext.form.Basic.hasUpload for details. If this returns true, the extractFileInput method must also be implemented to return the corresponding file input element. ReturnsBoolean


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

Determines whether this Component is the root of a layout. This returns `true` if this component can run its layout without assistance from or impact on its owner. If this component cannot run its layout given these restrictions, `false` is returned and its owner will be considered as the next candidate for the layout root. Setting the _isLayoutRoot property to `true` causes this method to always return `true`. This may be useful when updating a layout of a Container which shrink wraps content, and you know that it will not change size, and so can safely be the topmost participant in the layout run.


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


### isValid

Returns whether or not the field value is currently valid by validating the field's current value. ...

**Returns:** whether or not the field value is currently valid by validating the field's current value. The validitychange event will not be fired; use validate instead if you want the event to fire. **Note**: disabled fields are always treated as valid. Implementations are encouraged to ensure that this method does not have side-effects such as triggering error message display. ReturnsBooleanTrue if the value is valid, else false


### isVisible

Returns true if this component is visible. ...

**Parameters:** deep : Boolean (optional)Pass `true` to interrogate the visibility status of all parent Containers to determine whether this Component is truly visible to the user. Generally, to determine whether a Component is hidden, the no argument form is needed. For example when creating dynamically laid out UIs in a hidden Container before showing them. Defaults to: `false`

**Returns:** `true` if this component is visible. Available since: 1.1.0


### isXType

Tests whether or not this Component is of a specific xtype. ...

Tests whether or not this Component is of a specific xtype. This can test whether this Component is descended from the xtype (default) or whether it is directly of the xtype specified (`shallow = true`). If using your own subclasses, be aware that a Component must register its own xtype to participate in determination of inherited xtypes. For a list of all available xtypes, see the Ext.Component header. Example usage: Available since: 2.3.0

**Parameters:** xtype : StringThe xtype to check for this Component


### lookupComponent

...

**Parameters:** comp : Object


### makeFloating

...

**Parameters:** dom : Object


### markInvalid

Associate one or more error messages with this field. ...

Associate one or more error messages with this field. Components using this mixin should implement this method to update the component's rendering to display the messages. **Note**: this method does not cause the Field's validate or isValid methods to return `false` if the value does *pass* validation. So simply marking a Field as invalid will not prevent submission of forms submitted with the Ext.form.action.Submit.clientValidation option set.

**Parameters:** errors : String/String[]The error message(s) for the field.


### mask

...


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

When a checkbox is added to the group, monitor it for changes ...

When a checkbox is added to the group, monitor it for changes

**Parameters:** field : Object


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

**Parameters:** width : Object


### onChange

Called when the field's value changes. ...

Called when the field's value changes. Performs validation if the validateOnChange config is enabled, and invokes the dirty check.

**Parameters:** newVal : Object


### onChildFieldAdd

...

**Parameters:** field : Object


### onChildFieldRemove

...

**Parameters:** field : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onDestroy

Allows addition of behavior to the destroy operation. ...

Allows addition of behavior to the destroy operation. After calling the superclass's onDestroy, the Component will be destroyed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onDirtyChange

Called when the field's dirty state changes. ...

Called when the field's dirty state changes.

**Parameters:** isDirty : Boolean


### onDisable

Allows addition of behavior to the disable operation. ...

Allows addition of behavior to the disable operation. After calling the superclass's `onDisable`, the Component will be disabled. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onEnable

Allows addition of behavior to the enable operation. ...

Allows addition of behavior to the enable operation. After calling the superclass's `onEnable`, the Component will be enabled. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onFieldErrorChange

Fired when the error message of any field within the container changes, and updates the combined error message to match. ...

Fired when the error message of any field within the container changes, and updates the combined error message to match.

**Parameters:** field : Object


### onFieldValidityChange

Fired when the validity of any field within the container changes. ...

Fired when the validity of any field within the container changes.

**Parameters:** field : Ext.form.field.FieldThe sub-field whose validity changed


### onFloatShow

...


### onFocus

private ...

private

**Parameters:** e : Object


### onHide

Possibly animates down to a target element. ...

Possibly animates down to a target element. Allows addition of behavior to the hide operation. After calling the superclass’s onHide, the Component will be hidden. Gets passed the same parameters as hide. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onKeyDown

Listen for TAB events and wrap round if tabbing of either end of the Floater ...

Listen for TAB events and wrap round if tabbing of either end of the Floater

**Parameters:** e : Object


### onMouseDown

Mousedown brings to front, and programatically grabs focus unless the mousedown was on a focusable element ...

Mousedown brings to front, and programatically grabs focus *unless the mousedown was on a focusable element*

**Parameters:** e : Object


### onMove

...


### onPosition

Called after the component is moved, this method is empty by default but can be implemented by any subclass that need...

Called after the component is moved, this method is empty by default but can be implemented by any subclass that needs to perform custom logic after a move occurs. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRemove

Called when a Ext.form.Labelable instance is removed from the container's subtree. ...

Called when a Ext.form.Labelable instance is removed from the container's subtree.

**Parameters:** labelable : Ext.form.LabelableThe instance that was removed


### onRemoved

Method to manage awareness of when components are removed from their respective Container, firing a removed event. ...

Method to manage awareness of when components are removed from their respective Container, firing a removed event. References are properly cleaned up after removing a component from its owning container. Allows addition of behavior when a Component is removed from its parent Container. At this stage, the Component has been removed from its parent Container's collection of child items, but has not been destroyed (It will be destroyed if the parent Container's `autoDestroy` is `true`, or if the remove call was passed a truthy second parameter). After calling the superclass's `onRemoved`, the `ownerCt` and the `refOwner` will not be present. Available since: 3.4.0 This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRender

Template method called when this Component's DOM structure is created. ...

Template method called when this Component's DOM structure is created. At this point, this Component's (and all descendants') DOM structure *exists* but it has not been layed out (positioned and sized). Subclasses which override this to gain access to the structure at render time should call the parent class's method before attempting to access any child elements of the Component. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onResize

Allows addition of behavior to the resize operation. ...

Allows addition of behavior to the resize operation. Called when Ext.resizer.Resizer#drag event is fired. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


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


### parseBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** box : Object


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

Method which removes a specified UI + uiCls from the components element. ...

Method which removes a specified UI + `uiCls` from the components element. The `cls` which is added to the element will be: `this.baseCls + '-' + ui`.

**Parameters:** ui : StringThe UI to add to the element.


### removeUIFromElement

Method which removes a specified UI from the components element. ...

Method which removes a specified UI from the components element.


### render

Renders the Component into the passed HTML element. ...

Renders the Component into the passed HTML element. If you are using a Container object to house this Component, then do not use the render method. A Container's child Components are rendered by that Container's layout manager when the Container is first rendered. If the Container is already rendered when a new child Component is added, you may need to call the Container's doLayout to refresh the view which causes any unrendered child Components to be rendered. This is required so that you can add multiple child components if needed while only refreshing the layout once. When creating complex UIs, it is important to remember that sizing and positioning of child items is the responsibility of the Container's layout manager. If you expect child items to be sized in response to user interactions, you must configure the Container with a layout manager which creates and manages the type of layout you have in mind. Omitting the Container's layout config means that a basic layout manager is used which does nothing but render child components sequentially into the Container. No sizing or positioning will be performed in this situation.

**Parameters:** container : Ext.Element/HTMLElement/String (optional)The element this Component should be rendered into. If it is being created from existing markup, this should be omitted.


### renderActiveError

Updates the rendered DOM to match the current activeError. ...

Updates the rendered DOM to match the current activeError. This only updates the content and attributes, you'll have to call doComponentLayout to actually update the display.


### repositionFloatingItems

...


### reset

Resets the checked state of all checkboxes in the group to their originally loaded values and clears any validation m...

Resets the checked state of all checkboxes in the group to their originally loaded values and clears any validation messages. See Ext.form.Basic.trackResetOnLoad Overrides: Ext.form.field.Field.reset


### resetOriginalValue

Resets the field's originalValue property so it matches the current value. ...

Resets the field's originalValue property so it matches the current value. This is called by Ext.form.Basic.setValues if the form's trackResetOnLoad property is set to true. Overrides: Ext.form.field.Field.resetOriginalValue


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


### saveState

Saves the state of the object to the persistence store. ...

Saves the state of the object to the persistence store.


### scrollBy

Scrolls this Component's target element by the passed delta values, optionally animating. ...

Scrolls this Component's target element by the passed delta values, optionally animating. All of the following are equivalent:

**Parameters:** deltaX : Number/Number[]/ObjectEither the x delta, an Array specifying x and y deltas or an object with "x" and "y" properties.


### sequenceFx

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. ...

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. This is the opposite of syncFx.

**Returns:** Objectthis


### setActive

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been moved to th...

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been moved to the top of its zIndex stack, or pushed from the top of its zIndex stack. If a *Window* is superceded by another Window, deactivating it hides its shadow. This method also fires the activate or deactivate event depending on which action occurred.

**Parameters:** active : Boolean (optional)True to activate the Component, false to deactivate it. Defaults to: `false`


### setActiveError

Sets the active error message to the given string. ...

Sets the active error message to the given string. This replaces the entire error message contents with the given string. Also see setActiveErrors which accepts an Array of messages and formats them according to the activeErrorsTpl. Note that this only updates the error message element's text and attributes, you'll have to call doComponentLayout to actually update the field's layout to match. If the field extends Ext.form.field.Base you should call markInvalid instead.

**Parameters:** msg : StringThe error message


### setActiveErrors

Set the active error message to an Array of error messages. ...

Set the active error message to an Array of error messages. The messages are formatted into a single message string using the activeErrorsTpl. Also see setActiveError which allows setting the entire error contents with a single string. Note that this only updates the error message element's text and attributes, you'll have to call doComponentLayout to actually update the field's layout to match. If the field extends Ext.form.field.Base you should call markInvalid instead.

**Parameters:** errors : String[]The error messages


### setAutoScroll

Sets the overflow on the content element of the component. ...

Sets the overflow on the content element of the component.

**Parameters:** scroll : BooleanTrue to allow the Component to auto scroll.


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


### setFieldDefaults

Applies a set of default configuration values to this Labelable instance. ...

Applies a set of default configuration values to this Labelable instance. For each of the properties in the given object, check if this component hasOwnProperty that config; if not then it's inheriting a default value from its prototype and we should apply the default value.

**Parameters:** defaults : ObjectThe defaults to apply to the object.


### setFieldLabel

Set the label of this field. ...

Set the label of this field.

**Parameters:** label : StringThe new label. The labelSeparator will be automatically appended to the label string.


### setFloatParent

...

**Parameters:** floatParent : Object


### setHeight

Sets the height of the component. ...

Sets the height of the component. This method fires the resize event.

**Parameters:** - height : NumberThe new height to set. This may be one of: A Number specifying the new height in the Element's Ext.Element.defaultUnits (by default, pixels). - A String used to set the CSS height style. - *undefined* to leave the height unchanged.


### setHiddenState

...

**Parameters:** hidden : Object


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


### setReadOnly

private override ...

private override

**Parameters:** readOnly : Object


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


### setUI

Sets the UI for the component. ...

Sets the UI for the component. This will remove any existing UIs on the component. It will also loop through any `uiCls` set on the component and rename them so they include the new UI.

**Parameters:** ui : StringThe new UI for the component.


### setValue

Sets the value of the radio group. ...

Sets the value of the radio group. The radio with corresponding name and value will be set. This method is simpler than Ext.form.CheckboxGroup.setValue because only 1 value is allowed for each name.

**Parameters:** value : ObjectThe map from names to values to be set.


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


### transformOriginalValue

Allows for any necessary modifications before the original value is set ...

Allows for any necessary modifications before the original value is set

**Parameters:** value : ObjectThe initial value


### translatePoints

Translates the passed page coordinates into left/top css values for the element ...

Translates the passed page coordinates into left/top css values for the element

**Parameters:** x : Number/ArrayThe page x or an array containing [x, y]


### translateXY

Translates the passed page coordinates into x and y css values for the element ...

Translates the passed page coordinates into x and y css values for the element

**Parameters:** x : Number/ArrayThe page x or an array containing [x, y]


### trimLabelSeparator

Returns the trimmed label by slicing off the label separator character. ...

**Returns:** the trimmed label by slicing off the label separator character. Can be overridden. ReturnsStringThe trimmed field label, or empty string if not defined


### un

Shorthand for removeListener. ...

Shorthand for removeListener. Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### unitizeBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** box : Object


### unmask

...


### unregisterFloatingItem

...

**Parameters:** cmp : Object


### unsetActiveError

Clears the active error message(s). ...

Clears the active error message(s). Note that this only clears the error message element's text and attributes, you'll have to call doComponentLayout to actually update the field's layout to match. If the field extends Ext.form.field.Base you should call clearInvalid instead.


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


### updateFrame

...


### updateLabel

Updates the content of the labelEl if it is rendered ...

Updates the content of the labelEl if it is rendered


### updateLayout

Updates this component's layout. ...

Updates this component's layout. If this update affects this components ownerCt, that component's `updateLayout` method will be called to perform the layout instead. Otherwise, just this component (and its child items) will layout.

**Parameters:** options : Object (optional)An object with layout options. defer : Boolean`true` if this layout should be deferred.


### validate

Returns whether or not the field value is currently valid by validating the field's current value, and fires the vali...

**Returns:** whether or not the field value is currently valid by validating the field's current value, and fires the validitychange event if the field's validity has changed since the last validation. **Note**: disabled fields are always treated as valid. Custom implementations of this method are allowed to have side-effects such as triggering error message display. To validate without side-effects, use isValid. ReturnsBooleanTrue if the value is valid, else false


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


### beforedeactivate

Fires before a Component has been visually deactivated. ...

Fires before a Component has been visually deactivated. Returning `false` from an event listener can prevent the deactivate from occurring.

**Parameters:** this : Ext.Component


### beforedestroy

Fires before the component is destroyed. ...

Fires before the component is destroyed. Return `false` from an event handler to stop the destroy. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforehide

Fires before the component is hidden when calling the hide method. ...

Fires before the component is hidden when calling the hide method. Return `false` from an event handler to stop the hide. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeremove

Fires before any Ext.Component is removed from the container. ...

Fires before any Ext.Component is removed from the container. A handler can return false to cancel the remove. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### beforerender

Fires before the component is rendered. ...

Fires before the component is rendered. Return `false` from an event handler to stop the render. Available since: 1.1.0

**Parameters:** this : Ext.Component


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


### change

Fires when the value of a field is changed via the setValue method. ...

Fires when the value of a field is changed via the setValue method.

**Parameters:** this : Ext.form.field.Field


### deactivate

Fires after a Component has been visually deactivated. ...

Fires after a Component has been visually deactivated.

**Parameters:** this : Ext.Component


### destroy

Fires after the component is destroyed. ...

Fires after the component is destroyed. Available since: 1.1.0

**Parameters:** this : Ext.Component


### dirtychange

Fires when a change in the field's isDirty state is detected. ...

Fires when a change in the field's isDirty state is detected.

**Parameters:** this : Ext.form.field.Field


### disable

Fires after the component is disabled. ...

Fires after the component is disabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### enable

Fires after the component is enabled. ...

Fires after the component is enabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### errorchange

Fires when the active error message is changed via setActiveError. ...

Fires when the active error message is changed via setActiveError.

**Parameters:** this : Ext.form.Labelable


### fielderrorchange

Fires when the active error message is changed for any one of the Ext.form.Labelable instances within this container. ...

Fires when the active error message is changed for any one of the Ext.form.Labelable instances within this container.

**Parameters:** this : Ext.form.FieldAncestor


### fieldvaliditychange

Fires when the validity state of any one of the Ext.form.field.Field instances within this container changes. ...

Fires when the validity state of any one of the Ext.form.field.Field instances within this container changes.

**Parameters:** this : Ext.form.FieldAncestor


### focus

Fires when this Component receives focus. ...

Fires when this Component receives focus.

**Parameters:** this : Ext.Component


### hide

Fires after the component is hidden. ...

Fires after the component is hidden. Fires after the component is hidden when calling the hide method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### move

Fires after the component is moved. ...

Fires after the component is moved.

**Parameters:** this : Ext.Component


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


### show

Fires after the component is shown when calling the show method. ...

Fires after the component is shown when calling the show method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### staterestore

Fires after the state of the object is restored. ...

Fires after the state of the object is restored.

**Parameters:** this : Ext.state.Stateful


### statesave

Fires after the state of the object is saved to the configured state provider. ...

Fires after the state of the object is saved to the configured state provider.

**Parameters:** this : Ext.state.Stateful


### validitychange

Fires when a change in the field's validity is detected. ...

Fires when a change in the field's validity is detected.

**Parameters:** this : Ext.form.field.Field


### $form-checkboxgroup-body-padding

**Type:** number/list

The padding of the CheckboxGroup body element ...

The padding of the CheckboxGroup body element Defaults to: `0 4px`


### $form-checkboxgroup-label-border-color

**Type:** number

The border-color of the CheckboxGroup label ...

The border-color of the CheckboxGroup label Defaults to: `$form-checkboxgroup-label-color`


### $form-checkboxgroup-label-border-style

**Type:** number

The border-style of the CheckboxGroup label ...

The border-style of the CheckboxGroup label Defaults to: `solid`


### $form-checkboxgroup-label-border-width

**Type:** number

The border-width of the CheckboxGroup label ...

The border-width of the CheckboxGroup label Defaults to: `0 0 1px 0`


### $form-checkboxgroup-label-color

**Type:** color

The text color of the CheckboxGroup label ...

The text color of the CheckboxGroup label Defaults to: `$form-label-font-color`


### $form-checkboxgroup-label-margin

**Type:** number

The margin of the CheckboxGroup label ...

The margin of the CheckboxGroup label Defaults to: `0 30px 5px 0`


### $form-checkboxgroup-label-padding

**Type:** number

The padding of the CheckboxGroup label ...

The padding of the CheckboxGroup label Defaults to: `2px`


### $form-error-icon-height

**Type:** number

Height for form error icons. ...

Height for form error icons. Defaults to: `16px`


### $form-error-icon-side-margin

**Type:** number/list

Margin for error icons that are aligned to the side of the field ...

Margin for error icons that are aligned to the side of the field Defaults to: `0 1px`


### $form-error-icon-width

**Type:** number

Width for form error icons. ...

Width for form error icons. Defaults to: `16px`


### $form-error-msg-color

**Type:** color

The text color of form error messages ...

The text color of form error messages Defaults to: `$form-field-invalid-border-color`


### $form-error-msg-font-family

**Type:** string

The font-family of form error messages ...

The font-family of form error messages Defaults to: `$font-family`


### $form-error-msg-font-size

**Type:** number

The font-size of form error messages ...

The font-size of form error messages Defaults to: `$font-size`


### $form-error-msg-font-weight

**Type:** string

The font-weight of form error messages ...

The font-weight of form error messages Defaults to: `normal`


### $form-error-msg-line-height

**Type:** number

The line-height of form error messages ...

The line-height of form error messages Defaults to: `$form-error-icon-height`


### $form-error-under-icon-spacing

**Type:** number

The space between the icon and the message for errors that display under the field ...

The space between the icon and the message for errors that display under the field Defaults to: `4px`


### $form-error-under-padding

**Type:** number/list

The padding on errors that display under the form field ...

The padding on errors that display under the form field Defaults to: `2px 2px 2px 0`


### $form-item-margin-bottom

**Type:** measurement

The bottom margin to apply to form items when in auto, anchor, vbox, or table layout ...

The bottom margin to apply to form items when in auto, anchor, vbox, or table layout Defaults to: `5px`


### $form-label-font-color

**Type:** color

The text color of form field labels ...

The text color of form field labels Defaults to: `$color`


### $form-label-font-family

**Type:** string

The font-family of form field labels ...

The font-family of form field labels Defaults to: `$font-family`


### $form-label-font-size

**Type:** number

The font-size of form field labels ...

The font-size of form field labels Defaults to: `$font-size`


### $form-label-font-weight

**Type:** string

The font-weight of form field labels ...

The font-weight of form field labels Defaults to: `normal`


### $form-label-line-height

**Type:** number

The line-height of form field labels ...

The line-height of form field labels Defaults to: `round ( $form-label-font-size * 1.15 )`


### $form-toolbar-label-color

**Type:** color

The text color of toolbar field labels ...

The text color of toolbar field labels Defaults to: `$color`


### $form-toolbar-label-font-family

**Type:** string

The font-family of toolbar field labels ...

The font-family of toolbar field labels Defaults to: `$font-family`


### $form-toolbar-label-font-size

**Type:** number

The font-size of toolbar field labels ...

The font-size of toolbar field labels Defaults to: `$font-size`


### $form-toolbar-label-font-weight

**Type:** string

The font-weight of toolbar field labels ...

The font-weight of toolbar field labels Defaults to: `normal`


### $form-toolbar-label-line-height

**Type:** number

The line-height of toolbar field labels ...

The line-height of toolbar field labels Defaults to: `round ( $form-toolbar-label-font-size * 1.15 )`


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


### autoEl

**Type:** Object

...

Defaults to: `{tag: 'table', cellpadding: 0}`


### autoGenId

**Type:** Boolean

true indicates an id was auto-generated rather than provided by configuration. ...

`true` indicates an `id` was auto-generated rather than provided by configuration. Defaults to: `false`


### bodyEl

**Type:** Ext.Element

The div Element wrapping the component's contents. ...

The div Element wrapping the component's contents. Only available after the component has been rendered.


### borderBoxCls

**Type:** String

private ...

private Defaults to: `Ext.baseCSSPrefix + 'border-box'`


### bubbleEvents

**Type:** Array

...

Defaults to: `[]`


### childEls

**Type:** Array

...

Defaults to: `['containerEl']` Overrides: Ext.form.Labelable.childEls


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

The name of the padding property that is used by the layout to manage padding. See managePadding Defaults to: `'padding'`


### convertPositionSpec

**Type:** Object

By default this method does nothing but return the position spec passed to it. ...

By default this method does nothing but return the position spec passed to it. In rtl mode it is overridden to convert "l" to "r" and vice versa when required.


### customOverflowEl

**Type:** String

Used by the layout system, typically the scrolling el is the targetEl, however we need to let it know we're using som...

Used by the layout system, typically the scrolling el is the targetEl, however we need to let it know we're using something different Defaults to: `'containerEl'`


### defaultComponentLayoutType

**Type:** String

...

Defaults to: `'autocomponent'`


### deferLayouts

**Type:** Boolean

...

Defaults to: `false`


### draggable

**Type:** Boolean

Indicates whether or not the component can be dragged. ...

Indicates whether or not the component can be dragged. Defaults to: `false`


### errorEl

**Type:** Ext.Element

The div Element that will contain the component's error message(s). ...

The div Element that will contain the component's error message(s). Note that depending on the configured msgTarget, this element may be hidden in favor of some other form of presentation, but will always be present in the DOM for use by assistive technologies.


### eventsSuspended

**Type:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called. Defaults to: `0`


### extraFieldBodyCls

**Type:** String

private ...

private Defaults to: `Ext.baseCSSPrefix + 'form-checkboxgroup-body'`


### fieldSubTpl

**Type:** String

...

Defaults to: `'<div id="{id}-containerEl" class="{containerElCls}">{%this.renderContainer(out,values)%}</div>'`


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


### groupCls

**Type:** String

private ...

private Defaults to: `Ext.baseCSSPrefix + 'form-radio-group'` Overrides: Ext.form.CheckboxGroup.groupCls


### hasListeners

**Type:** Object

This object holds a key for any event that has a listener. ...

This object holds a key for any event that has a listener. The listener may be set directly on the instance, or on its class or a super class (via observe) or on the MVC EventBus. The values of this object are truthy (a non-zero number) and falsy (0 or undefined). They do not represent an exact count of listeners. The value for an event is truthy if the event must be fired and is falsy if there is no need to fire the event. The intended use of this property is to avoid the expense of fireEvent calls when there are no listeners. This can be particularly helpful when one would otherwise have to call fireEvent hundreds or thousands of times. It is used like this:


### horizontalPosProp

**Type:** String

...

Defaults to: `'left'`


### htmlActiveErrorsTpl

**Type:** Array

...

Defaults to: `['<tpl if="errors && errors.length">', '<ul class="{listCls}"><tpl for="errors"><li role="alert">{.}</li></tpl></ul>', '</tpl>']`


### initConfigList

**Type:** Array

...

Defaults to: `[]`


### initConfigMap

**Type:** Object

...

Defaults to: `{}`


### inputRowCls

**Type:** String

private ...

private Defaults to: `Ext.baseCSSPrefix + 'form-item-input-row'`


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


### isFieldLabelable

**Type:** Boolean

Flag denoting that this object is labelable as a field. ...

Flag denoting that this object is labelable as a field. Always true. Defaults to: `true`


### isFormField

**Type:** Boolean

Flag denoting that this component is a Field. ...

Flag denoting that this component is a Field. Always true. Defaults to: `true`


### isInstance

**Type:** Boolean

...

Defaults to: `true`


### isObservable

**Type:** Boolean

true in this class to identify an object as an instantiated Observable, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Observable, or subclass thereof. Defaults to: `true`


### isQueryable

**Type:** Boolean

...

Defaults to: `true`


### items

**Type:** Ext.util.AbstractMixedCollection

The MixedCollection containing all the child items of this container.

The MixedCollection containing all the child items of this container. Available since: 2.3.0


### labelCell

**Type:** Ext.Element

The <TD> Element which contains the label Element for this component. ...

The `<TD>` Element which contains the label Element for this component. Only available after the component has been rendered.


### labelEl

**Type:** Ext.Element

The label Element for this component. ...

The label Element for this component. Only available after the component has been rendered.


### labelableInsertions

**Type:** Array

...

Defaults to: `['beforeBodyEl', 'afterBodyEl', 'beforeLabelTpl', 'afterLabelTpl', 'beforeSubTpl', 'afterSubTpl', 'beforeLabelTextTpl', 'afterLabelTextTpl', 'labelAttrTpl']`


### labelableRenderProps

**Type:** Array

This is an array to avoid a split on every call to Ext.copyTo ...

This is an array to avoid a split on every call to Ext.copyTo Defaults to: `['allowBlank', 'id', 'labelAlign', 'fieldBodyCls', 'extraFieldBodyCls', 'baseBodyCls', 'clearCls', 'labelSeparator', 'msgTarget', 'inputRowCls']`


### layoutCounter

**Type:** Number

The number of container layout calls made on this object. ...

The number of container layout calls made on this object. Defaults to: `0`


### layoutSuspendCount

**Type:** Number

...

Defaults to: `0`


### maskOnDisable

**Type:** Boolean

This is an internal flag that you use when creating custom components. ...

This is an internal flag that you use when creating custom components. By default this is set to `true` which means that every component gets a mask when it's disabled. Components like FieldContainer, FieldSet, Field, Button, Tab override this property to `false` since they want to implement custom disable logic. Defaults to: `false` Overrides: Ext.AbstractComponent.maskOnDisable


### noWrap

**Type:** Boolean

Tells the layout system that the height can be measured immediately because the width does not need setting. ...

Tells the layout system that the height can be measured immediately because the width does not need setting. Defaults to: `true`


### offsetsCls

**Type:** String

...

Defaults to: `Ext.baseCSSPrefix + 'hide-offsets'`


### originalValue

**Type:** Object

The original value of the field as configured in the value configuration, or as loaded by the last form load operatio...

The original value of the field as configured in the value configuration, or as loaded by the last form load operation if the form's trackResetOnLoad setting is `true`.


### ownerCt

**Type:** Ext.Container

This Component's owner Container (is set automatically when this Component is added to a Container). ...

This Component's owner Container (is set automatically when this Component is added to a Container). *Important.* This is not a universal upwards navigation pointer. It indicates the Container which owns and manages this Component if any. There are other similar relationships such as the button which activates a menu, or the menu item which activated a submenu, or the column header which activated the column menu. These differences are abstracted away by the up method. **Note**: to access items within the Container see itemId. Available since: 2.3.0


### plaintextActiveErrorsTpl

**Type:** Array

...

Defaults to: `['<tpl if="errors && errors.length">', '<tpl for="errors"><tpl if="xindex &gt; 1">\n</tpl>{.}</tpl>', '</tpl>']`


### rendered

**Type:** Boolean

Indicates whether or not the component has been rendered. ...

Indicates whether or not the component has been rendered. Defaults to: `false` Available since: 1.1.0


### scrollFlags

**Type:** Object

An object property which provides unified information as to which dimensions are scrollable based upon the autoScroll...

An object property which provides unified information as to which dimensions are scrollable based upon the autoScroll, overflowX and overflowY settings (And for *views* of trees and grids, the owning panel's scroll setting). Note that if you set overflow styles using the style config or bodyStyle config, this object does not include that information; it is best to use autoScroll, overflowX and overflowY if you need to access these flags. This object has the following properties: x : Boolean`true` if this Component is scrollable horizontally - style setting may be `'auto'` or `'scroll'`.


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### suspendCheckChange

**Type:** Number

...

Defaults to: `0`


### weight

**Type:** Number

...

Defaults to: `0`


### xhooks

**Type:** Object


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


### Ext.form.RadioGroup

Creates new Component. ...

Creates new Component.

**Parameters:** - config : Ext.Element/String/ObjectThe configuration options may be specified as either: **an element** : it is set as the internal element and its id used as the component id - **a string** : it is assumed to be the id of an existing element and is used as the component id - **anything else** : it is assumed to be a standard config object and is applied to the component


### add

Adds Component(s) to this Container. ...

Adds Component(s) to this Container. Description: - Fires the beforeadd event before adding. - The Container's default config values will be applied accordingly (see `defaults` for details). - Fires the `add` event after the component has been added. Notes: If the Container is **already rendered** when `add` is called, it will render the newly added Component into its content area. **If** the Container was configured with a size-managing layout manager, the Container will recalculate its internal layout at this time too. Note that the default layout manager simply renders child Components sequentially into the content area and thereafter performs no sizing. If adding multiple new child Components, pass them as an array to the `add` method, so that only one layout recalculation is performed. To inject components between existing ones, use the insert method. Warning: Components directly managed by the BorderLayout layout manager may not be removed or added. See the Notes for BorderLayout for more details. Available since: 2.3.0

**Parameters:** component : Ext.Component[]|Object[]/Ext.Component.../Object...Either one or more Components to add or an Array of Components to add. See `items` for additional information.


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


### addUIClsToElement

Method which adds a specified UI + uiCls to the components element. ...

Method which adds a specified UI + `uiCls` to the components element. Can be overridden to remove the UI from more than just the components element.

**Parameters:** ui : StringThe UI to remove from the element.


### addUIToElement

Method which adds a specified UI to the components element. ...

Method which adds a specified UI to the components element.


### adjustForConstraints

private ==> used outside of core TODO: currently only used by ToolTip. ...

private ==> used outside of core TODO: currently only used by ToolTip. does this method belong here?

**Parameters:** xy : Object


### adjustPosition

...

**Parameters:** x : Object


### afterComponentLayout

Called by the layout system after the Component has been laid out. ...

Called by the layout system after the Component has been laid out. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterFirstLayout

...

**Parameters:** width : Object


### afterHide

Invoked after the Component has been hidden. ...

Invoked after the Component has been hidden. Gets passed the same `callback` and `scope` parameters that onHide received. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterLayout

Invoked after the Container has laid out (and rendered if necessary) its child Components. ...

Invoked after the Container has laid out (and rendered if necessary) its child Components. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


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


### batchChanges

A utility for grouping a set of modifications which may trigger value changes into a single transaction, to prevent e...

A utility for grouping a set of modifications which may trigger value changes into a single transaction, to prevent excessive firing of change events. This is useful for instance if the field has sub-fields which are being updated as a group; you don't want the container field to check its own changed state for each subfield change.

**Parameters:** fn : ObjectA function containing the transaction code


### beforeBlur

Template method to do any pre-blur processing. ...

Template method to do any pre-blur processing.

**Parameters:** e : Ext.EventObjectThe event object


### beforeComponentLayout

Occurs before componentLayout is run. ...

Occurs before `componentLayout` is run. Returning `false` from this method will prevent the `componentLayout` from being executed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeDestroy

...

Overrides: Ext.container.AbstractContainer.beforeDestroy, Ext.panel.Panel.beforeDestroy


### beforeFocus

Template method to do any pre-focus processing. ...

Template method to do any pre-focus processing.

**Parameters:** e : Ext.EventObjectThe event object


### beforeLayout

Occurs before componentLayout is run. ...

Occurs before componentLayout is run. In previous releases, this method could return `false` to prevent its layout but that is not supported in Ext JS 4.1 or higher. This method is simply a notification of the impending layout to give the component a chance to adjust the DOM. Ideally, DOM reads should be avoided at this time to reduce expensive document reflows. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeRender

...

Overrides: Ext.Component.beforeRender


### beforeReset

Template method before a field is reset. ...

Template method before a field is reset.


### beforeSetPosition

Template method called before a Component is positioned. ...

Template method called before a Component is positioned. Ensures that the position is adjusted so that the Component is constrained if so configured.

**Parameters:** x : Object


### beforeShow

Invoked before the Component is shown. ...

Invoked before the Component is shown. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### blur

...

**Returns:** Ext.Componentthis


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


### checkChange

Checks whether the value of the field has changed since the last time it was checked. ...

Checks whether the value of the field has changed since the last time it was checked. If the value has changed, it: - Fires the change event, - Performs validation if the validateOnChange config is enabled, firing the validitychange event if the validity has changed, and - Checks the dirty state of the field and fires the dirtychange event if it has changed. Overrides: Ext.form.field.Field.checkChange


### checkDirty

Checks the isDirty state of the field and if it has changed since the last time it was checked, fires the dirtychange...

Checks the isDirty state of the field and if it has changed since the last time it was checked, fires the dirtychange event.


### child

Retrieves the first direct child of this container which matches the passed selector or component. ...

Retrieves the first direct child of this container which matches the passed selector or component. The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.

**Parameters:** selector : String/Ext.Component (optional)An Ext.ComponentQuery selector. If no selector is specified, the first child will be returned.


### clearInvalid

Clear any invalid styles/messages for this field. ...

Clear any invalid styles/messages for this field. Components using this mixin should implement this method to update the components rendering to clear any existing messages. **Note**: this method does not cause the Field's validate or isValid methods to return `true` if the value does not *pass* validation. So simply clearing a field's errors will not necessarily allow submission of forms submitted with the Ext.form.action.Submit.clientValidation option set.


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


### configClass

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


### convertPositionSpec

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**

**Parameters:** posSpec : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### deleteMembers

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### detachComponent

Detach a component from the DOM ...

Detach a component from the DOM

**Parameters:** component : Object


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


### doRenderFramingDockedItems

...

**Parameters:** out : Object


### down

Retrieves the first descendant of this container which matches the passed selector. ...

Retrieves the first descendant of this container which matches the passed selector. The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.

**Parameters:** selector : String/Ext.Component (optional)An Ext.ComponentQuery selector or Ext.Component. If no selector is specified, the first child will be returned.


### eachBox

Convenience function which calls the given function for every checkbox in the group ...

Convenience function which calls the given function for every checkbox in the group

**Parameters:** fn : FunctionThe function to call


### enable

Enable all immediate children that was previously disabled Override enable because onEnable only gets called when ren...

Enable all immediate children that was previously disabled Override enable because onEnable only gets called when rendered Enable the component Available since: 1.1.0

**Parameters:** silent : Boolean (optional)Passing `true` will suppress the `enable` event from being fired. Defaults to: `false`


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if present. There is no implementation in the Observable base class. This is commonly used by Ext.Components to bubble events to owner Containers. See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the Component's immediate owner. But if a known target is required, this can be overridden to access the required target more quickly. Example:

**Parameters:** eventNames : String/String[]The event name to bubble, or an Array of event names.


### ensureAttachedToBody

Ensures that this component is attached to document.body. ...

Ensures that this component is attached to `document.body`. If the component was rendered to Ext.getDetachedBody, then it will be appended to `document.body`. Any configured position is also restored.

**Parameters:** runLayout : Boolean (optional)True to run the component's layout. Defaults to: `false`


### extractFileInput

Only relevant if the instance's isFileUpload method returns true. ...

Only relevant if the instance's isFileUpload method returns true.

**Returns:** a reference to the file input DOM element holding the user's selected file. The input will be appended into the submission form and will not be returned, so this method should also create a replacement. ReturnsHTMLElement


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


### getActiveError

Gets the active error message for this component, if any. ...

Gets the active error message for this component, if any. This does not trigger validation on its own, it merely returns any message that the component may already hold.

**Returns:** StringThe active error message on the component; if there is no error, an empty string is returned.


### getActiveErrors

Gets an Array of any active error messages currently applied to the field. ...

Gets an Array of any active error messages currently applied to the field. This does not trigger validation on its own, it merely returns any messages that the component may already hold.

**Returns:** String[]The active error messages on the component; if there are no errors, an empty Array is returned.


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


### getBodyColspan

Calculates the colspan value for the body cell - the cell which contains the input field. ...

Calculates the colspan value for the body cell - the cell which contains the input field. The field table structure contains 4 columns:


### getBorderPadding

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Returns:** the size of the element's borders and padding. ReturnsObjectan object with the following numeric properties - beforeX - afterX - beforeY - afterY


### getBox

Return an object defining the area of this Element which can be passed to setBox to set another Element's size/locati...

Return an object defining the area of this Element which can be passed to setBox to set another Element's size/location to match this element.

**Parameters:** contentBox : Boolean (optional)If true a box for the content of the element is returned.


### getBoxes

Returns all checkbox components within the container ...

**Parameters:** query : String (optional)An additional query to add to the selector.

**Returns:** all checkbox components within the container


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getBubbleTarget

Implements an upward event bubbling policy. ...

Implements an upward event bubbling policy. By default a Component bubbles events up to its reference owner. Component subclasses may implement a different bubbling strategy by overriding this method. Overrides: Ext.AbstractComponent.getBubbleTarget


### getChecked

Returns an Array of all checkboxes in the container which are currently checked ...

**Returns:** an Array of all checkboxes in the container which are currently checked ReturnsExt.form.field.Checkbox[]Array of Ext.form.field.Checkbox components


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


### getCombinedErrors

Takes an Array of invalid Ext.form.field.Field objects and builds a combined list of error messages from them. ...

Takes an Array of invalid Ext.form.field.Field objects and builds a combined list of error messages from them. Defaults to prepending each message by the field name and a colon. This can be overridden to provide custom combined error message handling, for instance changing the format of each message or sorting the array (it is sorted in order of appearance by default).

**Parameters:** invalidFields : Ext.form.field.Field[]An Array of the sub-fields which are currently invalid.


### getComponent

Examines this container's items property and gets a direct child component of this container. ...

Examines this container's items **property** and gets a direct child component of this container. Available since: 2.3.0

**Parameters:** - comp : String/NumberThis parameter may be any of the following: a **String** : representing the itemId or id of the child component. - a **Number** : representing the position of the child component within the items **property** For additional information see Ext.util.MixedCollection.get.


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


### getDragEl

...


### getEl

Retrieves the top level element representing this component. ...

Retrieves the top level element representing this component. Available since: 1.1.0

**Returns:** Ext.dom.Element


### getElConfig

...


### getErrorMsgCls

...


### getErrors

Runs CheckboxGroup's validations and returns an array of any errors. ...

Runs CheckboxGroup's validations and returns an array of any errors. The only error by default is if allowBlank is set to true and no items are checked.

**Returns:** String[]Array of all validation errors


### getFieldLabel

Returns the combined field label if combineLabels is set to true and if there is no set fieldLabel. ...

**Returns:** the combined field label if combineLabels is set to true and if there is no set fieldLabel. Otherwise returns the fieldLabel like normal. You can also override this method to provide a custom generated label. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


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


### getHeight

Gets the current height of the component's underlying element. ...

Gets the current height of the component's underlying element.

**Returns:** Number


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


### getInputId

Get the input id, if any, for this component. ...

Get the input id, if any, for this component. This is used as the "for" attribute on the label element. Implementing subclasses may also use this as e.g. the id for their own input element.

**Returns:** StringThe input id


### getInsertPosition

This function takes the position argument passed to onRender and returns a DOM element that you can use in the insert...

This function takes the position argument passed to onRender and returns a DOM element that you can use in the insertBefore.

**Parameters:** position : String/Number/Ext.dom.Element/HTMLElementIndex, element id or element you want to put this component before.


### getInsertionRenderData

...

**Parameters:** data : Object


### getItemId

Returns the value of itemId assigned to this component, or when that is not set, returns the value of id. ...

**Returns:** the value of itemId assigned to this component, or when that is not set, returns the value of id. ReturnsString


### getLabelCellAttrs

...


### getLabelCellStyle

...


### getLabelCls

...


### getLabelStyle

Gets any label styling for the labelEl ...

Gets any label styling for the labelEl

**Returns:** StringThe label styling


### getLabelWidth

Gets the width of the label (if visible) ...

Gets the width of the label (if visible)

**Returns:** NumberThe label width


### getLabelableRenderData

Generates the arguments for the field decorations rendering template. ...

Generates the arguments for the field decorations rendering template.

**Returns:** ObjectThe template arguments


### getLayout

Returns the layout instance currently associated with this Container. ...

**Returns:** the layout instance currently associated with this Container. If a layout has not been instantiated yet, that is done first ReturnsExt.layout.container.ContainerThe layout


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


### getMaskTarget

...


### getModelData

Don't return any data for the model; the form will get the info from the individual checkboxes themselves. ...

Don't return any data for the model; the form will get the info from the individual checkboxes themselves.

**Returns:** the value(s) that should be saved to the Ext.data.Model instance for this field, when Ext.form.Basic.updateRecord is called. Typically this will be an object with a single name-value pair, the name being this field's name and the value being its current data value. More advanced field implementations may return more than one name-value pair. The returned values will be saved to the corresponding field names in the Model. Note that the values returned from this method are not guaranteed to have been successfully validated. ReturnsObjectA mapping of submit parameter names to values; each value should be a string, or an array of strings if that particular name has multiple values. It can also return null if there are no parameters to be submitted.


### getName

Returns the name attribute of the field. ...

**Returns:** the name attribute of the field. This is used as the parameter name when including the field value in a form submit(). ReturnsStringname The field name


### getOffsetsTo

Returns the offsets of this element from the passed element. ...

**Parameters:** offsetsTo : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or element id to get get the offsets from.

**Returns:** the offsets of this element from the passed element. The element must both be part of the DOM tree and not have display:none to have page coordinates.


### getOuterSize

Include margins ...

Include margins


### getOverflowEl

Get an el for overflowing, defaults to the target el ...

Get an el for overflowing, defaults to the target el Overrides: Ext.AbstractComponent.getOverflowEl


### getOverflowStyle

Returns the CSS style object which will set the Component's scroll styles. ...

**Returns:** the CSS style object which will set the Component's scroll styles. This must be applied to the target element.


### getOwningBorderContainer

Returns the owning container if that container uses border layout. ...

**Returns:** the owning container if that container uses `border` layout. Otherwise this method returns `null`. **Defined in override Ext.layout.container.border.Region.** ReturnsExt.container.ContainerThe owning border container or `null`.


### getOwningBorderLayout

Returns the owning border (Ext.layout.container.Border) instance if there is one. ...

**Returns:** the owning `border` (`Ext.layout.container.Border`) instance if there is one. Otherwise this method returns `null`. **Defined in override Ext.layout.container.border.Region.** ReturnsExt.layout.container.BorderThe owning border layout or `null`.


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


### getProxy

...


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


### getStyleProxy

Returns an offscreen div with the same class name as the element this is being rendered. ...

**Parameters:** cls : Object

**Returns:** an offscreen div with the same class name as the element this is being rendered. This is because child item rendering takes place in a detached div which, being not part of the document, has no styling.


### getSubTplData

...


### getSubTplMarkup

Gets the markup to be inserted into the outer template's bodyEl. ...

Gets the markup to be inserted into the outer template's bodyEl. Defaults to empty string, should be implemented by classes including this mixin as needed.

**Returns:** StringThe markup to be inserted


### getSubmitData

Don't return any data for submit; the form will get the info from the individual checkboxes themselves. ...

Don't return any data for submit; the form will get the info from the individual checkboxes themselves.

**Returns:** the parameter(s) that would be included in a standard form submit for this field. Typically this will be an object with a single name-value pair, the name being this field's name and the value being its current stringified value. More advanced field implementations may return more than one name-value pair. Note that the values returned from this method are not guaranteed to have been successfully validated. ReturnsObjectA mapping of submit parameter names to values; each value should be a string, or an array of strings if that particular name has multiple values. It can also return null if there are no parameters to be submitted.


### getTargetEl

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. ...

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. Overrides: Ext.AbstractComponent.getTargetEl


### getTpl

...

**Parameters:** name : Object


### getValue

Returns an object containing the values of all checked checkboxes within the group. ...

**Returns:** an object containing the values of all checked checkboxes within the group. Each key-value pair in the object corresponds to a checkbox name. If there is only one checked checkbox with a particular name, the value of that pair will be the String inputValue of that checkbox. If there are multiple checked checkboxes with that name, the value of that pair will be an Array of the selected inputValues. The object format returned from this method can also be passed directly to the setValue method. NOTE: In Ext 3, this method returned an array of Checkbox components; this was changed to make it more consistent with other field components and with the setValue argument signature. If you need the old behavior in Ext 4+, use the getChecked method instead. Overrides: Ext.form.field.Field.getValue


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


### handleFieldErrorChange

Handle bubbled errorchange events from descendants; invoke the aggregated event and method ...

Handle bubbled errorchange events from descendants; invoke the aggregated event and method

**Parameters:** labelable : Object


### handleFieldValidityChange

Handle bubbled validitychange events from descendants; invoke the aggregated event and method ...

Handle bubbled validitychange events from descendants; invoke the aggregated event and method

**Parameters:** field : Object


### hasActiveError

Tells whether the field currently has an active error message. ...

Tells whether the field currently has an active error message. This does not trigger validation on its own, it merely looks for any message that the component may already hold.

**Returns:** Boolean


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


### hasUICls

Checks if there is currently a specified uiCls. ...

Checks if there is currently a specified `uiCls`.

**Parameters:** cls : StringThe `cls` to check.


### hasVisibleLabel

Checks if the field has a visible label ...

Checks if the field has a visible label

**Returns:** BooleanTrue if the field has a visible label


### hide

Hides this Component, setting it to invisible using the configured hideMode. ...

Hides this Component, setting it to invisible using the configured hideMode.

**Parameters:** animateTarget : String/Ext.Element/Ext.Component (optional)only valid for floating Components such as Windows or ToolTips, or regular Components which have been configured with `floating: true`.. The target to which the Component should animate while hiding. Defaults to: `null`


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


### initDraggable

...


### initEvents

Initialize any events on this component ...

Initialize any events on this component


### initField

Initializes this Field mixin on the current instance. ...

Initializes this Field mixin on the current instance. Components using this mixin should call this method during their own initialization process.


### initFieldAncestor

Initializes the FieldAncestor's state; this must be called from the initComponent method of any components importing ...

Initializes the FieldAncestor's state; this must be called from the initComponent method of any components importing this mixin.


### initFieldDefaults

Initialize the fieldDefaults object ...

Initialize the fieldDefaults object


### initFrame

...


### initFramingTpl

Poke in a reference to applyRenderTpl(frameInfo, out) ...

Poke in a reference to applyRenderTpl(frameInfo, out)

**Parameters:** table : Object


### initHierarchyEvents

...


### initHierarchyState

Called by getHierarchyState to initialize the hierarchyState the first time it is requested. ...

Called by getHierarchyState to initialize the hierarchyState the first time it is requested. **Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** hierarchyState : Object


### initItems

...


### initLabelable

Performs initialization of this mixin. ...

Performs initialization of this mixin. Component classes using this mixin should call this method during their own initialization.


### initMonitor

...


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

**Parameters:** resizable : Object


### initState

Initializes the state of the object upon construction. ...

Initializes the state of the object upon construction.


### initStyles

Applies padding, margin, border, top, left, height, and width configs to the appropriate elements. ...

Applies padding, margin, border, top, left, height, and width configs to the appropriate elements.

**Parameters:** targetEl : Object


### initValue

Initializes the field's value based on the initial config. ...

Initializes the field's value based on the initial config. If the value config is specified then we use that to set the value; otherwise we initialize the originalValue by querying the values of all sub-checkboxes after they have been initialized. Overrides: Ext.form.field.Field.initValue


### insert

Inserts a Component into this Container at a specified index. ...

Inserts a Component into this Container at a specified index. Fires the beforeadd event before inserting, then fires the add event after the Component has been inserted. Available since: 2.3.0

**Parameters:** index : NumberThe index at which the Component will be inserted into the Container's items collection


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


### isDirty

private override Returns true if the value of this Field has been changed from its originalValue. ...

private override

**Returns:** true if the value of this Field has been changed from its originalValue. Will always return false if the field is disabled. Note that if the owning form was configured with trackResetOnLoad then the originalValue is updated when the values are loaded by Ext.form.Basic.setValues. ReturnsBooleanTrue if this field has been changed from its original value (and is not disabled), false otherwise.


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


### isEqual

private override - the group value is a complex object, compare using object serialization Returns whether two field...

private override - the group value is a complex object, compare using object serialization

**Parameters:** value1 : ObjectThe first value to compare

**Returns:** whether two field values are logically equal. Field implementations may override this to provide custom comparison logic appropriate for the particular field's data type.


### isEqualAsString

Returns whether two values are logically equal. ...

**Parameters:** value1 : ObjectThe first value to compare

**Returns:** whether two values are logically equal. Similar to isEqual, however null or undefined values will be treated as empty strings.


### isFileUpload

Returns whether this Field is a file upload field; if it returns true, forms will use special techniques for submitti...

**Returns:** whether this Field is a file upload field; if it returns true, forms will use special techniques for submitting the form via AJAX. See Ext.form.Basic.hasUpload for details. If this returns true, the extractFileInput method must also be implemented to return the corresponding file input element. ReturnsBoolean


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

Determines whether this Component is the root of a layout. This returns `true` if this component can run its layout without assistance from or impact on its owner. If this component cannot run its layout given these restrictions, `false` is returned and its owner will be considered as the next candidate for the layout root. Setting the _isLayoutRoot property to `true` causes this method to always return `true`. This may be useful when updating a layout of a Container which shrink wraps content, and you know that it will not change size, and so can safely be the topmost participant in the layout run.


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


### isValid

Returns whether or not the field value is currently valid by validating the field's current value. ...

**Returns:** whether or not the field value is currently valid by validating the field's current value. The validitychange event will not be fired; use validate instead if you want the event to fire. **Note**: disabled fields are always treated as valid. Implementations are encouraged to ensure that this method does not have side-effects such as triggering error message display. ReturnsBooleanTrue if the value is valid, else false


### isVisible

Returns true if this component is visible. ...

**Parameters:** deep : Boolean (optional)Pass `true` to interrogate the visibility status of all parent Containers to determine whether this Component is truly visible to the user. Generally, to determine whether a Component is hidden, the no argument form is needed. For example when creating dynamically laid out UIs in a hidden Container before showing them. Defaults to: `false`

**Returns:** `true` if this component is visible. Available since: 1.1.0


### isXType

Tests whether or not this Component is of a specific xtype. ...

Tests whether or not this Component is of a specific xtype. This can test whether this Component is descended from the xtype (default) or whether it is directly of the xtype specified (`shallow = true`). If using your own subclasses, be aware that a Component must register its own xtype to participate in determination of inherited xtypes. For a list of all available xtypes, see the Ext.Component header. Example usage: Available since: 2.3.0

**Parameters:** xtype : StringThe xtype to check for this Component


### lookupComponent

...

**Parameters:** comp : Object


### makeFloating

...

**Parameters:** dom : Object


### markInvalid

Associate one or more error messages with this field. ...

Associate one or more error messages with this field. Components using this mixin should implement this method to update the component's rendering to display the messages. **Note**: this method does not cause the Field's validate or isValid methods to return `false` if the value does *pass* validation. So simply marking a Field as invalid will not prevent submission of forms submitted with the Ext.form.action.Submit.clientValidation option set.

**Parameters:** errors : String/String[]The error message(s) for the field.


### mask

...


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

When a checkbox is added to the group, monitor it for changes ...

When a checkbox is added to the group, monitor it for changes

**Parameters:** field : Object


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

**Parameters:** width : Object


### onChange

Called when the field's value changes. ...

Called when the field's value changes. Performs validation if the validateOnChange config is enabled, and invokes the dirty check.

**Parameters:** newVal : Object


### onChildFieldAdd

...

**Parameters:** field : Object


### onChildFieldRemove

...

**Parameters:** field : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onDestroy

Allows addition of behavior to the destroy operation. ...

Allows addition of behavior to the destroy operation. After calling the superclass's onDestroy, the Component will be destroyed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onDirtyChange

Called when the field's dirty state changes. ...

Called when the field's dirty state changes.

**Parameters:** isDirty : Boolean


### onDisable

Allows addition of behavior to the disable operation. ...

Allows addition of behavior to the disable operation. After calling the superclass's `onDisable`, the Component will be disabled. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onEnable

Allows addition of behavior to the enable operation. ...

Allows addition of behavior to the enable operation. After calling the superclass's `onEnable`, the Component will be enabled. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onFieldErrorChange

Fired when the error message of any field within the container changes, and updates the combined error message to match. ...

Fired when the error message of any field within the container changes, and updates the combined error message to match.

**Parameters:** field : Object


### onFieldValidityChange

Fired when the validity of any field within the container changes. ...

Fired when the validity of any field within the container changes.

**Parameters:** field : Ext.form.field.FieldThe sub-field whose validity changed


### onFloatShow

...


### onFocus

private ...

private

**Parameters:** e : Object


### onHide

Possibly animates down to a target element. ...

Possibly animates down to a target element. Allows addition of behavior to the hide operation. After calling the superclass’s onHide, the Component will be hidden. Gets passed the same parameters as hide. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onKeyDown

Listen for TAB events and wrap round if tabbing of either end of the Floater ...

Listen for TAB events and wrap round if tabbing of either end of the Floater

**Parameters:** e : Object


### onMouseDown

Mousedown brings to front, and programatically grabs focus unless the mousedown was on a focusable element ...

Mousedown brings to front, and programatically grabs focus *unless the mousedown was on a focusable element*

**Parameters:** e : Object


### onMove

...


### onPosition

Called after the component is moved, this method is empty by default but can be implemented by any subclass that need...

Called after the component is moved, this method is empty by default but can be implemented by any subclass that needs to perform custom logic after a move occurs. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRemove

Called when a Ext.form.Labelable instance is removed from the container's subtree. ...

Called when a Ext.form.Labelable instance is removed from the container's subtree.

**Parameters:** labelable : Ext.form.LabelableThe instance that was removed


### onRemoved

Method to manage awareness of when components are removed from their respective Container, firing a removed event. ...

Method to manage awareness of when components are removed from their respective Container, firing a removed event. References are properly cleaned up after removing a component from its owning container. Allows addition of behavior when a Component is removed from its parent Container. At this stage, the Component has been removed from its parent Container's collection of child items, but has not been destroyed (It will be destroyed if the parent Container's `autoDestroy` is `true`, or if the remove call was passed a truthy second parameter). After calling the superclass's `onRemoved`, the `ownerCt` and the `refOwner` will not be present. Available since: 3.4.0 This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRender

Template method called when this Component's DOM structure is created. ...

Template method called when this Component's DOM structure is created. At this point, this Component's (and all descendants') DOM structure *exists* but it has not been layed out (positioned and sized). Subclasses which override this to gain access to the structure at render time should call the parent class's method before attempting to access any child elements of the Component. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onResize

Allows addition of behavior to the resize operation. ...

Allows addition of behavior to the resize operation. Called when Ext.resizer.Resizer#drag event is fired. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


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


### parseBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** box : Object


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

Method which removes a specified UI + uiCls from the components element. ...

Method which removes a specified UI + `uiCls` from the components element. The `cls` which is added to the element will be: `this.baseCls + '-' + ui`.

**Parameters:** ui : StringThe UI to add to the element.


### removeUIFromElement

Method which removes a specified UI from the components element. ...

Method which removes a specified UI from the components element.


### render

Renders the Component into the passed HTML element. ...

Renders the Component into the passed HTML element. If you are using a Container object to house this Component, then do not use the render method. A Container's child Components are rendered by that Container's layout manager when the Container is first rendered. If the Container is already rendered when a new child Component is added, you may need to call the Container's doLayout to refresh the view which causes any unrendered child Components to be rendered. This is required so that you can add multiple child components if needed while only refreshing the layout once. When creating complex UIs, it is important to remember that sizing and positioning of child items is the responsibility of the Container's layout manager. If you expect child items to be sized in response to user interactions, you must configure the Container with a layout manager which creates and manages the type of layout you have in mind. Omitting the Container's layout config means that a basic layout manager is used which does nothing but render child components sequentially into the Container. No sizing or positioning will be performed in this situation.

**Parameters:** container : Ext.Element/HTMLElement/String (optional)The element this Component should be rendered into. If it is being created from existing markup, this should be omitted.


### renderActiveError

Updates the rendered DOM to match the current activeError. ...

Updates the rendered DOM to match the current activeError. This only updates the content and attributes, you'll have to call doComponentLayout to actually update the display.


### repositionFloatingItems

...


### reset

Resets the checked state of all checkboxes in the group to their originally loaded values and clears any validation m...

Resets the checked state of all checkboxes in the group to their originally loaded values and clears any validation messages. See Ext.form.Basic.trackResetOnLoad Overrides: Ext.form.field.Field.reset


### resetOriginalValue

Resets the field's originalValue property so it matches the current value. ...

Resets the field's originalValue property so it matches the current value. This is called by Ext.form.Basic.setValues if the form's trackResetOnLoad property is set to true. Overrides: Ext.form.field.Field.resetOriginalValue


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


### saveState

Saves the state of the object to the persistence store. ...

Saves the state of the object to the persistence store.


### scrollBy

Scrolls this Component's target element by the passed delta values, optionally animating. ...

Scrolls this Component's target element by the passed delta values, optionally animating. All of the following are equivalent:

**Parameters:** deltaX : Number/Number[]/ObjectEither the x delta, an Array specifying x and y deltas or an object with "x" and "y" properties.


### sequenceFx

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. ...

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. This is the opposite of syncFx.

**Returns:** Objectthis


### setActive

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been moved to th...

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been moved to the top of its zIndex stack, or pushed from the top of its zIndex stack. If a *Window* is superceded by another Window, deactivating it hides its shadow. This method also fires the activate or deactivate event depending on which action occurred.

**Parameters:** active : Boolean (optional)True to activate the Component, false to deactivate it. Defaults to: `false`


### setActiveError

Sets the active error message to the given string. ...

Sets the active error message to the given string. This replaces the entire error message contents with the given string. Also see setActiveErrors which accepts an Array of messages and formats them according to the activeErrorsTpl. Note that this only updates the error message element's text and attributes, you'll have to call doComponentLayout to actually update the field's layout to match. If the field extends Ext.form.field.Base you should call markInvalid instead.

**Parameters:** msg : StringThe error message


### setActiveErrors

Set the active error message to an Array of error messages. ...

Set the active error message to an Array of error messages. The messages are formatted into a single message string using the activeErrorsTpl. Also see setActiveError which allows setting the entire error contents with a single string. Note that this only updates the error message element's text and attributes, you'll have to call doComponentLayout to actually update the field's layout to match. If the field extends Ext.form.field.Base you should call markInvalid instead.

**Parameters:** errors : String[]The error messages


### setAutoScroll

Sets the overflow on the content element of the component. ...

Sets the overflow on the content element of the component.

**Parameters:** scroll : BooleanTrue to allow the Component to auto scroll.


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


### setFieldDefaults

Applies a set of default configuration values to this Labelable instance. ...

Applies a set of default configuration values to this Labelable instance. For each of the properties in the given object, check if this component hasOwnProperty that config; if not then it's inheriting a default value from its prototype and we should apply the default value.

**Parameters:** defaults : ObjectThe defaults to apply to the object.


### setFieldLabel

Set the label of this field. ...

Set the label of this field.

**Parameters:** label : StringThe new label. The labelSeparator will be automatically appended to the label string.


### setFloatParent

...

**Parameters:** floatParent : Object


### setHeight

Sets the height of the component. ...

Sets the height of the component. This method fires the resize event.

**Parameters:** - height : NumberThe new height to set. This may be one of: A Number specifying the new height in the Element's Ext.Element.defaultUnits (by default, pixels). - A String used to set the CSS height style. - *undefined* to leave the height unchanged.


### setHiddenState

...

**Parameters:** hidden : Object


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


### setReadOnly

private override ...

private override

**Parameters:** readOnly : Object


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


### setUI

Sets the UI for the component. ...

Sets the UI for the component. This will remove any existing UIs on the component. It will also loop through any `uiCls` set on the component and rename them so they include the new UI.

**Parameters:** ui : StringThe new UI for the component.


### setValue

Sets the value of the radio group. ...

Sets the value of the radio group. The radio with corresponding name and value will be set. This method is simpler than Ext.form.CheckboxGroup.setValue because only 1 value is allowed for each name.

**Parameters:** value : ObjectThe map from names to values to be set.


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


### transformOriginalValue

Allows for any necessary modifications before the original value is set ...

Allows for any necessary modifications before the original value is set

**Parameters:** value : ObjectThe initial value


### translatePoints

Translates the passed page coordinates into left/top css values for the element ...

Translates the passed page coordinates into left/top css values for the element

**Parameters:** x : Number/ArrayThe page x or an array containing [x, y]


### translateXY

Translates the passed page coordinates into x and y css values for the element ...

Translates the passed page coordinates into x and y css values for the element

**Parameters:** x : Number/ArrayThe page x or an array containing [x, y]


### trimLabelSeparator

Returns the trimmed label by slicing off the label separator character. ...

**Returns:** the trimmed label by slicing off the label separator character. Can be overridden. ReturnsStringThe trimmed field label, or empty string if not defined


### un

Shorthand for removeListener. ...

Shorthand for removeListener. Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### unitizeBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** box : Object


### unmask

...


### unregisterFloatingItem

...

**Parameters:** cmp : Object


### unsetActiveError

Clears the active error message(s). ...

Clears the active error message(s). Note that this only clears the error message element's text and attributes, you'll have to call doComponentLayout to actually update the field's layout to match. If the field extends Ext.form.field.Base you should call clearInvalid instead.


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


### updateFrame

...


### updateLabel

Updates the content of the labelEl if it is rendered ...

Updates the content of the labelEl if it is rendered


### updateLayout

Updates this component's layout. ...

Updates this component's layout. If this update affects this components ownerCt, that component's `updateLayout` method will be called to perform the layout instead. Otherwise, just this component (and its child items) will layout.

**Parameters:** options : Object (optional)An object with layout options. defer : Boolean`true` if this layout should be deferred.


### validate

Returns whether or not the field value is currently valid by validating the field's current value, and fires the vali...

**Returns:** whether or not the field value is currently valid by validating the field's current value, and fires the validitychange event if the field's validity has changed since the last validation. **Note**: disabled fields are always treated as valid. Custom implementations of this method are allowed to have side-effects such as triggering error message display. To validate without side-effects, use isValid. ReturnsBooleanTrue if the value is valid, else false


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


### beforedeactivate

Fires before a Component has been visually deactivated. ...

Fires before a Component has been visually deactivated. Returning `false` from an event listener can prevent the deactivate from occurring.

**Parameters:** this : Ext.Component


### beforedestroy

Fires before the component is destroyed. ...

Fires before the component is destroyed. Return `false` from an event handler to stop the destroy. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforehide

Fires before the component is hidden when calling the hide method. ...

Fires before the component is hidden when calling the hide method. Return `false` from an event handler to stop the hide. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeremove

Fires before any Ext.Component is removed from the container. ...

Fires before any Ext.Component is removed from the container. A handler can return false to cancel the remove. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### beforerender

Fires before the component is rendered. ...

Fires before the component is rendered. Return `false` from an event handler to stop the render. Available since: 1.1.0

**Parameters:** this : Ext.Component


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


### change

Fires when the value of a field is changed via the setValue method. ...

Fires when the value of a field is changed via the setValue method.

**Parameters:** this : Ext.form.field.Field


### deactivate

Fires after a Component has been visually deactivated. ...

Fires after a Component has been visually deactivated.

**Parameters:** this : Ext.Component


### destroy

Fires after the component is destroyed. ...

Fires after the component is destroyed. Available since: 1.1.0

**Parameters:** this : Ext.Component


### dirtychange

Fires when a change in the field's isDirty state is detected. ...

Fires when a change in the field's isDirty state is detected.

**Parameters:** this : Ext.form.field.Field


### disable

Fires after the component is disabled. ...

Fires after the component is disabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### enable

Fires after the component is enabled. ...

Fires after the component is enabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### errorchange

Fires when the active error message is changed via setActiveError. ...

Fires when the active error message is changed via setActiveError.

**Parameters:** this : Ext.form.Labelable


### fielderrorchange

Fires when the active error message is changed for any one of the Ext.form.Labelable instances within this container. ...

Fires when the active error message is changed for any one of the Ext.form.Labelable instances within this container.

**Parameters:** this : Ext.form.FieldAncestor


### fieldvaliditychange

Fires when the validity state of any one of the Ext.form.field.Field instances within this container changes. ...

Fires when the validity state of any one of the Ext.form.field.Field instances within this container changes.

**Parameters:** this : Ext.form.FieldAncestor


### focus

Fires when this Component receives focus. ...

Fires when this Component receives focus.

**Parameters:** this : Ext.Component


### hide

Fires after the component is hidden. ...

Fires after the component is hidden. Fires after the component is hidden when calling the hide method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### move

Fires after the component is moved. ...

Fires after the component is moved.

**Parameters:** this : Ext.Component


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


### show

Fires after the component is shown when calling the show method. ...

Fires after the component is shown when calling the show method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### staterestore

Fires after the state of the object is restored. ...

Fires after the state of the object is restored.

**Parameters:** this : Ext.state.Stateful


### statesave

Fires after the state of the object is saved to the configured state provider. ...

Fires after the state of the object is saved to the configured state provider.

**Parameters:** this : Ext.state.Stateful


### validitychange

Fires when a change in the field's validity is detected. ...

Fires when a change in the field's validity is detected.

**Parameters:** this : Ext.form.field.Field


### $form-checkboxgroup-body-padding

**Type:** number/list

The padding of the CheckboxGroup body element ...

The padding of the CheckboxGroup body element Defaults to: `0 4px`


### $form-checkboxgroup-label-border-color

**Type:** number

The border-color of the CheckboxGroup label ...

The border-color of the CheckboxGroup label Defaults to: `$form-checkboxgroup-label-color`


### $form-checkboxgroup-label-border-style

**Type:** number

The border-style of the CheckboxGroup label ...

The border-style of the CheckboxGroup label Defaults to: `solid`


### $form-checkboxgroup-label-border-width

**Type:** number

The border-width of the CheckboxGroup label ...

The border-width of the CheckboxGroup label Defaults to: `0 0 1px 0`


### $form-checkboxgroup-label-color

**Type:** color

The text color of the CheckboxGroup label ...

The text color of the CheckboxGroup label Defaults to: `$form-label-font-color`


### $form-checkboxgroup-label-margin

**Type:** number

The margin of the CheckboxGroup label ...

The margin of the CheckboxGroup label Defaults to: `0 30px 5px 0`


### $form-checkboxgroup-label-padding

**Type:** number

The padding of the CheckboxGroup label ...

The padding of the CheckboxGroup label Defaults to: `2px`


### $form-error-icon-height

**Type:** number

Height for form error icons. ...

Height for form error icons. Defaults to: `16px`


### $form-error-icon-side-margin

**Type:** number/list

Margin for error icons that are aligned to the side of the field ...

Margin for error icons that are aligned to the side of the field Defaults to: `0 1px`


### $form-error-icon-width

**Type:** number

Width for form error icons. ...

Width for form error icons. Defaults to: `16px`


### $form-error-msg-color

**Type:** color

The text color of form error messages ...

The text color of form error messages Defaults to: `$form-field-invalid-border-color`


### $form-error-msg-font-family

**Type:** string

The font-family of form error messages ...

The font-family of form error messages Defaults to: `$font-family`


### $form-error-msg-font-size

**Type:** number

The font-size of form error messages ...

The font-size of form error messages Defaults to: `$font-size`


### $form-error-msg-font-weight

**Type:** string

The font-weight of form error messages ...

The font-weight of form error messages Defaults to: `normal`


### $form-error-msg-line-height

**Type:** number

The line-height of form error messages ...

The line-height of form error messages Defaults to: `$form-error-icon-height`


### $form-error-under-icon-spacing

**Type:** number

The space between the icon and the message for errors that display under the field ...

The space between the icon and the message for errors that display under the field Defaults to: `4px`


### $form-error-under-padding

**Type:** number/list

The padding on errors that display under the form field ...

The padding on errors that display under the form field Defaults to: `2px 2px 2px 0`


### $form-item-margin-bottom

**Type:** measurement

The bottom margin to apply to form items when in auto, anchor, vbox, or table layout ...

The bottom margin to apply to form items when in auto, anchor, vbox, or table layout Defaults to: `5px`


### $form-label-font-color

**Type:** color

The text color of form field labels ...

The text color of form field labels Defaults to: `$color`


### $form-label-font-family

**Type:** string

The font-family of form field labels ...

The font-family of form field labels Defaults to: `$font-family`


### $form-label-font-size

**Type:** number

The font-size of form field labels ...

The font-size of form field labels Defaults to: `$font-size`


### $form-label-font-weight

**Type:** string

The font-weight of form field labels ...

The font-weight of form field labels Defaults to: `normal`


### $form-label-line-height

**Type:** number

The line-height of form field labels ...

The line-height of form field labels Defaults to: `round ( $form-label-font-size * 1.15 )`


### $form-toolbar-label-color

**Type:** color

The text color of toolbar field labels ...

The text color of toolbar field labels Defaults to: `$color`


### $form-toolbar-label-font-family

**Type:** string

The font-family of toolbar field labels ...

The font-family of toolbar field labels Defaults to: `$font-family`


### $form-toolbar-label-font-size

**Type:** number

The font-size of toolbar field labels ...

The font-size of toolbar field labels Defaults to: `$font-size`


### $form-toolbar-label-font-weight

**Type:** string

The font-weight of toolbar field labels ...

The font-weight of toolbar field labels Defaults to: `normal`


### $form-toolbar-label-line-height

**Type:** number

The line-height of toolbar field labels ...

The line-height of toolbar field labels Defaults to: `round ( $form-toolbar-label-font-size * 1.15 )`


## Methods

### Ext.form.RadioGroup

Creates new Component. ...

Creates new Component.

**Parameters:** - config : Ext.Element/String/ObjectThe configuration options may be specified as either: **an element** : it is set as the internal element and its id used as the component id - **a string** : it is assumed to be the id of an existing element and is used as the component id - **anything else** : it is assumed to be a standard config object and is applied to the component


### add

Adds Component(s) to this Container. ...

Adds Component(s) to this Container. Description: - Fires the beforeadd event before adding. - The Container's default config values will be applied accordingly (see `defaults` for details). - Fires the `add` event after the component has been added. Notes: If the Container is **already rendered** when `add` is called, it will render the newly added Component into its content area. **If** the Container was configured with a size-managing layout manager, the Container will recalculate its internal layout at this time too. Note that the default layout manager simply renders child Components sequentially into the content area and thereafter performs no sizing. If adding multiple new child Components, pass them as an array to the `add` method, so that only one layout recalculation is performed. To inject components between existing ones, use the insert method. Warning: Components directly managed by the BorderLayout layout manager may not be removed or added. See the Notes for BorderLayout for more details. Available since: 2.3.0

**Parameters:** component : Ext.Component[]|Object[]/Ext.Component.../Object...Either one or more Components to add or an Array of Components to add. See `items` for additional information.


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


### addUIClsToElement

Method which adds a specified UI + uiCls to the components element. ...

Method which adds a specified UI + `uiCls` to the components element. Can be overridden to remove the UI from more than just the components element.

**Parameters:** ui : StringThe UI to remove from the element.


### addUIToElement

Method which adds a specified UI to the components element. ...

Method which adds a specified UI to the components element.


### adjustForConstraints

private ==> used outside of core TODO: currently only used by ToolTip. ...

private ==> used outside of core TODO: currently only used by ToolTip. does this method belong here?

**Parameters:** xy : Object


### adjustPosition

...

**Parameters:** x : Object


### afterComponentLayout

Called by the layout system after the Component has been laid out. ...

Called by the layout system after the Component has been laid out. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterFirstLayout

...

**Parameters:** width : Object


### afterHide

Invoked after the Component has been hidden. ...

Invoked after the Component has been hidden. Gets passed the same `callback` and `scope` parameters that onHide received. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### afterLayout

Invoked after the Container has laid out (and rendered if necessary) its child Components. ...

Invoked after the Container has laid out (and rendered if necessary) its child Components. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


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


### batchChanges

A utility for grouping a set of modifications which may trigger value changes into a single transaction, to prevent e...

A utility for grouping a set of modifications which may trigger value changes into a single transaction, to prevent excessive firing of change events. This is useful for instance if the field has sub-fields which are being updated as a group; you don't want the container field to check its own changed state for each subfield change.

**Parameters:** fn : ObjectA function containing the transaction code


### beforeBlur

Template method to do any pre-blur processing. ...

Template method to do any pre-blur processing.

**Parameters:** e : Ext.EventObjectThe event object


### beforeComponentLayout

Occurs before componentLayout is run. ...

Occurs before `componentLayout` is run. Returning `false` from this method will prevent the `componentLayout` from being executed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeDestroy

...

Overrides: Ext.container.AbstractContainer.beforeDestroy, Ext.panel.Panel.beforeDestroy


### beforeFocus

Template method to do any pre-focus processing. ...

Template method to do any pre-focus processing.

**Parameters:** e : Ext.EventObjectThe event object


### beforeLayout

Occurs before componentLayout is run. ...

Occurs before componentLayout is run. In previous releases, this method could return `false` to prevent its layout but that is not supported in Ext JS 4.1 or higher. This method is simply a notification of the impending layout to give the component a chance to adjust the DOM. Ideally, DOM reads should be avoided at this time to reduce expensive document reflows. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### beforeRender

...

Overrides: Ext.Component.beforeRender


### beforeReset

Template method before a field is reset. ...

Template method before a field is reset.


### beforeSetPosition

Template method called before a Component is positioned. ...

Template method called before a Component is positioned. Ensures that the position is adjusted so that the Component is constrained if so configured.

**Parameters:** x : Object


### beforeShow

Invoked before the Component is shown. ...

Invoked before the Component is shown. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### blur

...

**Returns:** Ext.Componentthis


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


### checkChange

Checks whether the value of the field has changed since the last time it was checked. ...

Checks whether the value of the field has changed since the last time it was checked. If the value has changed, it: - Fires the change event, - Performs validation if the validateOnChange config is enabled, firing the validitychange event if the validity has changed, and - Checks the dirty state of the field and fires the dirtychange event if it has changed. Overrides: Ext.form.field.Field.checkChange


### checkDirty

Checks the isDirty state of the field and if it has changed since the last time it was checked, fires the dirtychange...

Checks the isDirty state of the field and if it has changed since the last time it was checked, fires the dirtychange event.


### child

Retrieves the first direct child of this container which matches the passed selector or component. ...

Retrieves the first direct child of this container which matches the passed selector or component. The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.

**Parameters:** selector : String/Ext.Component (optional)An Ext.ComponentQuery selector. If no selector is specified, the first child will be returned.


### clearInvalid

Clear any invalid styles/messages for this field. ...

Clear any invalid styles/messages for this field. Components using this mixin should implement this method to update the components rendering to clear any existing messages. **Note**: this method does not cause the Field's validate or isValid methods to return `true` if the value does not *pass* validation. So simply clearing a field's errors will not necessarily allow submission of forms submitted with the Ext.form.action.Submit.clientValidation option set.


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


### configClass

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


### convertPositionSpec

Defined in override Ext.rtl.AbstractComponent. ...

**Defined in override Ext.rtl.AbstractComponent.**

**Parameters:** posSpec : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.

**Parameters:** newName : StringThe name under which to refire the passed parameters.


### deleteMembers

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### detachComponent

Detach a component from the DOM ...

Detach a component from the DOM

**Parameters:** component : Object


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


### doRenderFramingDockedItems

...

**Parameters:** out : Object


### down

Retrieves the first descendant of this container which matches the passed selector. ...

Retrieves the first descendant of this container which matches the passed selector. The passed in selector must comply with an Ext.ComponentQuery selector, or it can be an actual Ext.Component.

**Parameters:** selector : String/Ext.Component (optional)An Ext.ComponentQuery selector or Ext.Component. If no selector is specified, the first child will be returned.


### eachBox

Convenience function which calls the given function for every checkbox in the group ...

Convenience function which calls the given function for every checkbox in the group

**Parameters:** fn : FunctionThe function to call


### enable

Enable all immediate children that was previously disabled Override enable because onEnable only gets called when ren...

Enable all immediate children that was previously disabled Override enable because onEnable only gets called when rendered Enable the component Available since: 1.1.0

**Parameters:** silent : Boolean (optional)Passing `true` will suppress the `enable` event from being fired. Defaults to: `false`


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if present. There is no implementation in the Observable base class. This is commonly used by Ext.Components to bubble events to owner Containers. See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the Component's immediate owner. But if a known target is required, this can be overridden to access the required target more quickly. Example:

**Parameters:** eventNames : String/String[]The event name to bubble, or an Array of event names.


### ensureAttachedToBody

Ensures that this component is attached to document.body. ...

Ensures that this component is attached to `document.body`. If the component was rendered to Ext.getDetachedBody, then it will be appended to `document.body`. Any configured position is also restored.

**Parameters:** runLayout : Boolean (optional)True to run the component's layout. Defaults to: `false`


### extractFileInput

Only relevant if the instance's isFileUpload method returns true. ...

Only relevant if the instance's isFileUpload method returns true.

**Returns:** a reference to the file input DOM element holding the user's selected file. The input will be appended into the submission form and will not be returned, so this method should also create a replacement. ReturnsHTMLElement


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


### getActiveError

Gets the active error message for this component, if any. ...

Gets the active error message for this component, if any. This does not trigger validation on its own, it merely returns any message that the component may already hold.

**Returns:** StringThe active error message on the component; if there is no error, an empty string is returned.


### getActiveErrors

Gets an Array of any active error messages currently applied to the field. ...

Gets an Array of any active error messages currently applied to the field. This does not trigger validation on its own, it merely returns any messages that the component may already hold.

**Returns:** String[]The active error messages on the component; if there are no errors, an empty Array is returned.


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


### getBodyColspan

Calculates the colspan value for the body cell - the cell which contains the input field. ...

Calculates the colspan value for the body cell - the cell which contains the input field. The field table structure contains 4 columns:


### getBorderPadding

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Returns:** the size of the element's borders and padding. ReturnsObjectan object with the following numeric properties - beforeX - afterX - beforeY - afterY


### getBox

Return an object defining the area of this Element which can be passed to setBox to set another Element's size/locati...

Return an object defining the area of this Element which can be passed to setBox to set another Element's size/location to match this element.

**Parameters:** contentBox : Boolean (optional)If true a box for the content of the element is returned.


### getBoxes

Returns all checkbox components within the container ...

**Parameters:** query : String (optional)An additional query to add to the selector.

**Returns:** all checkbox components within the container


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable

**Returns:** Ext.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getBubbleTarget

Implements an upward event bubbling policy. ...

Implements an upward event bubbling policy. By default a Component bubbles events up to its reference owner. Component subclasses may implement a different bubbling strategy by overriding this method. Overrides: Ext.AbstractComponent.getBubbleTarget


### getChecked

Returns an Array of all checkboxes in the container which are currently checked ...

**Returns:** an Array of all checkboxes in the container which are currently checked ReturnsExt.form.field.Checkbox[]Array of Ext.form.field.Checkbox components


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


### getCombinedErrors

Takes an Array of invalid Ext.form.field.Field objects and builds a combined list of error messages from them. ...

Takes an Array of invalid Ext.form.field.Field objects and builds a combined list of error messages from them. Defaults to prepending each message by the field name and a colon. This can be overridden to provide custom combined error message handling, for instance changing the format of each message or sorting the array (it is sorted in order of appearance by default).

**Parameters:** invalidFields : Ext.form.field.Field[]An Array of the sub-fields which are currently invalid.


### getComponent

Examines this container's items property and gets a direct child component of this container. ...

Examines this container's items **property** and gets a direct child component of this container. Available since: 2.3.0

**Parameters:** - comp : String/NumberThis parameter may be any of the following: a **String** : representing the itemId or id of the child component. - a **Number** : representing the position of the child component within the items **property** For additional information see Ext.util.MixedCollection.get.


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


### getDragEl

...


### getEl

Retrieves the top level element representing this component. ...

Retrieves the top level element representing this component. Available since: 1.1.0

**Returns:** Ext.dom.Element


### getElConfig

...


### getErrorMsgCls

...


### getErrors

Runs CheckboxGroup's validations and returns an array of any errors. ...

Runs CheckboxGroup's validations and returns an array of any errors. The only error by default is if allowBlank is set to true and no items are checked.

**Returns:** String[]Array of all validation errors


### getFieldLabel

Returns the combined field label if combineLabels is set to true and if there is no set fieldLabel. ...

**Returns:** the combined field label if combineLabels is set to true and if there is no set fieldLabel. Otherwise returns the fieldLabel like normal. You can also override this method to provide a custom generated label. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


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


### getHeight

Gets the current height of the component's underlying element. ...

Gets the current height of the component's underlying element.

**Returns:** Number


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


### getInputId

Get the input id, if any, for this component. ...

Get the input id, if any, for this component. This is used as the "for" attribute on the label element. Implementing subclasses may also use this as e.g. the id for their own input element.

**Returns:** StringThe input id


### getInsertPosition

This function takes the position argument passed to onRender and returns a DOM element that you can use in the insert...

This function takes the position argument passed to onRender and returns a DOM element that you can use in the insertBefore.

**Parameters:** position : String/Number/Ext.dom.Element/HTMLElementIndex, element id or element you want to put this component before.


### getInsertionRenderData

...

**Parameters:** data : Object


### getItemId

Returns the value of itemId assigned to this component, or when that is not set, returns the value of id. ...

**Returns:** the value of itemId assigned to this component, or when that is not set, returns the value of id. ReturnsString


### getLabelCellAttrs

...


### getLabelCellStyle

...


### getLabelCls

...


### getLabelStyle

Gets any label styling for the labelEl ...

Gets any label styling for the labelEl

**Returns:** StringThe label styling


### getLabelWidth

Gets the width of the label (if visible) ...

Gets the width of the label (if visible)

**Returns:** NumberThe label width


### getLabelableRenderData

Generates the arguments for the field decorations rendering template. ...

Generates the arguments for the field decorations rendering template.

**Returns:** ObjectThe template arguments


### getLayout

Returns the layout instance currently associated with this Container. ...

**Returns:** the layout instance currently associated with this Container. If a layout has not been instantiated yet, that is done first ReturnsExt.layout.container.ContainerThe layout


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


### getMaskTarget

...


### getModelData

Don't return any data for the model; the form will get the info from the individual checkboxes themselves. ...

Don't return any data for the model; the form will get the info from the individual checkboxes themselves.

**Returns:** the value(s) that should be saved to the Ext.data.Model instance for this field, when Ext.form.Basic.updateRecord is called. Typically this will be an object with a single name-value pair, the name being this field's name and the value being its current data value. More advanced field implementations may return more than one name-value pair. The returned values will be saved to the corresponding field names in the Model. Note that the values returned from this method are not guaranteed to have been successfully validated. ReturnsObjectA mapping of submit parameter names to values; each value should be a string, or an array of strings if that particular name has multiple values. It can also return null if there are no parameters to be submitted.


### getName

Returns the name attribute of the field. ...

**Returns:** the name attribute of the field. This is used as the parameter name when including the field value in a form submit(). ReturnsStringname The field name


### getOffsetsTo

Returns the offsets of this element from the passed element. ...

**Parameters:** offsetsTo : Ext.util.Positionable/HTMLElement/StringThe Positionable, HTMLElement, or element id to get get the offsets from.

**Returns:** the offsets of this element from the passed element. The element must both be part of the DOM tree and not have display:none to have page coordinates.


### getOuterSize

Include margins ...

Include margins


### getOverflowEl

Get an el for overflowing, defaults to the target el ...

Get an el for overflowing, defaults to the target el Overrides: Ext.AbstractComponent.getOverflowEl


### getOverflowStyle

Returns the CSS style object which will set the Component's scroll styles. ...

**Returns:** the CSS style object which will set the Component's scroll styles. This must be applied to the target element.


### getOwningBorderContainer

Returns the owning container if that container uses border layout. ...

**Returns:** the owning container if that container uses `border` layout. Otherwise this method returns `null`. **Defined in override Ext.layout.container.border.Region.** ReturnsExt.container.ContainerThe owning border container or `null`.


### getOwningBorderLayout

Returns the owning border (Ext.layout.container.Border) instance if there is one. ...

**Returns:** the owning `border` (`Ext.layout.container.Border`) instance if there is one. Otherwise this method returns `null`. **Defined in override Ext.layout.container.border.Region.** ReturnsExt.layout.container.BorderThe owning border layout or `null`.


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


### getProxy

...


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


### getStyleProxy

Returns an offscreen div with the same class name as the element this is being rendered. ...

**Parameters:** cls : Object

**Returns:** an offscreen div with the same class name as the element this is being rendered. This is because child item rendering takes place in a detached div which, being not part of the document, has no styling.


### getSubTplData

...


### getSubTplMarkup

Gets the markup to be inserted into the outer template's bodyEl. ...

Gets the markup to be inserted into the outer template's bodyEl. Defaults to empty string, should be implemented by classes including this mixin as needed.

**Returns:** StringThe markup to be inserted


### getSubmitData

Don't return any data for submit; the form will get the info from the individual checkboxes themselves. ...

Don't return any data for submit; the form will get the info from the individual checkboxes themselves.

**Returns:** the parameter(s) that would be included in a standard form submit for this field. Typically this will be an object with a single name-value pair, the name being this field's name and the value being its current stringified value. More advanced field implementations may return more than one name-value pair. Note that the values returned from this method are not guaranteed to have been successfully validated. ReturnsObjectA mapping of submit parameter names to values; each value should be a string, or an array of strings if that particular name has multiple values. It can also return null if there are no parameters to be submitted.


### getTargetEl

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. ...

This is used to determine where to insert the 'html', 'contentEl' and 'items' in this component. Overrides: Ext.AbstractComponent.getTargetEl


### getTpl

...

**Parameters:** name : Object


### getValue

Returns an object containing the values of all checked checkboxes within the group. ...

**Returns:** an object containing the values of all checked checkboxes within the group. Each key-value pair in the object corresponds to a checkbox name. If there is only one checked checkbox with a particular name, the value of that pair will be the String inputValue of that checkbox. If there are multiple checked checkboxes with that name, the value of that pair will be an Array of the selected inputValues. The object format returned from this method can also be passed directly to the setValue method. NOTE: In Ext 3, this method returned an array of Checkbox components; this was changed to make it more consistent with other field components and with the setValue argument signature. If you need the old behavior in Ext 4+, use the getChecked method instead. Overrides: Ext.form.field.Field.getValue


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


### handleFieldErrorChange

Handle bubbled errorchange events from descendants; invoke the aggregated event and method ...

Handle bubbled errorchange events from descendants; invoke the aggregated event and method

**Parameters:** labelable : Object


### handleFieldValidityChange

Handle bubbled validitychange events from descendants; invoke the aggregated event and method ...

Handle bubbled validitychange events from descendants; invoke the aggregated event and method

**Parameters:** field : Object


### hasActiveError

Tells whether the field currently has an active error message. ...

Tells whether the field currently has an active error message. This does not trigger validation on its own, it merely looks for any message that the component may already hold.

**Returns:** Boolean


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


### hasUICls

Checks if there is currently a specified uiCls. ...

Checks if there is currently a specified `uiCls`.

**Parameters:** cls : StringThe `cls` to check.


### hasVisibleLabel

Checks if the field has a visible label ...

Checks if the field has a visible label

**Returns:** BooleanTrue if the field has a visible label


### hide

Hides this Component, setting it to invisible using the configured hideMode. ...

Hides this Component, setting it to invisible using the configured hideMode.

**Parameters:** animateTarget : String/Ext.Element/Ext.Component (optional)only valid for floating Components such as Windows or ToolTips, or regular Components which have been configured with `floating: true`.. The target to which the Component should animate while hiding. Defaults to: `null`


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


### initDraggable

...


### initEvents

Initialize any events on this component ...

Initialize any events on this component


### initField

Initializes this Field mixin on the current instance. ...

Initializes this Field mixin on the current instance. Components using this mixin should call this method during their own initialization process.


### initFieldAncestor

Initializes the FieldAncestor's state; this must be called from the initComponent method of any components importing ...

Initializes the FieldAncestor's state; this must be called from the initComponent method of any components importing this mixin.


### initFieldDefaults

Initialize the fieldDefaults object ...

Initialize the fieldDefaults object


### initFrame

...


### initFramingTpl

Poke in a reference to applyRenderTpl(frameInfo, out) ...

Poke in a reference to applyRenderTpl(frameInfo, out)

**Parameters:** table : Object


### initHierarchyEvents

...


### initHierarchyState

Called by getHierarchyState to initialize the hierarchyState the first time it is requested. ...

Called by getHierarchyState to initialize the hierarchyState the first time it is requested. **Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** hierarchyState : Object


### initItems

...


### initLabelable

Performs initialization of this mixin. ...

Performs initialization of this mixin. Component classes using this mixin should call this method during their own initialization.


### initMonitor

...


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

**Parameters:** resizable : Object


### initState

Initializes the state of the object upon construction. ...

Initializes the state of the object upon construction.


### initStyles

Applies padding, margin, border, top, left, height, and width configs to the appropriate elements. ...

Applies padding, margin, border, top, left, height, and width configs to the appropriate elements.

**Parameters:** targetEl : Object


### initValue

Initializes the field's value based on the initial config. ...

Initializes the field's value based on the initial config. If the value config is specified then we use that to set the value; otherwise we initialize the originalValue by querying the values of all sub-checkboxes after they have been initialized. Overrides: Ext.form.field.Field.initValue


### insert

Inserts a Component into this Container at a specified index. ...

Inserts a Component into this Container at a specified index. Fires the beforeadd event before inserting, then fires the add event after the Component has been inserted. Available since: 2.3.0

**Parameters:** index : NumberThe index at which the Component will be inserted into the Container's items collection


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


### isDirty

private override Returns true if the value of this Field has been changed from its originalValue. ...

private override

**Returns:** true if the value of this Field has been changed from its originalValue. Will always return false if the field is disabled. Note that if the owning form was configured with trackResetOnLoad then the originalValue is updated when the values are loaded by Ext.form.Basic.setValues. ReturnsBooleanTrue if this field has been changed from its original value (and is not disabled), false otherwise.


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


### isEqual

private override - the group value is a complex object, compare using object serialization Returns whether two field...

private override - the group value is a complex object, compare using object serialization

**Parameters:** value1 : ObjectThe first value to compare

**Returns:** whether two field values are logically equal. Field implementations may override this to provide custom comparison logic appropriate for the particular field's data type.


### isEqualAsString

Returns whether two values are logically equal. ...

**Parameters:** value1 : ObjectThe first value to compare

**Returns:** whether two values are logically equal. Similar to isEqual, however null or undefined values will be treated as empty strings.


### isFileUpload

Returns whether this Field is a file upload field; if it returns true, forms will use special techniques for submitti...

**Returns:** whether this Field is a file upload field; if it returns true, forms will use special techniques for submitting the form via AJAX. See Ext.form.Basic.hasUpload for details. If this returns true, the extractFileInput method must also be implemented to return the corresponding file input element. ReturnsBoolean


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

Determines whether this Component is the root of a layout. This returns `true` if this component can run its layout without assistance from or impact on its owner. If this component cannot run its layout given these restrictions, `false` is returned and its owner will be considered as the next candidate for the layout root. Setting the _isLayoutRoot property to `true` causes this method to always return `true`. This may be useful when updating a layout of a Container which shrink wraps content, and you know that it will not change size, and so can safely be the topmost participant in the layout run.


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


### isValid

Returns whether or not the field value is currently valid by validating the field's current value. ...

**Returns:** whether or not the field value is currently valid by validating the field's current value. The validitychange event will not be fired; use validate instead if you want the event to fire. **Note**: disabled fields are always treated as valid. Implementations are encouraged to ensure that this method does not have side-effects such as triggering error message display. ReturnsBooleanTrue if the value is valid, else false


### isVisible

Returns true if this component is visible. ...

**Parameters:** deep : Boolean (optional)Pass `true` to interrogate the visibility status of all parent Containers to determine whether this Component is truly visible to the user. Generally, to determine whether a Component is hidden, the no argument form is needed. For example when creating dynamically laid out UIs in a hidden Container before showing them. Defaults to: `false`

**Returns:** `true` if this component is visible. Available since: 1.1.0


### isXType

Tests whether or not this Component is of a specific xtype. ...

Tests whether or not this Component is of a specific xtype. This can test whether this Component is descended from the xtype (default) or whether it is directly of the xtype specified (`shallow = true`). If using your own subclasses, be aware that a Component must register its own xtype to participate in determination of inherited xtypes. For a list of all available xtypes, see the Ext.Component header. Example usage: Available since: 2.3.0

**Parameters:** xtype : StringThe xtype to check for this Component


### lookupComponent

...

**Parameters:** comp : Object


### makeFloating

...

**Parameters:** dom : Object


### markInvalid

Associate one or more error messages with this field. ...

Associate one or more error messages with this field. Components using this mixin should implement this method to update the component's rendering to display the messages. **Note**: this method does not cause the Field's validate or isValid methods to return `false` if the value does *pass* validation. So simply marking a Field as invalid will not prevent submission of forms submitted with the Ext.form.action.Submit.clientValidation option set.

**Parameters:** errors : String/String[]The error message(s) for the field.


### mask

...


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

When a checkbox is added to the group, monitor it for changes ...

When a checkbox is added to the group, monitor it for changes

**Parameters:** field : Object


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

**Parameters:** width : Object


### onChange

Called when the field's value changes. ...

Called when the field's value changes. Performs validation if the validateOnChange config is enabled, and invokes the dirty check.

**Parameters:** newVal : Object


### onChildFieldAdd

...

**Parameters:** field : Object


### onChildFieldRemove

...

**Parameters:** field : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onDestroy

Allows addition of behavior to the destroy operation. ...

Allows addition of behavior to the destroy operation. After calling the superclass's onDestroy, the Component will be destroyed. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onDirtyChange

Called when the field's dirty state changes. ...

Called when the field's dirty state changes.

**Parameters:** isDirty : Boolean


### onDisable

Allows addition of behavior to the disable operation. ...

Allows addition of behavior to the disable operation. After calling the superclass's `onDisable`, the Component will be disabled. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onEnable

Allows addition of behavior to the enable operation. ...

Allows addition of behavior to the enable operation. After calling the superclass's `onEnable`, the Component will be enabled. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onFieldErrorChange

Fired when the error message of any field within the container changes, and updates the combined error message to match. ...

Fired when the error message of any field within the container changes, and updates the combined error message to match.

**Parameters:** field : Object


### onFieldValidityChange

Fired when the validity of any field within the container changes. ...

Fired when the validity of any field within the container changes.

**Parameters:** field : Ext.form.field.FieldThe sub-field whose validity changed


### onFloatShow

...


### onFocus

private ...

private

**Parameters:** e : Object


### onHide

Possibly animates down to a target element. ...

Possibly animates down to a target element. Allows addition of behavior to the hide operation. After calling the superclass’s onHide, the Component will be hidden. Gets passed the same parameters as hide. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onKeyDown

Listen for TAB events and wrap round if tabbing of either end of the Floater ...

Listen for TAB events and wrap round if tabbing of either end of the Floater

**Parameters:** e : Object


### onMouseDown

Mousedown brings to front, and programatically grabs focus unless the mousedown was on a focusable element ...

Mousedown brings to front, and programatically grabs focus *unless the mousedown was on a focusable element*

**Parameters:** e : Object


### onMove

...


### onPosition

Called after the component is moved, this method is empty by default but can be implemented by any subclass that need...

Called after the component is moved, this method is empty by default but can be implemented by any subclass that needs to perform custom logic after a move occurs. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRemove

Called when a Ext.form.Labelable instance is removed from the container's subtree. ...

Called when a Ext.form.Labelable instance is removed from the container's subtree.

**Parameters:** labelable : Ext.form.LabelableThe instance that was removed


### onRemoved

Method to manage awareness of when components are removed from their respective Container, firing a removed event. ...

Method to manage awareness of when components are removed from their respective Container, firing a removed event. References are properly cleaned up after removing a component from its owning container. Allows addition of behavior when a Component is removed from its parent Container. At this stage, the Component has been removed from its parent Container's collection of child items, but has not been destroyed (It will be destroyed if the parent Container's `autoDestroy` is `true`, or if the remove call was passed a truthy second parameter). After calling the superclass's `onRemoved`, the `ownerCt` and the `refOwner` will not be present. Available since: 3.4.0 This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onRender

Template method called when this Component's DOM structure is created. ...

Template method called when this Component's DOM structure is created. At this point, this Component's (and all descendants') DOM structure *exists* but it has not been layed out (positioned and sized). Subclasses which override this to gain access to the structure at render time should call the parent class's method before attempting to access any child elements of the Component. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


### onResize

Allows addition of behavior to the resize operation. ...

Allows addition of behavior to the resize operation. Called when Ext.resizer.Resizer#drag event is fired. This is a template method. a hook into the functionality of this class. Feel free to override it in child classes.


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


### parseBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** box : Object


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

Method which removes a specified UI + uiCls from the components element. ...

Method which removes a specified UI + `uiCls` from the components element. The `cls` which is added to the element will be: `this.baseCls + '-' + ui`.

**Parameters:** ui : StringThe UI to add to the element.


### removeUIFromElement

Method which removes a specified UI from the components element. ...

Method which removes a specified UI from the components element.


### render

Renders the Component into the passed HTML element. ...

Renders the Component into the passed HTML element. If you are using a Container object to house this Component, then do not use the render method. A Container's child Components are rendered by that Container's layout manager when the Container is first rendered. If the Container is already rendered when a new child Component is added, you may need to call the Container's doLayout to refresh the view which causes any unrendered child Components to be rendered. This is required so that you can add multiple child components if needed while only refreshing the layout once. When creating complex UIs, it is important to remember that sizing and positioning of child items is the responsibility of the Container's layout manager. If you expect child items to be sized in response to user interactions, you must configure the Container with a layout manager which creates and manages the type of layout you have in mind. Omitting the Container's layout config means that a basic layout manager is used which does nothing but render child components sequentially into the Container. No sizing or positioning will be performed in this situation.

**Parameters:** container : Ext.Element/HTMLElement/String (optional)The element this Component should be rendered into. If it is being created from existing markup, this should be omitted.


### renderActiveError

Updates the rendered DOM to match the current activeError. ...

Updates the rendered DOM to match the current activeError. This only updates the content and attributes, you'll have to call doComponentLayout to actually update the display.


### repositionFloatingItems

...


### reset

Resets the checked state of all checkboxes in the group to their originally loaded values and clears any validation m...

Resets the checked state of all checkboxes in the group to their originally loaded values and clears any validation messages. See Ext.form.Basic.trackResetOnLoad Overrides: Ext.form.field.Field.reset


### resetOriginalValue

Resets the field's originalValue property so it matches the current value. ...

Resets the field's originalValue property so it matches the current value. This is called by Ext.form.Basic.setValues if the form's trackResetOnLoad property is set to true. Overrides: Ext.form.field.Field.resetOriginalValue


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


### saveState

Saves the state of the object to the persistence store. ...

Saves the state of the object to the persistence store.


### scrollBy

Scrolls this Component's target element by the passed delta values, optionally animating. ...

Scrolls this Component's target element by the passed delta values, optionally animating. All of the following are equivalent:

**Parameters:** deltaX : Number/Number[]/ObjectEither the x delta, an Array specifying x and y deltas or an object with "x" and "y" properties.


### sequenceFx

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. ...

Ensures that all effects queued after sequenceFx is called on this object are run in sequence. This is the opposite of syncFx.

**Returns:** Objectthis


### setActive

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been moved to th...

This method is called internally by Ext.ZIndexManager to signal that a floating Component has either been moved to the top of its zIndex stack, or pushed from the top of its zIndex stack. If a *Window* is superceded by another Window, deactivating it hides its shadow. This method also fires the activate or deactivate event depending on which action occurred.

**Parameters:** active : Boolean (optional)True to activate the Component, false to deactivate it. Defaults to: `false`


### setActiveError

Sets the active error message to the given string. ...

Sets the active error message to the given string. This replaces the entire error message contents with the given string. Also see setActiveErrors which accepts an Array of messages and formats them according to the activeErrorsTpl. Note that this only updates the error message element's text and attributes, you'll have to call doComponentLayout to actually update the field's layout to match. If the field extends Ext.form.field.Base you should call markInvalid instead.

**Parameters:** msg : StringThe error message


### setActiveErrors

Set the active error message to an Array of error messages. ...

Set the active error message to an Array of error messages. The messages are formatted into a single message string using the activeErrorsTpl. Also see setActiveError which allows setting the entire error contents with a single string. Note that this only updates the error message element's text and attributes, you'll have to call doComponentLayout to actually update the field's layout to match. If the field extends Ext.form.field.Base you should call markInvalid instead.

**Parameters:** errors : String[]The error messages


### setAutoScroll

Sets the overflow on the content element of the component. ...

Sets the overflow on the content element of the component.

**Parameters:** scroll : BooleanTrue to allow the Component to auto scroll.


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


### setFieldDefaults

Applies a set of default configuration values to this Labelable instance. ...

Applies a set of default configuration values to this Labelable instance. For each of the properties in the given object, check if this component hasOwnProperty that config; if not then it's inheriting a default value from its prototype and we should apply the default value.

**Parameters:** defaults : ObjectThe defaults to apply to the object.


### setFieldLabel

Set the label of this field. ...

Set the label of this field.

**Parameters:** label : StringThe new label. The labelSeparator will be automatically appended to the label string.


### setFloatParent

...

**Parameters:** floatParent : Object


### setHeight

Sets the height of the component. ...

Sets the height of the component. This method fires the resize event.

**Parameters:** - height : NumberThe new height to set. This may be one of: A Number specifying the new height in the Element's Ext.Element.defaultUnits (by default, pixels). - A String used to set the CSS height style. - *undefined* to leave the height unchanged.


### setHiddenState

...

**Parameters:** hidden : Object


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


### setReadOnly

private override ...

private override

**Parameters:** readOnly : Object


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


### setUI

Sets the UI for the component. ...

Sets the UI for the component. This will remove any existing UIs on the component. It will also loop through any `uiCls` set on the component and rename them so they include the new UI.

**Parameters:** ui : StringThe new UI for the component.


### setValue

Sets the value of the radio group. ...

Sets the value of the radio group. The radio with corresponding name and value will be set. This method is simpler than Ext.form.CheckboxGroup.setValue because only 1 value is allowed for each name.

**Parameters:** value : ObjectThe map from names to values to be set.


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


### transformOriginalValue

Allows for any necessary modifications before the original value is set ...

Allows for any necessary modifications before the original value is set

**Parameters:** value : ObjectThe initial value


### translatePoints

Translates the passed page coordinates into left/top css values for the element ...

Translates the passed page coordinates into left/top css values for the element

**Parameters:** x : Number/ArrayThe page x or an array containing [x, y]


### translateXY

Translates the passed page coordinates into x and y css values for the element ...

Translates the passed page coordinates into x and y css values for the element

**Parameters:** x : Number/ArrayThe page x or an array containing [x, y]


### trimLabelSeparator

Returns the trimmed label by slicing off the label separator character. ...

**Returns:** the trimmed label by slicing off the label separator character. Can be overridden. ReturnsStringThe trimmed field label, or empty string if not defined


### un

Shorthand for removeListener. ...

Shorthand for removeListener. Removes an event handler.

**Parameters:** eventName : StringThe type of event the handler was associated with.


### unitizeBox

Overridden in Ext.rtl.AbstractComponent. ...

**Overridden in Ext.rtl.AbstractComponent.**

**Parameters:** box : Object


### unmask

...


### unregisterFloatingItem

...

**Parameters:** cmp : Object


### unsetActiveError

Clears the active error message(s). ...

Clears the active error message(s). Note that this only clears the error message element's text and attributes, you'll have to call doComponentLayout to actually update the field's layout to match. If the field extends Ext.form.field.Base you should call clearInvalid instead.


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


### updateFrame

...


### updateLabel

Updates the content of the labelEl if it is rendered ...

Updates the content of the labelEl if it is rendered


### updateLayout

Updates this component's layout. ...

Updates this component's layout. If this update affects this components ownerCt, that component's `updateLayout` method will be called to perform the layout instead. Otherwise, just this component (and its child items) will layout.

**Parameters:** options : Object (optional)An object with layout options. defer : Boolean`true` if this layout should be deferred.


### validate

Returns whether or not the field value is currently valid by validating the field's current value, and fires the vali...

**Returns:** whether or not the field value is currently valid by validating the field's current value, and fires the validitychange event if the field's validity has changed since the last validation. **Note**: disabled fields are always treated as valid. Custom implementations of this method are allowed to have side-effects such as triggering error message display. To validate without side-effects, use isValid. ReturnsBooleanTrue if the value is valid, else false


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


### beforedeactivate

Fires before a Component has been visually deactivated. ...

Fires before a Component has been visually deactivated. Returning `false` from an event listener can prevent the deactivate from occurring.

**Parameters:** this : Ext.Component


### beforedestroy

Fires before the component is destroyed. ...

Fires before the component is destroyed. Return `false` from an event handler to stop the destroy. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforehide

Fires before the component is hidden when calling the hide method. ...

Fires before the component is hidden when calling the hide method. Return `false` from an event handler to stop the hide. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeremove

Fires before any Ext.Component is removed from the container. ...

Fires before any Ext.Component is removed from the container. A handler can return false to cancel the remove. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### beforerender

Fires before the component is rendered. ...

Fires before the component is rendered. Return `false` from an event handler to stop the render. Available since: 1.1.0

**Parameters:** this : Ext.Component


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


### change

Fires when the value of a field is changed via the setValue method. ...

Fires when the value of a field is changed via the setValue method.

**Parameters:** this : Ext.form.field.Field


### deactivate

Fires after a Component has been visually deactivated. ...

Fires after a Component has been visually deactivated.

**Parameters:** this : Ext.Component


### destroy

Fires after the component is destroyed. ...

Fires after the component is destroyed. Available since: 1.1.0

**Parameters:** this : Ext.Component


### dirtychange

Fires when a change in the field's isDirty state is detected. ...

Fires when a change in the field's isDirty state is detected.

**Parameters:** this : Ext.form.field.Field


### disable

Fires after the component is disabled. ...

Fires after the component is disabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### enable

Fires after the component is enabled. ...

Fires after the component is enabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### errorchange

Fires when the active error message is changed via setActiveError. ...

Fires when the active error message is changed via setActiveError.

**Parameters:** this : Ext.form.Labelable


### fielderrorchange

Fires when the active error message is changed for any one of the Ext.form.Labelable instances within this container. ...

Fires when the active error message is changed for any one of the Ext.form.Labelable instances within this container.

**Parameters:** this : Ext.form.FieldAncestor


### fieldvaliditychange

Fires when the validity state of any one of the Ext.form.field.Field instances within this container changes. ...

Fires when the validity state of any one of the Ext.form.field.Field instances within this container changes.

**Parameters:** this : Ext.form.FieldAncestor


### focus

Fires when this Component receives focus. ...

Fires when this Component receives focus.

**Parameters:** this : Ext.Component


### hide

Fires after the component is hidden. ...

Fires after the component is hidden. Fires after the component is hidden when calling the hide method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### move

Fires after the component is moved. ...

Fires after the component is moved.

**Parameters:** this : Ext.Component


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


### show

Fires after the component is shown when calling the show method. ...

Fires after the component is shown when calling the show method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### staterestore

Fires after the state of the object is restored. ...

Fires after the state of the object is restored.

**Parameters:** this : Ext.state.Stateful


### statesave

Fires after the state of the object is saved to the configured state provider. ...

Fires after the state of the object is saved to the configured state provider.

**Parameters:** this : Ext.state.Stateful


### validitychange

Fires when a change in the field's validity is detected. ...

Fires when a change in the field's validity is detected.

**Parameters:** this : Ext.form.field.Field


### $form-checkboxgroup-body-padding

**Type:** number/list

The padding of the CheckboxGroup body element ...

The padding of the CheckboxGroup body element Defaults to: `0 4px`


### $form-checkboxgroup-label-border-color

**Type:** number

The border-color of the CheckboxGroup label ...

The border-color of the CheckboxGroup label Defaults to: `$form-checkboxgroup-label-color`


### $form-checkboxgroup-label-border-style

**Type:** number

The border-style of the CheckboxGroup label ...

The border-style of the CheckboxGroup label Defaults to: `solid`


### $form-checkboxgroup-label-border-width

**Type:** number

The border-width of the CheckboxGroup label ...

The border-width of the CheckboxGroup label Defaults to: `0 0 1px 0`


### $form-checkboxgroup-label-color

**Type:** color

The text color of the CheckboxGroup label ...

The text color of the CheckboxGroup label Defaults to: `$form-label-font-color`


### $form-checkboxgroup-label-margin

**Type:** number

The margin of the CheckboxGroup label ...

The margin of the CheckboxGroup label Defaults to: `0 30px 5px 0`


### $form-checkboxgroup-label-padding

**Type:** number

The padding of the CheckboxGroup label ...

The padding of the CheckboxGroup label Defaults to: `2px`


### $form-error-icon-height

**Type:** number

Height for form error icons. ...

Height for form error icons. Defaults to: `16px`


### $form-error-icon-side-margin

**Type:** number/list

Margin for error icons that are aligned to the side of the field ...

Margin for error icons that are aligned to the side of the field Defaults to: `0 1px`


### $form-error-icon-width

**Type:** number

Width for form error icons. ...

Width for form error icons. Defaults to: `16px`


### $form-error-msg-color

**Type:** color

The text color of form error messages ...

The text color of form error messages Defaults to: `$form-field-invalid-border-color`


### $form-error-msg-font-family

**Type:** string

The font-family of form error messages ...

The font-family of form error messages Defaults to: `$font-family`


### $form-error-msg-font-size

**Type:** number

The font-size of form error messages ...

The font-size of form error messages Defaults to: `$font-size`


### $form-error-msg-font-weight

**Type:** string

The font-weight of form error messages ...

The font-weight of form error messages Defaults to: `normal`


### $form-error-msg-line-height

**Type:** number

The line-height of form error messages ...

The line-height of form error messages Defaults to: `$form-error-icon-height`


### $form-error-under-icon-spacing

**Type:** number

The space between the icon and the message for errors that display under the field ...

The space between the icon and the message for errors that display under the field Defaults to: `4px`


### $form-error-under-padding

**Type:** number/list

The padding on errors that display under the form field ...

The padding on errors that display under the form field Defaults to: `2px 2px 2px 0`


### $form-item-margin-bottom

**Type:** measurement

The bottom margin to apply to form items when in auto, anchor, vbox, or table layout ...

The bottom margin to apply to form items when in auto, anchor, vbox, or table layout Defaults to: `5px`


### $form-label-font-color

**Type:** color

The text color of form field labels ...

The text color of form field labels Defaults to: `$color`


### $form-label-font-family

**Type:** string

The font-family of form field labels ...

The font-family of form field labels Defaults to: `$font-family`


### $form-label-font-size

**Type:** number

The font-size of form field labels ...

The font-size of form field labels Defaults to: `$font-size`


### $form-label-font-weight

**Type:** string

The font-weight of form field labels ...

The font-weight of form field labels Defaults to: `normal`


### $form-label-line-height

**Type:** number

The line-height of form field labels ...

The line-height of form field labels Defaults to: `round ( $form-label-font-size * 1.15 )`


### $form-toolbar-label-color

**Type:** color

The text color of toolbar field labels ...

The text color of toolbar field labels Defaults to: `$color`


### $form-toolbar-label-font-family

**Type:** string

The font-family of toolbar field labels ...

The font-family of toolbar field labels Defaults to: `$font-family`


### $form-toolbar-label-font-size

**Type:** number

The font-size of toolbar field labels ...

The font-size of toolbar field labels Defaults to: `$font-size`


### $form-toolbar-label-font-weight

**Type:** string

The font-weight of toolbar field labels ...

The font-weight of toolbar field labels Defaults to: `normal`


### $form-toolbar-label-line-height

**Type:** number

The line-height of toolbar field labels ...

The line-height of toolbar field labels Defaults to: `round ( $form-toolbar-label-font-size * 1.15 )`


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


### beforedeactivate

Fires before a Component has been visually deactivated. ...

Fires before a Component has been visually deactivated. Returning `false` from an event listener can prevent the deactivate from occurring.

**Parameters:** this : Ext.Component


### beforedestroy

Fires before the component is destroyed. ...

Fires before the component is destroyed. Return `false` from an event handler to stop the destroy. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforehide

Fires before the component is hidden when calling the hide method. ...

Fires before the component is hidden when calling the hide method. Return `false` from an event handler to stop the hide. Available since: 1.1.0

**Parameters:** this : Ext.Component


### beforeremove

Fires before any Ext.Component is removed from the container. ...

Fires before any Ext.Component is removed from the container. A handler can return false to cancel the remove. Available since: 2.3.0

**Parameters:** this : Ext.container.Container


### beforerender

Fires before the component is rendered. ...

Fires before the component is rendered. Return `false` from an event handler to stop the render. Available since: 1.1.0

**Parameters:** this : Ext.Component


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


### change

Fires when the value of a field is changed via the setValue method. ...

Fires when the value of a field is changed via the setValue method.

**Parameters:** this : Ext.form.field.Field


### deactivate

Fires after a Component has been visually deactivated. ...

Fires after a Component has been visually deactivated.

**Parameters:** this : Ext.Component


### destroy

Fires after the component is destroyed. ...

Fires after the component is destroyed. Available since: 1.1.0

**Parameters:** this : Ext.Component


### dirtychange

Fires when a change in the field's isDirty state is detected. ...

Fires when a change in the field's isDirty state is detected.

**Parameters:** this : Ext.form.field.Field


### disable

Fires after the component is disabled. ...

Fires after the component is disabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### enable

Fires after the component is enabled. ...

Fires after the component is enabled. Available since: 1.1.0

**Parameters:** this : Ext.Component


### errorchange

Fires when the active error message is changed via setActiveError. ...

Fires when the active error message is changed via setActiveError.

**Parameters:** this : Ext.form.Labelable


### fielderrorchange

Fires when the active error message is changed for any one of the Ext.form.Labelable instances within this container. ...

Fires when the active error message is changed for any one of the Ext.form.Labelable instances within this container.

**Parameters:** this : Ext.form.FieldAncestor


### fieldvaliditychange

Fires when the validity state of any one of the Ext.form.field.Field instances within this container changes. ...

Fires when the validity state of any one of the Ext.form.field.Field instances within this container changes.

**Parameters:** this : Ext.form.FieldAncestor


### focus

Fires when this Component receives focus. ...

Fires when this Component receives focus.

**Parameters:** this : Ext.Component


### hide

Fires after the component is hidden. ...

Fires after the component is hidden. Fires after the component is hidden when calling the hide method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### move

Fires after the component is moved. ...

Fires after the component is moved.

**Parameters:** this : Ext.Component


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


### show

Fires after the component is shown when calling the show method. ...

Fires after the component is shown when calling the show method. Available since: 1.1.0

**Parameters:** this : Ext.Component


### staterestore

Fires after the state of the object is restored. ...

Fires after the state of the object is restored.

**Parameters:** this : Ext.state.Stateful


### statesave

Fires after the state of the object is saved to the configured state provider. ...

Fires after the state of the object is saved to the configured state provider.

**Parameters:** this : Ext.state.Stateful


### validitychange

Fires when a change in the field's validity is detected. ...

Fires when a change in the field's validity is detected.

**Parameters:** this : Ext.form.field.Field


### $form-checkboxgroup-body-padding

**Type:** number/list

The padding of the CheckboxGroup body element ...

The padding of the CheckboxGroup body element Defaults to: `0 4px`


### $form-checkboxgroup-label-border-color

**Type:** number

The border-color of the CheckboxGroup label ...

The border-color of the CheckboxGroup label Defaults to: `$form-checkboxgroup-label-color`


### $form-checkboxgroup-label-border-style

**Type:** number

The border-style of the CheckboxGroup label ...

The border-style of the CheckboxGroup label Defaults to: `solid`


### $form-checkboxgroup-label-border-width

**Type:** number

The border-width of the CheckboxGroup label ...

The border-width of the CheckboxGroup label Defaults to: `0 0 1px 0`


### $form-checkboxgroup-label-color

**Type:** color

The text color of the CheckboxGroup label ...

The text color of the CheckboxGroup label Defaults to: `$form-label-font-color`


### $form-checkboxgroup-label-margin

**Type:** number

The margin of the CheckboxGroup label ...

The margin of the CheckboxGroup label Defaults to: `0 30px 5px 0`


### $form-checkboxgroup-label-padding

**Type:** number

The padding of the CheckboxGroup label ...

The padding of the CheckboxGroup label Defaults to: `2px`


### $form-error-icon-height

**Type:** number

Height for form error icons. ...

Height for form error icons. Defaults to: `16px`


### $form-error-icon-side-margin

**Type:** number/list

Margin for error icons that are aligned to the side of the field ...

Margin for error icons that are aligned to the side of the field Defaults to: `0 1px`


### $form-error-icon-width

**Type:** number

Width for form error icons. ...

Width for form error icons. Defaults to: `16px`


### $form-error-msg-color

**Type:** color

The text color of form error messages ...

The text color of form error messages Defaults to: `$form-field-invalid-border-color`


### $form-error-msg-font-family

**Type:** string

The font-family of form error messages ...

The font-family of form error messages Defaults to: `$font-family`


### $form-error-msg-font-size

**Type:** number

The font-size of form error messages ...

The font-size of form error messages Defaults to: `$font-size`


### $form-error-msg-font-weight

**Type:** string

The font-weight of form error messages ...

The font-weight of form error messages Defaults to: `normal`


### $form-error-msg-line-height

**Type:** number

The line-height of form error messages ...

The line-height of form error messages Defaults to: `$form-error-icon-height`


### $form-error-under-icon-spacing

**Type:** number

The space between the icon and the message for errors that display under the field ...

The space between the icon and the message for errors that display under the field Defaults to: `4px`


### $form-error-under-padding

**Type:** number/list

The padding on errors that display under the form field ...

The padding on errors that display under the form field Defaults to: `2px 2px 2px 0`


### $form-item-margin-bottom

**Type:** measurement

The bottom margin to apply to form items when in auto, anchor, vbox, or table layout ...

The bottom margin to apply to form items when in auto, anchor, vbox, or table layout Defaults to: `5px`


### $form-label-font-color

**Type:** color

The text color of form field labels ...

The text color of form field labels Defaults to: `$color`


### $form-label-font-family

**Type:** string

The font-family of form field labels ...

The font-family of form field labels Defaults to: `$font-family`


### $form-label-font-size

**Type:** number

The font-size of form field labels ...

The font-size of form field labels Defaults to: `$font-size`


### $form-label-font-weight

**Type:** string

The font-weight of form field labels ...

The font-weight of form field labels Defaults to: `normal`


### $form-label-line-height

**Type:** number

The line-height of form field labels ...

The line-height of form field labels Defaults to: `round ( $form-label-font-size * 1.15 )`


### $form-toolbar-label-color

**Type:** color

The text color of toolbar field labels ...

The text color of toolbar field labels Defaults to: `$color`


### $form-toolbar-label-font-family

**Type:** string

The font-family of toolbar field labels ...

The font-family of toolbar field labels Defaults to: `$font-family`


### $form-toolbar-label-font-size

**Type:** number

The font-size of toolbar field labels ...

The font-size of toolbar field labels Defaults to: `$font-size`


### $form-toolbar-label-font-weight

**Type:** string

The font-weight of toolbar field labels ...

The font-weight of toolbar field labels Defaults to: `normal`


### $form-toolbar-label-line-height

**Type:** number

The line-height of toolbar field labels ...

The line-height of toolbar field labels Defaults to: `round ( $form-toolbar-label-font-size * 1.15 )`


## CSS Variables

### $form-checkboxgroup-body-padding

**Type:** number/list

The padding of the CheckboxGroup body element ...

The padding of the CheckboxGroup body element Defaults to: `0 4px`


### $form-checkboxgroup-label-border-color

**Type:** number

The border-color of the CheckboxGroup label ...

The border-color of the CheckboxGroup label Defaults to: `$form-checkboxgroup-label-color`


### $form-checkboxgroup-label-border-style

**Type:** number

The border-style of the CheckboxGroup label ...

The border-style of the CheckboxGroup label Defaults to: `solid`


### $form-checkboxgroup-label-border-width

**Type:** number

The border-width of the CheckboxGroup label ...

The border-width of the CheckboxGroup label Defaults to: `0 0 1px 0`


### $form-checkboxgroup-label-color

**Type:** color

The text color of the CheckboxGroup label ...

The text color of the CheckboxGroup label Defaults to: `$form-label-font-color`


### $form-checkboxgroup-label-margin

**Type:** number

The margin of the CheckboxGroup label ...

The margin of the CheckboxGroup label Defaults to: `0 30px 5px 0`


### $form-checkboxgroup-label-padding

**Type:** number

The padding of the CheckboxGroup label ...

The padding of the CheckboxGroup label Defaults to: `2px`


### $form-error-icon-height

**Type:** number

Height for form error icons. ...

Height for form error icons. Defaults to: `16px`


### $form-error-icon-side-margin

**Type:** number/list

Margin for error icons that are aligned to the side of the field ...

Margin for error icons that are aligned to the side of the field Defaults to: `0 1px`


### $form-error-icon-width

**Type:** number

Width for form error icons. ...

Width for form error icons. Defaults to: `16px`


### $form-error-msg-color

**Type:** color

The text color of form error messages ...

The text color of form error messages Defaults to: `$form-field-invalid-border-color`


### $form-error-msg-font-family

**Type:** string

The font-family of form error messages ...

The font-family of form error messages Defaults to: `$font-family`


### $form-error-msg-font-size

**Type:** number

The font-size of form error messages ...

The font-size of form error messages Defaults to: `$font-size`


### $form-error-msg-font-weight

**Type:** string

The font-weight of form error messages ...

The font-weight of form error messages Defaults to: `normal`


### $form-error-msg-line-height

**Type:** number

The line-height of form error messages ...

The line-height of form error messages Defaults to: `$form-error-icon-height`


### $form-error-under-icon-spacing

**Type:** number

The space between the icon and the message for errors that display under the field ...

The space between the icon and the message for errors that display under the field Defaults to: `4px`


### $form-error-under-padding

**Type:** number/list

The padding on errors that display under the form field ...

The padding on errors that display under the form field Defaults to: `2px 2px 2px 0`


### $form-item-margin-bottom

**Type:** measurement

The bottom margin to apply to form items when in auto, anchor, vbox, or table layout ...

The bottom margin to apply to form items when in auto, anchor, vbox, or table layout Defaults to: `5px`


### $form-label-font-color

**Type:** color

The text color of form field labels ...

The text color of form field labels Defaults to: `$color`


### $form-label-font-family

**Type:** string

The font-family of form field labels ...

The font-family of form field labels Defaults to: `$font-family`


### $form-label-font-size

**Type:** number

The font-size of form field labels ...

The font-size of form field labels Defaults to: `$font-size`


### $form-label-font-weight

**Type:** string

The font-weight of form field labels ...

The font-weight of form field labels Defaults to: `normal`


### $form-label-line-height

**Type:** number

The line-height of form field labels ...

The line-height of form field labels Defaults to: `round ( $form-label-font-size * 1.15 )`


### $form-toolbar-label-color

**Type:** color

The text color of toolbar field labels ...

The text color of toolbar field labels Defaults to: `$color`


### $form-toolbar-label-font-family

**Type:** string

The font-family of toolbar field labels ...

The font-family of toolbar field labels Defaults to: `$font-family`


### $form-toolbar-label-font-size

**Type:** number

The font-size of toolbar field labels ...

The font-size of toolbar field labels Defaults to: `$font-size`


### $form-toolbar-label-font-weight

**Type:** string

The font-weight of toolbar field labels ...

The font-weight of toolbar field labels Defaults to: `normal`


### $form-toolbar-label-line-height

**Type:** number

The line-height of toolbar field labels ...

The line-height of toolbar field labels Defaults to: `round ( $form-toolbar-label-font-size * 1.15 )`


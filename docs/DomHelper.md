# Ext.DomHelper

**Extends:** Ext.dom.Helper

**Alternate Names:** Ext.core.DomHelper

## Description

The DomHelper class provides a layer of abstraction from DOM and transparently supports creating elements via DOM or using HTML fragments. It also has the ability to create HTML fragment templates from your DOM building code.

A specification object is used when creating elements. Attributes of this object are assumed to be element attributes, except for 4 special attributes:

**NOTE:** For other arbitrary attributes, the value will currently **not** be automatically HTML-escaped prior to building the element's HTML string. This means that if your attribute value contains special characters that would not normally be allowed in a double-quoted attribute value, you **must** manually HTML-encode it beforehand (see Ext.String.htmlEncode) or risk malformed HTML being created. This behavior may change in a future release.

Commonly used insertion methods:

This is an example, where an unordered list with 3 children items is appended to an existing element with id 'my-div':

var dh = Ext.DomHelper; // create shorthand alias // specification object var spec = { id: 'my-ul', tag: 'ul', cls: 'my-list', // append children after creating children: [ // may also specify 'cn' instead of 'children' {tag: 'li', id: 'item0', html: 'List Item 0'}, {tag: 'li', id: 'item1', html: 'List Item 1'}, {tag: 'li', id: 'item2', html: 'List Item 2'} ] }; var list = dh.append( 'my-div', // the context element 'my-div' can either be the id or the actual node spec // the specification object ); Element creation specification parameters in this class may also be passed as an Array of specification objects. This can be used to insert multiple sibling nodes into an existing container very efficiently. For example, to add more list items to the example above:

dh.append('my-ul', [ {tag: 'li', id: 'item3', html: 'List Item 3'}, {tag: 'li', id: 'item4', html: 'List Item 4'} ]); Templating The real power is in the built-in templating. Instead of creating or appending any elements, createTemplate returns a Template object which can be used over and over to insert new elements. Revisiting the example above, we could utilize templating this time:

// create the node var list = dh.append('my-div', {tag: 'ul', cls: 'my-list'}); // get template var tpl = dh.createTemplate({tag: 'li', id: 'item{0}', html: 'List Item {0}'}); for(var i = 0; i < 5, i++){ tpl.append(list, [i]); // use template to append to the actual node } An example using a template:

var html = '<a id="{0}" href="{1}" class="nav">{2}</a>'; var tpl = new Ext.DomHelper.createTemplate(html); tpl.append('blog-roll', ['link1', 'http://www.edspencer.net/', "Ed's Site"]); tpl.append('blog-roll', ['link2', 'http://www.dustindiaz.com/', "Dustin's Site"]); The same example using named parameters:

var html = '<a id="{id}" href="{url}" class="nav">{text}</a>'; var tpl = new Ext.DomHelper.createTemplate(html); tpl.append('blog-roll', { id: 'link1', url: 'http://www.edspencer.net/', text: "Ed's Site" }); tpl.append('blog-roll', { id: 'link2', url: 'http://www.dustindiaz.com/', text: "Dustin's Site" }); Compiling Templates Templates are applied using regular expressions. The performance is great, but if you are adding a bunch of DOM elements using the same template, you can increase performance even further by "compiling" the template. The way "compile()" works is the template is parsed and broken up at the different variable points and a dynamic function is created and eval'ed. The generated function performs string concatenation of these parts and the passed variables instead of using regular expressions.

var html = '<a id="{id}" href="{url}" class="nav">{text}</a>'; var tpl = new Ext.DomHelper.createTemplate(html); tpl.compile(); //... use template like normal Performance Boost DomHelper will transparently create HTML fragments when it can. Using HTML fragments instead of DOM can significantly boost performance.

Element creation specification parameters may also be strings. If useDom is false, then the string is used as innerHTML. If useDom is true, a string specification results in the creation of a text node. Usage:

## Properties

### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### attributeTransform

**Type:** Object

Since cls & for are reserved words, we need to transform them ...

Since cls & for are reserved words, we need to transform them Defaults to: `{cls: 'class', htmlFor: 'for'}`


### closeTags

**Type:** Object

...

Defaults to: `{}`


### confRe

**Type:** RegExp

...

Defaults to: `/^(?:tag|children|cn|html|tpl|tplData)$/i`


### configMap

**Type:** Object

...

Defaults to: `{}`


### decamelizeName

**Type:** Object


### emptyTags

**Type:** RegExp

...

Defaults to: `/^(?:br|frame|hr|img|input|link|meta|range|spacer|wbr|area|param|col)$/i`


### endRe

**Type:** RegExp

...

Defaults to: `/end/i`


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


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### styleSepRe

**Type:** RegExp

...

Defaults to: `/\s*(?::|;)\s*/`


### useDom

**Type:** Boolean

True to force the use of DOM instead of html fragments. ...

True to force the use of DOM instead of html fragments. Defaults to: `false`


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### append

Creates new DOM element(s) and appends them to el. ...

Creates new DOM element(s) and appends them to el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### applyStyles

Applies a style specification to an element. ...

Applies a style specification to an element.

**Parameters:** el : String/HTMLElementThe element to apply styles to


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


### configClass

...


### createContextualFragment

Fix for IE9 createContextualFragment missing method ...

Fix for IE9 createContextualFragment missing method

**Parameters:** html : Object


### createDom

Creates new DOM element(s) without inserting them to the document. ...

Creates new DOM element(s) without inserting them to the document.

**Parameters:** o : Object/StringThe DOM object spec (and children) or raw HTML blob


### createHtml

Alias for markup. ...

Alias for markup.

**Parameters:** spec : ObjectThe DOM object spec (and children)

**Returns:** the markup for the passed Element(s) config.


### createTemplate

Creates a new Ext.Template from the DOM object spec. ...

Creates a new Ext.Template from the DOM object spec.

**Parameters:** o : ObjectThe DOM object spec (and children)


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### doInsert

...

**Parameters:** el : Object


### generateMarkup

...

**Parameters:** spec : Object


### generateStyles

Converts the styles from the given object to text. ...

Converts the styles from the given object to text. The styles are CSS style names with their associated value. The basic form of this method returns a string: Alternatively, this method can append to an output array. In this case, the style text is pushed on to the array and the array is returned.

**Parameters:** styles : ObjectThe object describing the styles.


### getConfig

...

**Parameters:** name : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### hasConfig

...

**Parameters:** config : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### insertAfter

Creates new DOM element(s) and inserts them after el. ...

Creates new DOM element(s) and inserts them after el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### insertBefore

Creates new DOM element(s) and inserts them before el. ...

Creates new DOM element(s) and inserts them before el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### insertFirst

Creates new DOM element(s) and inserts them as the first child of el. ...

Creates new DOM element(s) and inserts them as the first child of el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### insertHtml

Inserts an HTML fragment into the DOM. ...

Inserts an HTML fragment into the DOM.

**Parameters:** - where : StringWhere to insert the html in relation to el - beforeBegin, afterBegin, beforeEnd, afterEnd. For example take the following HTML: `<div>Contents</div>` Using different `where` values inserts element to the following places: beforeBegin: `<HERE><div>Contents</div>` - afterBegin: `<div><HERE>Contents</div>` - beforeEnd: `<div>Contents<HERE></div>` - afterEnd: `<div>Contents</div><HERE>`


### insertIntoTable

Nasty code for IE's broken table implementation ...

Nasty code for IE's broken table implementation

**Parameters:** tag : Object


### markup

Returns the markup for the passed Element(s) config. ...

**Parameters:** spec : ObjectThe DOM object spec (and children)

**Returns:** the markup for the passed Element(s) config.


### onConfigUpdate

...

**Parameters:** names : Object


### overwrite

Creates new DOM element(s) and overwrites the contents of el with them. ...

Creates new DOM element(s) and overwrites the contents of el with them.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### setConfig

...

**Parameters:** config : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


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

### append

Creates new DOM element(s) and appends them to el. ...

Creates new DOM element(s) and appends them to el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### applyStyles

Applies a style specification to an element. ...

Applies a style specification to an element.

**Parameters:** el : String/HTMLElementThe element to apply styles to


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


### configClass

...


### createContextualFragment

Fix for IE9 createContextualFragment missing method ...

Fix for IE9 createContextualFragment missing method

**Parameters:** html : Object


### createDom

Creates new DOM element(s) without inserting them to the document. ...

Creates new DOM element(s) without inserting them to the document.

**Parameters:** o : Object/StringThe DOM object spec (and children) or raw HTML blob


### createHtml

Alias for markup. ...

Alias for markup.

**Parameters:** spec : ObjectThe DOM object spec (and children)

**Returns:** the markup for the passed Element(s) config.


### createTemplate

Creates a new Ext.Template from the DOM object spec. ...

Creates a new Ext.Template from the DOM object spec.

**Parameters:** o : ObjectThe DOM object spec (and children)


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### doInsert

...

**Parameters:** el : Object


### generateMarkup

...

**Parameters:** spec : Object


### generateStyles

Converts the styles from the given object to text. ...

Converts the styles from the given object to text. The styles are CSS style names with their associated value. The basic form of this method returns a string: Alternatively, this method can append to an output array. In this case, the style text is pushed on to the array and the array is returned.

**Parameters:** styles : ObjectThe object describing the styles.


### getConfig

...

**Parameters:** name : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### hasConfig

...

**Parameters:** config : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### insertAfter

Creates new DOM element(s) and inserts them after el. ...

Creates new DOM element(s) and inserts them after el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### insertBefore

Creates new DOM element(s) and inserts them before el. ...

Creates new DOM element(s) and inserts them before el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### insertFirst

Creates new DOM element(s) and inserts them as the first child of el. ...

Creates new DOM element(s) and inserts them as the first child of el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### insertHtml

Inserts an HTML fragment into the DOM. ...

Inserts an HTML fragment into the DOM.

**Parameters:** - where : StringWhere to insert the html in relation to el - beforeBegin, afterBegin, beforeEnd, afterEnd. For example take the following HTML: `<div>Contents</div>` Using different `where` values inserts element to the following places: beforeBegin: `<HERE><div>Contents</div>` - afterBegin: `<div><HERE>Contents</div>` - beforeEnd: `<div>Contents<HERE></div>` - afterEnd: `<div>Contents</div><HERE>`


### insertIntoTable

Nasty code for IE's broken table implementation ...

Nasty code for IE's broken table implementation

**Parameters:** tag : Object


### markup

Returns the markup for the passed Element(s) config. ...

**Parameters:** spec : ObjectThe DOM object spec (and children)

**Returns:** the markup for the passed Element(s) config.


### onConfigUpdate

...

**Parameters:** names : Object


### overwrite

Creates new DOM element(s) and overwrites the contents of el with them. ...

Creates new DOM element(s) and overwrites the contents of el with them.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### setConfig

...

**Parameters:** config : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


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


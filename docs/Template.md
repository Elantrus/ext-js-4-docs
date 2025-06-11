# Ext.Template

**Extends:** Ext.Base

## Description

Represents an HTML fragment template. Templates may be precompiled for greater performance.

An instance of this class may be created by passing to the constructor either a single argument, or multiple arguments:

The single argument may be either a String or an Array:

String:

var t = new Ext.Template("<div>Hello {0}.</div>"); t.append('some-element', ['foo']); Array:

An Array will be combined with `join('')`.

var t = new Ext.Template([ '<div name="{id}">', '<span class="{cls}">{name:trim} {value:ellipsis(10)}</span>', '</div>', ]); t.compile(); t.append('some-element', {id: 'myid', cls: 'myclass', name: 'foo', value: 'bar'}); Multiple arguments: String, Object, Array, ... Multiple arguments will be combined with `join('')`.

## Config options

### compiled

**Type:** Boolean

True to immediately compile the template. ...

True to immediately compile the template. Defaults to false.


### disableFormats

**Type:** Boolean

True to disable format functions in the template. ...

True to disable format functions in the template. If the template doesn't contain format functions, setting disableFormats to true will reduce apply time. Defaults to false. Defaults to: `false`


### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### compileARe

**Type:** RegExp

...

Defaults to: `/\\/g`


### compileBRe

**Type:** RegExp

...

Defaults to: `/(\r\n|\n)/g`


### compileCRe

**Type:** RegExp

...

Defaults to: `/'/g`


### configMap

**Type:** Object

...

Defaults to: `{}`


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


### isTemplate

**Type:** Boolean

true in this class to identify an object as an instantiated Template, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Template, or subclass thereof. Defaults to: `true`


### re

**Type:** RegExp

...

Defaults to: `/\{([\w\-]+)(?:\:([\w\.]*)(?:\((.*?)?\))?)?\}/g`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.Template

Creates new template. ...

Creates new template.

**Parameters:** html : String...List of strings to be concatenated into template. Alternatively an array of strings can be given, but then no config object may be passed.


### append

Applies the supplied values to the template and appends the new node(s) to the specified el. ...

Applies the supplied `values` to the template and appends the new node(s) to the specified `el`. For example usage see Ext.Template class docs.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### apply

Returns an HTML fragment of this template with the specified values applied. ...

**Parameters:** values : Object/ArrayThe template values. Can be an array if your params are numeric: or an object:

**Returns:** an HTML fragment of this template with the specified values applied.


### applyOut

Appends the result of this template to the provided output array. ...

Appends the result of this template to the provided output array.

**Parameters:** values : Object/ArrayThe template values. See apply.


### applyTemplate

Alias for apply. ...

Alias for apply.

**Parameters:** values : Object/ArrayThe template values. Can be an array if your params are numeric: or an object:

**Returns:** an HTML fragment of this template with the specified values applied.


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


### compile

Compiles the template into an internal function, eliminating the RegEx overhead. ...

Compiles the template into an internal function, eliminating the RegEx overhead.

**Returns:** Ext.Templatethis


### configClass

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### doInsert

...

**Parameters:** where : Object


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

Applies the supplied values to the template and inserts the new node(s) after el. ...

Applies the supplied values to the template and inserts the new node(s) after el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### insertBefore

Applies the supplied values to the template and inserts the new node(s) before el. ...

Applies the supplied values to the template and inserts the new node(s) before el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### insertFirst

Applies the supplied values to the template and inserts the new node(s) as the first child of el. ...

Applies the supplied values to the template and inserts the new node(s) as the first child of el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### onConfigUpdate

...

**Parameters:** names : Object


### overwrite

Applies the supplied values to the template and overwrites the content of el with the new node(s). ...

Applies the supplied values to the template and overwrites the content of el with the new node(s).

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### set

Sets the HTML used as the template and optionally compiles it. ...

Sets the HTML used as the template and optionally compiles it.

**Parameters:** html : String


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


### from

Creates a template from the passed element's value (display:none textarea, preferred) or innerHTML. ...

Creates a template from the passed element's value (*display:none* textarea, preferred) or innerHTML.

**Parameters:** el : String/HTMLElementA DOM element or its id


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


### compileARe

**Type:** RegExp

...

Defaults to: `/\\/g`


### compileBRe

**Type:** RegExp

...

Defaults to: `/(\r\n|\n)/g`


### compileCRe

**Type:** RegExp

...

Defaults to: `/'/g`


### configMap

**Type:** Object

...

Defaults to: `{}`


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


### isTemplate

**Type:** Boolean

true in this class to identify an object as an instantiated Template, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Template, or subclass thereof. Defaults to: `true`


### re

**Type:** RegExp

...

Defaults to: `/\{([\w\-]+)(?:\:([\w\.]*)(?:\((.*?)?\))?)?\}/g`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.Template

Creates new template. ...

Creates new template.

**Parameters:** html : String...List of strings to be concatenated into template. Alternatively an array of strings can be given, but then no config object may be passed.


### append

Applies the supplied values to the template and appends the new node(s) to the specified el. ...

Applies the supplied `values` to the template and appends the new node(s) to the specified `el`. For example usage see Ext.Template class docs.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### apply

Returns an HTML fragment of this template with the specified values applied. ...

**Parameters:** values : Object/ArrayThe template values. Can be an array if your params are numeric: or an object:

**Returns:** an HTML fragment of this template with the specified values applied.


### applyOut

Appends the result of this template to the provided output array. ...

Appends the result of this template to the provided output array.

**Parameters:** values : Object/ArrayThe template values. See apply.


### applyTemplate

Alias for apply. ...

Alias for apply.

**Parameters:** values : Object/ArrayThe template values. Can be an array if your params are numeric: or an object:

**Returns:** an HTML fragment of this template with the specified values applied.


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


### compile

Compiles the template into an internal function, eliminating the RegEx overhead. ...

Compiles the template into an internal function, eliminating the RegEx overhead.

**Returns:** Ext.Templatethis


### configClass

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### doInsert

...

**Parameters:** where : Object


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

Applies the supplied values to the template and inserts the new node(s) after el. ...

Applies the supplied values to the template and inserts the new node(s) after el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### insertBefore

Applies the supplied values to the template and inserts the new node(s) before el. ...

Applies the supplied values to the template and inserts the new node(s) before el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### insertFirst

Applies the supplied values to the template and inserts the new node(s) as the first child of el. ...

Applies the supplied values to the template and inserts the new node(s) as the first child of el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### onConfigUpdate

...

**Parameters:** names : Object


### overwrite

Applies the supplied values to the template and overwrites the content of el with the new node(s). ...

Applies the supplied values to the template and overwrites the content of el with the new node(s).

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### set

Sets the HTML used as the template and optionally compiles it. ...

Sets the HTML used as the template and optionally compiles it.

**Parameters:** html : String


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


### from

Creates a template from the passed element's value (display:none textarea, preferred) or innerHTML. ...

Creates a template from the passed element's value (*display:none* textarea, preferred) or innerHTML.

**Parameters:** el : String/HTMLElementA DOM element or its id


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

### Ext.Template

Creates new template. ...

Creates new template.

**Parameters:** html : String...List of strings to be concatenated into template. Alternatively an array of strings can be given, but then no config object may be passed.


### append

Applies the supplied values to the template and appends the new node(s) to the specified el. ...

Applies the supplied `values` to the template and appends the new node(s) to the specified `el`. For example usage see Ext.Template class docs.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### apply

Returns an HTML fragment of this template with the specified values applied. ...

**Parameters:** values : Object/ArrayThe template values. Can be an array if your params are numeric: or an object:

**Returns:** an HTML fragment of this template with the specified values applied.


### applyOut

Appends the result of this template to the provided output array. ...

Appends the result of this template to the provided output array.

**Parameters:** values : Object/ArrayThe template values. See apply.


### applyTemplate

Alias for apply. ...

Alias for apply.

**Parameters:** values : Object/ArrayThe template values. Can be an array if your params are numeric: or an object:

**Returns:** an HTML fragment of this template with the specified values applied.


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


### compile

Compiles the template into an internal function, eliminating the RegEx overhead. ...

Compiles the template into an internal function, eliminating the RegEx overhead.

**Returns:** Ext.Templatethis


### configClass

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### doInsert

...

**Parameters:** where : Object


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

Applies the supplied values to the template and inserts the new node(s) after el. ...

Applies the supplied values to the template and inserts the new node(s) after el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### insertBefore

Applies the supplied values to the template and inserts the new node(s) before el. ...

Applies the supplied values to the template and inserts the new node(s) before el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### insertFirst

Applies the supplied values to the template and inserts the new node(s) as the first child of el. ...

Applies the supplied values to the template and inserts the new node(s) as the first child of el.

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### onConfigUpdate

...

**Parameters:** names : Object


### overwrite

Applies the supplied values to the template and overwrites the content of el with the new node(s). ...

Applies the supplied values to the template and overwrites the content of el with the new node(s).

**Parameters:** el : String/HTMLElement/Ext.ElementThe context element


### set

Sets the HTML used as the template and optionally compiles it. ...

Sets the HTML used as the template and optionally compiles it.

**Parameters:** html : String


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


### from

Creates a template from the passed element's value (display:none textarea, preferred) or innerHTML. ...

Creates a template from the passed element's value (*display:none* textarea, preferred) or innerHTML.

**Parameters:** el : String/HTMLElementA DOM element or its id


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


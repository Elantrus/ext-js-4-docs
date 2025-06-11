# Ext.ClassManager

## Description

Ext.ClassManager manages all classes and handles mapping from string class name to actual class objects throughout the whole framework. It is not generally accessed directly, rather through these convenient shorthands:

Ext.define(className, properties); in which `properties` is an object represent a collection of properties that apply to the class. See create for more detailed instructions.

Ext.define('Person', { name: 'Unknown', constructor: function(name) { if (name) { this.name = name; } }, eat: function(foodType) { alert("I'm eating: " + foodType); return this; } }); var aaron = new Person("Aaron"); aaron.eat("Sandwich"); // alert("I'm eating: Sandwich"); Ext.Class has a powerful set of extensible pre-processors which takes care of everything related to class creation, including but not limited to inheritance, mixins, configuration, statics, etc.

Ext.define('Developer', { extend: 'Person', constructor: function(name, isGeek) { this.isGeek = isGeek; // Apply a method from the parent class' prototype this.callParent([name]); }, code: function(language) { alert("I'm coding in: " + language); this.eat("Bugs"); return this; } }); var jacky = new Developer("Jacky", true); jacky.code("JavaScript"); // alert("I'm coding in: JavaScript"); // alert("I'm eating: Bugs"); See Ext.Base.callParent for more details on calling superclass' methods

Ext.define('CanPlayGuitar', { playGuitar: function() { alert("F#...G...D...A"); } }); Ext.define('CanComposeSongs', { composeSongs: function() { ... } }); Ext.define('CanSing', { sing: function() { alert("I'm on the highway to hell...") } }); Ext.define('Musician', { extend: 'Person', mixins: { canPlayGuitar: 'CanPlayGuitar', canComposeSongs: 'CanComposeSongs', canSing: 'CanSing' } }) Ext.define('CoolPerson', { extend: 'Person', mixins: { canPlayGuitar: 'CanPlayGuitar', canSing: 'CanSing' }, sing: function() { alert("Ahem...."); this.mixins.canSing.sing.call(this); alert("[Playing guitar at the same time...]"); this.playGuitar(); } }); var me = new CoolPerson("Jacky"); me.sing(); // alert("Ahem..."); // alert("I'm on the highway to hell..."); // alert("[Playing guitar at the same time...]"); // alert("F#...G...D...A"); Config: Statics: Also see Ext.Base.statics and Ext.Base.self for more details on accessing static properties within class methods

## Properties

### classes

**Type:** Object

All classes which were defined through the ClassManager. ...

All classes which were defined through the ClassManager. Keys are the name of the classes and the values are references to the classes. Defaults to: `{}`


### createdListeners

**Type:** Array

...

Defaults to: `[]`


### defaultPostprocessors

**Type:** Array

...

Defaults to: `[]`


### enableNamespaceParseCache

**Type:** Boolean

...

Defaults to: `true`


### existCache

**Type:** Object

...

Defaults to: `{}`


### instantiators

**Type:** Array

...

Defaults to: `[]`


### maps

**Type:** Object

...

Defaults to: `{alternateToName: {}, aliasToName: {}, nameToAliases: {}, nameToAlternates: {}}`


### nameCreatedListeners

**Type:** Object

...

Defaults to: `{}`


### namespaceParseCache

**Type:** Object

...

Defaults to: `{}`


### namespaceRewrites

**Type:** Object


### postprocessors

**Type:** Object

...

Defaults to: `{}`


### addNameAliasMappings

Adds a batch of class name to alias mappings ...

Adds a batch of class name to alias mappings

**Parameters:** aliases : ObjectThe set of mappings of the form className : [values...]


### addNameAlternateMappings

...

**Parameters:** alternates : ObjectThe set of mappings of the form className : [values...]


### create

Defines a class. ...

Defines a class. This method has been **deprecated** since 4.1.0 Use Ext.define instead, as that also supports creating overrides.


### createNamespaces

The new Ext.ns, supports namespace rewriting ...

The new Ext.ns, supports namespace rewriting


### dynInstantiate

...

**Parameters:** name : Object


### get

Retrieve a class by its name. ...

Retrieve a class by its name.

**Parameters:** name : String


### getAliasesByName

Get the aliases of a class by the class name ...

Get the aliases of a class by the class name

**Parameters:** name : String


### getByAlias

Get a reference to the class by its alias. ...

Get a reference to the class by its alias.

**Parameters:** alias : String


### getClass

Get the class of the provided object; returns null if it's not an instance of any class created with Ext.define. ...

Get the class of the provided object; returns null if it's not an instance of any class created with Ext.define. getClass is usually invoked by the shorthand Ext.getClass.

**Parameters:** object : Object


### getDisplayName

Returns the displayName property or className or object. ...

**Parameters:** object : Object

**Returns:** the displayName property or className or object. When all else fails, returns "Anonymous".


### getInstantiator

...

**Parameters:** length : Object


### getName

Get the name of the class by its reference or its instance; getName is usually invoked by the shorthand Ext.getClass...

Get the name of the class by its reference or its instance; getName is usually invoked by the shorthand Ext.getClassName.

**Parameters:** object : Ext.Class/Object


### getNameByAlias

Get the name of a class by its alias. ...

Get the name of a class by its alias.

**Parameters:** alias : String


### getNameByAlternate

Get the name of a class by its alternate name. ...

Get the name of a class by its alternate name.

**Parameters:** alternate : String


### getNamesByExpression

Converts a string expression to an array of matching class names. ...

Converts a string expression to an array of matching class names. An expression can either refers to class aliases or class names. Expressions support wildcards:

**Parameters:** expression : String


### instantiate

...


### instantiateByAlias

Instantiate a class by its alias. ...

Instantiate a class by its alias. instantiateByAlias is usually invoked by the shorthand Ext.createByAlias. If Ext.Loader is enabled and the class has not been defined yet, it will attempt to load the class via synchronous loading.

**Parameters:** alias : String


### isCreated

Checks if a class has already been created. ...

Checks if a class has already been created.

**Parameters:** className : String


### onCreated

...

**Parameters:** fn : Object


### parseNamespace

Supports namespace rewriting ...

Supports namespace rewriting

**Parameters:** namespace : Object


### registerPostprocessor

Register a post-processor function. ...

Register a post-processor function.

**Parameters:** name : String


### set

Sets a name reference to a class. ...

Sets a name reference to a class.

**Parameters:** name : String


### setAlias

Register the alias for a class. ...

Register the alias for a class.

**Parameters:** cls : Ext.Class/Stringa reference to a class or a className


### setDefaultPostprocessorPosition

Insert this post-processor at a specific position in the stack, optionally relative to any existing post-processor ...

Insert this post-processor at a specific position in the stack, optionally relative to any existing post-processor

**Parameters:** name : StringThe post-processor name. Note that it needs to be registered with registerPostprocessor before this


### setDefaultPostprocessors

Set the default post processors array stack which are applied to every class. ...

Set the default post processors array stack which are applied to every class.

**Parameters:** postprocessors : String/ArrayThe name of a registered post processor or an array of registered names.


### setNamespace

Creates a namespace and assign the value to the created object Ext.ClassManager.setNamespace('MyCompany.pkg.Example'...

Creates a namespace and assign the `value` to the created object

**Parameters:** name : String


### triggerCreated

...

**Parameters:** className : Object


### undefine

Undefines a class defined using the #define method. ...

Undefines a class defined using the #define method. Typically used for unit testing where setting up and tearing down a class multiple times is required. For example: @param {String} className The class name to undefine in string dot-namespaced format.

**Parameters:** className : Object


## Methods

### addNameAliasMappings

Adds a batch of class name to alias mappings ...

Adds a batch of class name to alias mappings

**Parameters:** aliases : ObjectThe set of mappings of the form className : [values...]


### addNameAlternateMappings

...

**Parameters:** alternates : ObjectThe set of mappings of the form className : [values...]


### create

Defines a class. ...

Defines a class. This method has been **deprecated** since 4.1.0 Use Ext.define instead, as that also supports creating overrides.


### createNamespaces

The new Ext.ns, supports namespace rewriting ...

The new Ext.ns, supports namespace rewriting


### dynInstantiate

...

**Parameters:** name : Object


### get

Retrieve a class by its name. ...

Retrieve a class by its name.

**Parameters:** name : String


### getAliasesByName

Get the aliases of a class by the class name ...

Get the aliases of a class by the class name

**Parameters:** name : String


### getByAlias

Get a reference to the class by its alias. ...

Get a reference to the class by its alias.

**Parameters:** alias : String


### getClass

Get the class of the provided object; returns null if it's not an instance of any class created with Ext.define. ...

Get the class of the provided object; returns null if it's not an instance of any class created with Ext.define. getClass is usually invoked by the shorthand Ext.getClass.

**Parameters:** object : Object


### getDisplayName

Returns the displayName property or className or object. ...

**Parameters:** object : Object

**Returns:** the displayName property or className or object. When all else fails, returns "Anonymous".


### getInstantiator

...

**Parameters:** length : Object


### getName

Get the name of the class by its reference or its instance; getName is usually invoked by the shorthand Ext.getClass...

Get the name of the class by its reference or its instance; getName is usually invoked by the shorthand Ext.getClassName.

**Parameters:** object : Ext.Class/Object


### getNameByAlias

Get the name of a class by its alias. ...

Get the name of a class by its alias.

**Parameters:** alias : String


### getNameByAlternate

Get the name of a class by its alternate name. ...

Get the name of a class by its alternate name.

**Parameters:** alternate : String


### getNamesByExpression

Converts a string expression to an array of matching class names. ...

Converts a string expression to an array of matching class names. An expression can either refers to class aliases or class names. Expressions support wildcards:

**Parameters:** expression : String


### instantiate

...


### instantiateByAlias

Instantiate a class by its alias. ...

Instantiate a class by its alias. instantiateByAlias is usually invoked by the shorthand Ext.createByAlias. If Ext.Loader is enabled and the class has not been defined yet, it will attempt to load the class via synchronous loading.

**Parameters:** alias : String


### isCreated

Checks if a class has already been created. ...

Checks if a class has already been created.

**Parameters:** className : String


### onCreated

...

**Parameters:** fn : Object


### parseNamespace

Supports namespace rewriting ...

Supports namespace rewriting

**Parameters:** namespace : Object


### registerPostprocessor

Register a post-processor function. ...

Register a post-processor function.

**Parameters:** name : String


### set

Sets a name reference to a class. ...

Sets a name reference to a class.

**Parameters:** name : String


### setAlias

Register the alias for a class. ...

Register the alias for a class.

**Parameters:** cls : Ext.Class/Stringa reference to a class or a className


### setDefaultPostprocessorPosition

Insert this post-processor at a specific position in the stack, optionally relative to any existing post-processor ...

Insert this post-processor at a specific position in the stack, optionally relative to any existing post-processor

**Parameters:** name : StringThe post-processor name. Note that it needs to be registered with registerPostprocessor before this


### setDefaultPostprocessors

Set the default post processors array stack which are applied to every class. ...

Set the default post processors array stack which are applied to every class.

**Parameters:** postprocessors : String/ArrayThe name of a registered post processor or an array of registered names.


### setNamespace

Creates a namespace and assign the value to the created object Ext.ClassManager.setNamespace('MyCompany.pkg.Example'...

Creates a namespace and assign the `value` to the created object

**Parameters:** name : String


### triggerCreated

...

**Parameters:** className : Object


### undefine

Undefines a class defined using the #define method. ...

Undefines a class defined using the #define method. Typically used for unit testing where setting up and tearing down a class multiple times is required. For example: @param {String} className The class name to undefine in string dot-namespaced format.

**Parameters:** className : Object


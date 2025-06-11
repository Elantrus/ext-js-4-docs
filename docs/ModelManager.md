# Ext.ModelManager

**Extends:** Ext.AbstractManager

**Alternate Names:** Ext.ModelMgr

## Description

The ModelManager keeps track of all Ext.data.Model types defined in your application.

**Creating Model Instances**

Model instances can be created by using the Ext.create method. Ext.create replaces the deprecated Ext.ModelManager.create method. It is also possible to create a model instance this by using the Model type directly. The following 3 snippets are equivalent:

Ext.define('User', { extend: 'Ext.data.Model', fields: ['first', 'last'] }); // method 1, create using Ext.create (recommended) Ext.create('User', { first: 'Ed', last: 'Spencer' }); // method 2, create through the manager (deprecated) Ext.ModelManager.create({ first: 'Ed', last: 'Spencer' }, 'User'); // method 3, create on the type directly new User({ first: 'Ed', last: 'Spencer' }); **Accessing Model Types**

A reference to a Model type can be obtained by using the getModel function. Since models types are normal classes, you can access the type directly. The following snippets are equivalent:

## Properties

### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### all

**Type:** Ext.util.HashMap

Contains all of the items currently managed


### associationStack

**Type:** Ext.data.association.Association[]

Private stack of associations that must be created once their associated model has been defined ...

Private stack of associations that must be created once their associated model has been defined Defaults to: `[]`


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


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### typeName

**Type:** String

...

Defaults to: `'mtype'` Overrides: Ext.AbstractManager.typeName


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.ModelManager

...

**Parameters:** config : Object


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


### create

Creates a new instance of a Model using the given data. ...

Creates a new instance of a Model using the given data. Deprecated, instead use Ext.create: This method has been **deprecated** since 4.1 Use Ext.create instead.


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### each

Executes the specified function once for each item in the collection. ...

Executes the specified function once for each item in the collection.

**Parameters:** fn : FunctionThe function to execute. Parameterskey : StringThe key of the item


### get

Returns an item by id. ...

**Parameters:** id : StringThe id of the item

**Returns:** an item by id. For additional details see Ext.util.HashMap.get.


### getConfig

...

**Parameters:** name : Object


### getCount

Gets the number of items in the collection. ...

Gets the number of items in the collection.

**Returns:** NumberThe number of items in the collection.


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getModel

Returns the Ext.data.Model class for a given model name ...

**Parameters:** id : String/ObjectThe classname of the model or the model class itself.

**Returns:** the Ext.data.Model class for a given model name


### hasConfig

...

**Parameters:** config : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### isRegistered

Checks if an item type is registered. ...

Checks if an item type is registered.

**Parameters:** type : StringThe mnemonic string by which the class may be looked up


### onAvailable

Registers a function that will be called when an item with the specified id is added to the manager. ...

Registers a function that will be called when an item with the specified id is added to the manager. This will happen on instantiation.

**Parameters:** id : StringThe item id


### onConfigUpdate

...

**Parameters:** names : Object


### onModelDefined

Private callback called whenever a model has just been defined. ...

Private callback called whenever a model has just been defined. This sets up any associations that were waiting for the given model to be defined

**Parameters:** model : FunctionThe model that was just created


### register

Registers an item to be managed ...

Registers an item to be managed

**Parameters:** item : ObjectThe item to register


### registerDeferredAssociation

Registers an association where one of the models defined doesn't exist yet. ...

Registers an association where one of the models defined doesn't exist yet. The ModelManager will check when new models are registered if it can link them together

**Parameters:** association : Ext.data.association.AssociationThe association


### registerType

Registers a model definition. ...

Registers a model definition. All model plugins marked with isDefault: true are bootstrapped immediately, as are any addition plugins defined in the model config.

**Parameters:** name : Object


### setConfig

...

**Parameters:** config : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### unregister

Unregisters an item by removing it from this manager ...

Unregisters an item by removing it from this manager

**Parameters:** item : ObjectThe item to unregister


### unregisterType

Unregisters a model definition. ...

Unregisters a model definition. Generally used by stores with implicit model classes.

**Parameters:** name : Object


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

### Ext.ModelManager

...

**Parameters:** config : Object


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


### create

Creates a new instance of a Model using the given data. ...

Creates a new instance of a Model using the given data. Deprecated, instead use Ext.create: This method has been **deprecated** since 4.1 Use Ext.create instead.


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### each

Executes the specified function once for each item in the collection. ...

Executes the specified function once for each item in the collection.

**Parameters:** fn : FunctionThe function to execute. Parameterskey : StringThe key of the item


### get

Returns an item by id. ...

**Parameters:** id : StringThe id of the item

**Returns:** an item by id. For additional details see Ext.util.HashMap.get.


### getConfig

...

**Parameters:** name : Object


### getCount

Gets the number of items in the collection. ...

Gets the number of items in the collection.

**Returns:** NumberThe number of items in the collection.


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getModel

Returns the Ext.data.Model class for a given model name ...

**Parameters:** id : String/ObjectThe classname of the model or the model class itself.

**Returns:** the Ext.data.Model class for a given model name


### hasConfig

...

**Parameters:** config : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### isRegistered

Checks if an item type is registered. ...

Checks if an item type is registered.

**Parameters:** type : StringThe mnemonic string by which the class may be looked up


### onAvailable

Registers a function that will be called when an item with the specified id is added to the manager. ...

Registers a function that will be called when an item with the specified id is added to the manager. This will happen on instantiation.

**Parameters:** id : StringThe item id


### onConfigUpdate

...

**Parameters:** names : Object


### onModelDefined

Private callback called whenever a model has just been defined. ...

Private callback called whenever a model has just been defined. This sets up any associations that were waiting for the given model to be defined

**Parameters:** model : FunctionThe model that was just created


### register

Registers an item to be managed ...

Registers an item to be managed

**Parameters:** item : ObjectThe item to register


### registerDeferredAssociation

Registers an association where one of the models defined doesn't exist yet. ...

Registers an association where one of the models defined doesn't exist yet. The ModelManager will check when new models are registered if it can link them together

**Parameters:** association : Ext.data.association.AssociationThe association


### registerType

Registers a model definition. ...

Registers a model definition. All model plugins marked with isDefault: true are bootstrapped immediately, as are any addition plugins defined in the model config.

**Parameters:** name : Object


### setConfig

...

**Parameters:** config : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### unregister

Unregisters an item by removing it from this manager ...

Unregisters an item by removing it from this manager

**Parameters:** item : ObjectThe item to unregister


### unregisterType

Unregisters a model definition. ...

Unregisters a model definition. Generally used by stores with implicit model classes.

**Parameters:** name : Object


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


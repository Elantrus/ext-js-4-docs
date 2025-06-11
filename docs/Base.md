# Ext.Base

## Description

The root of all classes created with Ext.define.

Ext.Base is the building block of all Ext classes. All classes in Ext inherit from Ext.Base. All prototype and static members of this class are inherited by all other classes.

## Properties

### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


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


### $onExtended

**Type:** Array

...

Defaults to: `[]`


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


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


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


### onConfigUpdate

...

**Parameters:** names : Object


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


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


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


### onConfigUpdate

...

**Parameters:** names : Object


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


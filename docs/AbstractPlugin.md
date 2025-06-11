# Ext.AbstractPlugin

**Extends:** Ext.Base

## Description

The AbstractPlugin class is the base class from which user-implemented plugins should inherit.

This class defines the essential API of plugins as used by Components by defining the following methods:

`init` : The plugin initialization method which the owning Component calls at Component initialization time.

The Component passes itself as the sole parameter.

Subclasses should set up bidirectional links between the plugin and its client Component here.

`destroy` : The plugin cleanup method which the owning Component calls at Component destruction time.

Use this method to break links between the plugin and the Component and to free any allocated resources.

`enable` : The base implementation just sets the plugin's `disabled` flag to `false`

`disable` : The base implementation just sets the plugin's `disabled` flag to `true`

## Config options

### pluginId

**Type:** String

A name for the plugin that can be set at creation time to then retrieve the plugin through getPlugin method. ...

A name for the plugin that can be set at creation time to then retrieve the plugin through getPlugin method. For example:


### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### configMap

**Type:** Object

...

Defaults to: `{}`


### disabled

**Type:** Boolean

...

Defaults to: `false`


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


### isPlugin

**Type:** Boolean

true in this class to identify an object as an instantiated Plugin, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Plugin, or subclass thereof. Defaults to: `true`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.AbstractPlugin

Instantiates the plugin. ...

Instantiates the plugin.

**Parameters:** config : Object (optional)Configuration object.


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


### clonePlugin

Creates clone of the plugin. ...

Creates clone of the plugin.

**Parameters:** overrideCfg : Object (optional)Additional config for the derived plugin.


### configClass

...


### destroy

The destroy method is invoked by the owning Component at the time the Component is being destroyed. ...

The destroy method is invoked by the owning Component at the time the Component is being destroyed. The supplied implementation is empty. Subclasses should perform plugin cleanup in their own implementation of this method. Overrides: Ext.Base.destroy


### disable

The base implementation just sets the plugin's disabled flag to true Plugin subclasses which need more complex proce...

The base implementation just sets the plugin's `disabled` flag to `true` Plugin subclasses which need more complex processing may implement an overriding implementation.


### enable

The base implementation just sets the plugin's disabled flag to false Plugin subclasses which need more complex proc...

The base implementation just sets the plugin's `disabled` flag to `false` Plugin subclasses which need more complex processing may implement an overriding implementation.


### getCmp

Returns the component to which this plugin is attached. ...

**Returns:** the component to which this plugin is attached. ReturnsExt.ComponentOwner component.


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


### init

The init method is invoked after initComponent method has been run for the client Component. ...

The init method is invoked after initComponent method has been run for the client Component. The supplied implementation is empty. Subclasses should perform plugin initialization, and set up bidirectional links between the plugin and its client Component in their own implementation of this method.

**Parameters:** client : Ext.ComponentThe client Component which owns this plugin.


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### onClassExtended

Private. ...

Private. Inject a ptype property so that AbstractComponent.findPlugin(ptype) works.

**Parameters:** cls : Object


### onConfigUpdate

...

**Parameters:** names : Object


### setCmp

Sets the component to which this plugin is attached. ...

Sets the component to which this plugin is attached.

**Parameters:** cmp : Ext.ComponentOwner component.


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


## Properties

### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### configMap

**Type:** Object

...

Defaults to: `{}`


### disabled

**Type:** Boolean

...

Defaults to: `false`


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


### isPlugin

**Type:** Boolean

true in this class to identify an object as an instantiated Plugin, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Plugin, or subclass thereof. Defaults to: `true`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.AbstractPlugin

Instantiates the plugin. ...

Instantiates the plugin.

**Parameters:** config : Object (optional)Configuration object.


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


### clonePlugin

Creates clone of the plugin. ...

Creates clone of the plugin.

**Parameters:** overrideCfg : Object (optional)Additional config for the derived plugin.


### configClass

...


### destroy

The destroy method is invoked by the owning Component at the time the Component is being destroyed. ...

The destroy method is invoked by the owning Component at the time the Component is being destroyed. The supplied implementation is empty. Subclasses should perform plugin cleanup in their own implementation of this method. Overrides: Ext.Base.destroy


### disable

The base implementation just sets the plugin's disabled flag to true Plugin subclasses which need more complex proce...

The base implementation just sets the plugin's `disabled` flag to `true` Plugin subclasses which need more complex processing may implement an overriding implementation.


### enable

The base implementation just sets the plugin's disabled flag to false Plugin subclasses which need more complex proc...

The base implementation just sets the plugin's `disabled` flag to `false` Plugin subclasses which need more complex processing may implement an overriding implementation.


### getCmp

Returns the component to which this plugin is attached. ...

**Returns:** the component to which this plugin is attached. ReturnsExt.ComponentOwner component.


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


### init

The init method is invoked after initComponent method has been run for the client Component. ...

The init method is invoked after initComponent method has been run for the client Component. The supplied implementation is empty. Subclasses should perform plugin initialization, and set up bidirectional links between the plugin and its client Component in their own implementation of this method.

**Parameters:** client : Ext.ComponentThe client Component which owns this plugin.


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### onClassExtended

Private. ...

Private. Inject a ptype property so that AbstractComponent.findPlugin(ptype) works.

**Parameters:** cls : Object


### onConfigUpdate

...

**Parameters:** names : Object


### setCmp

Sets the component to which this plugin is attached. ...

Sets the component to which this plugin is attached.

**Parameters:** cmp : Ext.ComponentOwner component.


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

### Ext.AbstractPlugin

Instantiates the plugin. ...

Instantiates the plugin.

**Parameters:** config : Object (optional)Configuration object.


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


### clonePlugin

Creates clone of the plugin. ...

Creates clone of the plugin.

**Parameters:** overrideCfg : Object (optional)Additional config for the derived plugin.


### configClass

...


### destroy

The destroy method is invoked by the owning Component at the time the Component is being destroyed. ...

The destroy method is invoked by the owning Component at the time the Component is being destroyed. The supplied implementation is empty. Subclasses should perform plugin cleanup in their own implementation of this method. Overrides: Ext.Base.destroy


### disable

The base implementation just sets the plugin's disabled flag to true Plugin subclasses which need more complex proce...

The base implementation just sets the plugin's `disabled` flag to `true` Plugin subclasses which need more complex processing may implement an overriding implementation.


### enable

The base implementation just sets the plugin's disabled flag to false Plugin subclasses which need more complex proc...

The base implementation just sets the plugin's `disabled` flag to `false` Plugin subclasses which need more complex processing may implement an overriding implementation.


### getCmp

Returns the component to which this plugin is attached. ...

**Returns:** the component to which this plugin is attached. ReturnsExt.ComponentOwner component.


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


### init

The init method is invoked after initComponent method has been run for the client Component. ...

The init method is invoked after initComponent method has been run for the client Component. The supplied implementation is empty. Subclasses should perform plugin initialization, and set up bidirectional links between the plugin and its client Component in their own implementation of this method.

**Parameters:** client : Ext.ComponentThe client Component which owns this plugin.


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### onClassExtended

Private. ...

Private. Inject a ptype property so that AbstractComponent.findPlugin(ptype) works.

**Parameters:** cls : Object


### onConfigUpdate

...

**Parameters:** names : Object


### setCmp

Sets the component to which this plugin is attached. ...

Sets the component to which this plugin is attached.

**Parameters:** cmp : Ext.ComponentOwner component.


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


# Ext.Shadow

**Extends:** Ext.Base

## Description

Simple class that can provide a shadow effect for any element. Note that the element MUST be absolutely positioned, and the shadow does not provide any shimming. This should be used only in simple cases - for more advanced functionality that can also provide the same shadow effect, see the Ext.Layer class.

## Config options

### mode

**Type:** String

The shadow display mode. ...

The shadow display mode. Supports the following options: - sides : Shadow displays on both sides and bottom only - frame : Shadow displays equally on all four sides - drop : Traditional bottom-right drop shadow


### offset

**Type:** Number

The number of pixels to offset the shadow from the element ...

The number of pixels to offset the shadow from the element Defaults to: `4`


### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### boxShadowProperty

**Type:** Object

private - CSS property to use to set the box shadow


### configMap

**Type:** Object

...

Defaults to: `{}`


### defaultMode

**Type:** String

private ...

private Defaults to: `"drop"`


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


### localXYNames

**Type:** Object

...

Defaults to: `{get: 'getLocalXY', set: 'setLocalXY'}`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.Shadow

Creates new Shadow. ...

Creates new Shadow.

**Parameters:** config : Object (optional)Config object.


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


### getShadowSize

Returns the shadow size on each side of the element in standard CSS order: top, right, bottom, left; ...

**Returns:** the shadow size on each side of the element in standard CSS order: top, right, bottom, left; ReturnsNumber[]Top, right, bottom and left shadow size.


### hasConfig

...

**Parameters:** config : Object


### hide

Hides this shadow ...

Hides this shadow


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### isVisible

Returns true if the shadow is visible, else false ...

**Returns:** true if the shadow is visible, else false


### onConfigUpdate

...

**Parameters:** names : Object


### realign

Direct alignment when values are already available. ...

Direct alignment when values are already available. Show must be called at least once before calling this method to ensure it is initialized.

**Parameters:** left : NumberThe target element left position


### setConfig

...

**Parameters:** config : Object


### setOpacity

Sets the opacity of the shadow ...

Sets the opacity of the shadow

**Parameters:** opacity : NumberThe opacity


### setZIndex

Adjust the z-index of this shadow ...

Adjust the z-index of this shadow

**Parameters:** zindex : NumberThe new z-index


### show

Displays the shadow under the target element ...

Displays the shadow under the target element

**Parameters:** targetEl : String/HTMLElement/Ext.ElementThe id or element under which the shadow should display


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


### boxShadowProperty

**Type:** Object

private - CSS property to use to set the box shadow


### configMap

**Type:** Object

...

Defaults to: `{}`


### defaultMode

**Type:** String

private ...

private Defaults to: `"drop"`


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


### localXYNames

**Type:** Object

...

Defaults to: `{get: 'getLocalXY', set: 'setLocalXY'}`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.Shadow

Creates new Shadow. ...

Creates new Shadow.

**Parameters:** config : Object (optional)Config object.


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


### getShadowSize

Returns the shadow size on each side of the element in standard CSS order: top, right, bottom, left; ...

**Returns:** the shadow size on each side of the element in standard CSS order: top, right, bottom, left; ReturnsNumber[]Top, right, bottom and left shadow size.


### hasConfig

...

**Parameters:** config : Object


### hide

Hides this shadow ...

Hides this shadow


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### isVisible

Returns true if the shadow is visible, else false ...

**Returns:** true if the shadow is visible, else false


### onConfigUpdate

...

**Parameters:** names : Object


### realign

Direct alignment when values are already available. ...

Direct alignment when values are already available. Show must be called at least once before calling this method to ensure it is initialized.

**Parameters:** left : NumberThe target element left position


### setConfig

...

**Parameters:** config : Object


### setOpacity

Sets the opacity of the shadow ...

Sets the opacity of the shadow

**Parameters:** opacity : NumberThe opacity


### setZIndex

Adjust the z-index of this shadow ...

Adjust the z-index of this shadow

**Parameters:** zindex : NumberThe new z-index


### show

Displays the shadow under the target element ...

Displays the shadow under the target element

**Parameters:** targetEl : String/HTMLElement/Ext.ElementThe id or element under which the shadow should display


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

### Ext.Shadow

Creates new Shadow. ...

Creates new Shadow.

**Parameters:** config : Object (optional)Config object.


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


### getShadowSize

Returns the shadow size on each side of the element in standard CSS order: top, right, bottom, left; ...

**Returns:** the shadow size on each side of the element in standard CSS order: top, right, bottom, left; ReturnsNumber[]Top, right, bottom and left shadow size.


### hasConfig

...

**Parameters:** config : Object


### hide

Hides this shadow ...

Hides this shadow


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### isVisible

Returns true if the shadow is visible, else false ...

**Returns:** true if the shadow is visible, else false


### onConfigUpdate

...

**Parameters:** names : Object


### realign

Direct alignment when values are already available. ...

Direct alignment when values are already available. Show must be called at least once before calling this method to ensure it is initialized.

**Parameters:** left : NumberThe target element left position


### setConfig

...

**Parameters:** config : Object


### setOpacity

Sets the opacity of the shadow ...

Sets the opacity of the shadow

**Parameters:** opacity : NumberThe opacity


### setZIndex

Adjust the z-index of this shadow ...

Adjust the z-index of this shadow

**Parameters:** zindex : NumberThe new z-index


### show

Displays the shadow under the target element ...

Displays the shadow under the target element

**Parameters:** targetEl : String/HTMLElement/Ext.ElementThe id or element under which the shadow should display


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


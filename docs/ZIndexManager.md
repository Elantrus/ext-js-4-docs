# Ext.ZIndexManager

**Extends:** Ext.Base

**Alternate Names:** Ext.WindowGroup

## Description

A class that manages a group of Ext.Component.floating Components and provides z-order management, and Component activation behavior, including masking below the active (topmost) Component.

Floating Components which are rendered directly into the document (such as Windows) which are shown are managed by a global instance.

Floating Components which are descendants of floating *Containers* (for example a BoundList within an Window, or a Menu), are managed by a ZIndexManager owned by that floating Container. Therefore ComboBox dropdowns within Windows will have managed z-indices guaranteed to be correct, relative to the Window.

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


### zBase

**Type:** Number

...

Defaults to: `9000`


### Ext.ZIndexManager

...

**Parameters:** container : Object


### _activateLast

...


### _hideModalMask

...


### _onContainerResize

...


### _onMaskClick

...


### _setActiveChild

...

**Parameters:** comp : Object


### _showModalMask

...

**Parameters:** comp : Object


### assignZIndices

...


### bringToFront

Brings the specified Component to the front of any other active Components in this ZIndexManager. ...

Brings the specified Component to the front of any other active Components in this ZIndexManager.

**Parameters:** comp : String/ObjectThe id of the Component or a Ext.Component instance


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

Overrides: Ext.Base.destroy


### each

Executes the specified function once for every Component in this ZIndexManager, passing each Component as the only pa...

Executes the specified function once for every Component in this ZIndexManager, passing each Component as the only parameter. Returning false from the function will stop the iteration.

**Parameters:** fn : FunctionThe function to execute for each item


### eachBottomUp

Executes the specified function once for every Component in this ZIndexManager, passing each Component as the only pa...

Executes the specified function once for every Component in this ZIndexManager, passing each Component as the only parameter. Returning false from the function will stop the iteration. The components are passed to the function starting at the bottom and proceeding to the top.

**Parameters:** fn : FunctionThe function to execute for each item


### eachTopDown

Executes the specified function once for every Component in this ZIndexManager, passing each Component as the only pa...

Executes the specified function once for every Component in this ZIndexManager, passing each Component as the only parameter. Returning false from the function will stop the iteration. The components are passed to the function starting at the top and proceeding to the bottom.

**Parameters:** fn : FunctionThe function to execute for each item


### get

Gets a registered Component by id. ...

Gets a registered Component by id.

**Parameters:** id : String/ObjectThe id of the Component or a Ext.Component instance


### getActive

Gets the currently-active Component in this ZIndexManager. ...

Gets the currently-active Component in this ZIndexManager.

**Returns:** Ext.ComponentThe active Component


### getBy

Returns zero or more Components in this ZIndexManager using the custom search function passed to this method. ...

**Parameters:** fn : FunctionThe search function

**Returns:** zero or more Components in this ZIndexManager using the custom search function passed to this method. The function should accept a single Ext.Component reference as its only argument and should return true if the Component matches the search criteria, otherwise it should return false.


### getConfig

...

**Parameters:** name : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getMaskBox

...


### getNextZSeed

...


### hasConfig

...

**Parameters:** config : Object


### hide

Temporarily hides all currently visible managed Components. ...

Temporarily hides all currently visible managed Components. This is for when dragging a Window which may manage a set of floating descendants in its ZIndexManager; they should all be hidden just for the duration of the drag.


### hideAll

Hides all Components managed by this ZIndexManager. ...

Hides all Components managed by this ZIndexManager.


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### onComponentHide

...

**Parameters:** comp : Object


### onConfigUpdate

...

**Parameters:** names : Object


### register

Registers a floating Ext.Component with this ZIndexManager. ...

Registers a floating Ext.Component with this ZIndexManager. This should not need to be called under normal circumstances. Floating Components (such as Windows, BoundLists and Menus) are automatically registered with a zIndexManager at render time. Where this may be useful is moving Windows between two ZIndexManagers. For example, to bring the Ext.MessageBox dialog under the same manager as the Desktop's ZIndexManager in the desktop sample app:

**Parameters:** comp : Ext.ComponentThe Component to register.


### sendToBack

Sends the specified Component to the back of other active Components in this ZIndexManager. ...

Sends the specified Component to the back of other active Components in this ZIndexManager.

**Parameters:** comp : String/ObjectThe id of the Component or a Ext.Component instance


### setBase

...

**Parameters:** baseZIndex : Object


### setConfig

...

**Parameters:** config : Object


### show

Restores temporarily hidden managed Components to visibility. ...

Restores temporarily hidden managed Components to visibility.


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### unregister

Unregisters a Ext.Component from this ZIndexManager. ...

Unregisters a Ext.Component from this ZIndexManager. This should not need to be called. Components are automatically unregistered upon destruction. See register.

**Parameters:** comp : Ext.ComponentThe Component to unregister.


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

### Ext.ZIndexManager

...

**Parameters:** container : Object


### _activateLast

...


### _hideModalMask

...


### _onContainerResize

...


### _onMaskClick

...


### _setActiveChild

...

**Parameters:** comp : Object


### _showModalMask

...

**Parameters:** comp : Object


### assignZIndices

...


### bringToFront

Brings the specified Component to the front of any other active Components in this ZIndexManager. ...

Brings the specified Component to the front of any other active Components in this ZIndexManager.

**Parameters:** comp : String/ObjectThe id of the Component or a Ext.Component instance


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

Overrides: Ext.Base.destroy


### each

Executes the specified function once for every Component in this ZIndexManager, passing each Component as the only pa...

Executes the specified function once for every Component in this ZIndexManager, passing each Component as the only parameter. Returning false from the function will stop the iteration.

**Parameters:** fn : FunctionThe function to execute for each item


### eachBottomUp

Executes the specified function once for every Component in this ZIndexManager, passing each Component as the only pa...

Executes the specified function once for every Component in this ZIndexManager, passing each Component as the only parameter. Returning false from the function will stop the iteration. The components are passed to the function starting at the bottom and proceeding to the top.

**Parameters:** fn : FunctionThe function to execute for each item


### eachTopDown

Executes the specified function once for every Component in this ZIndexManager, passing each Component as the only pa...

Executes the specified function once for every Component in this ZIndexManager, passing each Component as the only parameter. Returning false from the function will stop the iteration. The components are passed to the function starting at the top and proceeding to the bottom.

**Parameters:** fn : FunctionThe function to execute for each item


### get

Gets a registered Component by id. ...

Gets a registered Component by id.

**Parameters:** id : String/ObjectThe id of the Component or a Ext.Component instance


### getActive

Gets the currently-active Component in this ZIndexManager. ...

Gets the currently-active Component in this ZIndexManager.

**Returns:** Ext.ComponentThe active Component


### getBy

Returns zero or more Components in this ZIndexManager using the custom search function passed to this method. ...

**Parameters:** fn : FunctionThe search function

**Returns:** zero or more Components in this ZIndexManager using the custom search function passed to this method. The function should accept a single Ext.Component reference as its only argument and should return true if the Component matches the search criteria, otherwise it should return false.


### getConfig

...

**Parameters:** name : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getMaskBox

...


### getNextZSeed

...


### hasConfig

...

**Parameters:** config : Object


### hide

Temporarily hides all currently visible managed Components. ...

Temporarily hides all currently visible managed Components. This is for when dragging a Window which may manage a set of floating descendants in its ZIndexManager; they should all be hidden just for the duration of the drag.


### hideAll

Hides all Components managed by this ZIndexManager. ...

Hides all Components managed by this ZIndexManager.


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### onComponentHide

...

**Parameters:** comp : Object


### onConfigUpdate

...

**Parameters:** names : Object


### register

Registers a floating Ext.Component with this ZIndexManager. ...

Registers a floating Ext.Component with this ZIndexManager. This should not need to be called under normal circumstances. Floating Components (such as Windows, BoundLists and Menus) are automatically registered with a zIndexManager at render time. Where this may be useful is moving Windows between two ZIndexManagers. For example, to bring the Ext.MessageBox dialog under the same manager as the Desktop's ZIndexManager in the desktop sample app:

**Parameters:** comp : Ext.ComponentThe Component to register.


### sendToBack

Sends the specified Component to the back of other active Components in this ZIndexManager. ...

Sends the specified Component to the back of other active Components in this ZIndexManager.

**Parameters:** comp : String/ObjectThe id of the Component or a Ext.Component instance


### setBase

...

**Parameters:** baseZIndex : Object


### setConfig

...

**Parameters:** config : Object


### show

Restores temporarily hidden managed Components to visibility. ...

Restores temporarily hidden managed Components to visibility.


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### unregister

Unregisters a Ext.Component from this ZIndexManager. ...

Unregisters a Ext.Component from this ZIndexManager. This should not need to be called. Components are automatically unregistered upon destruction. See register.

**Parameters:** comp : Ext.ComponentThe Component to unregister.


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


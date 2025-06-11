# Ext.Action

**Extends:** Ext.Base

## Description

An Action is a piece of reusable functionality that can be abstracted out of any particular component so that it can be usefully shared among multiple components. Actions let you share handlers, configuration options and UI updates across any components that support the Action interface (primarily Ext.toolbar.Toolbar, Ext.button.Button and Ext.menu.Menu components).

Use a single Action instance as the config object for any number of UI Components which share the same configuration. The Action not only supplies the configuration, but allows all Components based upon it to have a common set of methods called at once through a single call to the Action.

Any Component that is to be configured with an Action must also support the following methods:

This allows the Action to control its associated Components.

Example usage:

## Config options

### disabled

**Type:** Boolean

True to disable all components configured by this Action, false to enable them. ...

True to disable all components configured by this Action, false to enable them. Defaults to: `false`


### handler

**Type:** Function

The function that will be invoked by each component tied to this Action when the component's primary event is triggered.


### hidden

**Type:** Boolean

True to hide all components configured by this Action, false to show them. ...

True to hide all components configured by this Action, false to show them. Defaults to: `false`


### iconCls

**Type:** String

The CSS class selector that specifies a background image to be used as the header icon for all components configured ...

The CSS class selector that specifies a background image to be used as the header icon for all components configured by this Action. An example of specifying a custom icon class would be something like: Defaults to: `''`


### itemId

**Type:** String

See Ext.Component.itemId.


### scope

**Type:** Object

The scope (this reference) in which the handler is executed. ...

The scope (this reference) in which the handler is executed. Defaults to the browser window.


### text

**Type:** String

The text to set for all components configured by this Action. ...

The text to set for all components configured by this Action. Defaults to: `''`


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


### isAction

**Type:** Boolean

true in this class to identify an object as an instantiated Action, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Action, or subclass thereof. Defaults to: `true`


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


### Ext.Action

Creates new Action. ...

Creates new Action.

**Parameters:** config : ObjectConfig object.


### addComponent

...

**Parameters:** comp : Object


### callEach

...

**Parameters:** fnName : Object


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


### disable

Disables all components configured by this Action. ...

Disables all components configured by this Action.


### each

Executes the specified function once for each Component currently tied to this Action. ...

Executes the specified function once for each Component currently tied to this Action. The function passed in should accept a single argument that will be an object that supports the basic Action config/method interface.

**Parameters:** fn : FunctionThe function to execute for each component


### enable

Enables all components configured by this Action. ...

Enables all components configured by this Action.


### execute

Executes this Action manually using the handler function specified in the original config object or the handler funct...

Executes this Action manually using the handler function specified in the original config object or the handler function set with setHandler. Any arguments passed to this function will be passed on to the handler function.

**Parameters:** args : Object...Variable number of arguments passed to the handler function


### getConfig

...

**Parameters:** name : Object


### getIconCls

Gets the icon CSS class currently used by all components configured by this Action. ...

Gets the icon CSS class currently used by all components configured by this Action.


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getText

Gets the text currently displayed by all components configured by this Action. ...

Gets the text currently displayed by all components configured by this Action.


### hasConfig

...

**Parameters:** config : Object


### hide

Hides all components configured by this Action. ...

Hides all components configured by this Action.


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### isDisabled

Returns true if the components using this Action are currently disabled, else returns false. ...

**Returns:** true if the components using this Action are currently disabled, else returns false.


### isHidden

Returns true if the components configured by this Action are currently hidden, else returns false. ...

**Returns:** true if the components configured by this Action are currently hidden, else returns false.


### onConfigUpdate

...

**Parameters:** names : Object


### removeComponent

...

**Parameters:** comp : Object


### setConfig

...

**Parameters:** config : Object


### setDisabled

Sets the disabled state of all components configured by this Action. ...

Sets the disabled state of all components configured by this Action. Shortcut method for enable and disable.

**Parameters:** disabled : BooleanTrue to disable the component, false to enable it


### setHandler

Sets the function that will be called by each Component using this action when its primary event is triggered. ...

Sets the function that will be called by each Component using this action when its primary event is triggered.

**Parameters:** fn : FunctionThe function that will be invoked by the action's components. The function will be called with no arguments.


### setHidden

Sets the hidden state of all components configured by this Action. ...

Sets the hidden state of all components configured by this Action. Shortcut method for `hide` and `show`.

**Parameters:** hidden : BooleanTrue to hide the component, false to show it.


### setIconCls

Sets the icon CSS class for all components configured by this Action. ...

Sets the icon CSS class for all components configured by this Action. The class should supply a background image that will be used as the icon image.

**Parameters:** cls : StringThe CSS class supplying the icon image


### setText

Sets the text to be displayed by all components configured by this Action. ...

Sets the text to be displayed by all components configured by this Action.

**Parameters:** text : StringThe text to display


### show

Shows all components configured by this Action. ...

Shows all components configured by this Action.


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


### initConfigList

**Type:** Array

...

Defaults to: `[]`


### initConfigMap

**Type:** Object

...

Defaults to: `{}`


### isAction

**Type:** Boolean

true in this class to identify an object as an instantiated Action, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Action, or subclass thereof. Defaults to: `true`


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


### Ext.Action

Creates new Action. ...

Creates new Action.

**Parameters:** config : ObjectConfig object.


### addComponent

...

**Parameters:** comp : Object


### callEach

...

**Parameters:** fnName : Object


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


### disable

Disables all components configured by this Action. ...

Disables all components configured by this Action.


### each

Executes the specified function once for each Component currently tied to this Action. ...

Executes the specified function once for each Component currently tied to this Action. The function passed in should accept a single argument that will be an object that supports the basic Action config/method interface.

**Parameters:** fn : FunctionThe function to execute for each component


### enable

Enables all components configured by this Action. ...

Enables all components configured by this Action.


### execute

Executes this Action manually using the handler function specified in the original config object or the handler funct...

Executes this Action manually using the handler function specified in the original config object or the handler function set with setHandler. Any arguments passed to this function will be passed on to the handler function.

**Parameters:** args : Object...Variable number of arguments passed to the handler function


### getConfig

...

**Parameters:** name : Object


### getIconCls

Gets the icon CSS class currently used by all components configured by this Action. ...

Gets the icon CSS class currently used by all components configured by this Action.


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getText

Gets the text currently displayed by all components configured by this Action. ...

Gets the text currently displayed by all components configured by this Action.


### hasConfig

...

**Parameters:** config : Object


### hide

Hides all components configured by this Action. ...

Hides all components configured by this Action.


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### isDisabled

Returns true if the components using this Action are currently disabled, else returns false. ...

**Returns:** true if the components using this Action are currently disabled, else returns false.


### isHidden

Returns true if the components configured by this Action are currently hidden, else returns false. ...

**Returns:** true if the components configured by this Action are currently hidden, else returns false.


### onConfigUpdate

...

**Parameters:** names : Object


### removeComponent

...

**Parameters:** comp : Object


### setConfig

...

**Parameters:** config : Object


### setDisabled

Sets the disabled state of all components configured by this Action. ...

Sets the disabled state of all components configured by this Action. Shortcut method for enable and disable.

**Parameters:** disabled : BooleanTrue to disable the component, false to enable it


### setHandler

Sets the function that will be called by each Component using this action when its primary event is triggered. ...

Sets the function that will be called by each Component using this action when its primary event is triggered.

**Parameters:** fn : FunctionThe function that will be invoked by the action's components. The function will be called with no arguments.


### setHidden

Sets the hidden state of all components configured by this Action. ...

Sets the hidden state of all components configured by this Action. Shortcut method for `hide` and `show`.

**Parameters:** hidden : BooleanTrue to hide the component, false to show it.


### setIconCls

Sets the icon CSS class for all components configured by this Action. ...

Sets the icon CSS class for all components configured by this Action. The class should supply a background image that will be used as the icon image.

**Parameters:** cls : StringThe CSS class supplying the icon image


### setText

Sets the text to be displayed by all components configured by this Action. ...

Sets the text to be displayed by all components configured by this Action.

**Parameters:** text : StringThe text to display


### show

Shows all components configured by this Action. ...

Shows all components configured by this Action.


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

### Ext.Action

Creates new Action. ...

Creates new Action.

**Parameters:** config : ObjectConfig object.


### addComponent

...

**Parameters:** comp : Object


### callEach

...

**Parameters:** fnName : Object


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


### disable

Disables all components configured by this Action. ...

Disables all components configured by this Action.


### each

Executes the specified function once for each Component currently tied to this Action. ...

Executes the specified function once for each Component currently tied to this Action. The function passed in should accept a single argument that will be an object that supports the basic Action config/method interface.

**Parameters:** fn : FunctionThe function to execute for each component


### enable

Enables all components configured by this Action. ...

Enables all components configured by this Action.


### execute

Executes this Action manually using the handler function specified in the original config object or the handler funct...

Executes this Action manually using the handler function specified in the original config object or the handler function set with setHandler. Any arguments passed to this function will be passed on to the handler function.

**Parameters:** args : Object...Variable number of arguments passed to the handler function


### getConfig

...

**Parameters:** name : Object


### getIconCls

Gets the icon CSS class currently used by all components configured by this Action. ...

Gets the icon CSS class currently used by all components configured by this Action.


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getText

Gets the text currently displayed by all components configured by this Action. ...

Gets the text currently displayed by all components configured by this Action.


### hasConfig

...

**Parameters:** config : Object


### hide

Hides all components configured by this Action. ...

Hides all components configured by this Action.


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### isDisabled

Returns true if the components using this Action are currently disabled, else returns false. ...

**Returns:** true if the components using this Action are currently disabled, else returns false.


### isHidden

Returns true if the components configured by this Action are currently hidden, else returns false. ...

**Returns:** true if the components configured by this Action are currently hidden, else returns false.


### onConfigUpdate

...

**Parameters:** names : Object


### removeComponent

...

**Parameters:** comp : Object


### setConfig

...

**Parameters:** config : Object


### setDisabled

Sets the disabled state of all components configured by this Action. ...

Sets the disabled state of all components configured by this Action. Shortcut method for enable and disable.

**Parameters:** disabled : BooleanTrue to disable the component, false to enable it


### setHandler

Sets the function that will be called by each Component using this action when its primary event is triggered. ...

Sets the function that will be called by each Component using this action when its primary event is triggered.

**Parameters:** fn : FunctionThe function that will be invoked by the action's components. The function will be called with no arguments.


### setHidden

Sets the hidden state of all components configured by this Action. ...

Sets the hidden state of all components configured by this Action. Shortcut method for `hide` and `show`.

**Parameters:** hidden : BooleanTrue to hide the component, false to show it.


### setIconCls

Sets the icon CSS class for all components configured by this Action. ...

Sets the icon CSS class for all components configured by this Action. The class should supply a background image that will be used as the icon image.

**Parameters:** cls : StringThe CSS class supplying the icon image


### setText

Sets the text to be displayed by all components configured by this Action. ...

Sets the text to be displayed by all components configured by this Action.

**Parameters:** text : StringThe text to display


### show

Shows all components configured by this Action. ...

Shows all components configured by this Action.


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


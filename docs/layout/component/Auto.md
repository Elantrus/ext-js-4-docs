# Ext.layout.component.Auto

**Extends:** Ext.layout.component.Component

## Description

The class is the default component layout for Ext.Component when no explicit `componentLayout` is configured.

This class uses template methods to perform the individual aspects of measurement, calculation and publication of results. The methods called depend on the component's size model.

In either of these size models, the dimension of the outer element is of a known size. The size is found in the `ownerContext` (the Ext.layout.ContextItem for the owner component) as either "width" or "height". This value, if available, is passed to the `publishInnerWidth` or `publishInnerHeight` method, respectively.

When a dimension uses the `shrinkWrap` size model, that means the content is measured, then the outer (owner) size is calculated and published.

For example, for a shrinkWrap width, the following sequence of calls are made:

When a dimension uses the `natural` size model, the measurement is made on the outer (owner) element. This size is then used to determine the content area in much the same way as if the outer element had a `configured` or `calculated` size model.

## Config options

### setHeightInDom

**Type:** Boolean

When publishing height of an auto Component, it is usually not written to the DOM. ...

When publishing height of an auto Component, it is usually not written to the DOM. Setting this to `true` overrides this behaviour. Defaults to: `false`


### setWidthInDom

**Type:** Boolean

When publishing width of an auto Component, it is usually not written to the DOM. ...

When publishing width of an auto Component, it is usually not written to the DOM. Setting this to `true` overrides this behaviour. Defaults to: `false`


### $className

**Type:** String

...

Defaults to: `'Ext.Base'`


### autoSizePolicy

**Type:** Object

...

Defaults to: `{readsWidth: 1, readsHeight: 1, setsWidth: 0, setsHeight: 0}`


### configMap

**Type:** Object

...

Defaults to: `{}`


### done

**Type:** Boolean

Used only during a layout run, this value indicates that a layout has finished its calculations. ...

Used only during a layout run, this value indicates that a layout has finished its calculations. This flag is set to true prior to the call to calculate and should be set to false if this layout has more work to do.


### initConfigList

**Type:** Array

...

Defaults to: `[]`


### initConfigMap

**Type:** Object

...

Defaults to: `{}`


### initialized

**Type:** Boolean

...

Defaults to: `false`


### isComponentLayout

**Type:** Boolean

...

Defaults to: `true`


### isInstance

**Type:** Boolean

...

Defaults to: `true`


### isLayout

**Type:** Boolean

true in this class to identify an object as an instantiated Layout, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Layout, or subclass thereof. Defaults to: `true`


### nullBox

**Type:** Object

...

Defaults to: `{}`


### running

**Type:** Boolean

...

Defaults to: `false`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### type

**Type:** String

End Definitions ...

End Definitions Defaults to: `'autocomponent'` Overrides: Ext.layout.component.Component.type


### usesContentHeight

**Type:** Boolean

...

Defaults to: `true`


### usesContentWidth

**Type:** Boolean

...

Defaults to: `true`


### usesHeight

**Type:** Boolean

...

Defaults to: `true`


### usesWidth

**Type:** Boolean

...

Defaults to: `true`


### waitForOuterHeightInDom

**Type:** Boolean

...

Defaults to: `false`


### waitForOuterWidthInDom

**Type:** Boolean

...

Defaults to: `false`


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.layout.component.Auto

...

**Parameters:** config : Object


### afterRemove

Removes layout's itemCls and owning Container's itemCls. ...

Removes layout's itemCls and owning Container's itemCls. Clears the managed dimensions flags

**Parameters:** item : Object


### afterRenderItem

...


### beginLayout

Called before any calculation cycles to prepare for layout. ...

Called before any calculation cycles to prepare for layout. This is a write phase and DOM reads should be strictly avoided when overridding this method.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### beginLayoutCycle

Called before any calculation cycles to reset DOM values and prepare for calculation. ...

Called before any calculation cycles to reset DOM values and prepare for calculation. This is a write phase and DOM reads should be strictly avoided when overridding this method.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### cacheTargetInfo

...

**Parameters:** ownerContext : Object


### calculate

Called to perform the calculations for this layout. ...

Called to perform the calculations for this layout. This method will be called at least once and may be called repeatedly if the done property is cleared before return to indicate that this layout is not yet done. The done property is always set to `true` before entering this method. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### calculateOwnerHeightFromContentHeight

...

**Parameters:** ownerContext : Object


### calculateOwnerWidthFromContentWidth

...

**Parameters:** ownerContext : Object


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


### completeLayout

This method (if implemented) is called at the end of the cycle in which this layout completes (by not setting done to...

This method (if implemented) is called at the end of the cycle in which this layout completes (by not setting done to `false` in calculate). It is possible for the layout to complete and yet become invalid before the end of the cycle, in which case, this method will not be called. It is also possible for this method to be called and then later the layout becomes invalidated. This will result in calculate being called again, followed by another call to this method. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### configClass

...


### configureItem

Called before an item is rendered to allow the layout to configure the item. ...

Called before an item is rendered to allow the layout to configure the item.

**Parameters:** item : Ext.ComponentThe item to be configured


### destroy

Destroys this layout. ...

Destroys this layout. This method removes a `targetCls` from the `target` element and calls `onDestroy`. A derived class can override either this method or `onDestroy` but in all cases must call the base class versions of these methods to allow the base class to perform its cleanup. This method (or `onDestroy`) are overridden by subclasses most often to purge event handlers or remove unmanged DOM nodes. Overrides: Ext.Base.destroy


### finalizeLayout

This method (if implemented) is called after all layouts have completed. ...

This method (if implemented) is called after all layouts have completed. In most ways this is similar to completeLayout. This call can cause this (or any layout) to be become invalid (see Ext.layout.Context.invalidate), but this is best avoided. This method is intended to be where final reads are made and so it is best to avoid invalidating layouts at this point whenever possible. Even so, this method can be used to perform final checks that may require all other layouts to be complete and then invalidate some results. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### finishRender

...


### finishRenderItems

...

**Parameters:** target : Object


### finishedLayout

This method is called after all layouts are complete and their calculations flushed to the DOM. ...

This method is called after all layouts are complete and their calculations flushed to the DOM. No further layouts will be run and this method is only called once per layout run. The base component layout caches `lastComponentSize`. This is a write phase and DOM reads should be avoided if possible when overridding this method. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### getAnimatePolicy

...


### getConfig

...

**Parameters:** name : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getItemSizePolicy

Returns an object describing how this layout manages the size of the given component. ...

**Parameters:** item : Ext.Component

**Returns:** an object describing how this layout manages the size of the given component. This method must be implemented by any layout that manages components.


### getItemsRenderTree

...

**Parameters:** items : Object


### getLayoutItems

Returns the set of items to layout (empty by default). ...

**Returns:** the set of items to layout (empty by default).


### getPositionOffset

...

**Parameters:** position : Object


### getRenderTarget

Returns the element into which rendering must take place. ...

**Returns:** the element into which rendering must take place. Defaults to the owner Component's encapsulating element. May be overridden in Component layout managers which implement an inner element. ReturnsExt.Element


### getTarget

Returns the owner component's resize element. ...

**Returns:** the owner component's resize element. ReturnsExt.Element


### hasConfig

...

**Parameters:** config : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initLayout

A one-time initialization method called just before rendering. ...

A one-time initialization method called just before rendering.


### isItemBoxParent

...

**Parameters:** itemContext : Object


### isItemLayoutRoot

...

**Parameters:** item : Object


### isItemShrinkWrap

...

**Parameters:** item : Object


### isRunning

...


### isValidParent

Validates item is in the proper place in the dom. ...

Validates item is in the proper place in the dom.

**Parameters:** item : Object


### measureAutoDimensions

...

**Parameters:** ownerContext : Object


### measureContentHeight

...

**Parameters:** ownerContext : Object


### measureContentWidth

...

**Parameters:** ownerContext : Object


### measureOwnerHeight

...

**Parameters:** ownerContext : Object


### measureOwnerWidth

...

**Parameters:** ownerContext : Object


### moveItem

Moves Component to the provided target instead. ...

Moves Component to the provided target instead.

**Parameters:** item : Object


### notifyOwner

This method (if implemented) is called after all layouts are finished, and all have a lastComponentSize cached. ...

This method (if implemented) is called after all layouts are finished, and all have a `lastComponentSize` cached. No further layouts will be run and this method is only called once per layout run. It is the bookend to beginLayout. This is a write phase and DOM reads should be avoided if possible when overridding this method. This is the catch-all tail method to a layout and so the rules are more relaxed. Even so, for performance reasons, it is best to avoid reading the DOM. If a read is necessary, consider implementing a finalizeLayout method to do the required reads. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### onAdd

...

**Parameters:** item : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onContentChange

This method is called when a child item changes in some way. ...

This method is called when a child item changes in some way. By default this calls Ext.AbstractComponent.updateLayout on this layout's owner.

**Parameters:** child : Ext.ComponentThe child item that has changed.


### onDestroy

...


### onRemove

...


### publishOwnerHeight

...

**Parameters:** ownerContext : Object


### publishOwnerWidth

...

**Parameters:** ownerContext : Object


### renderChildren

...


### renderItem

Renders the given Component into the target Element. ...

Renders the given Component into the target Element.

**Parameters:** item : Ext.ComponentThe Component to render


### renderItems

Iterates over all passed items, ensuring they are rendered. ...

Iterates over all passed items, ensuring they are rendered. If the items are already rendered, also determines if the items are in the proper place in the dom.

**Parameters:** items : Object


### setConfig

...

**Parameters:** config : Object


### setOwner

Sets the layout owner ...

Sets the layout owner

**Parameters:** owner : Object


### sortWeightedItems

...

**Parameters:** items : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### undoLayout

...


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


### autoSizePolicy

**Type:** Object

...

Defaults to: `{readsWidth: 1, readsHeight: 1, setsWidth: 0, setsHeight: 0}`


### configMap

**Type:** Object

...

Defaults to: `{}`


### done

**Type:** Boolean

Used only during a layout run, this value indicates that a layout has finished its calculations. ...

Used only during a layout run, this value indicates that a layout has finished its calculations. This flag is set to true prior to the call to calculate and should be set to false if this layout has more work to do.


### initConfigList

**Type:** Array

...

Defaults to: `[]`


### initConfigMap

**Type:** Object

...

Defaults to: `{}`


### initialized

**Type:** Boolean

...

Defaults to: `false`


### isComponentLayout

**Type:** Boolean

...

Defaults to: `true`


### isInstance

**Type:** Boolean

...

Defaults to: `true`


### isLayout

**Type:** Boolean

true in this class to identify an object as an instantiated Layout, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Layout, or subclass thereof. Defaults to: `true`


### nullBox

**Type:** Object

...

Defaults to: `{}`


### running

**Type:** Boolean

...

Defaults to: `false`


### self

**Type:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics, `this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics for a detailed comparison


### type

**Type:** String

End Definitions ...

End Definitions Defaults to: `'autocomponent'` Overrides: Ext.layout.component.Component.type


### usesContentHeight

**Type:** Boolean

...

Defaults to: `true`


### usesContentWidth

**Type:** Boolean

...

Defaults to: `true`


### usesHeight

**Type:** Boolean

...

Defaults to: `true`


### usesWidth

**Type:** Boolean

...

Defaults to: `true`


### waitForOuterHeightInDom

**Type:** Boolean

...

Defaults to: `false`


### waitForOuterWidthInDom

**Type:** Boolean

...

Defaults to: `false`


### $onExtended

**Type:** Array

...

Defaults to: `[]`


### Ext.layout.component.Auto

...

**Parameters:** config : Object


### afterRemove

Removes layout's itemCls and owning Container's itemCls. ...

Removes layout's itemCls and owning Container's itemCls. Clears the managed dimensions flags

**Parameters:** item : Object


### afterRenderItem

...


### beginLayout

Called before any calculation cycles to prepare for layout. ...

Called before any calculation cycles to prepare for layout. This is a write phase and DOM reads should be strictly avoided when overridding this method.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### beginLayoutCycle

Called before any calculation cycles to reset DOM values and prepare for calculation. ...

Called before any calculation cycles to reset DOM values and prepare for calculation. This is a write phase and DOM reads should be strictly avoided when overridding this method.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### cacheTargetInfo

...

**Parameters:** ownerContext : Object


### calculate

Called to perform the calculations for this layout. ...

Called to perform the calculations for this layout. This method will be called at least once and may be called repeatedly if the done property is cleared before return to indicate that this layout is not yet done. The done property is always set to `true` before entering this method. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### calculateOwnerHeightFromContentHeight

...

**Parameters:** ownerContext : Object


### calculateOwnerWidthFromContentWidth

...

**Parameters:** ownerContext : Object


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


### completeLayout

This method (if implemented) is called at the end of the cycle in which this layout completes (by not setting done to...

This method (if implemented) is called at the end of the cycle in which this layout completes (by not setting done to `false` in calculate). It is possible for the layout to complete and yet become invalid before the end of the cycle, in which case, this method will not be called. It is also possible for this method to be called and then later the layout becomes invalidated. This will result in calculate being called again, followed by another call to this method. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### configClass

...


### configureItem

Called before an item is rendered to allow the layout to configure the item. ...

Called before an item is rendered to allow the layout to configure the item.

**Parameters:** item : Ext.ComponentThe item to be configured


### destroy

Destroys this layout. ...

Destroys this layout. This method removes a `targetCls` from the `target` element and calls `onDestroy`. A derived class can override either this method or `onDestroy` but in all cases must call the base class versions of these methods to allow the base class to perform its cleanup. This method (or `onDestroy`) are overridden by subclasses most often to purge event handlers or remove unmanged DOM nodes. Overrides: Ext.Base.destroy


### finalizeLayout

This method (if implemented) is called after all layouts have completed. ...

This method (if implemented) is called after all layouts have completed. In most ways this is similar to completeLayout. This call can cause this (or any layout) to be become invalid (see Ext.layout.Context.invalidate), but this is best avoided. This method is intended to be where final reads are made and so it is best to avoid invalidating layouts at this point whenever possible. Even so, this method can be used to perform final checks that may require all other layouts to be complete and then invalidate some results. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### finishRender

...


### finishRenderItems

...

**Parameters:** target : Object


### finishedLayout

This method is called after all layouts are complete and their calculations flushed to the DOM. ...

This method is called after all layouts are complete and their calculations flushed to the DOM. No further layouts will be run and this method is only called once per layout run. The base component layout caches `lastComponentSize`. This is a write phase and DOM reads should be avoided if possible when overridding this method. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### getAnimatePolicy

...


### getConfig

...

**Parameters:** name : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getItemSizePolicy

Returns an object describing how this layout manages the size of the given component. ...

**Parameters:** item : Ext.Component

**Returns:** an object describing how this layout manages the size of the given component. This method must be implemented by any layout that manages components.


### getItemsRenderTree

...

**Parameters:** items : Object


### getLayoutItems

Returns the set of items to layout (empty by default). ...

**Returns:** the set of items to layout (empty by default).


### getPositionOffset

...

**Parameters:** position : Object


### getRenderTarget

Returns the element into which rendering must take place. ...

**Returns:** the element into which rendering must take place. Defaults to the owner Component's encapsulating element. May be overridden in Component layout managers which implement an inner element. ReturnsExt.Element


### getTarget

Returns the owner component's resize element. ...

**Returns:** the owner component's resize element. ReturnsExt.Element


### hasConfig

...

**Parameters:** config : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initLayout

A one-time initialization method called just before rendering. ...

A one-time initialization method called just before rendering.


### isItemBoxParent

...

**Parameters:** itemContext : Object


### isItemLayoutRoot

...

**Parameters:** item : Object


### isItemShrinkWrap

...

**Parameters:** item : Object


### isRunning

...


### isValidParent

Validates item is in the proper place in the dom. ...

Validates item is in the proper place in the dom.

**Parameters:** item : Object


### measureAutoDimensions

...

**Parameters:** ownerContext : Object


### measureContentHeight

...

**Parameters:** ownerContext : Object


### measureContentWidth

...

**Parameters:** ownerContext : Object


### measureOwnerHeight

...

**Parameters:** ownerContext : Object


### measureOwnerWidth

...

**Parameters:** ownerContext : Object


### moveItem

Moves Component to the provided target instead. ...

Moves Component to the provided target instead.

**Parameters:** item : Object


### notifyOwner

This method (if implemented) is called after all layouts are finished, and all have a lastComponentSize cached. ...

This method (if implemented) is called after all layouts are finished, and all have a `lastComponentSize` cached. No further layouts will be run and this method is only called once per layout run. It is the bookend to beginLayout. This is a write phase and DOM reads should be avoided if possible when overridding this method. This is the catch-all tail method to a layout and so the rules are more relaxed. Even so, for performance reasons, it is best to avoid reading the DOM. If a read is necessary, consider implementing a finalizeLayout method to do the required reads. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### onAdd

...

**Parameters:** item : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onContentChange

This method is called when a child item changes in some way. ...

This method is called when a child item changes in some way. By default this calls Ext.AbstractComponent.updateLayout on this layout's owner.

**Parameters:** child : Ext.ComponentThe child item that has changed.


### onDestroy

...


### onRemove

...


### publishOwnerHeight

...

**Parameters:** ownerContext : Object


### publishOwnerWidth

...

**Parameters:** ownerContext : Object


### renderChildren

...


### renderItem

Renders the given Component into the target Element. ...

Renders the given Component into the target Element.

**Parameters:** item : Ext.ComponentThe Component to render


### renderItems

Iterates over all passed items, ensuring they are rendered. ...

Iterates over all passed items, ensuring they are rendered. If the items are already rendered, also determines if the items are in the proper place in the dom.

**Parameters:** items : Object


### setConfig

...

**Parameters:** config : Object


### setOwner

Sets the layout owner ...

Sets the layout owner

**Parameters:** owner : Object


### sortWeightedItems

...

**Parameters:** items : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### undoLayout

...


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

### Ext.layout.component.Auto

...

**Parameters:** config : Object


### afterRemove

Removes layout's itemCls and owning Container's itemCls. ...

Removes layout's itemCls and owning Container's itemCls. Clears the managed dimensions flags

**Parameters:** item : Object


### afterRenderItem

...


### beginLayout

Called before any calculation cycles to prepare for layout. ...

Called before any calculation cycles to prepare for layout. This is a write phase and DOM reads should be strictly avoided when overridding this method.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### beginLayoutCycle

Called before any calculation cycles to reset DOM values and prepare for calculation. ...

Called before any calculation cycles to reset DOM values and prepare for calculation. This is a write phase and DOM reads should be strictly avoided when overridding this method.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### cacheTargetInfo

...

**Parameters:** ownerContext : Object


### calculate

Called to perform the calculations for this layout. ...

Called to perform the calculations for this layout. This method will be called at least once and may be called repeatedly if the done property is cleared before return to indicate that this layout is not yet done. The done property is always set to `true` before entering this method. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### calculateOwnerHeightFromContentHeight

...

**Parameters:** ownerContext : Object


### calculateOwnerWidthFromContentWidth

...

**Parameters:** ownerContext : Object


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


### completeLayout

This method (if implemented) is called at the end of the cycle in which this layout completes (by not setting done to...

This method (if implemented) is called at the end of the cycle in which this layout completes (by not setting done to `false` in calculate). It is possible for the layout to complete and yet become invalid before the end of the cycle, in which case, this method will not be called. It is also possible for this method to be called and then later the layout becomes invalidated. This will result in calculate being called again, followed by another call to this method. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### configClass

...


### configureItem

Called before an item is rendered to allow the layout to configure the item. ...

Called before an item is rendered to allow the layout to configure the item.

**Parameters:** item : Ext.ComponentThe item to be configured


### destroy

Destroys this layout. ...

Destroys this layout. This method removes a `targetCls` from the `target` element and calls `onDestroy`. A derived class can override either this method or `onDestroy` but in all cases must call the base class versions of these methods to allow the base class to perform its cleanup. This method (or `onDestroy`) are overridden by subclasses most often to purge event handlers or remove unmanged DOM nodes. Overrides: Ext.Base.destroy


### finalizeLayout

This method (if implemented) is called after all layouts have completed. ...

This method (if implemented) is called after all layouts have completed. In most ways this is similar to completeLayout. This call can cause this (or any layout) to be become invalid (see Ext.layout.Context.invalidate), but this is best avoided. This method is intended to be where final reads are made and so it is best to avoid invalidating layouts at this point whenever possible. Even so, this method can be used to perform final checks that may require all other layouts to be complete and then invalidate some results. This is a read phase and DOM writes should be strictly avoided in derived classes. Instead, DOM writes need to be written to Ext.layout.ContextItem objects to be flushed at the next opportunity. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### finishRender

...


### finishRenderItems

...

**Parameters:** target : Object


### finishedLayout

This method is called after all layouts are complete and their calculations flushed to the DOM. ...

This method is called after all layouts are complete and their calculations flushed to the DOM. No further layouts will be run and this method is only called once per layout run. The base component layout caches `lastComponentSize`. This is a write phase and DOM reads should be avoided if possible when overridding this method. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### getAnimatePolicy

...


### getConfig

...

**Parameters:** name : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating this class. ...

**Parameters:** name : String (optional)Name of the config option to return.

**Returns:** the initial configuration passed to constructor when instantiating this class.


### getItemSizePolicy

Returns an object describing how this layout manages the size of the given component. ...

**Parameters:** item : Ext.Component

**Returns:** an object describing how this layout manages the size of the given component. This method must be implemented by any layout that manages components.


### getItemsRenderTree

...

**Parameters:** items : Object


### getLayoutItems

Returns the set of items to layout (empty by default). ...

**Returns:** the set of items to layout (empty by default).


### getPositionOffset

...

**Parameters:** position : Object


### getRenderTarget

Returns the element into which rendering must take place. ...

**Returns:** the element into which rendering must take place. Defaults to the owner Component's encapsulating element. May be overridden in Component layout managers which implement an inner element. ReturnsExt.Element


### getTarget

Returns the owner component's resize element. ...

**Returns:** the owner component's resize element. ReturnsExt.Element


### hasConfig

...

**Parameters:** config : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

**Parameters:** config : Object


### initLayout

A one-time initialization method called just before rendering. ...

A one-time initialization method called just before rendering.


### isItemBoxParent

...

**Parameters:** itemContext : Object


### isItemLayoutRoot

...

**Parameters:** item : Object


### isItemShrinkWrap

...

**Parameters:** item : Object


### isRunning

...


### isValidParent

Validates item is in the proper place in the dom. ...

Validates item is in the proper place in the dom.

**Parameters:** item : Object


### measureAutoDimensions

...

**Parameters:** ownerContext : Object


### measureContentHeight

...

**Parameters:** ownerContext : Object


### measureContentWidth

...

**Parameters:** ownerContext : Object


### measureOwnerHeight

...

**Parameters:** ownerContext : Object


### measureOwnerWidth

...

**Parameters:** ownerContext : Object


### moveItem

Moves Component to the provided target instead. ...

Moves Component to the provided target instead.

**Parameters:** item : Object


### notifyOwner

This method (if implemented) is called after all layouts are finished, and all have a lastComponentSize cached. ...

This method (if implemented) is called after all layouts are finished, and all have a `lastComponentSize` cached. No further layouts will be run and this method is only called once per layout run. It is the bookend to beginLayout. This is a write phase and DOM reads should be avoided if possible when overridding this method. This is the catch-all tail method to a layout and so the rules are more relaxed. Even so, for performance reasons, it is best to avoid reading the DOM. If a read is necessary, consider implementing a finalizeLayout method to do the required reads. This method need not be implemented by derived classes and, in fact, should only be implemented when needed.

**Parameters:** ownerContext : Ext.layout.ContextItemThe context item for the layout's owner component.


### onAdd

...

**Parameters:** item : Object


### onConfigUpdate

...

**Parameters:** names : Object


### onContentChange

This method is called when a child item changes in some way. ...

This method is called when a child item changes in some way. By default this calls Ext.AbstractComponent.updateLayout on this layout's owner.

**Parameters:** child : Ext.ComponentThe child item that has changed.


### onDestroy

...


### onRemove

...


### publishOwnerHeight

...

**Parameters:** ownerContext : Object


### publishOwnerWidth

...

**Parameters:** ownerContext : Object


### renderChildren

...


### renderItem

Renders the given Component into the target Element. ...

Renders the given Component into the target Element.

**Parameters:** item : Ext.ComponentThe Component to render


### renderItems

Iterates over all passed items, ensuring they are rendered. ...

Iterates over all passed items, ensuring they are rendered. If the items are already rendered, also determines if the items are in the proper place in the dom.

**Parameters:** items : Object


### setConfig

...

**Parameters:** config : Object


### setOwner

Sets the layout owner ...

Sets the layout owner

**Parameters:** owner : Object


### sortWeightedItems

...

**Parameters:** items : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self, `this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what `this` points to during run-time

**Returns:** Ext.Class


### undoLayout

...


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


# Ext.Class

## Description

Handles class creation throughout the framework. This is a low level factory that is used by Ext.ClassManager and generally should not be used directly. If you choose to use Ext.Class you will lose out on the namespace, aliasing and depency loading features made available by Ext.ClassManager. The only time you would use Ext.Class directly is to create an anonymous class.

If you wish to create a class you should use Ext.define which aliases Ext.ClassManager.create to enable namespacing and dynamic dependency resolution.

Ext.Class is the factory and **not** the superclass of everything. For the base class that **all** Ext classes inherit from, see Ext.Base.

## Config options

### alias

**Type:** String[]

List of short aliases for class names. ...

List of short aliases for class names. Most useful for defining xtypes for widgets: Besides "widget" for xtype there are alias namespaces like "feature" for ftype and "plugin" for ptype.


### alternateClassName

**Type:** String/String[]

Defines alternate names for this class. ...

Defines alternate names for this class. For example:


### config

**Type:** Object

List of configuration options with their default values, for which automatically accessor methods are generated. ...

List of configuration options with their default values, for which automatically accessor methods are generated. For example: NOTE for when configs are reference types, the getter and setter methods do not make copies. For example, when a config value is set, the reference is stored on the instance. All instances that set the same reference type will share it. In the case of the getter, the value with either come from the prototype if the setter was never called or from the instance as the last value passed to the setter. For some config properties, the value passed to the setter is transformed prior to being stored on the instance.


### extend

**Type:** String

The parent class that this class extends. ...

The parent class that this class extends. For example:


### inheritableStatics

**Type:** Object

List of inheritable static methods for this class. ...

List of inheritable static methods for this class. Otherwise just like statics but subclasses inherit these methods.


### mixins

**Type:** String[]/Object

List of classes to mix into this class. ...

List of classes to mix into this class. For example: In this case the Musician class will get a `sing` method from CanSing mixin. But what if the Musician already has a `sing` method? Or you want to mix in two classes, both of which define `sing`? In such a cases it's good to define mixins as an object, where you assign a name to each mixin: In this case the `sing` method of Musician will overwrite the mixed in `sing` method. But you can access the original mixed in method through special `mixins` property.


### requires

**Type:** String[]

List of classes that have to be loaded before instantiating this class. ...

List of classes that have to be loaded before instantiating this class. For example:


### singleton

**Type:** Boolean

When set to true, the class will be instantiated as singleton. ...

When set to true, the class will be instantiated as singleton. For example:


### statics

**Type:** Object

List of static methods for this class. ...

List of static methods for this class. For example:


### uses

**Type:** String[]

List of optional classes to load together with this class. ...

List of optional classes to load together with this class. These aren't neccessarily loaded before this class is created, but are guaranteed to be available before Ext.onReady listeners are invoked. For example:


### defaultPreprocessors

**Type:** Array

...

Defaults to: `[]`


### preprocessors

**Type:** Object

...

Defaults to: `{}`


### Ext.Class

Create a new anonymous class. ...

Create a new anonymous class.

**Parameters:** data : ObjectAn object represent the properties of this class


### create

...

**Parameters:** Class : Object


### getPreprocessors

...


### onBeforeCreated

...

**Parameters:** Class : Object


### process

...

**Parameters:** Class : Object


### getDefaultPreprocessors

Retrieve the array stack of default pre-processors ...

Retrieve the array stack of default pre-processors

**Returns:** Function[]defaultPreprocessors


### getPreprocessor

Retrieve a pre-processor callback function by its name, which has been registered before ...

Retrieve a pre-processor callback function by its name, which has been registered before

**Parameters:** name : String


### registerPreprocessor

Register a new pre-processor to be used during the class creation process ...

Register a new pre-processor to be used during the class creation process

**Parameters:** name : StringThe pre-processor's name


### setDefaultPreprocessorPosition

Insert this pre-processor at a specific position in the stack, optionally relative to any existing pre-processor. ...

Insert this pre-processor at a specific position in the stack, optionally relative to any existing pre-processor. For example:

**Parameters:** name : StringThe pre-processor name. Note that it needs to be registered with registerPreprocessor before this


### setDefaultPreprocessors

Set the default array stack of default pre-processors ...

Set the default array stack of default pre-processors

**Parameters:** preprocessors : Array


## Properties

### defaultPreprocessors

**Type:** Array

...

Defaults to: `[]`


### preprocessors

**Type:** Object

...

Defaults to: `{}`


### Ext.Class

Create a new anonymous class. ...

Create a new anonymous class.

**Parameters:** data : ObjectAn object represent the properties of this class


### create

...

**Parameters:** Class : Object


### getPreprocessors

...


### onBeforeCreated

...

**Parameters:** Class : Object


### process

...

**Parameters:** Class : Object


### getDefaultPreprocessors

Retrieve the array stack of default pre-processors ...

Retrieve the array stack of default pre-processors

**Returns:** Function[]defaultPreprocessors


### getPreprocessor

Retrieve a pre-processor callback function by its name, which has been registered before ...

Retrieve a pre-processor callback function by its name, which has been registered before

**Parameters:** name : String


### registerPreprocessor

Register a new pre-processor to be used during the class creation process ...

Register a new pre-processor to be used during the class creation process

**Parameters:** name : StringThe pre-processor's name


### setDefaultPreprocessorPosition

Insert this pre-processor at a specific position in the stack, optionally relative to any existing pre-processor. ...

Insert this pre-processor at a specific position in the stack, optionally relative to any existing pre-processor. For example:

**Parameters:** name : StringThe pre-processor name. Note that it needs to be registered with registerPreprocessor before this


### setDefaultPreprocessors

Set the default array stack of default pre-processors ...

Set the default array stack of default pre-processors

**Parameters:** preprocessors : Array


## Methods

### Ext.Class

Create a new anonymous class. ...

Create a new anonymous class.

**Parameters:** data : ObjectAn object represent the properties of this class


### create

...

**Parameters:** Class : Object


### getPreprocessors

...


### onBeforeCreated

...

**Parameters:** Class : Object


### process

...

**Parameters:** Class : Object


### getDefaultPreprocessors

Retrieve the array stack of default pre-processors ...

Retrieve the array stack of default pre-processors

**Returns:** Function[]defaultPreprocessors


### getPreprocessor

Retrieve a pre-processor callback function by its name, which has been registered before ...

Retrieve a pre-processor callback function by its name, which has been registered before

**Parameters:** name : String


### registerPreprocessor

Register a new pre-processor to be used during the class creation process ...

Register a new pre-processor to be used during the class creation process

**Parameters:** name : StringThe pre-processor's name


### setDefaultPreprocessorPosition

Insert this pre-processor at a specific position in the stack, optionally relative to any existing pre-processor. ...

Insert this pre-processor at a specific position in the stack, optionally relative to any existing pre-processor. For example:

**Parameters:** name : StringThe pre-processor name. Note that it needs to be registered with registerPreprocessor before this


### setDefaultPreprocessors

Set the default array stack of default pre-processors ...

Set the default array stack of default pre-processors

**Parameters:** preprocessors : Array


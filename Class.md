# Ext.Class

## Descrição

Handles class creation throughout the framework. This is a low level factory that is used by Ext.ClassManager and generally
should not be used directly. If you choose to use Ext.Class you will lose out on the namespace, aliasing and depency loading
features made available by Ext.ClassManager. The only time you would use Ext.Class directly is to create an anonymous class.

If you wish to create a class you should use Ext.define which aliases
Ext.ClassManager.create to enable namespacing and dynamic dependency resolution.

Ext.Class is the factory and **not** the superclass of everything. For the base class that **all** Ext classes inherit
from, see Ext.Base.

## Config options

### alias

**Tipo:** String[]

List of short aliases for class names. ...

List of short aliases for class names.  Most useful for defining xtypes for widgets:

Ext.define('MyApp.CoolPanel', {
    extend: 'Ext.panel.Panel',
    alias: ['widget.coolpanel'],
    title: 'Yeah!'
});

// Using Ext.create
Ext.create('widget.coolpanel');

// Using the shorthand for defining widgets by xtype
Ext.widget('panel', {
    items: [
        {xtype: 'coolpanel', html: 'Foo'},
        {xtype: 'coolpanel', html: 'Bar'}
    ]
});


Besides "widget" for xtype there are alias namespaces like "feature" for ftype and "plugin" for ptype.


### alternateClassName

**Tipo:** String/String[]

Defines alternate names for this class. ...

Defines alternate names for this class.  For example:

Ext.define('Developer', {
    alternateClassName: ['Coder', 'Hacker'],
    code: function(msg) {
        alert('Typing... ' + msg);
    }
});

var joe = Ext.create('Developer');
joe.code('stackoverflow');

var rms = Ext.create('Hacker');
rms.code('hack hack');


### config

**Tipo:** Object

List of configuration options with their default values, for which automatically
accessor methods are generated. ...

List of configuration options with their default values, for which automatically
accessor methods are generated.  For example:

Ext.define('SmartPhone', {
     config: {
         hasTouchScreen: false,
         operatingSystem: 'Other',
         price: 500
     },
     constructor: function(cfg) {
         this.initConfig(cfg);
     }
});

var iPhone = new SmartPhone({
     hasTouchScreen: true,
     operatingSystem: 'iOS'
});

iPhone.getPrice(); // 500;
iPhone.getOperatingSystem(); // 'iOS'
iPhone.getHasTouchScreen(); // true;


NOTE for when configs are reference types, the getter and setter methods do not make copies.

For example, when a config value is set, the reference is stored on the instance. All instances that set
the same reference type will share it.

In the case of the getter, the value with either come from the prototype if the setter was never called or from
the instance as the last value passed to the setter.

For some config properties, the value passed to the setter is transformed prior to being stored on the instance.


### extend

**Tipo:** String

The parent class that this class extends. ...

The parent class that this class extends. For example:

Ext.define('Person', {
    say: function(text) { alert(text); }
});

Ext.define('Developer', {
    extend: 'Person',
    say: function(text) { this.callParent(["print "+text]); }
});


### inheritableStatics

**Tipo:** Object

List of inheritable static methods for this class. ...

List of inheritable static methods for this class.
Otherwise just like statics but subclasses inherit these methods.


### mixins

**Tipo:** String[]/Object

List of classes to mix into this class. ...

List of classes to mix into this class. For example:

Ext.define('CanSing', {
     sing: function() {
         alert("I'm on the highway to hell...")
     }
});

Ext.define('Musician', {
     mixins: ['CanSing']
})


In this case the Musician class will get a `sing` method from CanSing mixin.

But what if the Musician already has a `sing` method? Or you want to mix
in two classes, both of which define `sing`?  In such a cases it's good
to define mixins as an object, where you assign a name to each mixin:

Ext.define('Musician', {
     mixins: {
         canSing: 'CanSing'
     },

     sing: function() {
         // delegate singing operation to mixin
         this.mixins.canSing.sing.call(this);
     }
})


In this case the `sing` method of Musician will overwrite the
mixed in `sing` method. But you can access the original mixed in method
through special `mixins` property.


### requires

**Tipo:** String[]

List of classes that have to be loaded before instantiating this class. ...

List of classes that have to be loaded before instantiating this class.
For example:

Ext.define('Mother', {
    requires: ['Child'],
    giveBirth: function() {
        // we can be sure that child class is available.
        return new Child();
    }
});


### singleton

**Tipo:** Boolean

When set to true, the class will be instantiated as singleton. ...

When set to true, the class will be instantiated as singleton.  For example:

Ext.define('Logger', {
    singleton: true,
    log: function(msg) {
        console.log(msg);
    }
});

Logger.log('Hello');


### statics

**Tipo:** Object

List of static methods for this class. ...

List of static methods for this class. For example:

Ext.define('Computer', {
     statics: {
         factory: function(brand) {
             // 'this' in static methods refer to the class itself
             return new this(brand);
         }
     },

     constructor: function() { ... }
});

var dellComputer = Computer.factory('Dell');


### uses

**Tipo:** String[]

List of optional classes to load together with this class. ...

List of optional classes to load together with this class. These aren't neccessarily loaded before
this class is created, but are guaranteed to be available before Ext.onReady listeners are
invoked. For example:

Ext.define('Mother', {
    uses: ['Child'],
    giveBirth: function() {
        // This code might, or might not work:
        // return new Child();

        // Instead use Ext.create() to load the class at the spot if not loaded already:
        return Ext.create('Child');
    }
});


### defaultPreprocessors

**Tipo:** Array

...

Defaults to: `[]`


### preprocessors

**Tipo:** Object

...

Defaults to: `{}`


### Ext.Class

Create a new anonymous class. ...

Create a new anonymous class.
Parametersdata : ObjectAn object represent the properties of this class


### create

...

ParametersClass : Object


### getPreprocessors

...


### onBeforeCreated

...

ParametersClass : Object


### process

...

ParametersClass : Object


### getDefaultPreprocessors

Retrieve the array stack of default pre-processors ...

Retrieve the array stack of default pre-processors
ReturnsFunction[]defaultPreprocessors


### getPreprocessor

Retrieve a pre-processor callback function by its name, which has been registered before ...

Retrieve a pre-processor callback function by its name, which has been registered before
Parametersname : String


### registerPreprocessor

Register a new pre-processor to be used during the class creation process ...

Register a new pre-processor to be used during the class creation process
Parametersname : StringThe pre-processor's name


### setDefaultPreprocessorPosition

Insert this pre-processor at a specific position in the stack, optionally relative to
any existing pre-processor. ...

Insert this pre-processor at a specific position in the stack, optionally relative to
any existing pre-processor. For example:

Ext.Class.registerPreprocessor('debug', function(cls, data, fn) {
    // Your code here

    if (fn) {
        fn.call(this, cls, data);
    }
}).setDefaultPreprocessorPosition('debug', 'last');

Parametersname : StringThe pre-processor name. Note that it needs to be registered with
registerPreprocessor before this


### setDefaultPreprocessors

Set the default array stack of default pre-processors ...

Set the default array stack of default pre-processors
Parameterspreprocessors : Array


## Properties

### defaultPreprocessors

**Tipo:** Array

...

Defaults to: `[]`


### preprocessors

**Tipo:** Object

...

Defaults to: `{}`


### Ext.Class

Create a new anonymous class. ...

Create a new anonymous class.
Parametersdata : ObjectAn object represent the properties of this class


### create

...

ParametersClass : Object


### getPreprocessors

...


### onBeforeCreated

...

ParametersClass : Object


### process

...

ParametersClass : Object


### getDefaultPreprocessors

Retrieve the array stack of default pre-processors ...

Retrieve the array stack of default pre-processors
ReturnsFunction[]defaultPreprocessors


### getPreprocessor

Retrieve a pre-processor callback function by its name, which has been registered before ...

Retrieve a pre-processor callback function by its name, which has been registered before
Parametersname : String


### registerPreprocessor

Register a new pre-processor to be used during the class creation process ...

Register a new pre-processor to be used during the class creation process
Parametersname : StringThe pre-processor's name


### setDefaultPreprocessorPosition

Insert this pre-processor at a specific position in the stack, optionally relative to
any existing pre-processor. ...

Insert this pre-processor at a specific position in the stack, optionally relative to
any existing pre-processor. For example:

Ext.Class.registerPreprocessor('debug', function(cls, data, fn) {
    // Your code here

    if (fn) {
        fn.call(this, cls, data);
    }
}).setDefaultPreprocessorPosition('debug', 'last');

Parametersname : StringThe pre-processor name. Note that it needs to be registered with
registerPreprocessor before this


### setDefaultPreprocessors

Set the default array stack of default pre-processors ...

Set the default array stack of default pre-processors
Parameterspreprocessors : Array


## Methods

### Ext.Class

Create a new anonymous class. ...

Create a new anonymous class.
Parametersdata : ObjectAn object represent the properties of this class


### create

...

ParametersClass : Object


### getPreprocessors

...


### onBeforeCreated

...

ParametersClass : Object


### process

...

ParametersClass : Object


### getDefaultPreprocessors

Retrieve the array stack of default pre-processors ...

Retrieve the array stack of default pre-processors
ReturnsFunction[]defaultPreprocessors


### getPreprocessor

Retrieve a pre-processor callback function by its name, which has been registered before ...

Retrieve a pre-processor callback function by its name, which has been registered before
Parametersname : String


### registerPreprocessor

Register a new pre-processor to be used during the class creation process ...

Register a new pre-processor to be used during the class creation process
Parametersname : StringThe pre-processor's name


### setDefaultPreprocessorPosition

Insert this pre-processor at a specific position in the stack, optionally relative to
any existing pre-processor. ...

Insert this pre-processor at a specific position in the stack, optionally relative to
any existing pre-processor. For example:

Ext.Class.registerPreprocessor('debug', function(cls, data, fn) {
    // Your code here

    if (fn) {
        fn.call(this, cls, data);
    }
}).setDefaultPreprocessorPosition('debug', 'last');

Parametersname : StringThe pre-processor name. Note that it needs to be registered with
registerPreprocessor before this


### setDefaultPreprocessors

Set the default array stack of default pre-processors ...

Set the default array stack of default pre-processors
Parameterspreprocessors : Array


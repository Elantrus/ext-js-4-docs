# Ext.ClassManager

## Descrição

Ext.ClassManager manages all classes and handles mapping from string class name to
actual class objects throughout the whole framework. It is not generally accessed directly, rather through
these convenient shorthands:

Ext.define(className, properties);


in which `properties` is an object represent a collection of properties that apply to the class. See
create for more detailed instructions.

Ext.define('Person', {
     name: 'Unknown',

     constructor: function(name) {
         if (name) {
             this.name = name;
         }
     },

     eat: function(foodType) {
         alert("I'm eating: " + foodType);

         return this;
     }
});

var aaron = new Person("Aaron");
aaron.eat("Sandwich"); // alert("I'm eating: Sandwich");


Ext.Class has a powerful set of extensible pre-processors which takes care of
everything related to class creation, including but not limited to inheritance, mixins, configuration, statics, etc.

Ext.define('Developer', {
     extend: 'Person',

     constructor: function(name, isGeek) {
         this.isGeek = isGeek;

         // Apply a method from the parent class' prototype
         this.callParent([name]);
     },

     code: function(language) {
         alert("I'm coding in: " + language);

         this.eat("Bugs");

         return this;
     }
});

var jacky = new Developer("Jacky", true);
jacky.code("JavaScript"); // alert("I'm coding in: JavaScript");
                          // alert("I'm eating: Bugs");


See Ext.Base.callParent for more details on calling superclass' methods

Ext.define('CanPlayGuitar', {
     playGuitar: function() {
        alert("F#...G...D...A");
     }
});

Ext.define('CanComposeSongs', {
     composeSongs: function() { ... }
});

Ext.define('CanSing', {
     sing: function() {
         alert("I'm on the highway to hell...")
     }
});

Ext.define('Musician', {
     extend: 'Person',

     mixins: {
         canPlayGuitar: 'CanPlayGuitar',
         canComposeSongs: 'CanComposeSongs',
         canSing: 'CanSing'
     }
})

Ext.define('CoolPerson', {
     extend: 'Person',

     mixins: {
         canPlayGuitar: 'CanPlayGuitar',
         canSing: 'CanSing'
     },

     sing: function() {
         alert("Ahem....");

         this.mixins.canSing.sing.call(this);

         alert("[Playing guitar at the same time...]");

         this.playGuitar();
     }
});

var me = new CoolPerson("Jacky");

me.sing(); // alert("Ahem...");
           // alert("I'm on the highway to hell...");
           // alert("[Playing guitar at the same time...]");
           // alert("F#...G...D...A");


Config:

Ext.define('SmartPhone', {
     config: {
         hasTouchScreen: false,
         operatingSystem: 'Other',
         price: 500
     },

     isExpensive: false,

     constructor: function(config) {
         this.initConfig(config);
     },

     applyPrice: function(price) {
         this.isExpensive = (price > 500);

         return price;
     },

     applyOperatingSystem: function(operatingSystem) {
         if (!(/^(iOS|Android|BlackBerry)$/i).test(operatingSystem)) {
             return 'Other';
         }

         return operatingSystem;
     }
});

var iPhone = new SmartPhone({
     hasTouchScreen: true,
     operatingSystem: 'iOS'
});

iPhone.getPrice(); // 500;
iPhone.getOperatingSystem(); // 'iOS'
iPhone.getHasTouchScreen(); // true;
iPhone.hasTouchScreen(); // true

iPhone.isExpensive; // false;
iPhone.setPrice(600);
iPhone.getPrice(); // 600
iPhone.isExpensive; // true;

iPhone.setOperatingSystem('AlienOS');
iPhone.getOperatingSystem(); // 'Other'


Statics:

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


Also see Ext.Base.statics and Ext.Base.self for more details on accessing
static properties within class methods

## Properties

### classes

**Tipo:** Object

All classes which were defined through the ClassManager. ...

All classes which were defined through the ClassManager. Keys are the
name of the classes and the values are references to the classes.
Defaults to: `{}`


### createdListeners

**Tipo:** Array

...

Defaults to: `[]`


### defaultPostprocessors

**Tipo:** Array

...

Defaults to: `[]`


### enableNamespaceParseCache

**Tipo:** Boolean

...

Defaults to: `true`


### existCache

**Tipo:** Object

...

Defaults to: `{}`


### instantiators

**Tipo:** Array

...

Defaults to: `[]`


### maps

**Tipo:** Object

...

Defaults to: `{alternateToName: {}, aliasToName: {}, nameToAliases: {}, nameToAlternates: {}}`


### nameCreatedListeners

**Tipo:** Object

...

Defaults to: `{}`


### namespaceParseCache

**Tipo:** Object

...

Defaults to: `{}`


### namespaceRewrites

**Tipo:** Object


### postprocessors

**Tipo:** Object

...

Defaults to: `{}`


### addNameAliasMappings

Adds a batch of class name to alias mappings ...

Adds a batch of class name to alias mappings
Parametersaliases : ObjectThe set of mappings of the form
className : [values...]


### addNameAlternateMappings

...

Parametersalternates : ObjectThe set of mappings of the form
className : [values...]


### create

Defines a class. ...

Defines a class.
        
        This method has been **deprecated** since 4.1.0
        Use Ext.define instead, as that also supports creating overrides.


### createNamespaces

The new Ext.ns, supports namespace rewriting ...

The new Ext.ns, supports namespace rewriting


### dynInstantiate

...

Parametersname : Object


### get

Retrieve a class by its name. ...

Retrieve a class by its name.
Parametersname : String


### getAliasesByName

Get the aliases of a class by the class name ...

Get the aliases of a class by the class name
Parametersname : String


### getByAlias

Get a reference to the class by its alias. ...

Get a reference to the class by its alias.
Parametersalias : String


### getClass

Get the class of the provided object; returns null if it's not an instance
of any class created with Ext.define. ...

Get the class of the provided object; returns null if it's not an instance
of any class created with Ext.define.

getClass is usually invoked by the shorthand Ext.getClass.

var component = new Ext.Component();

Ext.getClass(component); // returns Ext.Component

Parametersobject : Object


### getDisplayName

Returns the displayName property or className or object. ...

Returns the displayName property or className or object. When all else fails, returns "Anonymous".
Parametersobject : Object


### getInstantiator

...

Parameterslength : Object


### getName

Get the name of the class by its reference or its instance;

getName is usually invoked by the shorthand Ext.getClass...

Get the name of the class by its reference or its instance;

getName is usually invoked by the shorthand Ext.getClassName.

Ext.getName(Ext.Action); // returns "Ext.Action"

Parametersobject : Ext.Class/Object


### getNameByAlias

Get the name of a class by its alias. ...

Get the name of a class by its alias.
Parametersalias : String


### getNameByAlternate

Get the name of a class by its alternate name. ...

Get the name of a class by its alternate name.
Parametersalternate : String


### getNamesByExpression

Converts a string expression to an array of matching class names. ...

Converts a string expression to an array of matching class names. An expression can either refers to class aliases
or class names. Expressions support wildcards:

 // returns ['Ext.window.Window']
var window = Ext.ClassManager.getNamesByExpression('widget.window');

// returns ['widget.panel', 'widget.window', ...]
var allWidgets = Ext.ClassManager.getNamesByExpression('widget.*');

// returns ['Ext.data.Store', 'Ext.data.ArrayProxy', ...]
var allData = Ext.ClassManager.getNamesByExpression('Ext.data.*');

Parametersexpression : String


### instantiate

...


### instantiateByAlias

Instantiate a class by its alias. ...

Instantiate a class by its alias.

instantiateByAlias is usually invoked by the shorthand Ext.createByAlias.

If Ext.Loader is enabled and the class has not been defined yet, it will
attempt to load the class via synchronous loading.

var window = Ext.createByAlias('widget.window', { width: 600, height: 800, ... });

Parametersalias : String


### isCreated

Checks if a class has already been created. ...

Checks if a class has already been created.
ParametersclassName : String


### onCreated

...

Parametersfn : Object


### parseNamespace

Supports namespace rewriting ...

Supports namespace rewriting
Parametersnamespace : Object


### registerPostprocessor

Register a post-processor function. ...

Register a post-processor function.
Parametersname : String


### set

Sets a name reference to a class. ...

Sets a name reference to a class.
Parametersname : String


### setAlias

Register the alias for a class. ...

Register the alias for a class.
Parameterscls : Ext.Class/Stringa reference to a class or a className


### setDefaultPostprocessorPosition

Insert this post-processor at a specific position in the stack, optionally relative to
any existing post-processor ...

Insert this post-processor at a specific position in the stack, optionally relative to
any existing post-processor
Parametersname : StringThe post-processor name. Note that it needs to be registered with
registerPostprocessor before this


### setDefaultPostprocessors

Set the default post processors array stack which are applied to every class. ...

Set the default post processors array stack which are applied to every class.
Parameterspostprocessors : String/ArrayThe name of a registered post processor or an array of registered names.


### setNamespace

Creates a namespace and assign the value to the created object

Ext.ClassManager.setNamespace('MyCompany.pkg.Example'...

Creates a namespace and assign the `value` to the created object

Ext.ClassManager.setNamespace('MyCompany.pkg.Example', someObject);

alert(MyCompany.pkg.Example === someObject); // alerts true

Parametersname : String


### triggerCreated

...

ParametersclassName : Object


### undefine

Undefines a class defined using the #define method. ...

Undefines a class defined using the #define method. Typically used
for unit testing where setting up and tearing down a class multiple
times is required.  For example:

// define a class
Ext.define('Foo', {
   ...
});

// run test

// undefine the class
Ext.undefine('Foo');


@param {String} className The class name to undefine in string dot-namespaced format.
ParametersclassName : Object


## Methods

### addNameAliasMappings

Adds a batch of class name to alias mappings ...

Adds a batch of class name to alias mappings
Parametersaliases : ObjectThe set of mappings of the form
className : [values...]


### addNameAlternateMappings

...

Parametersalternates : ObjectThe set of mappings of the form
className : [values...]


### create

Defines a class. ...

Defines a class.
        
        This method has been **deprecated** since 4.1.0
        Use Ext.define instead, as that also supports creating overrides.


### createNamespaces

The new Ext.ns, supports namespace rewriting ...

The new Ext.ns, supports namespace rewriting


### dynInstantiate

...

Parametersname : Object


### get

Retrieve a class by its name. ...

Retrieve a class by its name.
Parametersname : String


### getAliasesByName

Get the aliases of a class by the class name ...

Get the aliases of a class by the class name
Parametersname : String


### getByAlias

Get a reference to the class by its alias. ...

Get a reference to the class by its alias.
Parametersalias : String


### getClass

Get the class of the provided object; returns null if it's not an instance
of any class created with Ext.define. ...

Get the class of the provided object; returns null if it's not an instance
of any class created with Ext.define.

getClass is usually invoked by the shorthand Ext.getClass.

var component = new Ext.Component();

Ext.getClass(component); // returns Ext.Component

Parametersobject : Object


### getDisplayName

Returns the displayName property or className or object. ...

Returns the displayName property or className or object. When all else fails, returns "Anonymous".
Parametersobject : Object


### getInstantiator

...

Parameterslength : Object


### getName

Get the name of the class by its reference or its instance;

getName is usually invoked by the shorthand Ext.getClass...

Get the name of the class by its reference or its instance;

getName is usually invoked by the shorthand Ext.getClassName.

Ext.getName(Ext.Action); // returns "Ext.Action"

Parametersobject : Ext.Class/Object


### getNameByAlias

Get the name of a class by its alias. ...

Get the name of a class by its alias.
Parametersalias : String


### getNameByAlternate

Get the name of a class by its alternate name. ...

Get the name of a class by its alternate name.
Parametersalternate : String


### getNamesByExpression

Converts a string expression to an array of matching class names. ...

Converts a string expression to an array of matching class names. An expression can either refers to class aliases
or class names. Expressions support wildcards:

 // returns ['Ext.window.Window']
var window = Ext.ClassManager.getNamesByExpression('widget.window');

// returns ['widget.panel', 'widget.window', ...]
var allWidgets = Ext.ClassManager.getNamesByExpression('widget.*');

// returns ['Ext.data.Store', 'Ext.data.ArrayProxy', ...]
var allData = Ext.ClassManager.getNamesByExpression('Ext.data.*');

Parametersexpression : String


### instantiate

...


### instantiateByAlias

Instantiate a class by its alias. ...

Instantiate a class by its alias.

instantiateByAlias is usually invoked by the shorthand Ext.createByAlias.

If Ext.Loader is enabled and the class has not been defined yet, it will
attempt to load the class via synchronous loading.

var window = Ext.createByAlias('widget.window', { width: 600, height: 800, ... });

Parametersalias : String


### isCreated

Checks if a class has already been created. ...

Checks if a class has already been created.
ParametersclassName : String


### onCreated

...

Parametersfn : Object


### parseNamespace

Supports namespace rewriting ...

Supports namespace rewriting
Parametersnamespace : Object


### registerPostprocessor

Register a post-processor function. ...

Register a post-processor function.
Parametersname : String


### set

Sets a name reference to a class. ...

Sets a name reference to a class.
Parametersname : String


### setAlias

Register the alias for a class. ...

Register the alias for a class.
Parameterscls : Ext.Class/Stringa reference to a class or a className


### setDefaultPostprocessorPosition

Insert this post-processor at a specific position in the stack, optionally relative to
any existing post-processor ...

Insert this post-processor at a specific position in the stack, optionally relative to
any existing post-processor
Parametersname : StringThe post-processor name. Note that it needs to be registered with
registerPostprocessor before this


### setDefaultPostprocessors

Set the default post processors array stack which are applied to every class. ...

Set the default post processors array stack which are applied to every class.
Parameterspostprocessors : String/ArrayThe name of a registered post processor or an array of registered names.


### setNamespace

Creates a namespace and assign the value to the created object

Ext.ClassManager.setNamespace('MyCompany.pkg.Example'...

Creates a namespace and assign the `value` to the created object

Ext.ClassManager.setNamespace('MyCompany.pkg.Example', someObject);

alert(MyCompany.pkg.Example === someObject); // alerts true

Parametersname : String


### triggerCreated

...

ParametersclassName : Object


### undefine

Undefines a class defined using the #define method. ...

Undefines a class defined using the #define method. Typically used
for unit testing where setting up and tearing down a class multiple
times is required.  For example:

// define a class
Ext.define('Foo', {
   ...
});

// run test

// undefine the class
Ext.undefine('Foo');


@param {String} className The class name to undefine in string dot-namespaced format.
ParametersclassName : Object


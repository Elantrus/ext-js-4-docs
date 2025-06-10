# Ext.XTemplate

**Extends:** Ext.Template

## Descrição

A template class that supports advanced functionality like:

XTemplate provides the templating mechanism built into Ext.view.View.

The Ext.Template describes the acceptable parameters to pass to the constructor. The following examples
demonstrate all of the supported features.

This is the data object used for reference in each code example:

var data = {
    name: 'Don Griffin',
    title: 'Senior Technomage',
    company: 'Sencha Inc.',
    drinks: ['Coffee', 'Water', 'More Coffee'],
    kids: [
        { name: 'Aubrey',  age: 17 },
        { name: 'Joshua',  age: 13 },
        { name: 'Cale',    age: 10 },
        { name: 'Nikol',   age: 5 },
        { name: 'Solomon', age: 0 }
    ]
};


Auto filling of arrays

The **tpl** tag and the **for** operator are used to process the provided data object:

Examples:

<tpl for=".">...</tpl>       // loop through array at root node
<tpl for="foo">...</tpl>     // loop through array at foo node
<tpl for="foo.bar">...</tpl> // loop through array at foo.bar node
<tpl for="." between=",">...</tpl> // loop through array at root node and insert ',' between each item


Using the sample data above:

var tpl = new Ext.XTemplate(
    '<p>Kids: ',
    '<tpl for=".">',       // process the data.kids node
        '<p>{#}. {name}</p>',  // use current array index to autonumber
    '</tpl></p>'
);
tpl.overwrite(panel.body, data.kids); // pass the kids property of the data object


An example illustrating how the **for** property can be leveraged to access specified members of the provided data
object to populate the template:

var tpl = new Ext.XTemplate(
    '<p>Name: {name}</p>',
    '<p>Title: {title}</p>',
    '<p>Company: {company}</p>',
    '<p>Kids: ',
    '<tpl for="kids">',     // interrogate the kids property within the data
        '<p>{name}</p>',
    '</tpl></p>'
);
tpl.overwrite(panel.body, data);  // pass the root node of the data object


Flat arrays that contain values (and not objects) can be auto-rendered using the special **`{.}`** variable inside a
loop. This variable will represent the value of the array at the current index:

var tpl = new Ext.XTemplate(
    '<p>{name}\'s favorite beverages:</p>',
    '<tpl for="drinks">',
        '<div> - {.}</div>',
    '</tpl>'
);
tpl.overwrite(panel.body, data);


When processing a sub-template, for example while looping through a child array, you can access the parent object's
members via the **parent** object:

var tpl = new Ext.XTemplate(
    '<p>Name: {name}</p>',
    '<p>Kids: ',
    '<tpl for="kids">',
        '<tpl if="age &gt; 1">',
            '<p>{name}</p>',
            '<p>Dad: {parent.name}</p>',
        '</tpl>',
    '</tpl></p>'
);
tpl.overwrite(panel.body, data);


The **foreach** operator is used to loop over an object's properties.  The following
example demonstrates looping over the main data object's properties:

var tpl = new Ext.XTemplate(
    '<dl>',
        '<tpl foreach=".">',
            '<dt>{$}</dt>', // the special **`{$}`** variable contains the property name
            '<dd>{.}</dd>', // within the loop, the **`{.}`** variable is set to the property value
        '</tpl>',
    '</dl>'
);
tpl.overwrite(panel.body, data);


Conditional processing with basic comparison operators

The **tpl** tag and the **if** operator are used to provide conditional checks for deciding whether or not to render
specific parts of the template.

Using the sample data above:

var tpl = new Ext.XTemplate(
    '<p>Name: {name}</p>',
    '<p>Kids: ',
    '<tpl for="kids">',
        '<tpl if="age &gt; 1">',
            '<p>{name}</p>',
        '</tpl>',
    '</tpl></p>'
);
tpl.overwrite(panel.body, data);


More advanced conditionals are also supported:

var tpl = new Ext.XTemplate(
    '<p>Name: {name}</p>',
    '<p>Kids: ',
    '<tpl for="kids">',
        '<p>{name} is a ',
        '<tpl if="age &gt;= 13">',
            '<p>teenager</p>',
        '<tpl elseif="age &gt;= 2">',
            '<p>kid</p>',
        '<tpl else>',
            '<p>baby</p>',
        '</tpl>',
    '</tpl></p>'
);

var tpl = new Ext.XTemplate(
    '<p>Name: {name}</p>',
    '<p>Kids: ',
    '<tpl for="kids">',
        '<p>{name} is a ',
        '<tpl switch="name">',
            '<tpl case="Aubrey" case="Nikol">',
                '<p>girl</p>',
            '<tpl default>',
                '<p>boy</p>',
        '</tpl>',
    '</tpl></p>'
);


A `break` is implied between each case and default, however, multiple cases can be listed
in a single <tpl> tag.

Examples:

+ - * /


For example:

var tpl = new Ext.XTemplate(
    '<p>Name: {name}</p>',
    '<p>Kids: ',
    '<tpl for="kids">',
        '<tpl if="age &gt; 1">',  // <-- Note that the > is encoded
            '<p>{#}: {name}</p>',  // <-- Auto-number each item
            '<p>In 5 Years: {age+5}</p>',  // <-- Basic math
            '<p>Dad: {parent.name}</p>',
        '</tpl>',
    '</tpl></p>'
);
tpl.overwrite(panel.body, data);


Execute arbitrary inline code with special built-in template variables

Anything between `{[ ... ]}` is considered code to be executed in the scope of the template.
The expression is evaluated and the result is included in the generated result. There are
some special variables available in that code:

This example demonstrates basic row striping using an inline code block and the xindex variable:

var tpl = new Ext.XTemplate(
    '<p>Name: {name}</p>',
    '<p>Company: {[values.company.toUpperCase() + ", " + values.title]}</p>',
    '<p>Kids: ',
    '<tpl for="kids">',
        '<div class="{[xindex % 2 === 0 ? "even" : "odd"]}">',
        '{name}',
        '</div>',
    '</tpl></p>'
 );


Any code contained in "verbatim" blocks (using "{% ... %}") will be inserted directly in
the generated code for the template. These blocks are not included in the output. This
can be used for simple things like break/continue in a loop, or control structures or
method calls (when they don't produce output). The `this` references the template instance.

var tpl = new Ext.XTemplate(
    '<p>Name: {name}</p>',
    '<p>Company: {[values.company.toUpperCase() + ", " + values.title]}</p>',
    '<p>Kids: ',
    '<tpl for="kids">',
        '{% if (xindex % 2 === 0) continue; %}',
        '{name}',
        '{% if (xindex > 100) break; %}',
        '</div>',
    '</tpl></p>'
 );


Template member functions

One or more member functions can be specified in a configuration object passed into the XTemplate constructor for
more complex processing:

## Config options

### definitions

**Tipo:** String/Array

Optional. ...

Optional. A statement, or array of statements which set up `var`s which may then
be accessed within the scope of the generated function.


### disableFormats

**Tipo:** Boolean

True to disable format functions in the template. ...

True to disable format functions in the template. If the template doesn't contain
format functions, setting disableFormats to true will reduce apply time. Defaults to false.
Defaults to: `false`


### $className

**Tipo:** String

...

Defaults to: `'Ext.Base'`


### compileARe

**Tipo:** RegExp

...

Defaults to: `/\\/g`


### compileBRe

**Tipo:** RegExp

...

Defaults to: `/(\r\n|\n)/g`


### compileCRe

**Tipo:** RegExp

...

Defaults to: `/'/g`


### configMap

**Tipo:** Object

...

Defaults to: `{}`


### emptyObj

**Tipo:** Object

...

Defaults to: `{}`


### initConfigList

**Tipo:** Array

...

Defaults to: `[]`


### initConfigMap

**Tipo:** Object

...

Defaults to: `{}`


### isInstance

**Tipo:** Boolean

...

Defaults to: `true`


### isTemplate

**Tipo:** Boolean

true in this class to identify an object as an instantiated Template, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Template, or subclass thereof.
Defaults to: `true`


### re

**Tipo:** RegExp

...

Defaults to: `/\{([\w\-]+)(?:\:([\w\.]*)(?:\((.*?)?\))?)?\}/g`


### self

**Tipo:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics,
`this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics
for a detailed comparison

Ext.define('My.Cat', {
    statics: {
        speciesName: 'Cat' // My.Cat.speciesName = 'Cat'
    },

    constructor: function() {
        alert(this.self.speciesName); // dependent on 'this'
    },

    clone: function() {
        return new this.self();
    }
});


Ext.define('My.SnowLeopard', {
    extend: 'My.Cat',
    statics: {
        speciesName: 'Snow Leopard'         // My.SnowLeopard.speciesName = 'Snow Leopard'
    }
});

var cat = new My.Cat();                     // alerts 'Cat'
var snowLeopard = new My.SnowLeopard();     // alerts 'Snow Leopard'

var clone = snowLeopard.clone();
alert(Ext.getClassName(clone));             // alerts 'My.SnowLeopard'


### $onExtended

**Tipo:** Array

...

Defaults to: `[]`


### Ext.XTemplate

Creates new template. ...

Creates new template.
Parametershtml : String...List of strings to be concatenated into template.
Alternatively an array of strings can be given, but then no config object may be passed.


### append

Applies the supplied values to the template and appends the new node(s) to the specified el. ...

Applies the supplied `values` to the template and appends the new node(s) to the specified `el`.

For example usage see Ext.Template class docs.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### apply

Returns an HTML fragment of this template with the specified values applied. ...

Returns an HTML fragment of this template with the specified values applied.
Parametersvalues : Object/ArrayThe template values. Can be an array if your params are numeric:




var tpl = new Ext.Template('Name: {0}, Age: {1}');
tpl.apply(['John', 25]);





or an object:




var tpl = new Ext.Template('Name: {name}, Age: {age}');
tpl.apply({name: 'John', age: 25});


### applyOut

Appends the result of this template to the provided output array. ...

Appends the result of this template to the provided output array.
Parametersvalues : Object/ArrayThe template values. See apply.


### applyTemplate

Alias for apply. ...

Alias for apply.

Returns an HTML fragment of this template with the specified values applied.
Parametersvalues : Object/ArrayThe template values. Can be an array if your params are numeric:




var tpl = new Ext.Template('Name: {0}, Age: {1}');
tpl.apply(['John', 25]);





or an object:




var tpl = new Ext.Template('Name: {name}, Age: {age}');
tpl.apply({name: 'John', age: 25});


### callOverridden

Call the original method that was previously overridden with override

Ext.define('My.Cat', {
    constructor: functi...

Call the original method that was previously overridden with override

Ext.define('My.Cat', {
    constructor: function() {
        alert("I'm a cat!");
    }
});

My.Cat.override({
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callOverridden();

        alert("Meeeeoooowwww");
    }
});

var kitty = new My.Cat(); // alerts "I'm going to be a cat!"
                          // alerts "I'm a cat!"
                          // alerts "Meeeeoooowwww"

        
        This method has been **deprecated** 
        as of 4.1. Use callParent instead.


### callParent

Call the "parent" method of the current method. ...

Call the "parent" method of the current method. That is the method previously
overridden by derivation or by an override (see Ext.define).

 Ext.define('My.Base', {
     constructor: function (x) {
         this.x = x;
     },

     statics: {
         method: function (x) {
             return x;
         }
     }
 });

 Ext.define('My.Derived', {
     extend: 'My.Base',

     constructor: function () {
         this.callParent([21]);
     }
 });

 var obj = new My.Derived();

 alert(obj.x);  // alerts 21


This can be used with an override as follows:

 Ext.define('My.DerivedOverride', {
     override: 'My.Derived',

     constructor: function (x) {
         this.callParent([x*2]); // calls original My.Derived constructor
     }
 });

 var obj = new My.Derived();

 alert(obj.x);  // now alerts 42


This also works with static methods.

 Ext.define('My.Derived2', {
     extend: 'My.Base',

     statics: {
         method: function (x) {
             return this.callParent([x*2]); // calls My.Base.method
         }
     }
 });

 alert(My.Base.method(10);     // alerts 10
 alert(My.Derived2.method(10); // alerts 20


Lastly, it also works with overridden static methods.

 Ext.define('My.Derived2Override', {
     override: 'My.Derived2',

     statics: {
         method: function (x) {
             return this.callParent([x*2]); // calls My.Derived2.method
         }
     }
 });

 alert(My.Derived2.method(10); // now alerts 40


To override a method and replace it and also call the superclass method, use
callSuper. This is often done to patch a method to fix a bug.
Parametersargs : Array/ArgumentsThe arguments, either an array or the `arguments` object
from the current method, for example: `this.callParent(arguments)`


### callSuper

This method is used by an override to call the superclass method but bypass any
overridden method. ...

This method is used by an override to call the superclass method but bypass any
overridden method. This is often done to "patch" a method that contains a bug
but for whatever reason cannot be fixed directly.

Consider:

 Ext.define('Ext.some.Class', {
     method: function () {
         console.log('Good');
     }
 });

 Ext.define('Ext.some.DerivedClass', {
     method: function () {
         console.log('Bad');

         // ... logic but with a bug ...

         this.callParent();
     }
 });


To patch the bug in `DerivedClass.method`, the typical solution is to create an
override:

 Ext.define('App.paches.DerivedClass', {
     override: 'Ext.some.DerivedClass',

     method: function () {
         console.log('Fixed');

         // ... logic but with bug fixed ...

         this.callSuper();
     }
 });


The patch method cannot use `callParent` to call the superclass `method` since
that would call the overridden method containing the bug. In other words, the
above patch would only produce "Fixed" then "Good" in the console log, whereas,
using `callParent` would produce "Fixed" then "Bad" then "Good".
Parametersargs : Array/ArgumentsThe arguments, either an array or the `arguments` object
from the current method, for example: `this.callSuper(arguments)`


### compile

Does nothing. ...

Does nothing. XTemplates are compiled automatically, so this function simply returns this.
ReturnsExt.XTemplatethis


### configClass

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### doInsert

...

Parameterswhere : Object


### getConfig

...

Parametersname : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### hasConfig

...

Parametersconfig : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

Ext.define('My.awesome.Class', {
    // The default config
    config: {
        name: 'Awesome',
        isAwesome: true
    },

    constructor: function(config) {
        this.initConfig(config);
    }
});

var awesome = new My.awesome.Class({
    name: 'Super Awesome'
});

alert(awesome.getName()); // 'Super Awesome'

Parametersconfig : Object


### insertAfter

Applies the supplied values to the template and inserts the new node(s) after el. ...

Applies the supplied values to the template and inserts the new node(s) after el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### insertBefore

Applies the supplied values to the template and inserts the new node(s) before el. ...

Applies the supplied values to the template and inserts the new node(s) before el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### insertFirst

Applies the supplied values to the template and inserts the new node(s) as the first child of el. ...

Applies the supplied values to the template and inserts the new node(s) as the first child of el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### onConfigUpdate

...

Parametersnames : Object


### overwrite

Applies the supplied values to the template and overwrites the content of el with the new node(s). ...

Applies the supplied values to the template and overwrites the content of el with the new node(s).
Parametersel : String/HTMLElement/Ext.ElementThe context element


### set

Sets the HTML used as the template and optionally compiles it. ...

Sets the HTML used as the template and optionally compiles it.
Parametershtml : String


### setConfig

...

Parametersconfig : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self,
`this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what
`this` points to during run-time

Ext.define('My.Cat', {
    statics: {
        totalCreated: 0,
        speciesName: 'Cat' // My.Cat.speciesName = 'Cat'
    },

    constructor: function() {
        var statics = this.statics();

        alert(statics.speciesName);     // always equals to 'Cat' no matter what 'this' refers to
                                        // equivalent to: My.Cat.speciesName

        alert(this.self.speciesName);   // dependent on 'this'

        statics.totalCreated++;
    },

    clone: function() {
        var cloned = new this.self;                      // dependent on 'this'

        cloned.groupName = this.statics().speciesName;   // equivalent to: My.Cat.speciesName

        return cloned;
    }
});


Ext.define('My.SnowLeopard', {
    extend: 'My.Cat',

    statics: {
        speciesName: 'Snow Leopard'     // My.SnowLeopard.speciesName = 'Snow Leopard'
    },

    constructor: function() {
        this.callParent();
    }
});

var cat = new My.Cat();                 // alerts 'Cat', then alerts 'Cat'

var snowLeopard = new My.SnowLeopard(); // alerts 'Cat', then alerts 'Snow Leopard'

var clone = snowLeopard.clone();
alert(Ext.getClassName(clone));         // alerts 'My.SnowLeopard'
alert(clone.groupName);                 // alerts 'Cat'

alert(My.Cat.totalCreated);             // alerts 3

ReturnsExt.Class


### addConfig

...

Parametersconfig : Object


### addInheritableStatics

...

Parametersmembers : Object


### addMember

...

Parametersname : Object


### addMembers

Add methods / properties to the prototype of this class. ...

Add methods / properties to the prototype of this class.

Ext.define('My.awesome.Cat', {
    constructor: function() {
        ...
    }
});

 My.awesome.Cat.addMembers({
     meow: function() {
        alert('Meowww...');
     }
 });

 var kitty = new My.awesome.Cat;
 kitty.meow();

Parametersmembers : Object


### addStatics

Add / override static properties of this class. ...

Add / override static properties of this class.

Ext.define('My.cool.Class', {
    ...
});

My.cool.Class.addStatics({
    someProperty: 'someValue',      // My.cool.Class.someProperty = 'someValue'
    method1: function() { ... },    // My.cool.Class.method1 = function() { ... };
    method2: function() { ... }     // My.cool.Class.method2 = function() { ... };
});

Parametersmembers : Object


### addXtype

...

Parametersxtype : Object


### borrow

Borrow another class' members to the prototype of this class. ...

Borrow another class' members to the prototype of this class.

Ext.define('Bank', {
    money: '$$$',
    printMoney: function() {
        alert('$$$$$$$');
    }
});

Ext.define('Thief', {
    ...
});

Thief.borrow(Bank, ['money', 'printMoney']);

var steve = new Thief();

alert(steve.money); // alerts '$$$'
steve.printMoney(); // alerts '$$$$$$$'

ParametersfromClass : Ext.BaseThe class to borrow members from


### create

Create a new instance of this Class. ...

Create a new instance of this Class.

Ext.define('My.cool.Class', {
    ...
});

My.cool.Class.create({
    someConfig: true
});


All parameters are passed to the constructor of the class.
ReturnsObjectthe created instance.


### createAlias

Create aliases for existing prototype methods. ...

Create aliases for existing prototype methods. Example:

Ext.define('My.cool.Class', {
    method1: function() { ... },
    method2: function() { ... }
});

var test = new My.cool.Class();

My.cool.Class.createAlias({
    method3: 'method1',
    method4: 'method2'
});

test.method3(); // test.method1()

My.cool.Class.createAlias('method5', 'method3');

test.method5(); // test.method3() -> test.method1()

Parametersalias : String/ObjectThe new method name, or an object to set multiple aliases. See
flexSetter


### extend

...

Parametersconfig : Object


### from

Creates a template from the passed element's value (display:none textarea, preferred) or innerHTML. ...

Creates a template from the passed element's value (*display:none* textarea, preferred) or innerHTML.
Parametersel : String/HTMLElementA DOM element or its id


### getName

Get the current class' name in string format. ...

Get the current class' name in string format.

Ext.define('My.cool.Class', {
    constructor: function() {
        alert(this.self.getName()); // alerts 'My.cool.Class'
    }
});

My.cool.Class.getName(); // 'My.cool.Class'

ReturnsStringclassName


### getTpl

Gets an XTemplate from an object (an instance of an Ext.define'd class). ...

Gets an `XTemplate` from an object (an instance of an Ext.define'd class).
Many times, templates are configured high in the class hierarchy and are to be
shared by all classes that derive from that base. To further complicate matters,
these templates are seldom actual instances but are rather configurations. For
example:

 Ext.define('MyApp.Class', {
     extraCls: 'extra-class',

     someTpl: [
         '<div class="{%this.emitClass(out)%}"></div>',
     {
         // Member fn - outputs the owing class's extra CSS class
         emitClass: function(out) {
             out.push(this.owner.extraCls);
         }
     }]
 });


The goal being to share that template definition with all instances and even
instances of derived classes, until `someTpl` is overridden. This method will
"upgrade" these configurations to be real `XTemplate` instances *in place* (to
avoid creating one instance per object).

The resulting XTemplate will have an `owner` reference injected which refers back
to the owning object whether that is an object which has an *own instance*, or a
class prototype. Through this link, XTemplate member functions will be able to access
prototype properties of its owning class.
Parametersinstance : ObjectThe object from which to get the `XTemplate` (must be
an instance of an Ext.define'd class).


### implement

Adds members to class. ...

Adds members to class.
        
        This method has been **deprecated** since 4.1
        Use addMembers instead.


### mixin

Used internally by the mixins pre-processor ...

Used internally by the mixins pre-processor
Parametersname : Object


### onExtended

...

Parametersfn : Object


### override

Override members of this class. ...

Override members of this class. Overridden methods can be invoked via
callParent.

Ext.define('My.Cat', {
    constructor: function() {
        alert("I'm a cat!");
    }
});

My.Cat.override({
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callParent(arguments);

        alert("Meeeeoooowwww");
    }
});

var kitty = new My.Cat(); // alerts "I'm going to be a cat!"
                          // alerts "I'm a cat!"
                          // alerts "Meeeeoooowwww"


As of 4.1, direct use of this method is deprecated. Use Ext.define
instead:

Ext.define('My.CatOverride', {
    override: 'My.Cat',
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callParent(arguments);

        alert("Meeeeoooowwww");
    }
});


The above accomplishes the same result but can be managed by the Ext.Loader
which can properly order the override and its target class and the build process
can determine whether the override is needed based on the required state of the
target class (My.Cat).
        
        This method has been **deprecated** since 4.1.0
        Use Ext.define instead


### triggerExtended

...


## Properties

### $className

**Tipo:** String

...

Defaults to: `'Ext.Base'`


### compileARe

**Tipo:** RegExp

...

Defaults to: `/\\/g`


### compileBRe

**Tipo:** RegExp

...

Defaults to: `/(\r\n|\n)/g`


### compileCRe

**Tipo:** RegExp

...

Defaults to: `/'/g`


### configMap

**Tipo:** Object

...

Defaults to: `{}`


### emptyObj

**Tipo:** Object

...

Defaults to: `{}`


### initConfigList

**Tipo:** Array

...

Defaults to: `[]`


### initConfigMap

**Tipo:** Object

...

Defaults to: `{}`


### isInstance

**Tipo:** Boolean

...

Defaults to: `true`


### isTemplate

**Tipo:** Boolean

true in this class to identify an object as an instantiated Template, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Template, or subclass thereof.
Defaults to: `true`


### re

**Tipo:** RegExp

...

Defaults to: `/\{([\w\-]+)(?:\:([\w\.]*)(?:\((.*?)?\))?)?\}/g`


### self

**Tipo:** Ext.Class

Get the reference to the current class from which this object was instantiated. ...

Get the reference to the current class from which this object was instantiated. Unlike statics,
`this.self` is scope-dependent and it's meant to be used for dynamic inheritance. See statics
for a detailed comparison

Ext.define('My.Cat', {
    statics: {
        speciesName: 'Cat' // My.Cat.speciesName = 'Cat'
    },

    constructor: function() {
        alert(this.self.speciesName); // dependent on 'this'
    },

    clone: function() {
        return new this.self();
    }
});


Ext.define('My.SnowLeopard', {
    extend: 'My.Cat',
    statics: {
        speciesName: 'Snow Leopard'         // My.SnowLeopard.speciesName = 'Snow Leopard'
    }
});

var cat = new My.Cat();                     // alerts 'Cat'
var snowLeopard = new My.SnowLeopard();     // alerts 'Snow Leopard'

var clone = snowLeopard.clone();
alert(Ext.getClassName(clone));             // alerts 'My.SnowLeopard'


### $onExtended

**Tipo:** Array

...

Defaults to: `[]`


### Ext.XTemplate

Creates new template. ...

Creates new template.
Parametershtml : String...List of strings to be concatenated into template.
Alternatively an array of strings can be given, but then no config object may be passed.


### append

Applies the supplied values to the template and appends the new node(s) to the specified el. ...

Applies the supplied `values` to the template and appends the new node(s) to the specified `el`.

For example usage see Ext.Template class docs.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### apply

Returns an HTML fragment of this template with the specified values applied. ...

Returns an HTML fragment of this template with the specified values applied.
Parametersvalues : Object/ArrayThe template values. Can be an array if your params are numeric:




var tpl = new Ext.Template('Name: {0}, Age: {1}');
tpl.apply(['John', 25]);





or an object:




var tpl = new Ext.Template('Name: {name}, Age: {age}');
tpl.apply({name: 'John', age: 25});


### applyOut

Appends the result of this template to the provided output array. ...

Appends the result of this template to the provided output array.
Parametersvalues : Object/ArrayThe template values. See apply.


### applyTemplate

Alias for apply. ...

Alias for apply.

Returns an HTML fragment of this template with the specified values applied.
Parametersvalues : Object/ArrayThe template values. Can be an array if your params are numeric:




var tpl = new Ext.Template('Name: {0}, Age: {1}');
tpl.apply(['John', 25]);





or an object:




var tpl = new Ext.Template('Name: {name}, Age: {age}');
tpl.apply({name: 'John', age: 25});


### callOverridden

Call the original method that was previously overridden with override

Ext.define('My.Cat', {
    constructor: functi...

Call the original method that was previously overridden with override

Ext.define('My.Cat', {
    constructor: function() {
        alert("I'm a cat!");
    }
});

My.Cat.override({
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callOverridden();

        alert("Meeeeoooowwww");
    }
});

var kitty = new My.Cat(); // alerts "I'm going to be a cat!"
                          // alerts "I'm a cat!"
                          // alerts "Meeeeoooowwww"

        
        This method has been **deprecated** 
        as of 4.1. Use callParent instead.


### callParent

Call the "parent" method of the current method. ...

Call the "parent" method of the current method. That is the method previously
overridden by derivation or by an override (see Ext.define).

 Ext.define('My.Base', {
     constructor: function (x) {
         this.x = x;
     },

     statics: {
         method: function (x) {
             return x;
         }
     }
 });

 Ext.define('My.Derived', {
     extend: 'My.Base',

     constructor: function () {
         this.callParent([21]);
     }
 });

 var obj = new My.Derived();

 alert(obj.x);  // alerts 21


This can be used with an override as follows:

 Ext.define('My.DerivedOverride', {
     override: 'My.Derived',

     constructor: function (x) {
         this.callParent([x*2]); // calls original My.Derived constructor
     }
 });

 var obj = new My.Derived();

 alert(obj.x);  // now alerts 42


This also works with static methods.

 Ext.define('My.Derived2', {
     extend: 'My.Base',

     statics: {
         method: function (x) {
             return this.callParent([x*2]); // calls My.Base.method
         }
     }
 });

 alert(My.Base.method(10);     // alerts 10
 alert(My.Derived2.method(10); // alerts 20


Lastly, it also works with overridden static methods.

 Ext.define('My.Derived2Override', {
     override: 'My.Derived2',

     statics: {
         method: function (x) {
             return this.callParent([x*2]); // calls My.Derived2.method
         }
     }
 });

 alert(My.Derived2.method(10); // now alerts 40


To override a method and replace it and also call the superclass method, use
callSuper. This is often done to patch a method to fix a bug.
Parametersargs : Array/ArgumentsThe arguments, either an array or the `arguments` object
from the current method, for example: `this.callParent(arguments)`


### callSuper

This method is used by an override to call the superclass method but bypass any
overridden method. ...

This method is used by an override to call the superclass method but bypass any
overridden method. This is often done to "patch" a method that contains a bug
but for whatever reason cannot be fixed directly.

Consider:

 Ext.define('Ext.some.Class', {
     method: function () {
         console.log('Good');
     }
 });

 Ext.define('Ext.some.DerivedClass', {
     method: function () {
         console.log('Bad');

         // ... logic but with a bug ...

         this.callParent();
     }
 });


To patch the bug in `DerivedClass.method`, the typical solution is to create an
override:

 Ext.define('App.paches.DerivedClass', {
     override: 'Ext.some.DerivedClass',

     method: function () {
         console.log('Fixed');

         // ... logic but with bug fixed ...

         this.callSuper();
     }
 });


The patch method cannot use `callParent` to call the superclass `method` since
that would call the overridden method containing the bug. In other words, the
above patch would only produce "Fixed" then "Good" in the console log, whereas,
using `callParent` would produce "Fixed" then "Bad" then "Good".
Parametersargs : Array/ArgumentsThe arguments, either an array or the `arguments` object
from the current method, for example: `this.callSuper(arguments)`


### compile

Does nothing. ...

Does nothing. XTemplates are compiled automatically, so this function simply returns this.
ReturnsExt.XTemplatethis


### configClass

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### doInsert

...

Parameterswhere : Object


### getConfig

...

Parametersname : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### hasConfig

...

Parametersconfig : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

Ext.define('My.awesome.Class', {
    // The default config
    config: {
        name: 'Awesome',
        isAwesome: true
    },

    constructor: function(config) {
        this.initConfig(config);
    }
});

var awesome = new My.awesome.Class({
    name: 'Super Awesome'
});

alert(awesome.getName()); // 'Super Awesome'

Parametersconfig : Object


### insertAfter

Applies the supplied values to the template and inserts the new node(s) after el. ...

Applies the supplied values to the template and inserts the new node(s) after el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### insertBefore

Applies the supplied values to the template and inserts the new node(s) before el. ...

Applies the supplied values to the template and inserts the new node(s) before el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### insertFirst

Applies the supplied values to the template and inserts the new node(s) as the first child of el. ...

Applies the supplied values to the template and inserts the new node(s) as the first child of el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### onConfigUpdate

...

Parametersnames : Object


### overwrite

Applies the supplied values to the template and overwrites the content of el with the new node(s). ...

Applies the supplied values to the template and overwrites the content of el with the new node(s).
Parametersel : String/HTMLElement/Ext.ElementThe context element


### set

Sets the HTML used as the template and optionally compiles it. ...

Sets the HTML used as the template and optionally compiles it.
Parametershtml : String


### setConfig

...

Parametersconfig : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self,
`this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what
`this` points to during run-time

Ext.define('My.Cat', {
    statics: {
        totalCreated: 0,
        speciesName: 'Cat' // My.Cat.speciesName = 'Cat'
    },

    constructor: function() {
        var statics = this.statics();

        alert(statics.speciesName);     // always equals to 'Cat' no matter what 'this' refers to
                                        // equivalent to: My.Cat.speciesName

        alert(this.self.speciesName);   // dependent on 'this'

        statics.totalCreated++;
    },

    clone: function() {
        var cloned = new this.self;                      // dependent on 'this'

        cloned.groupName = this.statics().speciesName;   // equivalent to: My.Cat.speciesName

        return cloned;
    }
});


Ext.define('My.SnowLeopard', {
    extend: 'My.Cat',

    statics: {
        speciesName: 'Snow Leopard'     // My.SnowLeopard.speciesName = 'Snow Leopard'
    },

    constructor: function() {
        this.callParent();
    }
});

var cat = new My.Cat();                 // alerts 'Cat', then alerts 'Cat'

var snowLeopard = new My.SnowLeopard(); // alerts 'Cat', then alerts 'Snow Leopard'

var clone = snowLeopard.clone();
alert(Ext.getClassName(clone));         // alerts 'My.SnowLeopard'
alert(clone.groupName);                 // alerts 'Cat'

alert(My.Cat.totalCreated);             // alerts 3

ReturnsExt.Class


### addConfig

...

Parametersconfig : Object


### addInheritableStatics

...

Parametersmembers : Object


### addMember

...

Parametersname : Object


### addMembers

Add methods / properties to the prototype of this class. ...

Add methods / properties to the prototype of this class.

Ext.define('My.awesome.Cat', {
    constructor: function() {
        ...
    }
});

 My.awesome.Cat.addMembers({
     meow: function() {
        alert('Meowww...');
     }
 });

 var kitty = new My.awesome.Cat;
 kitty.meow();

Parametersmembers : Object


### addStatics

Add / override static properties of this class. ...

Add / override static properties of this class.

Ext.define('My.cool.Class', {
    ...
});

My.cool.Class.addStatics({
    someProperty: 'someValue',      // My.cool.Class.someProperty = 'someValue'
    method1: function() { ... },    // My.cool.Class.method1 = function() { ... };
    method2: function() { ... }     // My.cool.Class.method2 = function() { ... };
});

Parametersmembers : Object


### addXtype

...

Parametersxtype : Object


### borrow

Borrow another class' members to the prototype of this class. ...

Borrow another class' members to the prototype of this class.

Ext.define('Bank', {
    money: '$$$',
    printMoney: function() {
        alert('$$$$$$$');
    }
});

Ext.define('Thief', {
    ...
});

Thief.borrow(Bank, ['money', 'printMoney']);

var steve = new Thief();

alert(steve.money); // alerts '$$$'
steve.printMoney(); // alerts '$$$$$$$'

ParametersfromClass : Ext.BaseThe class to borrow members from


### create

Create a new instance of this Class. ...

Create a new instance of this Class.

Ext.define('My.cool.Class', {
    ...
});

My.cool.Class.create({
    someConfig: true
});


All parameters are passed to the constructor of the class.
ReturnsObjectthe created instance.


### createAlias

Create aliases for existing prototype methods. ...

Create aliases for existing prototype methods. Example:

Ext.define('My.cool.Class', {
    method1: function() { ... },
    method2: function() { ... }
});

var test = new My.cool.Class();

My.cool.Class.createAlias({
    method3: 'method1',
    method4: 'method2'
});

test.method3(); // test.method1()

My.cool.Class.createAlias('method5', 'method3');

test.method5(); // test.method3() -> test.method1()

Parametersalias : String/ObjectThe new method name, or an object to set multiple aliases. See
flexSetter


### extend

...

Parametersconfig : Object


### from

Creates a template from the passed element's value (display:none textarea, preferred) or innerHTML. ...

Creates a template from the passed element's value (*display:none* textarea, preferred) or innerHTML.
Parametersel : String/HTMLElementA DOM element or its id


### getName

Get the current class' name in string format. ...

Get the current class' name in string format.

Ext.define('My.cool.Class', {
    constructor: function() {
        alert(this.self.getName()); // alerts 'My.cool.Class'
    }
});

My.cool.Class.getName(); // 'My.cool.Class'

ReturnsStringclassName


### getTpl

Gets an XTemplate from an object (an instance of an Ext.define'd class). ...

Gets an `XTemplate` from an object (an instance of an Ext.define'd class).
Many times, templates are configured high in the class hierarchy and are to be
shared by all classes that derive from that base. To further complicate matters,
these templates are seldom actual instances but are rather configurations. For
example:

 Ext.define('MyApp.Class', {
     extraCls: 'extra-class',

     someTpl: [
         '<div class="{%this.emitClass(out)%}"></div>',
     {
         // Member fn - outputs the owing class's extra CSS class
         emitClass: function(out) {
             out.push(this.owner.extraCls);
         }
     }]
 });


The goal being to share that template definition with all instances and even
instances of derived classes, until `someTpl` is overridden. This method will
"upgrade" these configurations to be real `XTemplate` instances *in place* (to
avoid creating one instance per object).

The resulting XTemplate will have an `owner` reference injected which refers back
to the owning object whether that is an object which has an *own instance*, or a
class prototype. Through this link, XTemplate member functions will be able to access
prototype properties of its owning class.
Parametersinstance : ObjectThe object from which to get the `XTemplate` (must be
an instance of an Ext.define'd class).


### implement

Adds members to class. ...

Adds members to class.
        
        This method has been **deprecated** since 4.1
        Use addMembers instead.


### mixin

Used internally by the mixins pre-processor ...

Used internally by the mixins pre-processor
Parametersname : Object


### onExtended

...

Parametersfn : Object


### override

Override members of this class. ...

Override members of this class. Overridden methods can be invoked via
callParent.

Ext.define('My.Cat', {
    constructor: function() {
        alert("I'm a cat!");
    }
});

My.Cat.override({
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callParent(arguments);

        alert("Meeeeoooowwww");
    }
});

var kitty = new My.Cat(); // alerts "I'm going to be a cat!"
                          // alerts "I'm a cat!"
                          // alerts "Meeeeoooowwww"


As of 4.1, direct use of this method is deprecated. Use Ext.define
instead:

Ext.define('My.CatOverride', {
    override: 'My.Cat',
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callParent(arguments);

        alert("Meeeeoooowwww");
    }
});


The above accomplishes the same result but can be managed by the Ext.Loader
which can properly order the override and its target class and the build process
can determine whether the override is needed based on the required state of the
target class (My.Cat).
        
        This method has been **deprecated** since 4.1.0
        Use Ext.define instead


### triggerExtended

...


## Methods

### Ext.XTemplate

Creates new template. ...

Creates new template.
Parametershtml : String...List of strings to be concatenated into template.
Alternatively an array of strings can be given, but then no config object may be passed.


### append

Applies the supplied values to the template and appends the new node(s) to the specified el. ...

Applies the supplied `values` to the template and appends the new node(s) to the specified `el`.

For example usage see Ext.Template class docs.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### apply

Returns an HTML fragment of this template with the specified values applied. ...

Returns an HTML fragment of this template with the specified values applied.
Parametersvalues : Object/ArrayThe template values. Can be an array if your params are numeric:




var tpl = new Ext.Template('Name: {0}, Age: {1}');
tpl.apply(['John', 25]);





or an object:




var tpl = new Ext.Template('Name: {name}, Age: {age}');
tpl.apply({name: 'John', age: 25});


### applyOut

Appends the result of this template to the provided output array. ...

Appends the result of this template to the provided output array.
Parametersvalues : Object/ArrayThe template values. See apply.


### applyTemplate

Alias for apply. ...

Alias for apply.

Returns an HTML fragment of this template with the specified values applied.
Parametersvalues : Object/ArrayThe template values. Can be an array if your params are numeric:




var tpl = new Ext.Template('Name: {0}, Age: {1}');
tpl.apply(['John', 25]);





or an object:




var tpl = new Ext.Template('Name: {name}, Age: {age}');
tpl.apply({name: 'John', age: 25});


### callOverridden

Call the original method that was previously overridden with override

Ext.define('My.Cat', {
    constructor: functi...

Call the original method that was previously overridden with override

Ext.define('My.Cat', {
    constructor: function() {
        alert("I'm a cat!");
    }
});

My.Cat.override({
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callOverridden();

        alert("Meeeeoooowwww");
    }
});

var kitty = new My.Cat(); // alerts "I'm going to be a cat!"
                          // alerts "I'm a cat!"
                          // alerts "Meeeeoooowwww"

        
        This method has been **deprecated** 
        as of 4.1. Use callParent instead.


### callParent

Call the "parent" method of the current method. ...

Call the "parent" method of the current method. That is the method previously
overridden by derivation or by an override (see Ext.define).

 Ext.define('My.Base', {
     constructor: function (x) {
         this.x = x;
     },

     statics: {
         method: function (x) {
             return x;
         }
     }
 });

 Ext.define('My.Derived', {
     extend: 'My.Base',

     constructor: function () {
         this.callParent([21]);
     }
 });

 var obj = new My.Derived();

 alert(obj.x);  // alerts 21


This can be used with an override as follows:

 Ext.define('My.DerivedOverride', {
     override: 'My.Derived',

     constructor: function (x) {
         this.callParent([x*2]); // calls original My.Derived constructor
     }
 });

 var obj = new My.Derived();

 alert(obj.x);  // now alerts 42


This also works with static methods.

 Ext.define('My.Derived2', {
     extend: 'My.Base',

     statics: {
         method: function (x) {
             return this.callParent([x*2]); // calls My.Base.method
         }
     }
 });

 alert(My.Base.method(10);     // alerts 10
 alert(My.Derived2.method(10); // alerts 20


Lastly, it also works with overridden static methods.

 Ext.define('My.Derived2Override', {
     override: 'My.Derived2',

     statics: {
         method: function (x) {
             return this.callParent([x*2]); // calls My.Derived2.method
         }
     }
 });

 alert(My.Derived2.method(10); // now alerts 40


To override a method and replace it and also call the superclass method, use
callSuper. This is often done to patch a method to fix a bug.
Parametersargs : Array/ArgumentsThe arguments, either an array or the `arguments` object
from the current method, for example: `this.callParent(arguments)`


### callSuper

This method is used by an override to call the superclass method but bypass any
overridden method. ...

This method is used by an override to call the superclass method but bypass any
overridden method. This is often done to "patch" a method that contains a bug
but for whatever reason cannot be fixed directly.

Consider:

 Ext.define('Ext.some.Class', {
     method: function () {
         console.log('Good');
     }
 });

 Ext.define('Ext.some.DerivedClass', {
     method: function () {
         console.log('Bad');

         // ... logic but with a bug ...

         this.callParent();
     }
 });


To patch the bug in `DerivedClass.method`, the typical solution is to create an
override:

 Ext.define('App.paches.DerivedClass', {
     override: 'Ext.some.DerivedClass',

     method: function () {
         console.log('Fixed');

         // ... logic but with bug fixed ...

         this.callSuper();
     }
 });


The patch method cannot use `callParent` to call the superclass `method` since
that would call the overridden method containing the bug. In other words, the
above patch would only produce "Fixed" then "Good" in the console log, whereas,
using `callParent` would produce "Fixed" then "Bad" then "Good".
Parametersargs : Array/ArgumentsThe arguments, either an array or the `arguments` object
from the current method, for example: `this.callSuper(arguments)`


### compile

Does nothing. ...

Does nothing. XTemplates are compiled automatically, so this function simply returns this.
ReturnsExt.XTemplatethis


### configClass

...


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### doInsert

...

Parameterswhere : Object


### getConfig

...

Parametersname : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### hasConfig

...

Parametersconfig : Object


### initConfig

Initialize configuration for this class. ...

Initialize configuration for this class. a typical example:

Ext.define('My.awesome.Class', {
    // The default config
    config: {
        name: 'Awesome',
        isAwesome: true
    },

    constructor: function(config) {
        this.initConfig(config);
    }
});

var awesome = new My.awesome.Class({
    name: 'Super Awesome'
});

alert(awesome.getName()); // 'Super Awesome'

Parametersconfig : Object


### insertAfter

Applies the supplied values to the template and inserts the new node(s) after el. ...

Applies the supplied values to the template and inserts the new node(s) after el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### insertBefore

Applies the supplied values to the template and inserts the new node(s) before el. ...

Applies the supplied values to the template and inserts the new node(s) before el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### insertFirst

Applies the supplied values to the template and inserts the new node(s) as the first child of el. ...

Applies the supplied values to the template and inserts the new node(s) as the first child of el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### onConfigUpdate

...

Parametersnames : Object


### overwrite

Applies the supplied values to the template and overwrites the content of el with the new node(s). ...

Applies the supplied values to the template and overwrites the content of el with the new node(s).
Parametersel : String/HTMLElement/Ext.ElementThe context element


### set

Sets the HTML used as the template and optionally compiles it. ...

Sets the HTML used as the template and optionally compiles it.
Parametershtml : String


### setConfig

...

Parametersconfig : Object


### statics

Get the reference to the class from which this object was instantiated. ...

Get the reference to the class from which this object was instantiated. Note that unlike self,
`this.statics()` is scope-independent and it always returns the class from which it was called, regardless of what
`this` points to during run-time

Ext.define('My.Cat', {
    statics: {
        totalCreated: 0,
        speciesName: 'Cat' // My.Cat.speciesName = 'Cat'
    },

    constructor: function() {
        var statics = this.statics();

        alert(statics.speciesName);     // always equals to 'Cat' no matter what 'this' refers to
                                        // equivalent to: My.Cat.speciesName

        alert(this.self.speciesName);   // dependent on 'this'

        statics.totalCreated++;
    },

    clone: function() {
        var cloned = new this.self;                      // dependent on 'this'

        cloned.groupName = this.statics().speciesName;   // equivalent to: My.Cat.speciesName

        return cloned;
    }
});


Ext.define('My.SnowLeopard', {
    extend: 'My.Cat',

    statics: {
        speciesName: 'Snow Leopard'     // My.SnowLeopard.speciesName = 'Snow Leopard'
    },

    constructor: function() {
        this.callParent();
    }
});

var cat = new My.Cat();                 // alerts 'Cat', then alerts 'Cat'

var snowLeopard = new My.SnowLeopard(); // alerts 'Cat', then alerts 'Snow Leopard'

var clone = snowLeopard.clone();
alert(Ext.getClassName(clone));         // alerts 'My.SnowLeopard'
alert(clone.groupName);                 // alerts 'Cat'

alert(My.Cat.totalCreated);             // alerts 3

ReturnsExt.Class


### addConfig

...

Parametersconfig : Object


### addInheritableStatics

...

Parametersmembers : Object


### addMember

...

Parametersname : Object


### addMembers

Add methods / properties to the prototype of this class. ...

Add methods / properties to the prototype of this class.

Ext.define('My.awesome.Cat', {
    constructor: function() {
        ...
    }
});

 My.awesome.Cat.addMembers({
     meow: function() {
        alert('Meowww...');
     }
 });

 var kitty = new My.awesome.Cat;
 kitty.meow();

Parametersmembers : Object


### addStatics

Add / override static properties of this class. ...

Add / override static properties of this class.

Ext.define('My.cool.Class', {
    ...
});

My.cool.Class.addStatics({
    someProperty: 'someValue',      // My.cool.Class.someProperty = 'someValue'
    method1: function() { ... },    // My.cool.Class.method1 = function() { ... };
    method2: function() { ... }     // My.cool.Class.method2 = function() { ... };
});

Parametersmembers : Object


### addXtype

...

Parametersxtype : Object


### borrow

Borrow another class' members to the prototype of this class. ...

Borrow another class' members to the prototype of this class.

Ext.define('Bank', {
    money: '$$$',
    printMoney: function() {
        alert('$$$$$$$');
    }
});

Ext.define('Thief', {
    ...
});

Thief.borrow(Bank, ['money', 'printMoney']);

var steve = new Thief();

alert(steve.money); // alerts '$$$'
steve.printMoney(); // alerts '$$$$$$$'

ParametersfromClass : Ext.BaseThe class to borrow members from


### create

Create a new instance of this Class. ...

Create a new instance of this Class.

Ext.define('My.cool.Class', {
    ...
});

My.cool.Class.create({
    someConfig: true
});


All parameters are passed to the constructor of the class.
ReturnsObjectthe created instance.


### createAlias

Create aliases for existing prototype methods. ...

Create aliases for existing prototype methods. Example:

Ext.define('My.cool.Class', {
    method1: function() { ... },
    method2: function() { ... }
});

var test = new My.cool.Class();

My.cool.Class.createAlias({
    method3: 'method1',
    method4: 'method2'
});

test.method3(); // test.method1()

My.cool.Class.createAlias('method5', 'method3');

test.method5(); // test.method3() -> test.method1()

Parametersalias : String/ObjectThe new method name, or an object to set multiple aliases. See
flexSetter


### extend

...

Parametersconfig : Object


### from

Creates a template from the passed element's value (display:none textarea, preferred) or innerHTML. ...

Creates a template from the passed element's value (*display:none* textarea, preferred) or innerHTML.
Parametersel : String/HTMLElementA DOM element or its id


### getName

Get the current class' name in string format. ...

Get the current class' name in string format.

Ext.define('My.cool.Class', {
    constructor: function() {
        alert(this.self.getName()); // alerts 'My.cool.Class'
    }
});

My.cool.Class.getName(); // 'My.cool.Class'

ReturnsStringclassName


### getTpl

Gets an XTemplate from an object (an instance of an Ext.define'd class). ...

Gets an `XTemplate` from an object (an instance of an Ext.define'd class).
Many times, templates are configured high in the class hierarchy and are to be
shared by all classes that derive from that base. To further complicate matters,
these templates are seldom actual instances but are rather configurations. For
example:

 Ext.define('MyApp.Class', {
     extraCls: 'extra-class',

     someTpl: [
         '<div class="{%this.emitClass(out)%}"></div>',
     {
         // Member fn - outputs the owing class's extra CSS class
         emitClass: function(out) {
             out.push(this.owner.extraCls);
         }
     }]
 });


The goal being to share that template definition with all instances and even
instances of derived classes, until `someTpl` is overridden. This method will
"upgrade" these configurations to be real `XTemplate` instances *in place* (to
avoid creating one instance per object).

The resulting XTemplate will have an `owner` reference injected which refers back
to the owning object whether that is an object which has an *own instance*, or a
class prototype. Through this link, XTemplate member functions will be able to access
prototype properties of its owning class.
Parametersinstance : ObjectThe object from which to get the `XTemplate` (must be
an instance of an Ext.define'd class).


### implement

Adds members to class. ...

Adds members to class.
        
        This method has been **deprecated** since 4.1
        Use addMembers instead.


### mixin

Used internally by the mixins pre-processor ...

Used internally by the mixins pre-processor
Parametersname : Object


### onExtended

...

Parametersfn : Object


### override

Override members of this class. ...

Override members of this class. Overridden methods can be invoked via
callParent.

Ext.define('My.Cat', {
    constructor: function() {
        alert("I'm a cat!");
    }
});

My.Cat.override({
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callParent(arguments);

        alert("Meeeeoooowwww");
    }
});

var kitty = new My.Cat(); // alerts "I'm going to be a cat!"
                          // alerts "I'm a cat!"
                          // alerts "Meeeeoooowwww"


As of 4.1, direct use of this method is deprecated. Use Ext.define
instead:

Ext.define('My.CatOverride', {
    override: 'My.Cat',
    constructor: function() {
        alert("I'm going to be a cat!");

        this.callParent(arguments);

        alert("Meeeeoooowwww");
    }
});


The above accomplishes the same result but can be managed by the Ext.Loader
which can properly order the override and its target class and the build process
can determine whether the override is needed based on the required state of the
target class (My.Cat).
        
        This method has been **deprecated** since 4.1.0
        Use Ext.define instead


### triggerExtended

...


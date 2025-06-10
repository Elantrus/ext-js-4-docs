# Ext.DomHelper

**Extends:** Ext.dom.Helper

**Alternate Names:** Ext.core.DomHelper

## Descrição

The DomHelper class provides a layer of abstraction from DOM and transparently supports creating elements via DOM or
using HTML fragments. It also has the ability to create HTML fragment templates from your DOM building code.

A specification object is used when creating elements. Attributes of this object are assumed to be element
attributes, except for 4 special attributes:

**NOTE:** For other arbitrary attributes, the value will currently **not** be automatically HTML-escaped prior to
building the element's HTML string. This means that if your attribute value contains special characters that would
not normally be allowed in a double-quoted attribute value, you **must** manually HTML-encode it beforehand (see
Ext.String.htmlEncode) or risk malformed HTML being created. This behavior may change in a future release.

Commonly used insertion methods:

This is an example, where an unordered list with 3 children items is appended to an existing element with
id 'my-div':

var dh = Ext.DomHelper; // create shorthand alias
// specification object
var spec = {
    id: 'my-ul',
    tag: 'ul',
    cls: 'my-list',
    // append children after creating
    children: [     // may also specify 'cn' instead of 'children'
        {tag: 'li', id: 'item0', html: 'List Item 0'},
        {tag: 'li', id: 'item1', html: 'List Item 1'},
        {tag: 'li', id: 'item2', html: 'List Item 2'}
    ]
};
var list = dh.append(
    'my-div', // the context element 'my-div' can either be the id or the actual node
    spec      // the specification object
);


Element creation specification parameters in this class may also be passed as an Array of specification objects. This
can be used to insert multiple sibling nodes into an existing container very efficiently. For example, to add more
list items to the example above:

dh.append('my-ul', [
    {tag: 'li', id: 'item3', html: 'List Item 3'},
    {tag: 'li', id: 'item4', html: 'List Item 4'}
]);


Templating

The real power is in the built-in templating. Instead of creating or appending any elements, createTemplate
returns a Template object which can be used over and over to insert new elements. Revisiting the example above, we
could utilize templating this time:

// create the node
var list = dh.append('my-div', {tag: 'ul', cls: 'my-list'});
// get template
var tpl = dh.createTemplate({tag: 'li', id: 'item{0}', html: 'List Item {0}'});

for(var i = 0; i < 5, i++){
    tpl.append(list, [i]); // use template to append to the actual node
}


An example using a template:

var html = '<a id="{0}" href="{1}" class="nav">{2}</a>';

var tpl = new Ext.DomHelper.createTemplate(html);
tpl.append('blog-roll', ['link1', 'http://www.edspencer.net/', "Ed's Site"]);
tpl.append('blog-roll', ['link2', 'http://www.dustindiaz.com/', "Dustin's Site"]);


The same example using named parameters:

var html = '<a id="{id}" href="{url}" class="nav">{text}</a>';

var tpl = new Ext.DomHelper.createTemplate(html);
tpl.append('blog-roll', {
    id: 'link1',
    url: 'http://www.edspencer.net/',
    text: "Ed's Site"
});
tpl.append('blog-roll', {
    id: 'link2',
    url: 'http://www.dustindiaz.com/',
    text: "Dustin's Site"
});


Compiling Templates

Templates are applied using regular expressions. The performance is great, but if you are adding a bunch of DOM
elements using the same template, you can increase performance even further by "compiling" the template. The way "compile()" works is the template is parsed and
broken up at the different variable points and a dynamic function is created and eval'ed. The generated function
performs string concatenation of these parts and the passed variables instead of using regular expressions.

var html = '<a id="{id}" href="{url}" class="nav">{text}</a>';

var tpl = new Ext.DomHelper.createTemplate(html);
tpl.compile();

//... use template like normal


Performance Boost

DomHelper will transparently create HTML fragments when it can. Using HTML fragments instead of DOM can significantly
boost performance.

Element creation specification parameters may also be strings. If useDom is false, then the string is used
as innerHTML. If useDom is true, a string specification results in the creation of a text node. Usage:

## Properties

### $className

**Tipo:** String

...

Defaults to: `'Ext.Base'`


### attributeTransform

**Tipo:** Object

Since cls & for are reserved words, we need to transform them ...

Since cls & for are reserved words, we need to transform them
Defaults to: `{cls: 'class', htmlFor: 'for'}`


### closeTags

**Tipo:** Object

...

Defaults to: `{}`


### confRe

**Tipo:** RegExp

...

Defaults to: `/^(?:tag|children|cn|html|tpl|tplData)$/i`


### configMap

**Tipo:** Object

...

Defaults to: `{}`


### decamelizeName

**Tipo:** Object


### emptyTags

**Tipo:** RegExp

...

Defaults to: `/^(?:br|frame|hr|img|input|link|meta|range|spacer|wbr|area|param|col)$/i`


### endRe

**Tipo:** RegExp

...

Defaults to: `/end/i`


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


### styleSepRe

**Tipo:** RegExp

...

Defaults to: `/\s*(?::|;)\s*/`


### useDom

**Tipo:** Boolean

True to force the use of DOM instead of html fragments. ...

True to force the use of DOM instead of html fragments.
Defaults to: `false`


### $onExtended

**Tipo:** Array

...

Defaults to: `[]`


### append

Creates new DOM element(s) and appends them to el. ...

Creates new DOM element(s) and appends them to el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### applyStyles

Applies a style specification to an element. ...

Applies a style specification to an element.
Parametersel : String/HTMLElementThe element to apply styles to


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


### configClass

...


### createContextualFragment

Fix for IE9 createContextualFragment missing method ...

Fix for IE9 createContextualFragment missing method
Parametershtml : Object


### createDom

Creates new DOM element(s) without inserting them to the document. ...

Creates new DOM element(s) without inserting them to the document.
Parameterso : Object/StringThe DOM object spec (and children) or raw HTML blob


### createHtml

Alias for markup. ...

Alias for markup.

Returns the markup for the passed Element(s) config.
Parametersspec : ObjectThe DOM object spec (and children)


### createTemplate

Creates a new Ext.Template from the DOM object spec. ...

Creates a new Ext.Template from the DOM object spec.
Parameterso : ObjectThe DOM object spec (and children)


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### doInsert

...

Parametersel : Object


### generateMarkup

...

Parametersspec : Object


### generateStyles

Converts the styles from the given object to text. ...

Converts the styles from the given object to text. The styles are CSS style names
with their associated value.

The basic form of this method returns a string:

 var s = Ext.DomHelper.generateStyles({
     backgroundColor: 'red'
 });

 // s = 'background-color:red;'


Alternatively, this method can append to an output array.

 var buf = [];

 ...

 Ext.DomHelper.generateStyles({
     backgroundColor: 'red'
 }, buf);


In this case, the style text is pushed on to the array and the array is returned.
Parametersstyles : ObjectThe object describing the styles.


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

Creates new DOM element(s) and inserts them after el. ...

Creates new DOM element(s) and inserts them after el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### insertBefore

Creates new DOM element(s) and inserts them before el. ...

Creates new DOM element(s) and inserts them before el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### insertFirst

Creates new DOM element(s) and inserts them as the first child of el. ...

Creates new DOM element(s) and inserts them as the first child of el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### insertHtml

Inserts an HTML fragment into the DOM. ...

Inserts an HTML fragment into the DOM.
Parameterswhere : StringWhere to insert the html in relation to el - beforeBegin, afterBegin, beforeEnd, afterEnd.

For example take the following HTML: `<div>Contents</div>`

Using different `where` values inserts element to the following places:


beforeBegin: `<HERE><div>Contents</div>`
afterBegin: `<div><HERE>Contents</div>`
beforeEnd: `<div>Contents<HERE></div>`
afterEnd: `<div>Contents</div><HERE>`


### insertIntoTable

Nasty code for IE's broken table implementation ...

Nasty code for IE's broken table implementation
Parameterstag : Object


### markup

Returns the markup for the passed Element(s) config. ...

Returns the markup for the passed Element(s) config.
Parametersspec : ObjectThe DOM object spec (and children)


### onConfigUpdate

...

Parametersnames : Object


### overwrite

Creates new DOM element(s) and overwrites the contents of el with them. ...

Creates new DOM element(s) and overwrites the contents of el with them.
Parametersel : String/HTMLElement/Ext.ElementThe context element


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

### append

Creates new DOM element(s) and appends them to el. ...

Creates new DOM element(s) and appends them to el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### applyStyles

Applies a style specification to an element. ...

Applies a style specification to an element.
Parametersel : String/HTMLElementThe element to apply styles to


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


### configClass

...


### createContextualFragment

Fix for IE9 createContextualFragment missing method ...

Fix for IE9 createContextualFragment missing method
Parametershtml : Object


### createDom

Creates new DOM element(s) without inserting them to the document. ...

Creates new DOM element(s) without inserting them to the document.
Parameterso : Object/StringThe DOM object spec (and children) or raw HTML blob


### createHtml

Alias for markup. ...

Alias for markup.

Returns the markup for the passed Element(s) config.
Parametersspec : ObjectThe DOM object spec (and children)


### createTemplate

Creates a new Ext.Template from the DOM object spec. ...

Creates a new Ext.Template from the DOM object spec.
Parameterso : ObjectThe DOM object spec (and children)


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### doInsert

...

Parametersel : Object


### generateMarkup

...

Parametersspec : Object


### generateStyles

Converts the styles from the given object to text. ...

Converts the styles from the given object to text. The styles are CSS style names
with their associated value.

The basic form of this method returns a string:

 var s = Ext.DomHelper.generateStyles({
     backgroundColor: 'red'
 });

 // s = 'background-color:red;'


Alternatively, this method can append to an output array.

 var buf = [];

 ...

 Ext.DomHelper.generateStyles({
     backgroundColor: 'red'
 }, buf);


In this case, the style text is pushed on to the array and the array is returned.
Parametersstyles : ObjectThe object describing the styles.


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

Creates new DOM element(s) and inserts them after el. ...

Creates new DOM element(s) and inserts them after el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### insertBefore

Creates new DOM element(s) and inserts them before el. ...

Creates new DOM element(s) and inserts them before el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### insertFirst

Creates new DOM element(s) and inserts them as the first child of el. ...

Creates new DOM element(s) and inserts them as the first child of el.
Parametersel : String/HTMLElement/Ext.ElementThe context element


### insertHtml

Inserts an HTML fragment into the DOM. ...

Inserts an HTML fragment into the DOM.
Parameterswhere : StringWhere to insert the html in relation to el - beforeBegin, afterBegin, beforeEnd, afterEnd.

For example take the following HTML: `<div>Contents</div>`

Using different `where` values inserts element to the following places:


beforeBegin: `<HERE><div>Contents</div>`
afterBegin: `<div><HERE>Contents</div>`
beforeEnd: `<div>Contents<HERE></div>`
afterEnd: `<div>Contents</div><HERE>`


### insertIntoTable

Nasty code for IE's broken table implementation ...

Nasty code for IE's broken table implementation
Parameterstag : Object


### markup

Returns the markup for the passed Element(s) config. ...

Returns the markup for the passed Element(s) config.
Parametersspec : ObjectThe DOM object spec (and children)


### onConfigUpdate

...

Parametersnames : Object


### overwrite

Creates new DOM element(s) and overwrites the contents of el with them. ...

Creates new DOM element(s) and overwrites the contents of el with them.
Parametersel : String/HTMLElement/Ext.ElementThe context element


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


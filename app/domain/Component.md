# Ext.app.domain.Component

**Extends:** Ext.app.EventDomain

## Descrição

This class implements the component event domain. All classes extending from
Ext.Component are included in this domain. The matching criteria uses
Ext.ComponentQuery.

## Config options

### idProperty

**Tipo:** String

Name of the identifier property for this event domain.


### $className

**Tipo:** String

...

Defaults to: `'Ext.Base'`


### configMap

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


### type

**Tipo:** String

...

Defaults to: `'component'`


### $onExtended

**Tipo:** Array

...

Defaults to: `[]`


### Ext.app.domain.Component

...

ReturnsExt.app.domain.Component


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


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### dispatch

This method dispatches an event fired by an object monitored by this domain. ...

This method dispatches an event fired by an object monitored by this domain. This
is not called directly but is called by interceptors injected by the `monitor` method.
Parameterstarget : ObjectThe firer of the event.


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


### listen

This method adds listeners on behalf of a controller. ...

This method adds listeners on behalf of a controller. This method is passed an
object that is keyed by selectors. The value of these is also an object but now
keyed by event name. For example:

 domain.listen({
     'some[selector]': {
         click: function() { ... }
     },

     'other selector': {
         change: {
             fn: function() { ... },
             delay: 10
         }
     }

 }, controller);

Parametersselectors : ObjectConfig object containing selectors and listeners.


### match

This method matches the firer of the event (the target) to the given selector. ...

This method matches the firer of the event (the `target`) to the given `selector`.
Default matching is very simple: a match is true when selector equals target's
idProperty, or when selector is '*' wildcard to match any
target.
Parameterstarget : ObjectThe firer of the event.


### monitor

This method is called by the derived class to monitor fireEvent calls. ...

This method is called by the derived class to monitor `fireEvent` calls. Any call
to `fireEvent` on the target Observable will be intercepted and dispatched to any
listening Controllers. Assuming the original `fireEvent` method does not return
`false`, the event is passed to the `dispatch` method of this object.

This is typically called in the `constructor` of derived classes.
Parametersobservable : Ext.ClassThe Observable to monitor for events.


### onConfigUpdate

...

Parametersnames : Object


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


### unlisten

Removes all of a controller's attached listeners. ...

Removes all of a controller's attached listeners.
ParameterscontrollerId : StringThe id of the controller.


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


## Properties

### $className

**Tipo:** String

...

Defaults to: `'Ext.Base'`


### configMap

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


### type

**Tipo:** String

...

Defaults to: `'component'`


### $onExtended

**Tipo:** Array

...

Defaults to: `[]`


### Ext.app.domain.Component

...

ReturnsExt.app.domain.Component


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


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### dispatch

This method dispatches an event fired by an object monitored by this domain. ...

This method dispatches an event fired by an object monitored by this domain. This
is not called directly but is called by interceptors injected by the `monitor` method.
Parameterstarget : ObjectThe firer of the event.


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


### listen

This method adds listeners on behalf of a controller. ...

This method adds listeners on behalf of a controller. This method is passed an
object that is keyed by selectors. The value of these is also an object but now
keyed by event name. For example:

 domain.listen({
     'some[selector]': {
         click: function() { ... }
     },

     'other selector': {
         change: {
             fn: function() { ... },
             delay: 10
         }
     }

 }, controller);

Parametersselectors : ObjectConfig object containing selectors and listeners.


### match

This method matches the firer of the event (the target) to the given selector. ...

This method matches the firer of the event (the `target`) to the given `selector`.
Default matching is very simple: a match is true when selector equals target's
idProperty, or when selector is '*' wildcard to match any
target.
Parameterstarget : ObjectThe firer of the event.


### monitor

This method is called by the derived class to monitor fireEvent calls. ...

This method is called by the derived class to monitor `fireEvent` calls. Any call
to `fireEvent` on the target Observable will be intercepted and dispatched to any
listening Controllers. Assuming the original `fireEvent` method does not return
`false`, the event is passed to the `dispatch` method of this object.

This is typically called in the `constructor` of derived classes.
Parametersobservable : Ext.ClassThe Observable to monitor for events.


### onConfigUpdate

...

Parametersnames : Object


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


### unlisten

Removes all of a controller's attached listeners. ...

Removes all of a controller's attached listeners.
ParameterscontrollerId : StringThe id of the controller.


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

### Ext.app.domain.Component

...

ReturnsExt.app.domain.Component


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


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### dispatch

This method dispatches an event fired by an object monitored by this domain. ...

This method dispatches an event fired by an object monitored by this domain. This
is not called directly but is called by interceptors injected by the `monitor` method.
Parameterstarget : ObjectThe firer of the event.


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


### listen

This method adds listeners on behalf of a controller. ...

This method adds listeners on behalf of a controller. This method is passed an
object that is keyed by selectors. The value of these is also an object but now
keyed by event name. For example:

 domain.listen({
     'some[selector]': {
         click: function() { ... }
     },

     'other selector': {
         change: {
             fn: function() { ... },
             delay: 10
         }
     }

 }, controller);

Parametersselectors : ObjectConfig object containing selectors and listeners.


### match

This method matches the firer of the event (the target) to the given selector. ...

This method matches the firer of the event (the `target`) to the given `selector`.
Default matching is very simple: a match is true when selector equals target's
idProperty, or when selector is '*' wildcard to match any
target.
Parameterstarget : ObjectThe firer of the event.


### monitor

This method is called by the derived class to monitor fireEvent calls. ...

This method is called by the derived class to monitor `fireEvent` calls. Any call
to `fireEvent` on the target Observable will be intercepted and dispatched to any
listening Controllers. Assuming the original `fireEvent` method does not return
`false`, the event is passed to the `dispatch` method of this object.

This is typically called in the `constructor` of derived classes.
Parametersobservable : Ext.ClassThe Observable to monitor for events.


### onConfigUpdate

...

Parametersnames : Object


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


### unlisten

Removes all of a controller's attached listeners. ...

Removes all of a controller's attached listeners.
ParameterscontrollerId : StringThe id of the controller.


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


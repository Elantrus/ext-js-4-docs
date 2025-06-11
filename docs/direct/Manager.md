# Ext.direct.Manager

**Extends:** Ext.Base

**Alternate Names:** Ext.Direct

## Descrição

Ext.Direct aims to streamline communication between the client and server by providing a single interface that
reduces the amount of common code typically required to validate data and handle returned data packets (reading data,
error conditions, etc).

The Ext.direct namespace includes several classes for a closer integration with the server-side. The Ext.data
namespace also includes classes for working with Ext.data.Stores which are backed by data from an Ext.Direct method.

For additional information consult the Ext.Direct Specification.

Ext.Direct uses a provider architecture, where one or more providers are used to transport data to and from the
server. There are several providers that exist in the core at the moment:

A provider does not need to be invoked directly, providers are added via Ext.direct.Manager.addProvider.

Ext.Direct utilizes a "router" on the server to direct requests from the client to the appropriate server-side
method. Because the Ext.Direct API is completely platform-agnostic, you could completely swap out a Java based server
solution and replace it with one that uses C# without changing the client side JavaScript at all.

Custom events from the server may be handled by the client by adding listeners, for example:

## Config options

### listeners

**Tipo:** Object

A config object containing one or more event handlers to be added to this object during initialization. ...

A config object containing one or more event handlers to be added to this object during initialization. This
should be a valid listeners config object as specified in the addListener example for attaching multiple
handlers at once.

**DOM events from Ext JS Components**

While *some* Ext JS Component classes export selected DOM events (e.g. "click", "mouseover" etc), this is usually
only done when extra value can be added. For example the DataView's **`itemclick`** event passing the node clicked on. To access DOM events directly from a
child element of a Component, we need to specify the `element` option to identify the Component property to add a
DOM listener to:

new Ext.panel.Panel({
    width: 400,
    height: 200,
    dockedItems: [{
        xtype: 'toolbar'
    }],
    listeners: {
        click: {
            element: 'el', //bind to the underlying el property on the panel
            fn: function(){ console.log('click el'); }
        },
        dblclick: {
            element: 'body', //bind to the underlying body property on the panel
            fn: function(){ console.log('dblclick body'); }
        }
    }
});


### $className

**Tipo:** String

...

Defaults to: `'Ext.Base'`


### configMap

**Tipo:** Object

...

Defaults to: `{}`


### eventsSuspended

**Tipo:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called.
Defaults to: `0`


### exceptions

**Tipo:** Object

Exception types. ...

Exception types.
Defaults to: `{TRANSPORT: 'xhr', PARSE: 'parse', DATA: 'data', LOGIN: 'login', SERVER: 'exception'}`


### hasListeners

**Tipo:** Object

This object holds a key for any event that has a listener. ...

This object holds a key for any event that has a listener. The listener may be set
directly on the instance, or on its class or a super class (via observe) or
on the MVC EventBus. The values of this object are truthy
(a non-zero number) and falsy (0 or undefined). They do not represent an exact count
of listeners. The value for an event is truthy if the event must be fired and is
falsy if there is no need to fire the event.

The intended use of this property is to avoid the expense of fireEvent calls when
there are no listeners. This can be particularly helpful when one would otherwise
have to call fireEvent hundreds or thousands of times. It is used like this:

 if (this.hasListeners.foo) {
     this.fireEvent('foo', this, arg1);
 }


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


### isObservable

**Tipo:** Boolean

true in this class to identify an object as an instantiated Observable, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Observable, or subclass thereof.
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


### $onExtended

**Tipo:** Array

...

Defaults to: `[]`


### Ext.direct.Manager

...

ReturnsExt.direct.Manager


### addEvents

Adds the specified events to the list of events which this Observable may fire. ...

Adds the specified events to the list of events which this Observable may fire.
ParameterseventNames : Object/String...Either an object with event names as properties with
a value of `true`. For example:

this.addEvents({
    storeloaded: true,
    storecleared: true
});


Or any number of event names as separate parameters. For example:

this.addEvents('storeloaded', 'storecleared');


### addListener

Appends an event handler to this object. ...

Appends an event handler to this object.  For example:

myGridPanel.on("mouseover", this.onMouseOver, this);


The method also allows for a single argument to be passed which is a config object
containing properties which specify multiple events. For example:

myGridPanel.on({
    cellClick: this.onCellClick,
    mouseover: this.onMouseOver,
    mouseout: this.onMouseOut,
    scope: this // Important. Ensure "this" is correct during handler execution
});


One can also specify options for each event handler separately:

myGridPanel.on({
    cellClick: {fn: this.onCellClick, scope: this, single: true},
    mouseover: {fn: panel.onMouseOver, scope: panel}
});


*Names* of methods in a specified scope may also be used. Note that
`scope` MUST be specified to use this option:

myGridPanel.on({
    cellClick: {fn: 'onCellClick', scope: this, single: true},
    mouseover: {fn: 'onMouseOver', scope: panel}
});

ParameterseventName : String/ObjectThe name of the event to listen for.
May also be an object who's property names are event names.


### addManagedListener

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destr...

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destroyed.
Parametersitem : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### addProvider

Adds an Ext.Direct Provider and creates the proxy or stub methods to execute server-side methods. ...

Adds an Ext.Direct Provider and creates the proxy or stub methods to execute server-side methods. If the provider
is not already connected, it will auto-connect.

 var pollProv = new Ext.direct.PollingProvider({
     url: 'php/poll2.php'
 });

 Ext.direct.Manager.addProvider({
     type: 'remoting',           // create a Ext.direct.RemotingProvider
     url:  'php/router.php',     // url to connect to the Ext.Direct server-side router.
     actions: {                  // each property within the actions object represents a Class
         TestAction: [{          // array of methods within each server side Class
             name: 'doEcho',     // name of method
             len:  1
         }, {
             name: 'multiply',
             len:  1
         }, {
             name: 'doForm',
             formHandler: true   // handle form on server with Ext.Direct.Transaction
         }]
     },
     namespace: 'myApplication', // namespace to create the Remoting Provider in
 }, {
     type: 'polling',            // create a Ext.direct.PollingProvider
     url:  'php/poll.php'
 },
 pollProv);                      // reference to previously created instance

Parametersprovider : Ext.direct.Provider/Object...Accepts any number of Provider descriptions (an instance or config object for
a Provider). Each Provider description instructs Ext.Direct how to create
client-side stub methods.


### addTransaction

Adds a transaction to the manager. ...

Adds a transaction to the manager.
Parameterstransaction : Ext.direct.TransactionThe transaction to add


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


### captureArgs

...

Parameterso : Object


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### configClass

...


### continueFireEvent

Continue to fire event. ...

Continue to fire event.
ParameterseventName : String


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.
ParametersnewName : StringThe name under which to refire the passed parameters.


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if
present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if
present. There is no implementation in the Observable base class.

This is commonly used by Ext.Components to bubble events to owner Containers.
See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the
Component's immediate owner. But if a known target is required, this can be overridden to access the
required target more quickly.

Example:

Ext.define('Ext.overrides.form.field.Base', {
    override: 'Ext.form.field.Base',

    //  Add functionality to Field's initComponent to enable the change event to bubble
    initComponent: function () {
        this.callParent();
        this.enableBubble('change');
    }
});

var myForm = Ext.create('Ext.form.Panel', {
    title: 'User Details',
    items: [{
        ...
    }],
    listeners: {
        change: function() {
            // Title goes red if form has been modified.
            myForm.header.setStyle('color', 'red');
        }
    }
});

ParameterseventNames : String/String[]The event name to bubble, or an Array of event names.


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed
to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed
to addListener).

An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by
calling enableBubble.
ParameterseventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list.

An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by
calling enableBubble.
ParameterseventName : StringThe name of the event to fire.


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable
ReturnsExt.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getConfig

...

Parametersname : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### getProvider

Retrieves a provider by the id specified when the
provider is added. ...

Retrieves a provider by the **id** specified when the
provider is added.
Parametersid : String/Ext.direct.ProviderThe id of the provider, or the provider instance.


### getTransaction

Gets a transaction ...

Gets a transaction
Parameterstransaction : String/Ext.direct.TransactionThe transaction/id of transaction to get


### hasConfig

...

Parametersconfig : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer
indicates whether the event needs firing or not.
ParameterseventName : StringThe name of the event to check for


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


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener.

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destroyed.
Parametersitem : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener.

Removes listeners that were added by the mon method.
Parametersitem : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### on

Shorthand for addListener. ...

Shorthand for addListener.

Appends an event handler to this object.  For example:

myGridPanel.on("mouseover", this.onMouseOver, this);


The method also allows for a single argument to be passed which is a config object
containing properties which specify multiple events. For example:

myGridPanel.on({
    cellClick: this.onCellClick,
    mouseover: this.onMouseOver,
    mouseout: this.onMouseOut,
    scope: this // Important. Ensure "this" is correct during handler execution
});


One can also specify options for each event handler separately:

myGridPanel.on({
    cellClick: {fn: this.onCellClick, scope: this, single: true},
    mouseover: {fn: panel.onMouseOver, scope: panel}
});


*Names* of methods in a specified scope may also be used. Note that
`scope` MUST be specified to use this option:

myGridPanel.on({
    cellClick: {fn: 'onCellClick', scope: this, single: true},
    mouseover: {fn: 'onMouseOver', scope: panel}
});

ParameterseventName : String/ObjectThe name of the event to listen for.
May also be an object who's property names are event names.


### onConfigUpdate

...

Parametersnames : Object


### onProviderData

...

Parametersprovider : Object


### parseMethod

Parses a direct function. ...

Parses a direct function. It may be passed in a string format, for example:
"MyApp.Person.read".
Parametersfn : String/FunctionThe direct function


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a
class derives from this class or uses this class as a mixin.
ParametersT : FunctionThe class constructor to prepare.


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`.

For example if you are extending Grid, you might decide to forward some events from store.
So you can do this inside your initComponent:

this.relayEvents(this.getStore(), ['load']);


The grid instance will then have an observable 'load' event which will be passed the
parameters of the store's load event and any function fired with the grid's load event
would have access to the grid using the `this` keyword.
Parametersorigin : ObjectThe Observable whose events this object is to relay.


### removeListener

Removes an event handler. ...

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


### removeManagedListener

Removes listeners that were added by the mon method. ...

Removes listeners that were added by the mon method.
Parametersitem : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### removeManagedListenerItem

Remove a single managed listener item ...

Remove a single managed listener item
ParametersisClear : BooleanTrue if this is being called during a clear


### removeProvider

Removes the provider. ...

Removes the provider.
Parametersprovider : String/Ext.direct.ProviderThe provider instance or the id of the provider.


### removeTransaction

Removes a transaction from the manager. ...

Removes a transaction from the manager.
Parameterstransaction : String/Ext.direct.TransactionThe transaction/id of transaction to remove


### resumeEvent

Resumes firing of the named event(s). ...

Resumes firing of the named event(s).

After calling this method to resume events, the events will fire when requested to fire.

Note that if the suspendEvent method is called multiple times for a certain event,
this converse method will have to be called the same number of times for it to resume firing.
ParameterseventName : String...Multiple event names to resume.


### resumeEvents

Resumes firing events (see suspendEvents). ...

Resumes firing events (see suspendEvents).

If events were suspended using the `queueSuspended` parameter, then all events fired
during event suspension will be sent to any listeners now.


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


### suspendEvent

Suspends firing of the named event(s). ...

Suspends firing of the named event(s).

After calling this method to suspend events, the events will no longer fire when requested to fire.

Note that if this is called multiple times for a certain event, the converse method
resumeEvent will have to be called the same number of times for it to resume firing.
ParameterseventName : String...Multiple event names to suspend.


### suspendEvents

Suspends the firing of all events. ...

Suspends the firing of all events. (see resumeEvents)
ParametersqueueSuspended : BooleanPass as true to queue up suspended events to be fired
after the resumeEvents call instead of discarding all suspended events.


### un

Shorthand for removeListener. ...

Shorthand for removeListener.

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


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


### event

Fires after an event. ...

Fires after an event.
Parametersevent : Ext.direct.EventThe Ext.direct.Event type that occurred.


### exception

Fires after an event exception. ...

Fires after an event exception.
Parametersevent : Ext.direct.EventThe event type that occurred.


## Properties

### $className

**Tipo:** String

...

Defaults to: `'Ext.Base'`


### configMap

**Tipo:** Object

...

Defaults to: `{}`


### eventsSuspended

**Tipo:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called.
Defaults to: `0`


### exceptions

**Tipo:** Object

Exception types. ...

Exception types.
Defaults to: `{TRANSPORT: 'xhr', PARSE: 'parse', DATA: 'data', LOGIN: 'login', SERVER: 'exception'}`


### hasListeners

**Tipo:** Object

This object holds a key for any event that has a listener. ...

This object holds a key for any event that has a listener. The listener may be set
directly on the instance, or on its class or a super class (via observe) or
on the MVC EventBus. The values of this object are truthy
(a non-zero number) and falsy (0 or undefined). They do not represent an exact count
of listeners. The value for an event is truthy if the event must be fired and is
falsy if there is no need to fire the event.

The intended use of this property is to avoid the expense of fireEvent calls when
there are no listeners. This can be particularly helpful when one would otherwise
have to call fireEvent hundreds or thousands of times. It is used like this:

 if (this.hasListeners.foo) {
     this.fireEvent('foo', this, arg1);
 }


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


### isObservable

**Tipo:** Boolean

true in this class to identify an object as an instantiated Observable, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Observable, or subclass thereof.
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


### $onExtended

**Tipo:** Array

...

Defaults to: `[]`


### Ext.direct.Manager

...

ReturnsExt.direct.Manager


### addEvents

Adds the specified events to the list of events which this Observable may fire. ...

Adds the specified events to the list of events which this Observable may fire.
ParameterseventNames : Object/String...Either an object with event names as properties with
a value of `true`. For example:

this.addEvents({
    storeloaded: true,
    storecleared: true
});


Or any number of event names as separate parameters. For example:

this.addEvents('storeloaded', 'storecleared');


### addListener

Appends an event handler to this object. ...

Appends an event handler to this object.  For example:

myGridPanel.on("mouseover", this.onMouseOver, this);


The method also allows for a single argument to be passed which is a config object
containing properties which specify multiple events. For example:

myGridPanel.on({
    cellClick: this.onCellClick,
    mouseover: this.onMouseOver,
    mouseout: this.onMouseOut,
    scope: this // Important. Ensure "this" is correct during handler execution
});


One can also specify options for each event handler separately:

myGridPanel.on({
    cellClick: {fn: this.onCellClick, scope: this, single: true},
    mouseover: {fn: panel.onMouseOver, scope: panel}
});


*Names* of methods in a specified scope may also be used. Note that
`scope` MUST be specified to use this option:

myGridPanel.on({
    cellClick: {fn: 'onCellClick', scope: this, single: true},
    mouseover: {fn: 'onMouseOver', scope: panel}
});

ParameterseventName : String/ObjectThe name of the event to listen for.
May also be an object who's property names are event names.


### addManagedListener

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destr...

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destroyed.
Parametersitem : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### addProvider

Adds an Ext.Direct Provider and creates the proxy or stub methods to execute server-side methods. ...

Adds an Ext.Direct Provider and creates the proxy or stub methods to execute server-side methods. If the provider
is not already connected, it will auto-connect.

 var pollProv = new Ext.direct.PollingProvider({
     url: 'php/poll2.php'
 });

 Ext.direct.Manager.addProvider({
     type: 'remoting',           // create a Ext.direct.RemotingProvider
     url:  'php/router.php',     // url to connect to the Ext.Direct server-side router.
     actions: {                  // each property within the actions object represents a Class
         TestAction: [{          // array of methods within each server side Class
             name: 'doEcho',     // name of method
             len:  1
         }, {
             name: 'multiply',
             len:  1
         }, {
             name: 'doForm',
             formHandler: true   // handle form on server with Ext.Direct.Transaction
         }]
     },
     namespace: 'myApplication', // namespace to create the Remoting Provider in
 }, {
     type: 'polling',            // create a Ext.direct.PollingProvider
     url:  'php/poll.php'
 },
 pollProv);                      // reference to previously created instance

Parametersprovider : Ext.direct.Provider/Object...Accepts any number of Provider descriptions (an instance or config object for
a Provider). Each Provider description instructs Ext.Direct how to create
client-side stub methods.


### addTransaction

Adds a transaction to the manager. ...

Adds a transaction to the manager.
Parameterstransaction : Ext.direct.TransactionThe transaction to add


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


### captureArgs

...

Parameterso : Object


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### configClass

...


### continueFireEvent

Continue to fire event. ...

Continue to fire event.
ParameterseventName : String


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.
ParametersnewName : StringThe name under which to refire the passed parameters.


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if
present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if
present. There is no implementation in the Observable base class.

This is commonly used by Ext.Components to bubble events to owner Containers.
See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the
Component's immediate owner. But if a known target is required, this can be overridden to access the
required target more quickly.

Example:

Ext.define('Ext.overrides.form.field.Base', {
    override: 'Ext.form.field.Base',

    //  Add functionality to Field's initComponent to enable the change event to bubble
    initComponent: function () {
        this.callParent();
        this.enableBubble('change');
    }
});

var myForm = Ext.create('Ext.form.Panel', {
    title: 'User Details',
    items: [{
        ...
    }],
    listeners: {
        change: function() {
            // Title goes red if form has been modified.
            myForm.header.setStyle('color', 'red');
        }
    }
});

ParameterseventNames : String/String[]The event name to bubble, or an Array of event names.


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed
to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed
to addListener).

An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by
calling enableBubble.
ParameterseventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list.

An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by
calling enableBubble.
ParameterseventName : StringThe name of the event to fire.


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable
ReturnsExt.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getConfig

...

Parametersname : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### getProvider

Retrieves a provider by the id specified when the
provider is added. ...

Retrieves a provider by the **id** specified when the
provider is added.
Parametersid : String/Ext.direct.ProviderThe id of the provider, or the provider instance.


### getTransaction

Gets a transaction ...

Gets a transaction
Parameterstransaction : String/Ext.direct.TransactionThe transaction/id of transaction to get


### hasConfig

...

Parametersconfig : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer
indicates whether the event needs firing or not.
ParameterseventName : StringThe name of the event to check for


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


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener.

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destroyed.
Parametersitem : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener.

Removes listeners that were added by the mon method.
Parametersitem : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### on

Shorthand for addListener. ...

Shorthand for addListener.

Appends an event handler to this object.  For example:

myGridPanel.on("mouseover", this.onMouseOver, this);


The method also allows for a single argument to be passed which is a config object
containing properties which specify multiple events. For example:

myGridPanel.on({
    cellClick: this.onCellClick,
    mouseover: this.onMouseOver,
    mouseout: this.onMouseOut,
    scope: this // Important. Ensure "this" is correct during handler execution
});


One can also specify options for each event handler separately:

myGridPanel.on({
    cellClick: {fn: this.onCellClick, scope: this, single: true},
    mouseover: {fn: panel.onMouseOver, scope: panel}
});


*Names* of methods in a specified scope may also be used. Note that
`scope` MUST be specified to use this option:

myGridPanel.on({
    cellClick: {fn: 'onCellClick', scope: this, single: true},
    mouseover: {fn: 'onMouseOver', scope: panel}
});

ParameterseventName : String/ObjectThe name of the event to listen for.
May also be an object who's property names are event names.


### onConfigUpdate

...

Parametersnames : Object


### onProviderData

...

Parametersprovider : Object


### parseMethod

Parses a direct function. ...

Parses a direct function. It may be passed in a string format, for example:
"MyApp.Person.read".
Parametersfn : String/FunctionThe direct function


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a
class derives from this class or uses this class as a mixin.
ParametersT : FunctionThe class constructor to prepare.


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`.

For example if you are extending Grid, you might decide to forward some events from store.
So you can do this inside your initComponent:

this.relayEvents(this.getStore(), ['load']);


The grid instance will then have an observable 'load' event which will be passed the
parameters of the store's load event and any function fired with the grid's load event
would have access to the grid using the `this` keyword.
Parametersorigin : ObjectThe Observable whose events this object is to relay.


### removeListener

Removes an event handler. ...

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


### removeManagedListener

Removes listeners that were added by the mon method. ...

Removes listeners that were added by the mon method.
Parametersitem : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### removeManagedListenerItem

Remove a single managed listener item ...

Remove a single managed listener item
ParametersisClear : BooleanTrue if this is being called during a clear


### removeProvider

Removes the provider. ...

Removes the provider.
Parametersprovider : String/Ext.direct.ProviderThe provider instance or the id of the provider.


### removeTransaction

Removes a transaction from the manager. ...

Removes a transaction from the manager.
Parameterstransaction : String/Ext.direct.TransactionThe transaction/id of transaction to remove


### resumeEvent

Resumes firing of the named event(s). ...

Resumes firing of the named event(s).

After calling this method to resume events, the events will fire when requested to fire.

Note that if the suspendEvent method is called multiple times for a certain event,
this converse method will have to be called the same number of times for it to resume firing.
ParameterseventName : String...Multiple event names to resume.


### resumeEvents

Resumes firing events (see suspendEvents). ...

Resumes firing events (see suspendEvents).

If events were suspended using the `queueSuspended` parameter, then all events fired
during event suspension will be sent to any listeners now.


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


### suspendEvent

Suspends firing of the named event(s). ...

Suspends firing of the named event(s).

After calling this method to suspend events, the events will no longer fire when requested to fire.

Note that if this is called multiple times for a certain event, the converse method
resumeEvent will have to be called the same number of times for it to resume firing.
ParameterseventName : String...Multiple event names to suspend.


### suspendEvents

Suspends the firing of all events. ...

Suspends the firing of all events. (see resumeEvents)
ParametersqueueSuspended : BooleanPass as true to queue up suspended events to be fired
after the resumeEvents call instead of discarding all suspended events.


### un

Shorthand for removeListener. ...

Shorthand for removeListener.

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


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


### event

Fires after an event. ...

Fires after an event.
Parametersevent : Ext.direct.EventThe Ext.direct.Event type that occurred.


### exception

Fires after an event exception. ...

Fires after an event exception.
Parametersevent : Ext.direct.EventThe event type that occurred.


## Methods

### Ext.direct.Manager

...

ReturnsExt.direct.Manager


### addEvents

Adds the specified events to the list of events which this Observable may fire. ...

Adds the specified events to the list of events which this Observable may fire.
ParameterseventNames : Object/String...Either an object with event names as properties with
a value of `true`. For example:

this.addEvents({
    storeloaded: true,
    storecleared: true
});


Or any number of event names as separate parameters. For example:

this.addEvents('storeloaded', 'storecleared');


### addListener

Appends an event handler to this object. ...

Appends an event handler to this object.  For example:

myGridPanel.on("mouseover", this.onMouseOver, this);


The method also allows for a single argument to be passed which is a config object
containing properties which specify multiple events. For example:

myGridPanel.on({
    cellClick: this.onCellClick,
    mouseover: this.onMouseOver,
    mouseout: this.onMouseOut,
    scope: this // Important. Ensure "this" is correct during handler execution
});


One can also specify options for each event handler separately:

myGridPanel.on({
    cellClick: {fn: this.onCellClick, scope: this, single: true},
    mouseover: {fn: panel.onMouseOver, scope: panel}
});


*Names* of methods in a specified scope may also be used. Note that
`scope` MUST be specified to use this option:

myGridPanel.on({
    cellClick: {fn: 'onCellClick', scope: this, single: true},
    mouseover: {fn: 'onMouseOver', scope: panel}
});

ParameterseventName : String/ObjectThe name of the event to listen for.
May also be an object who's property names are event names.


### addManagedListener

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destr...

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destroyed.
Parametersitem : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### addProvider

Adds an Ext.Direct Provider and creates the proxy or stub methods to execute server-side methods. ...

Adds an Ext.Direct Provider and creates the proxy or stub methods to execute server-side methods. If the provider
is not already connected, it will auto-connect.

 var pollProv = new Ext.direct.PollingProvider({
     url: 'php/poll2.php'
 });

 Ext.direct.Manager.addProvider({
     type: 'remoting',           // create a Ext.direct.RemotingProvider
     url:  'php/router.php',     // url to connect to the Ext.Direct server-side router.
     actions: {                  // each property within the actions object represents a Class
         TestAction: [{          // array of methods within each server side Class
             name: 'doEcho',     // name of method
             len:  1
         }, {
             name: 'multiply',
             len:  1
         }, {
             name: 'doForm',
             formHandler: true   // handle form on server with Ext.Direct.Transaction
         }]
     },
     namespace: 'myApplication', // namespace to create the Remoting Provider in
 }, {
     type: 'polling',            // create a Ext.direct.PollingProvider
     url:  'php/poll.php'
 },
 pollProv);                      // reference to previously created instance

Parametersprovider : Ext.direct.Provider/Object...Accepts any number of Provider descriptions (an instance or config object for
a Provider). Each Provider description instructs Ext.Direct how to create
client-side stub methods.


### addTransaction

Adds a transaction to the manager. ...

Adds a transaction to the manager.
Parameterstransaction : Ext.direct.TransactionThe transaction to add


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


### captureArgs

...

Parameterso : Object


### clearListeners

Removes all listeners for this object including the managed listeners ...

Removes all listeners for this object including the managed listeners


### clearManagedListeners

Removes all managed listeners for this object. ...

Removes all managed listeners for this object.


### configClass

...


### continueFireEvent

Continue to fire event. ...

Continue to fire event.
ParameterseventName : String


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.
ParametersnewName : StringThe name under which to refire the passed parameters.


### destroy

...

Overrides: Ext.state.Stateful.destroy, Ext.util.ElementContainer.destroy, Ext.AbstractComponent.destroy, Ext.AbstractPlugin.destroy


### enableBubble

Enables events fired by this Observable to bubble up an owner hierarchy by calling this.getBubbleTarget() if
present. ...

Enables events fired by this Observable to bubble up an owner hierarchy by calling `this.getBubbleTarget()` if
present. There is no implementation in the Observable base class.

This is commonly used by Ext.Components to bubble events to owner Containers.
See Ext.Component.getBubbleTarget. The default implementation in Ext.Component returns the
Component's immediate owner. But if a known target is required, this can be overridden to access the
required target more quickly.

Example:

Ext.define('Ext.overrides.form.field.Base', {
    override: 'Ext.form.field.Base',

    //  Add functionality to Field's initComponent to enable the change event to bubble
    initComponent: function () {
        this.callParent();
        this.enableBubble('change');
    }
});

var myForm = Ext.create('Ext.form.Panel', {
    title: 'User Details',
    items: [{
        ...
    }],
    listeners: {
        change: function() {
            // Title goes red if form has been modified.
            myForm.header.setStyle('color', 'red');
        }
    }
});

ParameterseventNames : String/String[]The event name to bubble, or an Array of event names.


### fireEvent

Fires the specified event with the passed parameters (minus the event name, plus the options object passed
to addList...

Fires the specified event with the passed parameters (minus the event name, plus the `options` object passed
to addListener).

An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by
calling enableBubble.
ParameterseventName : StringThe name of the event to fire.


### fireEventArgs

Fires the specified event with the passed parameter list. ...

Fires the specified event with the passed parameter list.

An event may be set to bubble up an Observable parent hierarchy (See Ext.Component.getBubbleTarget) by
calling enableBubble.
ParameterseventName : StringThe name of the event to fire.


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable
ReturnsExt.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getConfig

...

Parametersname : Object


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### getProvider

Retrieves a provider by the id specified when the
provider is added. ...

Retrieves a provider by the **id** specified when the
provider is added.
Parametersid : String/Ext.direct.ProviderThe id of the provider, or the provider instance.


### getTransaction

Gets a transaction ...

Gets a transaction
Parameterstransaction : String/Ext.direct.TransactionThe transaction/id of transaction to get


### hasConfig

...

Parametersconfig : Object


### hasListener

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. ...

Checks to see if this object has any listeners for a specified event, or whether the event bubbles. The answer
indicates whether the event needs firing or not.
ParameterseventName : StringThe name of the event to check for


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


### mon

Shorthand for addManagedListener. ...

Shorthand for addManagedListener.

Adds listeners to any Observable object (or Ext.Element) which are automatically removed when this Component is
destroyed.
Parametersitem : Ext.util.Observable/Ext.ElementThe item to which to add a listener/listeners.


### mun

Shorthand for removeManagedListener. ...

Shorthand for removeManagedListener.

Removes listeners that were added by the mon method.
Parametersitem : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### on

Shorthand for addListener. ...

Shorthand for addListener.

Appends an event handler to this object.  For example:

myGridPanel.on("mouseover", this.onMouseOver, this);


The method also allows for a single argument to be passed which is a config object
containing properties which specify multiple events. For example:

myGridPanel.on({
    cellClick: this.onCellClick,
    mouseover: this.onMouseOver,
    mouseout: this.onMouseOut,
    scope: this // Important. Ensure "this" is correct during handler execution
});


One can also specify options for each event handler separately:

myGridPanel.on({
    cellClick: {fn: this.onCellClick, scope: this, single: true},
    mouseover: {fn: panel.onMouseOver, scope: panel}
});


*Names* of methods in a specified scope may also be used. Note that
`scope` MUST be specified to use this option:

myGridPanel.on({
    cellClick: {fn: 'onCellClick', scope: this, single: true},
    mouseover: {fn: 'onMouseOver', scope: panel}
});

ParameterseventName : String/ObjectThe name of the event to listen for.
May also be an object who's property names are event names.


### onConfigUpdate

...

Parametersnames : Object


### onProviderData

...

Parametersprovider : Object


### parseMethod

Parses a direct function. ...

Parses a direct function. It may be passed in a string format, for example:
"MyApp.Person.read".
Parametersfn : String/FunctionThe direct function


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a
class derives from this class or uses this class as a mixin.
ParametersT : FunctionThe class constructor to prepare.


### relayEvents

Relays selected events from the specified Observable as if the events were fired by this. ...

Relays selected events from the specified Observable as if the events were fired by `this`.

For example if you are extending Grid, you might decide to forward some events from store.
So you can do this inside your initComponent:

this.relayEvents(this.getStore(), ['load']);


The grid instance will then have an observable 'load' event which will be passed the
parameters of the store's load event and any function fired with the grid's load event
would have access to the grid using the `this` keyword.
Parametersorigin : ObjectThe Observable whose events this object is to relay.


### removeListener

Removes an event handler. ...

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


### removeManagedListener

Removes listeners that were added by the mon method. ...

Removes listeners that were added by the mon method.
Parametersitem : Ext.util.Observable/Ext.ElementThe item from which to remove a listener/listeners.


### removeManagedListenerItem

Remove a single managed listener item ...

Remove a single managed listener item
ParametersisClear : BooleanTrue if this is being called during a clear


### removeProvider

Removes the provider. ...

Removes the provider.
Parametersprovider : String/Ext.direct.ProviderThe provider instance or the id of the provider.


### removeTransaction

Removes a transaction from the manager. ...

Removes a transaction from the manager.
Parameterstransaction : String/Ext.direct.TransactionThe transaction/id of transaction to remove


### resumeEvent

Resumes firing of the named event(s). ...

Resumes firing of the named event(s).

After calling this method to resume events, the events will fire when requested to fire.

Note that if the suspendEvent method is called multiple times for a certain event,
this converse method will have to be called the same number of times for it to resume firing.
ParameterseventName : String...Multiple event names to resume.


### resumeEvents

Resumes firing events (see suspendEvents). ...

Resumes firing events (see suspendEvents).

If events were suspended using the `queueSuspended` parameter, then all events fired
during event suspension will be sent to any listeners now.


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


### suspendEvent

Suspends firing of the named event(s). ...

Suspends firing of the named event(s).

After calling this method to suspend events, the events will no longer fire when requested to fire.

Note that if this is called multiple times for a certain event, the converse method
resumeEvent will have to be called the same number of times for it to resume firing.
ParameterseventName : String...Multiple event names to suspend.


### suspendEvents

Suspends the firing of all events. ...

Suspends the firing of all events. (see resumeEvents)
ParametersqueueSuspended : BooleanPass as true to queue up suspended events to be fired
after the resumeEvents call instead of discarding all suspended events.


### un

Shorthand for removeListener. ...

Shorthand for removeListener.

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


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


### event

Fires after an event. ...

Fires after an event.
Parametersevent : Ext.direct.EventThe Ext.direct.Event type that occurred.


### exception

Fires after an event exception. ...

Fires after an event exception.
Parametersevent : Ext.direct.EventThe event type that occurred.


## Events

### event

Fires after an event. ...

Fires after an event.
Parametersevent : Ext.direct.EventThe Ext.direct.Event type that occurred.


### exception

Fires after an event exception. ...

Fires after an event exception.
Parametersevent : Ext.direct.EventThe event type that occurred.


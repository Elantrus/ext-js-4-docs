# Ext.data.AbstractStore

**Extends:** Ext.Base

## Descrição

AbstractStore is a superclass of Ext.data.Store and Ext.data.TreeStore. It's never used directly,
but offers a set of methods used by both of those subclasses.

We've left it here in the docs for reference purposes, but unless you need to make a whole new type of Store, what
you're probably looking for is Ext.data.Store. If you're still interested, here's a brief description of what
AbstractStore is and is not.

AbstractStore provides the basic configuration for anything that can be considered a Store. It expects to be
given a Model that represents the type of data in the Store. It also expects to be given a
Proxy that handles the loading of data into the Store.

AbstractStore provides a few helpful methods such as load and sync, which load and save data
respectively, passing the requests through the configured proxy. Both built-in Store subclasses add extra
behavior to each of these functions. Note also that each AbstractStore subclass has its own way of storing data -
in Ext.data.Store the data is saved as a flat MixedCollection, whereas in
TreeStore we use a Ext.data.Tree to maintain the data's hierarchy.

The store provides filtering and sorting support. This sorting/filtering can happen on the client side
or can be completed on the server. This is controlled by the remoteSort and
remoteFilter config options. For more information see the sort and
filter methods.

## Config options

### autoLoad

**Tipo:** Boolean/Object

If data is not specified, and if autoLoad is true or an Object, this store's load method is automatically called
afte...

If data is not specified, and if autoLoad is true or an Object, this store's load method is automatically called
after creation. If the value of autoLoad is an Object, this Object will be passed to the store's load method.
        Available since: 2.3.0


### autoSync

**Tipo:** Boolean

True to automatically sync the Store with its Proxy after every edit to one of its Records. ...

True to automatically sync the Store with its Proxy after every edit to one of its Records. Defaults to false.
Defaults to: `false`


### batchUpdateMode

**Tipo:** String

Sets the updating behavior based on batch synchronization. ...

Sets the updating behavior based on batch synchronization. 'operation' (the default) will update the Store's
internal representation of the data after each operation of the batch has completed, 'complete' will wait until
the entire batch has been completed before updating the Store's data. 'complete' is a good choice for local
storage proxies, 'operation' is better for remote proxies, where there is a comparatively high latency.
Defaults to: `'operation'`


### defaultSortDirection

**Tipo:** String

The default sort direction to use if one is not specified. ...

The default sort direction to use if one is not specified.
Defaults to: `"ASC"`


### fields

**Tipo:** Object[]

This may be used in place of specifying a model configuration. ...

This may be used in place of specifying a model configuration. The fields should be a
set of Ext.data.Field configuration objects. The store will automatically create a Ext.data.Model
with these fields. In general this configuration option should only be used for simple stores like
a two-field store of ComboBox. For anything more complicated, such as specifying a particular id property or
associations, a Ext.data.Model should be defined and specified for the model
config.
        Available since: 2.3.0


### filterOnLoad

**Tipo:** Boolean

If true, any filters attached to this Store will be run after loading data, before the datachanged event is fired. ...

If true, any filters attached to this Store will be run after loading data, before the datachanged event is fired.
Defaults to true, ignored if remoteFilter is true
Defaults to: `true`


### filters

**Tipo:** Object[]/Function[]

Array of Filters for this store. ...

Array of Filters for this store. Can also be passed array of
functions which will be used as the filterFn config
for filters:

filters: [
    function(item) {
        return item.weight > 0;
    }
]


To filter after the grid is loaded use the filterBy function.


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


### model

**Tipo:** String

Name of the Model associated with this store. ...

Name of the Model associated with this store.
The string is used as an argument for Ext.ModelManager.getModel.


### proxy

**Tipo:** String/Ext.data.proxy.Proxy/Object

The Proxy to use for this Store. ...

The Proxy to use for this Store. This can be either a string, a config object or a Proxy instance -
see setProxy for details.
        Available since: 1.1.0


### remoteFilter

**Tipo:** Boolean

True to defer any filtering operation to the server. ...

True to defer any filtering operation to the server. If false, filtering is done locally on the client.
Defaults to: `false`


### remoteSort

**Tipo:** Boolean

True to defer any sorting operation to the server. ...

True to defer any sorting operation to the server. If false, sorting is done locally on the client.
Defaults to: `false`


### sortOnLoad

**Tipo:** Boolean

If true, any sorters attached to this Store will be run after loading data, before the datachanged event is fired. ...

If true, any sorters attached to this Store will be run after loading data, before the datachanged event is fired.
Defaults to true, igored if remoteSort is true
Defaults to: `true`


### sortRoot

**Tipo:** String

The property in each item that contains the data to sort.


### sorters

**Tipo:** Ext.util.Sorter[]/Object[]

The initial set of Sorters


### statefulFilters

**Tipo:** Boolean

Configure as true to have the filters saved when a client grid saves its state. ...

Configure as `true` to have the filters saved when a client grid saves its state.
Defaults to: `false`


### storeId

**Tipo:** String

Unique identifier for this store. ...

Unique identifier for this store. If present, this Store will be registered with the Ext.data.StoreManager,
making it easy to reuse elsewhere.

Note that when store is instatiated by Controller, the storeId will be overridden by the name of the store.


### $className

**Tipo:** String

...

Defaults to: `'Ext.Base'`


### configMap

**Tipo:** Object

...

Defaults to: `{}`


### defaultProxyType

**Tipo:** String

The string type of the Proxy to create if none is specified. ...

The string type of the Proxy to create if none is specified. This defaults to creating a
memory proxy.
Defaults to: `'memory'`


### eventsSuspended

**Tipo:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called.
Defaults to: `0`


### filters

**Tipo:** Ext.util.MixedCollection

The collection of Filters currently applied to this Store


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


### implicitModel

**Tipo:** Boolean

True if a model was created implicitly for this Store. ...

True if a model was created implicitly for this Store. This happens if a fields array is passed to the Store's
constructor instead of a model constructor or name.
Defaults to: `false`


### initConfigList

**Tipo:** Array

...

Defaults to: `[]`


### initConfigMap

**Tipo:** Object

...

Defaults to: `{}`


### isDestroyed

**Tipo:** Boolean

True if the Store has already been destroyed. ...

True if the Store has already been destroyed. If this is true, the reference to Store should be deleted
as it will not function correctly any more.
Defaults to: `false`        Available since: 3.4.0


### isInstance

**Tipo:** Boolean

...

Defaults to: `true`


### isObservable

**Tipo:** Boolean

true in this class to identify an object as an instantiated Observable, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Observable, or subclass thereof.
Defaults to: `true`


### isSortable

**Tipo:** Boolean

true in this class to identify an object as an instantiated Sortable, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Sortable, or subclass thereof.
Defaults to: `true`


### isStore

**Tipo:** Boolean

true in this class to identify an object as an instantiated Store, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Store, or subclass thereof.
Defaults to: `true`


### modelDefaults

**Tipo:** Object

A set of default values to be applied to every model instance added via insert or created
via createModel. ...

A set of default values to be applied to every model instance added via insert or created
via createModel. This is used internally by associations to set foreign keys and
other fields. See the Association classes source code for examples. This should not need to be used by application developers.


### removed

**Tipo:** Ext.data.Model[]

Temporary cache in which removed model instances are kept until successfully synchronised with a Proxy,
at which poin...

Temporary cache in which removed model instances are kept until successfully synchronised with a Proxy,
at which point this is cleared.


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


### sorters

**Tipo:** Ext.util.MixedCollection

The collection of Sorters currently applied to this Store


### $onExtended

**Tipo:** Array

...

Defaults to: `[]`


### Ext.data.AbstractStore

documented above ...

documented above
Parametersconfig : Object


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


### afterCommit

A model instance should call this method on the Store it has been joined to. ...

A model instance should call this method on the Store it has been joined to.
        Available since: 3.4.0
Parametersrecord : Ext.data.ModelThe model instance that was edited


### afterEdit

A model instance should call this method on the Store it has been joined to. ...

A model instance should call this method on the Store it has been joined to.
        Available since: 3.4.0
Parametersrecord : Ext.data.ModelThe model instance that was edited


### afterReject

A model instance should call this method on the Store it has been joined to.. ...

A model instance should call this method on the Store it has been joined to..
        Available since: 3.4.0
Parametersrecord : Ext.data.ModelThe model instance that was edited


### applyState

Restores state to the passed state ...

Restores state to the passed state
Parametersstate : Object


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


### clearData

to be implemented by subclasses ...

to be implemented by subclasses


### clearFilter

...

ParameterssupressEvent : Object


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


### create

saves any phantom records ...

saves any phantom records
Parametersdata : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.
ParametersnewName : StringThe name under which to refire the passed parameters.


### decodeFilters

Normalizes an array of filter objects, ensuring that they are all Ext.util.Filter instances ...

Normalizes an array of filter objects, ensuring that they are all Ext.util.Filter instances
Parametersfilters : Object[]The filters array


### decodeSorters

Normalizes an array of sorter objects, ensuring that they are all Ext.util.Sorter instances ...

Normalizes an array of sorter objects, ensuring that they are all Ext.util.Sorter instances
Parameterssorters : Object[]The sorters array


### destroy

tells the attached proxy to destroy the given records ...

tells the attached proxy to destroy the given records
        Available since: 3.4.0
Overrides: Ext.Base.destroy


### destroyStore

private ...

private


### doSort

private ...

private
ParameterssorterFn : Object


### emptyComparator

...


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


### filter

...

Parametersfilters : Object


### filterBy

...

Parametersfn : Object


### filterNew

Filter function for new records. ...

Filter function for new records.
Parametersitem : Object


### filterUpdated

Filter function for updated records. ...

Filter function for updated records.
Parametersitem : Object


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


### generateComparator

Returns a comparator function which compares two items and returns -1, 0, or 1 depending
on the currently defined set...

Returns a comparator function which compares two items and returns -1, 0, or 1 depending
on the currently defined set of sorters.

If there are no sorters defined, it returns a function which returns `0` meaning
that no sorting will occur.


### getBatchListeners

Returns an object which is passed in as the listeners argument to proxy.batch inside this.sync. ...

Returns an object which is passed in as the listeners argument to proxy.batch inside this.sync.
This is broken out into a separate function to allow for customisation of the listeners
ReturnsObjectThe listeners object


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable
ReturnsExt.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getById

to be implemented by subclasses ...

to be implemented by subclasses


### getConfig

...

Parametersname : Object


### getCount

to be implemented by subclasses ...

to be implemented by subclasses


### getFirstSorter

Gets the first sorter from the sorters collection, excluding
any groupers that may be in place ...

Gets the first sorter from the sorters collection, excluding
any groupers that may be in place
ReturnsExt.util.SorterThe sorter, null if none exist


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### getModifiedRecords

Gets all records added or updated since the last commit. ...

Gets all records added or updated since the last commit. Note that the order of records
returned is not deterministic and does not indicate the order in which records were modified. Note also that
removed records are not included (use getRemovedRecords for that).
ReturnsExt.data.Model[]The added and updated Model instances


### getNewRecords

Returns all Model instances that are either currently a phantom (e.g. ...

Returns all Model instances that are either currently a phantom (e.g. have no id), or have an ID but have not
yet been saved on this Store (this happens when adding a non-phantom record from another Store into this one)
ReturnsExt.data.Model[]The Model instances


### getProxy

Returns the proxy currently attached to this proxy instance ...

Returns the proxy currently attached to this proxy instance
ReturnsExt.data.proxy.ProxyThe Proxy instance


### getRemovedRecords

Returns any records that have been removed from the store but not yet destroyed on the proxy. ...

Returns any records that have been removed from the store but not yet destroyed on the proxy.
ReturnsExt.data.Model[]The removed Model instances


### getSorters

...


### getState

Returns the grouping, sorting and filtered state of this Store. ...

Returns the grouping, sorting and filtered state of this Store.


### getUpdatedRecords

Returns all Model instances that have been updated in the Store but not yet synchronized with the Proxy ...

Returns all Model instances that have been updated in the Store but not yet synchronized with the Proxy
ReturnsExt.data.Model[]The updated Model instances


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


### initSortable

Performs initialization of this mixin. ...

Performs initialization of this mixin. Component classes using this mixin should call this method during their
own initialization.


### isFiltered

...


### isLoading

Returns true if the Store is currently performing a load operation ...

Returns true if the Store is currently performing a load operation
ReturnsBooleanTrue if the Store is currently loading


### load

Loads the Store using its configured proxy. ...

Loads the Store using its configured proxy.
        Available since: 1.1.0
Parametersoptions : Object (optional)config object. This is passed into the Operation
object that is created and then sent to the proxy's Ext.data.proxy.Proxy.read function


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


### onBatchComplete

Attached as the 'complete' event listener to a proxy's Batch object. ...

Attached as the 'complete' event listener to a proxy's Batch object. Iterates over the batch operations
and updates the Store's internal data MixedCollection.
Parametersbatch : Object


### onBatchException

...

Parametersbatch : Object


### onBatchOperationComplete

Attached as the 'operationcomplete' event listener to a proxy's Batch object. ...

Attached as the 'operationcomplete' event listener to a proxy's Batch object. By default just calls through
to onProxyWrite.
Parametersbatch : Object


### onBeforeSort

...


### onClassExtended

...

Parameterscls : Object


### onConfigUpdate

...

Parametersnames : Object


### onCreateRecords

may be implemented by store subclasses ...

may be implemented by store subclasses


### onDestroyRecords

Removes any records when a write is returned from the server. ...

Removes any records when a write is returned from the server.
Parametersrecords : Ext.data.Model[]The array of removed records


### onIdChanged

...

Parametersmodel : Object


### onMetaChange

private ...

private
Parametersproxy : Object


### onProxyWrite

Callback for any write Operation over the Proxy. ...

Callback for any write Operation over the Proxy. Updates the Store's MixedCollection to reflect
the updates provided by the Proxy
Parametersoperation : Object


### onUpdate

...


### onUpdateRecords

may be implemented by store subclasses ...

may be implemented by store subclasses


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a
class derives from this class or uses this class as a mixin.
ParametersT : FunctionThe class constructor to prepare.


### read

...


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


### reload

Reloads the store using the last options passed to the load method. ...

Reloads the store using the last options passed to the load method.
Parametersoptions : ObjectA config object which contains options which may override the options passed to the previous load call.


### removeAll

Removes all records from the store. ...

Removes all records from the store. This method does a "fast remove",
individual remove events are not called. The clear event is
fired upon completion.
        Available since: 1.1.0


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


### resumeAutoSync

Resumes automatically syncing the Store with its Proxy. ...

Resumes automatically syncing the Store with its Proxy.  Only applicable if autoSync is `true`


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


### save

Saves all pending changes via the configured proxy. ...

Saves all pending changes via the configured proxy. Use sync instead.
        
        This method has been **deprecated** since 4.0.0
        Will be removed in the next major version


### setConfig

...

Parametersconfig : Object


### setProxy

Sets the Store's Proxy by string, config object or Proxy instance ...

Sets the Store's Proxy by string, config object or Proxy instance
Parametersproxy : String/Object/Ext.data.proxy.ProxyThe new Proxy, which can be either a type string, a configuration object
or an Ext.data.proxy.Proxy instance


### sort

Sorts the data in the Store by one or more of its properties. ...

Sorts the data in the Store by one or more of its properties. Example usage:

//sort by a single field
myStore.sort('myField', 'DESC');

//sorting by multiple fields
myStore.sort([
    {
        property : 'age',
        direction: 'ASC'
    },
    {
        property : 'name',
        direction: 'DESC'
    }
]);


Internally, Store converts the passed arguments into an array of Ext.util.Sorter instances, and delegates
the actual sorting to its internal Ext.util.MixedCollection.

When passing a single string argument to sort, Store maintains a ASC/DESC toggler per field, so this code:

store.sort('myField');
store.sort('myField');


Is equivalent to this code, because Store handles the toggling automatically:

store.sort('myField', 'ASC');
store.sort('myField', 'DESC');

Parameterssorters : String/Ext.util.Sorter[] (optional)Either a string name of one of the fields in this Store's configured
Model, or an array of sorter configurations.


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


### suspendAutoSync

Suspends automatically syncing the Store with its Proxy. ...

Suspends automatically syncing the Store with its Proxy.  Only applicable if autoSync is `true`


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


### sync

Synchronizes the store with its proxy. ...

Synchronizes the store with its proxy. This asks the proxy to batch together any new, updated
and deleted records in the store, updating the store's internal representation of the records
as each operation completes.
Parametersoptions : Object (optional)Object containing one or more properties supported by the sync method (these get
passed along to the underlying proxy's batch method):
batch : Ext.data.Batch/Object (optional)A Ext.data.Batch object (or batch config to apply
to the created batch). If unspecified a default batch will be auto-created as needed.


### un

Shorthand for removeListener. ...

Shorthand for removeListener.

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


### update

...

Parametersoptions : Object


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

Creates a store from config object. ...

Creates a store from config object.
Parametersstore : Object/Ext.data.AbstractStoreA config for
the store to be created.  It may contain a `type` field
which defines the particular type of store to create.

Alteratively passing an actual store to this method will
just return it, no changes made.


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


### add

Fired when a Model instance has been added to this Store. ...

Fired when a Model instance has been added to this Store.
        Available since: 1.1.0
Parametersstore : Ext.data.StoreThe store


### beforeload

Fires before a request is made for a new data object. ...

Fires before a request is made for a new data object. If the beforeload handler returns false the load
action will be canceled.
        Available since: 1.1.0
Parametersstore : Ext.data.StoreThis Store


### beforesync

Fired before a call to sync is executed. ...

Fired before a call to sync is executed. Return false from any listener to cancel the sync
Parametersoptions : ObjectHash of all records to be synchronized, broken down into create, update and destroy


### bulkremove

Fired at the end of the remove method when all records in the passed array have been removed. ...

Fired at the *end* of the remove method when all records in the passed array have been removed.

If many records may be removed in one go, then it is more efficient to listen for this event
and perform any processing for a bulk remove than to listen for many remove events.
Parametersstore : Ext.data.StoreThe Store object


### clear

Fired after the removeAll method is called. ...

Fired after the removeAll method is called.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### datachanged

Fires whenever the records in the Store have changed in some way - this could include adding or removing
records, or ...

Fires whenever the records in the Store have changed in some way - this could include adding or removing
records, or updating the data in existing records
        Available since: 1.1.0
Parametersthis : Ext.data.StoreThe data store


### load

Fires whenever the store reads data from a remote data source. ...

Fires whenever the store reads data from a remote data source.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### metachange

Fires when this store's underlying reader (available via the proxy) provides new metadata. ...

Fires when this store's underlying reader (available via the proxy) provides new metadata.
Metadata usually consists of new field definitions, but can include any configuration data
required by an application, and can be processed as needed in the event handler.
This event is currently only fired for JsonReaders.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### refresh

Fires when the data cache has changed in a bulk manner (e.g., it has been sorted, filtered, etc.) and a
widget that i...

Fires when the data cache has changed in a bulk manner (e.g., it has been sorted, filtered, etc.) and a
widget that is using this Store as a Record cache should refresh its view.
Parametersthis : Ext.data.StoreThe data store


### remove

Fired when a Model instance has been removed from this Store. ...

Fired when a Model instance has been removed from this Store.

If many records may be removed in one go, then it is more efficient to listen for the bulkremove event
and perform any processing for a bulk remove than to listen for this remove event.
        Available since: 1.1.0
Parametersstore : Ext.data.StoreThe Store object


### update

Fires when a Model instance has been updated. ...

Fires when a Model instance has been updated.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### write

Fires whenever a successful write has been made via the configured Proxy ...

Fires whenever a successful write has been made via the configured Proxy
        Available since: 3.4.0
Parametersstore : Ext.data.StoreThis Store


## Properties

### $className

**Tipo:** String

...

Defaults to: `'Ext.Base'`


### configMap

**Tipo:** Object

...

Defaults to: `{}`


### defaultProxyType

**Tipo:** String

The string type of the Proxy to create if none is specified. ...

The string type of the Proxy to create if none is specified. This defaults to creating a
memory proxy.
Defaults to: `'memory'`


### eventsSuspended

**Tipo:** Number

Initial suspended call count. ...

Initial suspended call count. Incremented when suspendEvents is called, decremented when resumeEvents is called.
Defaults to: `0`


### filters

**Tipo:** Ext.util.MixedCollection

The collection of Filters currently applied to this Store


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


### implicitModel

**Tipo:** Boolean

True if a model was created implicitly for this Store. ...

True if a model was created implicitly for this Store. This happens if a fields array is passed to the Store's
constructor instead of a model constructor or name.
Defaults to: `false`


### initConfigList

**Tipo:** Array

...

Defaults to: `[]`


### initConfigMap

**Tipo:** Object

...

Defaults to: `{}`


### isDestroyed

**Tipo:** Boolean

True if the Store has already been destroyed. ...

True if the Store has already been destroyed. If this is true, the reference to Store should be deleted
as it will not function correctly any more.
Defaults to: `false`        Available since: 3.4.0


### isInstance

**Tipo:** Boolean

...

Defaults to: `true`


### isObservable

**Tipo:** Boolean

true in this class to identify an object as an instantiated Observable, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Observable, or subclass thereof.
Defaults to: `true`


### isSortable

**Tipo:** Boolean

true in this class to identify an object as an instantiated Sortable, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Sortable, or subclass thereof.
Defaults to: `true`


### isStore

**Tipo:** Boolean

true in this class to identify an object as an instantiated Store, or subclass thereof. ...

`true` in this class to identify an object as an instantiated Store, or subclass thereof.
Defaults to: `true`


### modelDefaults

**Tipo:** Object

A set of default values to be applied to every model instance added via insert or created
via createModel. ...

A set of default values to be applied to every model instance added via insert or created
via createModel. This is used internally by associations to set foreign keys and
other fields. See the Association classes source code for examples. This should not need to be used by application developers.


### removed

**Tipo:** Ext.data.Model[]

Temporary cache in which removed model instances are kept until successfully synchronised with a Proxy,
at which poin...

Temporary cache in which removed model instances are kept until successfully synchronised with a Proxy,
at which point this is cleared.


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


### sorters

**Tipo:** Ext.util.MixedCollection

The collection of Sorters currently applied to this Store


### $onExtended

**Tipo:** Array

...

Defaults to: `[]`


### Ext.data.AbstractStore

documented above ...

documented above
Parametersconfig : Object


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


### afterCommit

A model instance should call this method on the Store it has been joined to. ...

A model instance should call this method on the Store it has been joined to.
        Available since: 3.4.0
Parametersrecord : Ext.data.ModelThe model instance that was edited


### afterEdit

A model instance should call this method on the Store it has been joined to. ...

A model instance should call this method on the Store it has been joined to.
        Available since: 3.4.0
Parametersrecord : Ext.data.ModelThe model instance that was edited


### afterReject

A model instance should call this method on the Store it has been joined to.. ...

A model instance should call this method on the Store it has been joined to..
        Available since: 3.4.0
Parametersrecord : Ext.data.ModelThe model instance that was edited


### applyState

Restores state to the passed state ...

Restores state to the passed state
Parametersstate : Object


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


### clearData

to be implemented by subclasses ...

to be implemented by subclasses


### clearFilter

...

ParameterssupressEvent : Object


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


### create

saves any phantom records ...

saves any phantom records
Parametersdata : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.
ParametersnewName : StringThe name under which to refire the passed parameters.


### decodeFilters

Normalizes an array of filter objects, ensuring that they are all Ext.util.Filter instances ...

Normalizes an array of filter objects, ensuring that they are all Ext.util.Filter instances
Parametersfilters : Object[]The filters array


### decodeSorters

Normalizes an array of sorter objects, ensuring that they are all Ext.util.Sorter instances ...

Normalizes an array of sorter objects, ensuring that they are all Ext.util.Sorter instances
Parameterssorters : Object[]The sorters array


### destroy

tells the attached proxy to destroy the given records ...

tells the attached proxy to destroy the given records
        Available since: 3.4.0
Overrides: Ext.Base.destroy


### destroyStore

private ...

private


### doSort

private ...

private
ParameterssorterFn : Object


### emptyComparator

...


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


### filter

...

Parametersfilters : Object


### filterBy

...

Parametersfn : Object


### filterNew

Filter function for new records. ...

Filter function for new records.
Parametersitem : Object


### filterUpdated

Filter function for updated records. ...

Filter function for updated records.
Parametersitem : Object


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


### generateComparator

Returns a comparator function which compares two items and returns -1, 0, or 1 depending
on the currently defined set...

Returns a comparator function which compares two items and returns -1, 0, or 1 depending
on the currently defined set of sorters.

If there are no sorters defined, it returns a function which returns `0` meaning
that no sorting will occur.


### getBatchListeners

Returns an object which is passed in as the listeners argument to proxy.batch inside this.sync. ...

Returns an object which is passed in as the listeners argument to proxy.batch inside this.sync.
This is broken out into a separate function to allow for customisation of the listeners
ReturnsObjectThe listeners object


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable
ReturnsExt.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getById

to be implemented by subclasses ...

to be implemented by subclasses


### getConfig

...

Parametersname : Object


### getCount

to be implemented by subclasses ...

to be implemented by subclasses


### getFirstSorter

Gets the first sorter from the sorters collection, excluding
any groupers that may be in place ...

Gets the first sorter from the sorters collection, excluding
any groupers that may be in place
ReturnsExt.util.SorterThe sorter, null if none exist


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### getModifiedRecords

Gets all records added or updated since the last commit. ...

Gets all records added or updated since the last commit. Note that the order of records
returned is not deterministic and does not indicate the order in which records were modified. Note also that
removed records are not included (use getRemovedRecords for that).
ReturnsExt.data.Model[]The added and updated Model instances


### getNewRecords

Returns all Model instances that are either currently a phantom (e.g. ...

Returns all Model instances that are either currently a phantom (e.g. have no id), or have an ID but have not
yet been saved on this Store (this happens when adding a non-phantom record from another Store into this one)
ReturnsExt.data.Model[]The Model instances


### getProxy

Returns the proxy currently attached to this proxy instance ...

Returns the proxy currently attached to this proxy instance
ReturnsExt.data.proxy.ProxyThe Proxy instance


### getRemovedRecords

Returns any records that have been removed from the store but not yet destroyed on the proxy. ...

Returns any records that have been removed from the store but not yet destroyed on the proxy.
ReturnsExt.data.Model[]The removed Model instances


### getSorters

...


### getState

Returns the grouping, sorting and filtered state of this Store. ...

Returns the grouping, sorting and filtered state of this Store.


### getUpdatedRecords

Returns all Model instances that have been updated in the Store but not yet synchronized with the Proxy ...

Returns all Model instances that have been updated in the Store but not yet synchronized with the Proxy
ReturnsExt.data.Model[]The updated Model instances


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


### initSortable

Performs initialization of this mixin. ...

Performs initialization of this mixin. Component classes using this mixin should call this method during their
own initialization.


### isFiltered

...


### isLoading

Returns true if the Store is currently performing a load operation ...

Returns true if the Store is currently performing a load operation
ReturnsBooleanTrue if the Store is currently loading


### load

Loads the Store using its configured proxy. ...

Loads the Store using its configured proxy.
        Available since: 1.1.0
Parametersoptions : Object (optional)config object. This is passed into the Operation
object that is created and then sent to the proxy's Ext.data.proxy.Proxy.read function


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


### onBatchComplete

Attached as the 'complete' event listener to a proxy's Batch object. ...

Attached as the 'complete' event listener to a proxy's Batch object. Iterates over the batch operations
and updates the Store's internal data MixedCollection.
Parametersbatch : Object


### onBatchException

...

Parametersbatch : Object


### onBatchOperationComplete

Attached as the 'operationcomplete' event listener to a proxy's Batch object. ...

Attached as the 'operationcomplete' event listener to a proxy's Batch object. By default just calls through
to onProxyWrite.
Parametersbatch : Object


### onBeforeSort

...


### onClassExtended

...

Parameterscls : Object


### onConfigUpdate

...

Parametersnames : Object


### onCreateRecords

may be implemented by store subclasses ...

may be implemented by store subclasses


### onDestroyRecords

Removes any records when a write is returned from the server. ...

Removes any records when a write is returned from the server.
Parametersrecords : Ext.data.Model[]The array of removed records


### onIdChanged

...

Parametersmodel : Object


### onMetaChange

private ...

private
Parametersproxy : Object


### onProxyWrite

Callback for any write Operation over the Proxy. ...

Callback for any write Operation over the Proxy. Updates the Store's MixedCollection to reflect
the updates provided by the Proxy
Parametersoperation : Object


### onUpdate

...


### onUpdateRecords

may be implemented by store subclasses ...

may be implemented by store subclasses


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a
class derives from this class or uses this class as a mixin.
ParametersT : FunctionThe class constructor to prepare.


### read

...


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


### reload

Reloads the store using the last options passed to the load method. ...

Reloads the store using the last options passed to the load method.
Parametersoptions : ObjectA config object which contains options which may override the options passed to the previous load call.


### removeAll

Removes all records from the store. ...

Removes all records from the store. This method does a "fast remove",
individual remove events are not called. The clear event is
fired upon completion.
        Available since: 1.1.0


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


### resumeAutoSync

Resumes automatically syncing the Store with its Proxy. ...

Resumes automatically syncing the Store with its Proxy.  Only applicable if autoSync is `true`


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


### save

Saves all pending changes via the configured proxy. ...

Saves all pending changes via the configured proxy. Use sync instead.
        
        This method has been **deprecated** since 4.0.0
        Will be removed in the next major version


### setConfig

...

Parametersconfig : Object


### setProxy

Sets the Store's Proxy by string, config object or Proxy instance ...

Sets the Store's Proxy by string, config object or Proxy instance
Parametersproxy : String/Object/Ext.data.proxy.ProxyThe new Proxy, which can be either a type string, a configuration object
or an Ext.data.proxy.Proxy instance


### sort

Sorts the data in the Store by one or more of its properties. ...

Sorts the data in the Store by one or more of its properties. Example usage:

//sort by a single field
myStore.sort('myField', 'DESC');

//sorting by multiple fields
myStore.sort([
    {
        property : 'age',
        direction: 'ASC'
    },
    {
        property : 'name',
        direction: 'DESC'
    }
]);


Internally, Store converts the passed arguments into an array of Ext.util.Sorter instances, and delegates
the actual sorting to its internal Ext.util.MixedCollection.

When passing a single string argument to sort, Store maintains a ASC/DESC toggler per field, so this code:

store.sort('myField');
store.sort('myField');


Is equivalent to this code, because Store handles the toggling automatically:

store.sort('myField', 'ASC');
store.sort('myField', 'DESC');

Parameterssorters : String/Ext.util.Sorter[] (optional)Either a string name of one of the fields in this Store's configured
Model, or an array of sorter configurations.


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


### suspendAutoSync

Suspends automatically syncing the Store with its Proxy. ...

Suspends automatically syncing the Store with its Proxy.  Only applicable if autoSync is `true`


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


### sync

Synchronizes the store with its proxy. ...

Synchronizes the store with its proxy. This asks the proxy to batch together any new, updated
and deleted records in the store, updating the store's internal representation of the records
as each operation completes.
Parametersoptions : Object (optional)Object containing one or more properties supported by the sync method (these get
passed along to the underlying proxy's batch method):
batch : Ext.data.Batch/Object (optional)A Ext.data.Batch object (or batch config to apply
to the created batch). If unspecified a default batch will be auto-created as needed.


### un

Shorthand for removeListener. ...

Shorthand for removeListener.

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


### update

...

Parametersoptions : Object


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

Creates a store from config object. ...

Creates a store from config object.
Parametersstore : Object/Ext.data.AbstractStoreA config for
the store to be created.  It may contain a `type` field
which defines the particular type of store to create.

Alteratively passing an actual store to this method will
just return it, no changes made.


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


### add

Fired when a Model instance has been added to this Store. ...

Fired when a Model instance has been added to this Store.
        Available since: 1.1.0
Parametersstore : Ext.data.StoreThe store


### beforeload

Fires before a request is made for a new data object. ...

Fires before a request is made for a new data object. If the beforeload handler returns false the load
action will be canceled.
        Available since: 1.1.0
Parametersstore : Ext.data.StoreThis Store


### beforesync

Fired before a call to sync is executed. ...

Fired before a call to sync is executed. Return false from any listener to cancel the sync
Parametersoptions : ObjectHash of all records to be synchronized, broken down into create, update and destroy


### bulkremove

Fired at the end of the remove method when all records in the passed array have been removed. ...

Fired at the *end* of the remove method when all records in the passed array have been removed.

If many records may be removed in one go, then it is more efficient to listen for this event
and perform any processing for a bulk remove than to listen for many remove events.
Parametersstore : Ext.data.StoreThe Store object


### clear

Fired after the removeAll method is called. ...

Fired after the removeAll method is called.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### datachanged

Fires whenever the records in the Store have changed in some way - this could include adding or removing
records, or ...

Fires whenever the records in the Store have changed in some way - this could include adding or removing
records, or updating the data in existing records
        Available since: 1.1.0
Parametersthis : Ext.data.StoreThe data store


### load

Fires whenever the store reads data from a remote data source. ...

Fires whenever the store reads data from a remote data source.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### metachange

Fires when this store's underlying reader (available via the proxy) provides new metadata. ...

Fires when this store's underlying reader (available via the proxy) provides new metadata.
Metadata usually consists of new field definitions, but can include any configuration data
required by an application, and can be processed as needed in the event handler.
This event is currently only fired for JsonReaders.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### refresh

Fires when the data cache has changed in a bulk manner (e.g., it has been sorted, filtered, etc.) and a
widget that i...

Fires when the data cache has changed in a bulk manner (e.g., it has been sorted, filtered, etc.) and a
widget that is using this Store as a Record cache should refresh its view.
Parametersthis : Ext.data.StoreThe data store


### remove

Fired when a Model instance has been removed from this Store. ...

Fired when a Model instance has been removed from this Store.

If many records may be removed in one go, then it is more efficient to listen for the bulkremove event
and perform any processing for a bulk remove than to listen for this remove event.
        Available since: 1.1.0
Parametersstore : Ext.data.StoreThe Store object


### update

Fires when a Model instance has been updated. ...

Fires when a Model instance has been updated.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### write

Fires whenever a successful write has been made via the configured Proxy ...

Fires whenever a successful write has been made via the configured Proxy
        Available since: 3.4.0
Parametersstore : Ext.data.StoreThis Store


## Methods

### Ext.data.AbstractStore

documented above ...

documented above
Parametersconfig : Object


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


### afterCommit

A model instance should call this method on the Store it has been joined to. ...

A model instance should call this method on the Store it has been joined to.
        Available since: 3.4.0
Parametersrecord : Ext.data.ModelThe model instance that was edited


### afterEdit

A model instance should call this method on the Store it has been joined to. ...

A model instance should call this method on the Store it has been joined to.
        Available since: 3.4.0
Parametersrecord : Ext.data.ModelThe model instance that was edited


### afterReject

A model instance should call this method on the Store it has been joined to.. ...

A model instance should call this method on the Store it has been joined to..
        Available since: 3.4.0
Parametersrecord : Ext.data.ModelThe model instance that was edited


### applyState

Restores state to the passed state ...

Restores state to the passed state
Parametersstate : Object


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


### clearData

to be implemented by subclasses ...

to be implemented by subclasses


### clearFilter

...

ParameterssupressEvent : Object


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


### create

saves any phantom records ...

saves any phantom records
Parametersdata : Object


### createRelayer

Creates an event handling function which refires the event from this object as the passed event name. ...

Creates an event handling function which refires the event from this object as the passed event name.
ParametersnewName : StringThe name under which to refire the passed parameters.


### decodeFilters

Normalizes an array of filter objects, ensuring that they are all Ext.util.Filter instances ...

Normalizes an array of filter objects, ensuring that they are all Ext.util.Filter instances
Parametersfilters : Object[]The filters array


### decodeSorters

Normalizes an array of sorter objects, ensuring that they are all Ext.util.Sorter instances ...

Normalizes an array of sorter objects, ensuring that they are all Ext.util.Sorter instances
Parameterssorters : Object[]The sorters array


### destroy

tells the attached proxy to destroy the given records ...

tells the attached proxy to destroy the given records
        Available since: 3.4.0
Overrides: Ext.Base.destroy


### destroyStore

private ...

private


### doSort

private ...

private
ParameterssorterFn : Object


### emptyComparator

...


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


### filter

...

Parametersfilters : Object


### filterBy

...

Parametersfn : Object


### filterNew

Filter function for new records. ...

Filter function for new records.
Parametersitem : Object


### filterUpdated

Filter function for updated records. ...

Filter function for updated records.
Parametersitem : Object


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


### generateComparator

Returns a comparator function which compares two items and returns -1, 0, or 1 depending
on the currently defined set...

Returns a comparator function which compares two items and returns -1, 0, or 1 depending
on the currently defined set of sorters.

If there are no sorters defined, it returns a function which returns `0` meaning
that no sorting will occur.


### getBatchListeners

Returns an object which is passed in as the listeners argument to proxy.batch inside this.sync. ...

Returns an object which is passed in as the listeners argument to proxy.batch inside this.sync.
This is broken out into a separate function to allow for customisation of the listeners
ReturnsObjectThe listeners object


### getBubbleParent

Gets the bubbling parent for an Observable ...

Gets the bubbling parent for an Observable
ReturnsExt.util.ObservableThe bubble parent. null is returned if no bubble target exists


### getById

to be implemented by subclasses ...

to be implemented by subclasses


### getConfig

...

Parametersname : Object


### getCount

to be implemented by subclasses ...

to be implemented by subclasses


### getFirstSorter

Gets the first sorter from the sorters collection, excluding
any groupers that may be in place ...

Gets the first sorter from the sorters collection, excluding
any groupers that may be in place
ReturnsExt.util.SorterThe sorter, null if none exist


### getInitialConfig

Returns the initial configuration passed to constructor when instantiating
this class. ...

Returns the initial configuration passed to constructor when instantiating
this class.
Parametersname : String (optional)Name of the config option to return.


### getModifiedRecords

Gets all records added or updated since the last commit. ...

Gets all records added or updated since the last commit. Note that the order of records
returned is not deterministic and does not indicate the order in which records were modified. Note also that
removed records are not included (use getRemovedRecords for that).
ReturnsExt.data.Model[]The added and updated Model instances


### getNewRecords

Returns all Model instances that are either currently a phantom (e.g. ...

Returns all Model instances that are either currently a phantom (e.g. have no id), or have an ID but have not
yet been saved on this Store (this happens when adding a non-phantom record from another Store into this one)
ReturnsExt.data.Model[]The Model instances


### getProxy

Returns the proxy currently attached to this proxy instance ...

Returns the proxy currently attached to this proxy instance
ReturnsExt.data.proxy.ProxyThe Proxy instance


### getRemovedRecords

Returns any records that have been removed from the store but not yet destroyed on the proxy. ...

Returns any records that have been removed from the store but not yet destroyed on the proxy.
ReturnsExt.data.Model[]The removed Model instances


### getSorters

...


### getState

Returns the grouping, sorting and filtered state of this Store. ...

Returns the grouping, sorting and filtered state of this Store.


### getUpdatedRecords

Returns all Model instances that have been updated in the Store but not yet synchronized with the Proxy ...

Returns all Model instances that have been updated in the Store but not yet synchronized with the Proxy
ReturnsExt.data.Model[]The updated Model instances


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


### initSortable

Performs initialization of this mixin. ...

Performs initialization of this mixin. Component classes using this mixin should call this method during their
own initialization.


### isFiltered

...


### isLoading

Returns true if the Store is currently performing a load operation ...

Returns true if the Store is currently performing a load operation
ReturnsBooleanTrue if the Store is currently loading


### load

Loads the Store using its configured proxy. ...

Loads the Store using its configured proxy.
        Available since: 1.1.0
Parametersoptions : Object (optional)config object. This is passed into the Operation
object that is created and then sent to the proxy's Ext.data.proxy.Proxy.read function


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


### onBatchComplete

Attached as the 'complete' event listener to a proxy's Batch object. ...

Attached as the 'complete' event listener to a proxy's Batch object. Iterates over the batch operations
and updates the Store's internal data MixedCollection.
Parametersbatch : Object


### onBatchException

...

Parametersbatch : Object


### onBatchOperationComplete

Attached as the 'operationcomplete' event listener to a proxy's Batch object. ...

Attached as the 'operationcomplete' event listener to a proxy's Batch object. By default just calls through
to onProxyWrite.
Parametersbatch : Object


### onBeforeSort

...


### onClassExtended

...

Parameterscls : Object


### onConfigUpdate

...

Parametersnames : Object


### onCreateRecords

may be implemented by store subclasses ...

may be implemented by store subclasses


### onDestroyRecords

Removes any records when a write is returned from the server. ...

Removes any records when a write is returned from the server.
Parametersrecords : Ext.data.Model[]The array of removed records


### onIdChanged

...

Parametersmodel : Object


### onMetaChange

private ...

private
Parametersproxy : Object


### onProxyWrite

Callback for any write Operation over the Proxy. ...

Callback for any write Operation over the Proxy. Updates the Store's MixedCollection to reflect
the updates provided by the Proxy
Parametersoperation : Object


### onUpdate

...


### onUpdateRecords

may be implemented by store subclasses ...

may be implemented by store subclasses


### prepareClass

Prepares a given class for observable instances. ...

Prepares a given class for observable instances. This method is called when a
class derives from this class or uses this class as a mixin.
ParametersT : FunctionThe class constructor to prepare.


### read

...


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


### reload

Reloads the store using the last options passed to the load method. ...

Reloads the store using the last options passed to the load method.
Parametersoptions : ObjectA config object which contains options which may override the options passed to the previous load call.


### removeAll

Removes all records from the store. ...

Removes all records from the store. This method does a "fast remove",
individual remove events are not called. The clear event is
fired upon completion.
        Available since: 1.1.0


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


### resumeAutoSync

Resumes automatically syncing the Store with its Proxy. ...

Resumes automatically syncing the Store with its Proxy.  Only applicable if autoSync is `true`


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


### save

Saves all pending changes via the configured proxy. ...

Saves all pending changes via the configured proxy. Use sync instead.
        
        This method has been **deprecated** since 4.0.0
        Will be removed in the next major version


### setConfig

...

Parametersconfig : Object


### setProxy

Sets the Store's Proxy by string, config object or Proxy instance ...

Sets the Store's Proxy by string, config object or Proxy instance
Parametersproxy : String/Object/Ext.data.proxy.ProxyThe new Proxy, which can be either a type string, a configuration object
or an Ext.data.proxy.Proxy instance


### sort

Sorts the data in the Store by one or more of its properties. ...

Sorts the data in the Store by one or more of its properties. Example usage:

//sort by a single field
myStore.sort('myField', 'DESC');

//sorting by multiple fields
myStore.sort([
    {
        property : 'age',
        direction: 'ASC'
    },
    {
        property : 'name',
        direction: 'DESC'
    }
]);


Internally, Store converts the passed arguments into an array of Ext.util.Sorter instances, and delegates
the actual sorting to its internal Ext.util.MixedCollection.

When passing a single string argument to sort, Store maintains a ASC/DESC toggler per field, so this code:

store.sort('myField');
store.sort('myField');


Is equivalent to this code, because Store handles the toggling automatically:

store.sort('myField', 'ASC');
store.sort('myField', 'DESC');

Parameterssorters : String/Ext.util.Sorter[] (optional)Either a string name of one of the fields in this Store's configured
Model, or an array of sorter configurations.


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


### suspendAutoSync

Suspends automatically syncing the Store with its Proxy. ...

Suspends automatically syncing the Store with its Proxy.  Only applicable if autoSync is `true`


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


### sync

Synchronizes the store with its proxy. ...

Synchronizes the store with its proxy. This asks the proxy to batch together any new, updated
and deleted records in the store, updating the store's internal representation of the records
as each operation completes.
Parametersoptions : Object (optional)Object containing one or more properties supported by the sync method (these get
passed along to the underlying proxy's batch method):
batch : Ext.data.Batch/Object (optional)A Ext.data.Batch object (or batch config to apply
to the created batch). If unspecified a default batch will be auto-created as needed.


### un

Shorthand for removeListener. ...

Shorthand for removeListener.

Removes an event handler.
ParameterseventName : StringThe type of event the handler was associated with.


### update

...

Parametersoptions : Object


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

Creates a store from config object. ...

Creates a store from config object.
Parametersstore : Object/Ext.data.AbstractStoreA config for
the store to be created.  It may contain a `type` field
which defines the particular type of store to create.

Alteratively passing an actual store to this method will
just return it, no changes made.


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


### add

Fired when a Model instance has been added to this Store. ...

Fired when a Model instance has been added to this Store.
        Available since: 1.1.0
Parametersstore : Ext.data.StoreThe store


### beforeload

Fires before a request is made for a new data object. ...

Fires before a request is made for a new data object. If the beforeload handler returns false the load
action will be canceled.
        Available since: 1.1.0
Parametersstore : Ext.data.StoreThis Store


### beforesync

Fired before a call to sync is executed. ...

Fired before a call to sync is executed. Return false from any listener to cancel the sync
Parametersoptions : ObjectHash of all records to be synchronized, broken down into create, update and destroy


### bulkremove

Fired at the end of the remove method when all records in the passed array have been removed. ...

Fired at the *end* of the remove method when all records in the passed array have been removed.

If many records may be removed in one go, then it is more efficient to listen for this event
and perform any processing for a bulk remove than to listen for many remove events.
Parametersstore : Ext.data.StoreThe Store object


### clear

Fired after the removeAll method is called. ...

Fired after the removeAll method is called.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### datachanged

Fires whenever the records in the Store have changed in some way - this could include adding or removing
records, or ...

Fires whenever the records in the Store have changed in some way - this could include adding or removing
records, or updating the data in existing records
        Available since: 1.1.0
Parametersthis : Ext.data.StoreThe data store


### load

Fires whenever the store reads data from a remote data source. ...

Fires whenever the store reads data from a remote data source.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### metachange

Fires when this store's underlying reader (available via the proxy) provides new metadata. ...

Fires when this store's underlying reader (available via the proxy) provides new metadata.
Metadata usually consists of new field definitions, but can include any configuration data
required by an application, and can be processed as needed in the event handler.
This event is currently only fired for JsonReaders.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### refresh

Fires when the data cache has changed in a bulk manner (e.g., it has been sorted, filtered, etc.) and a
widget that i...

Fires when the data cache has changed in a bulk manner (e.g., it has been sorted, filtered, etc.) and a
widget that is using this Store as a Record cache should refresh its view.
Parametersthis : Ext.data.StoreThe data store


### remove

Fired when a Model instance has been removed from this Store. ...

Fired when a Model instance has been removed from this Store.

If many records may be removed in one go, then it is more efficient to listen for the bulkremove event
and perform any processing for a bulk remove than to listen for this remove event.
        Available since: 1.1.0
Parametersstore : Ext.data.StoreThe Store object


### update

Fires when a Model instance has been updated. ...

Fires when a Model instance has been updated.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### write

Fires whenever a successful write has been made via the configured Proxy ...

Fires whenever a successful write has been made via the configured Proxy
        Available since: 3.4.0
Parametersstore : Ext.data.StoreThis Store


## Events

### add

Fired when a Model instance has been added to this Store. ...

Fired when a Model instance has been added to this Store.
        Available since: 1.1.0
Parametersstore : Ext.data.StoreThe store


### beforeload

Fires before a request is made for a new data object. ...

Fires before a request is made for a new data object. If the beforeload handler returns false the load
action will be canceled.
        Available since: 1.1.0
Parametersstore : Ext.data.StoreThis Store


### beforesync

Fired before a call to sync is executed. ...

Fired before a call to sync is executed. Return false from any listener to cancel the sync
Parametersoptions : ObjectHash of all records to be synchronized, broken down into create, update and destroy


### bulkremove

Fired at the end of the remove method when all records in the passed array have been removed. ...

Fired at the *end* of the remove method when all records in the passed array have been removed.

If many records may be removed in one go, then it is more efficient to listen for this event
and perform any processing for a bulk remove than to listen for many remove events.
Parametersstore : Ext.data.StoreThe Store object


### clear

Fired after the removeAll method is called. ...

Fired after the removeAll method is called.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### datachanged

Fires whenever the records in the Store have changed in some way - this could include adding or removing
records, or ...

Fires whenever the records in the Store have changed in some way - this could include adding or removing
records, or updating the data in existing records
        Available since: 1.1.0
Parametersthis : Ext.data.StoreThe data store


### load

Fires whenever the store reads data from a remote data source. ...

Fires whenever the store reads data from a remote data source.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### metachange

Fires when this store's underlying reader (available via the proxy) provides new metadata. ...

Fires when this store's underlying reader (available via the proxy) provides new metadata.
Metadata usually consists of new field definitions, but can include any configuration data
required by an application, and can be processed as needed in the event handler.
This event is currently only fired for JsonReaders.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### refresh

Fires when the data cache has changed in a bulk manner (e.g., it has been sorted, filtered, etc.) and a
widget that i...

Fires when the data cache has changed in a bulk manner (e.g., it has been sorted, filtered, etc.) and a
widget that is using this Store as a Record cache should refresh its view.
Parametersthis : Ext.data.StoreThe data store


### remove

Fired when a Model instance has been removed from this Store. ...

Fired when a Model instance has been removed from this Store.

If many records may be removed in one go, then it is more efficient to listen for the bulkremove event
and perform any processing for a bulk remove than to listen for this remove event.
        Available since: 1.1.0
Parametersstore : Ext.data.StoreThe Store object


### update

Fires when a Model instance has been updated. ...

Fires when a Model instance has been updated.
        Available since: 1.1.0
Parametersthis : Ext.data.Store


### write

Fires whenever a successful write has been made via the configured Proxy ...

Fires whenever a successful write has been made via the configured Proxy
        Available since: 3.4.0
Parametersstore : Ext.data.StoreThis Store


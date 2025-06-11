# Object

## Description

Creates an object wrapper.

The Object constructor creates an object wrapper for the given value. If the value is null or undefined, it will create and return an empty object, otherwise, it will return an object of a type that corresponds to the given value.

When called in a non-constructor context, Object behaves identically.

The following examples store an empty Object object in o:

var o = new Object(); var o = new Object(undefined); var o = new Object(null); Using Object to create Boolean objects The following examples store Boolean objects in o:

## Properties

### constructor

**Type:** Object

Specifies the function that creates an object's prototype. ...

Specifies the function that creates an object's prototype.

**Returns:** a reference to the Object function that created the instance's prototype. Note that the value of this property is a reference to the function itself, not a string containing the function's name, but it isn't read only (except for primitive Boolean, Number or String values: 1, true, "read-only"). All objects inherit a `constructor` property from their `prototype`: Even though you cannot construct most HTML objects, you can do comparisons. For example, The following example creates a prototype, `Tree`, and an object of that type, theTree. The example then displays the `constructor` property for the object `theTree`. This example displays the following output: The following example shows how to modify constructor value of generic objects. Only true, 1 and "test" variable constructors will not be changed. This example explains that is not always so safe to believe in constructor function.


### prototype

**Type:** Object

Allows the addition of properties to all objects of type Object.


### Object

Creates new Object. ...

Creates new Object.

**Parameters:** value : Object (optional)The value to wrap.


### hasOwnProperty

Returns a boolean indicating whether an object contains the specified property as a direct property of that object an...

**Parameters:** prop : StringThe name of the property to test.

**Returns:** a boolean indicating whether an object contains the specified property as a direct property of that object and not inherited through the prototype chain. Every object descended from `Object` inherits the `hasOwnProperty` method. This method can be used to determine whether an object has the specified property as a direct property of that object; unlike the `in` operator, this method does not check down the object's prototype chain. The following example determines whether the o object contains a property named prop: The following example differentiates between direct properties and properties inherited through the prototype chain: The following example shows how to iterate over the properties of an object without executing on inherit properties.


### isPrototypeOf

Returns a boolean indication whether the specified object is in the prototype chain of the object this method is call...

**Parameters:** prototype : Objectan object to be tested against each link in the prototype chain of the *object* argument

**Returns:** a boolean indication whether the specified object is in the prototype chain of the object this method is called upon. `isPrototypeOf` allows you to check whether or not an object exists within another object's prototype chain. For example, consider the following prototype chain: Later on down the road, if you instantiate `Fum` and need to check if `Fi`'s prototype exists within the `Fum` prototype chain, you could do this: This, along with the `instanceof` operator particularly comes in handy if you have code that can only function when dealing with objects descended from a specific prototype chain, e.g., to guarantee that certain methods or properties will be present on that object.


### propertyIsEnumerable

Returns a boolean indicating if the internal ECMAScript DontEnum attribute is set. ...

**Parameters:** prop : StringThe name of the property to test.

**Returns:** a boolean indicating if the internal ECMAScript DontEnum attribute is set. Every object has a `propertyIsEnumerable` method. This method can determine whether the specified property in an object can be enumerated by a `for...in` loop, with the exception of properties inherited through the prototype chain. If the object does not have the specified property, this method returns false. The following example shows the use of `propertyIsEnumerable` on objects and arrays: The following example demonstrates the enumerability of user-defined versus built-in properties: Direct versus inherited properties


### toLocaleString

Returns a string representing the object. ...

**Returns:** a string representing the object. This method is meant to be overridden by derived objects for locale-specific purposes. `Object`'s `toLocaleString` returns the result of calling `toString`. This function is provided to give objects a generic `toLocaleString` method, even though not all may use it. Currently, only `Array`, `Number`, and `Date` override `toLocaleString`. ReturnsStringObject represented as a string.


### toString

Returns a string representation of the object. ...

**Returns:** a string representation of the object. Every object has a `toString()` method that is automatically called when the object is to be represented as a text value or when an object is referred to in a manner in which a string is expected. By default, the `toString()` method is inherited by every object descended from `Object`. If this method is not overridden in a custom object, `toString()` returns "[object type]", where `type` is the object type. The following code illustrates this: You can create a function to be called in place of the default `toString()` method. The `toString()` method takes no arguments and should return a string. The `toString()` method you create can be any value you want, but it will be most useful if it carries information about the object. The following code defines the `Dog` object type and creates `theDog`, an object of type `Dog`: If you call the `toString()` method on this custom object, it returns the default value inherited from `Object`: The following code creates and assigns `dogToString()` to override the default `toString()` method. This function generates a string containing the name, breed, color, and sex of the object, in the form `"property = value;"`. With the preceding code in place, any time theDog is used in a string context, JavaScript automatically calls the `dogToString()` function, which returns the following string: `toString()` can be used with every object and allows you to get its class. To use the `Object.prototype.toString()` with every object, you need to call `Function.prototype.call()` or `Function.prototype.apply()` on it, passing the object you want to inspect as the first parameter called `thisArg`. ReturnsStringObject represented as a string.


### valueOf

Returns the primitive value of the specified object. ...

**Returns:** the primitive value of the specified object. JavaScript calls the `valueOf` method to convert an object to a primitive value. You rarely need to invoke the `valueOf` method yourself; JavaScript automatically invokes it when encountering an object where a primitive value is expected. By default, the `valueOf` method is inherited by every object descended from `Object`. Every built- in core object overrides this method to return an appropriate value. If an object has no primitive value, `valueOf` returns the object itself, which is displayed as: You can use `valueOf` within your own code to convert a built-in object into a primitive value. When you create a custom object, you can override `Object.valueOf` to call a custom method instead of the default `Object` method. You can create a function to be called in place of the default `valueOf` method. Your function must take no arguments. Suppose you have an object type `myNumberType` and you want to create a `valueOf` method for it. The following code assigns a user-defined function to the object's valueOf method: With the preceding code in place, any time an object of type `myNumberType` is used in a context where it is to be represented as a primitive value, JavaScript automatically calls the function defined in the preceding code. An object's `valueOf` method is usually invoked by JavaScript, but you can invoke it yourself as follows: Note: Objects in string contexts convert via the `toString` method, which is different from `String` objects converting to string primitives using `valueOf`. All objects have a string conversion, if only `"[object type]"`. But many objects do not convert to number, boolean, or function. ReturnsObjectReturns value of the object or the object itself.


### create

Creates a new object with the specified prototype object and properties. ...

Creates a new object with the specified prototype object and properties. Classical inheritance with Object.create Below is an example of how to use `Object.create` to achieve classical inheritance, this is for single inheritance, which is all that Javascript supports. If you wish to inherit from multiple objects, then mixins are a possibility. The mixin function would copy the functions from the superclass prototype to the subclass prototype, the mixin function needs to be supplied by the user. Using `propertiesObject` argument with Object.create **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** proto : ObjectThe object which should be the prototype of the newly-created object. Throws a `TypeError` exception if the `proto` parameter isn't null or an object.


### defineProperties

Defines new or modifies existing properties directly on an object, returning the object. ...

Defines new or modifies existing properties directly on an object, returning the object. In essence, it defines all properties corresponding to the enumerable own properties of props on the object. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object on which to define or modify properties.


### defineProperty

Defines a new property directly on an object, or modifies an existing property on an object, and returns the object. ...

Defines a new property directly on an object, or modifies an existing property on an object, and returns the object. This method allows precise addition to or modification of a property on an object. Normal property addition through assignment creates properties which show up during property enumeration (for...in loop or keys method), whose values may be changed, and which may be deleted. This method allows these extra details to be changed from their defaults. Property descriptors present in objects come in two main flavors: data descriptors and accessor descriptors. A data descriptor is a property that has a value, which may or may not be writable. An accessor descriptor is a property described by a getter-setter pair of functions. A descriptor must be one of these two flavors; it cannot be both. Both data and accessor descriptor is an object with the following optional keys: - **configurable** True if and only if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object. Defaults to false. - **enumerable** True if and only if this property shows up during enumeration of the properties on the corresponding object. Defaults to false. A data descriptor is an object with the following optional keys: - **value** The value associated with the property. Can be any valid JavaScript value (number, object, function, etc) Defaults to undefined. - **writable** True if and only if the value associated with the property may be changed with an assignment operator. Defaults to false. An accessor descriptor is an object with the following optional keys: - **get** A function which serves as a getter for the property, or undefined if there is no getter. The function return will be used as the value of property. Defaults to undefined. - **set** A function which serves as a setter for the property, or undefined if there is no setter. The function will receive as only argument the new value being assigned to the property. Defaults to undefined. Bear in mind that these options are not necessarily own properties so, if inherited, will be considered too. In order to ensure these defaults are preserved you might freeze the Object.prototype upfront, specify all options explicitly, or point to null as **proto** property. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object on which to define the property.


### freeze

Freezes an object: that is, prevents new properties from being added to it; prevents existing properties from being r...

Freezes an object: that is, prevents new properties from being added to it; prevents existing properties from being removed; and prevents existing properties, or their enumerability, configurability, or writability, from being changed. In essence the object is made effectively immutable. The method returns the object being frozen. Nothing can be added to or removed from the properties set of a frozen object. Any attempt to do so will fail, either silently or by throwing a TypeError exception (most commonly, but not exclusively, when in strict mode). Values cannot be changed for data properties. Accessor properties (getters and setters) work the same (and still give the illusion that you are changing the value). Note that values that are objects can still be modified, unless they are also frozen. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object to freeze.


### getOwnPropertyDescriptor

Returns a property descriptor for an own property (that is, one directly present on an object, not present by dint of...

**Parameters:** obj : ObjectThe object in which to look for the property.

**Returns:** a property descriptor for an own property (that is, one directly present on an object, not present by dint of being along an object's prototype chain) of a given object. This method permits examination of the precise description of a property. A property in JavaScript consists of a string-valued name and a property descriptor. Further information about property descriptor types and their attributes can be found in defineProperty. **NOTE:** This method is part of the ECMAScript 5 standard.


### getOwnPropertyNames

Returns an array of all properties (enumerable or not) found directly upon a given object. ...

**Parameters:** obj : ObjectThe object whose enumerable and non-enumerable own properties are to be returned.

**Returns:** an array of all properties (enumerable or not) found directly upon a given object. Rreturns an array whose elements are strings corresponding to the enumerable and non-enumerable properties found directly upon obj. The ordering of the enumerable properties in the array is consistent with the ordering exposed by a for...in loop (or by keys) over the properties of the object. The ordering of the non-enumerable properties in the array, and among the enumerable properties, is not defined. If you want only the enumerable properties, see keys or use a for...in loop (although note that this will return enumerable properties not found directly upon that object but also along the prototype chain for the object unless the latter is filtered with hasOwnProperty). Items on the prototype chain are not listed: **NOTE:** This method is part of the ECMAScript 5 standard.


### getPrototypeOf

Returns the prototype (i.e. ...

**Parameters:** object : ObjectThe object whose prototype is to be returned. Throws a TypeError exception if this parameter isn't an Object.

**Returns:** the prototype (i.e. the internal `[[Prototype]]`) of the specified object. **NOTE:** This method is part of the ECMAScript 5 standard.


### isExtensible

Determines if an object is extensible (whether it can have new properties added to it). ...

Determines if an object is extensible (whether it can have new properties added to it). Objects are extensible by default: they can have new properties added to them, and can be modified. An object can be marked as non-extensible using preventExtensions, seal, or freeze. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object which should be checked.


### isFrozen

Determines if an object is frozen. ...

Determines if an object is frozen. An object is frozen if and only if it is not extensible, all its properties are non-configurable, and all its data properties (that is, properties which are not accessor properties with getter or setter components) are non-writable. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object which should be checked.


### isSealed

Determines if an object is sealed. ...

Determines if an object is sealed. An object is sealed if it is non-extensible and if all its properties are non-configurable and therefore not removable (but not necessarily non-writable). **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object which should be checked.


### keys

Returns an array of a given object's own enumerable properties, in the same order as that provided by a for-in loop (...

**Parameters:** obj : ObjectThe object whose enumerable own properties are to be returned.

**Returns:** an array of a given object's own enumerable properties, in the same order as that provided by a for-in loop (the difference being that a for-in loop enumerates properties in the prototype chain as well). Returns an array whose elements are strings corresponding to the enumerable properties found directly upon object. The ordering of the properties is the same as that given by looping over the properties of the object manually. If you want all properties, even the not enumerable, see getOwnPropertyNames. **NOTE:** This method is part of the ECMAScript 5 standard.


### preventExtensions

Prevents new properties from ever being added to an object (i.e. ...

Prevents new properties from ever being added to an object (i.e. prevents future extensions to the object). An object is extensible if new properties can be added to it. `preventExtensions` marks an object as no longer extensible, so that it will never have properties beyond the ones it had at the time it was marked as non-extensible. Note that the properties of a non-extensible object, in general, may still be deleted. Attempting to add new properties to a non-extensible object will fail, either silently or by throwing a TypeError (most commonly, but not exclusively, when in strict mode). It only prevents addition of own properties. Properties can still be added to the object prototype. If there is a way to turn an extensible object to a non-extensible one, there is no way to do the opposite in ECMAScript 5 **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object which should be made non-extensible.


### seal

Seals an object, preventing new properties from being added to it and marking all existing properties as non-configur...

Seals an object, preventing new properties from being added to it and marking all existing properties as non-configurable. Values of present properties can still be changed as long as they are writable. By default, objects are extensible (new properties can be added to them). Sealing an object prevents new properties from being added and marks all existing properties as non-configurable. This has the effect of making the set of properties on the object fixed and immutable. Making all properties non-configurable also prevents them from being converted from data properties to accessor properties and vice versa, but it does not prevent the values of data properties from being changed. Attempting to delete or add properties to a sealed object, or to convert a data property to accessor or vice versa, will fail, either silently or by throwing a TypeError (most commonly, although not exclusively, when in strict mode code). The prototype chain remains untouched. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object which should be sealed.


## Methods

### Object

Creates new Object. ...

Creates new Object.

**Parameters:** value : Object (optional)The value to wrap.


### hasOwnProperty

Returns a boolean indicating whether an object contains the specified property as a direct property of that object an...

**Parameters:** prop : StringThe name of the property to test.

**Returns:** a boolean indicating whether an object contains the specified property as a direct property of that object and not inherited through the prototype chain. Every object descended from `Object` inherits the `hasOwnProperty` method. This method can be used to determine whether an object has the specified property as a direct property of that object; unlike the `in` operator, this method does not check down the object's prototype chain. The following example determines whether the o object contains a property named prop: The following example differentiates between direct properties and properties inherited through the prototype chain: The following example shows how to iterate over the properties of an object without executing on inherit properties.


### isPrototypeOf

Returns a boolean indication whether the specified object is in the prototype chain of the object this method is call...

**Parameters:** prototype : Objectan object to be tested against each link in the prototype chain of the *object* argument

**Returns:** a boolean indication whether the specified object is in the prototype chain of the object this method is called upon. `isPrototypeOf` allows you to check whether or not an object exists within another object's prototype chain. For example, consider the following prototype chain: Later on down the road, if you instantiate `Fum` and need to check if `Fi`'s prototype exists within the `Fum` prototype chain, you could do this: This, along with the `instanceof` operator particularly comes in handy if you have code that can only function when dealing with objects descended from a specific prototype chain, e.g., to guarantee that certain methods or properties will be present on that object.


### propertyIsEnumerable

Returns a boolean indicating if the internal ECMAScript DontEnum attribute is set. ...

**Parameters:** prop : StringThe name of the property to test.

**Returns:** a boolean indicating if the internal ECMAScript DontEnum attribute is set. Every object has a `propertyIsEnumerable` method. This method can determine whether the specified property in an object can be enumerated by a `for...in` loop, with the exception of properties inherited through the prototype chain. If the object does not have the specified property, this method returns false. The following example shows the use of `propertyIsEnumerable` on objects and arrays: The following example demonstrates the enumerability of user-defined versus built-in properties: Direct versus inherited properties


### toLocaleString

Returns a string representing the object. ...

**Returns:** a string representing the object. This method is meant to be overridden by derived objects for locale-specific purposes. `Object`'s `toLocaleString` returns the result of calling `toString`. This function is provided to give objects a generic `toLocaleString` method, even though not all may use it. Currently, only `Array`, `Number`, and `Date` override `toLocaleString`. ReturnsStringObject represented as a string.


### toString

Returns a string representation of the object. ...

**Returns:** a string representation of the object. Every object has a `toString()` method that is automatically called when the object is to be represented as a text value or when an object is referred to in a manner in which a string is expected. By default, the `toString()` method is inherited by every object descended from `Object`. If this method is not overridden in a custom object, `toString()` returns "[object type]", where `type` is the object type. The following code illustrates this: You can create a function to be called in place of the default `toString()` method. The `toString()` method takes no arguments and should return a string. The `toString()` method you create can be any value you want, but it will be most useful if it carries information about the object. The following code defines the `Dog` object type and creates `theDog`, an object of type `Dog`: If you call the `toString()` method on this custom object, it returns the default value inherited from `Object`: The following code creates and assigns `dogToString()` to override the default `toString()` method. This function generates a string containing the name, breed, color, and sex of the object, in the form `"property = value;"`. With the preceding code in place, any time theDog is used in a string context, JavaScript automatically calls the `dogToString()` function, which returns the following string: `toString()` can be used with every object and allows you to get its class. To use the `Object.prototype.toString()` with every object, you need to call `Function.prototype.call()` or `Function.prototype.apply()` on it, passing the object you want to inspect as the first parameter called `thisArg`. ReturnsStringObject represented as a string.


### valueOf

Returns the primitive value of the specified object. ...

**Returns:** the primitive value of the specified object. JavaScript calls the `valueOf` method to convert an object to a primitive value. You rarely need to invoke the `valueOf` method yourself; JavaScript automatically invokes it when encountering an object where a primitive value is expected. By default, the `valueOf` method is inherited by every object descended from `Object`. Every built- in core object overrides this method to return an appropriate value. If an object has no primitive value, `valueOf` returns the object itself, which is displayed as: You can use `valueOf` within your own code to convert a built-in object into a primitive value. When you create a custom object, you can override `Object.valueOf` to call a custom method instead of the default `Object` method. You can create a function to be called in place of the default `valueOf` method. Your function must take no arguments. Suppose you have an object type `myNumberType` and you want to create a `valueOf` method for it. The following code assigns a user-defined function to the object's valueOf method: With the preceding code in place, any time an object of type `myNumberType` is used in a context where it is to be represented as a primitive value, JavaScript automatically calls the function defined in the preceding code. An object's `valueOf` method is usually invoked by JavaScript, but you can invoke it yourself as follows: Note: Objects in string contexts convert via the `toString` method, which is different from `String` objects converting to string primitives using `valueOf`. All objects have a string conversion, if only `"[object type]"`. But many objects do not convert to number, boolean, or function. ReturnsObjectReturns value of the object or the object itself.


### create

Creates a new object with the specified prototype object and properties. ...

Creates a new object with the specified prototype object and properties. Classical inheritance with Object.create Below is an example of how to use `Object.create` to achieve classical inheritance, this is for single inheritance, which is all that Javascript supports. If you wish to inherit from multiple objects, then mixins are a possibility. The mixin function would copy the functions from the superclass prototype to the subclass prototype, the mixin function needs to be supplied by the user. Using `propertiesObject` argument with Object.create **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** proto : ObjectThe object which should be the prototype of the newly-created object. Throws a `TypeError` exception if the `proto` parameter isn't null or an object.


### defineProperties

Defines new or modifies existing properties directly on an object, returning the object. ...

Defines new or modifies existing properties directly on an object, returning the object. In essence, it defines all properties corresponding to the enumerable own properties of props on the object. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object on which to define or modify properties.


### defineProperty

Defines a new property directly on an object, or modifies an existing property on an object, and returns the object. ...

Defines a new property directly on an object, or modifies an existing property on an object, and returns the object. This method allows precise addition to or modification of a property on an object. Normal property addition through assignment creates properties which show up during property enumeration (for...in loop or keys method), whose values may be changed, and which may be deleted. This method allows these extra details to be changed from their defaults. Property descriptors present in objects come in two main flavors: data descriptors and accessor descriptors. A data descriptor is a property that has a value, which may or may not be writable. An accessor descriptor is a property described by a getter-setter pair of functions. A descriptor must be one of these two flavors; it cannot be both. Both data and accessor descriptor is an object with the following optional keys: - **configurable** True if and only if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object. Defaults to false. - **enumerable** True if and only if this property shows up during enumeration of the properties on the corresponding object. Defaults to false. A data descriptor is an object with the following optional keys: - **value** The value associated with the property. Can be any valid JavaScript value (number, object, function, etc) Defaults to undefined. - **writable** True if and only if the value associated with the property may be changed with an assignment operator. Defaults to false. An accessor descriptor is an object with the following optional keys: - **get** A function which serves as a getter for the property, or undefined if there is no getter. The function return will be used as the value of property. Defaults to undefined. - **set** A function which serves as a setter for the property, or undefined if there is no setter. The function will receive as only argument the new value being assigned to the property. Defaults to undefined. Bear in mind that these options are not necessarily own properties so, if inherited, will be considered too. In order to ensure these defaults are preserved you might freeze the Object.prototype upfront, specify all options explicitly, or point to null as **proto** property. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object on which to define the property.


### freeze

Freezes an object: that is, prevents new properties from being added to it; prevents existing properties from being r...

Freezes an object: that is, prevents new properties from being added to it; prevents existing properties from being removed; and prevents existing properties, or their enumerability, configurability, or writability, from being changed. In essence the object is made effectively immutable. The method returns the object being frozen. Nothing can be added to or removed from the properties set of a frozen object. Any attempt to do so will fail, either silently or by throwing a TypeError exception (most commonly, but not exclusively, when in strict mode). Values cannot be changed for data properties. Accessor properties (getters and setters) work the same (and still give the illusion that you are changing the value). Note that values that are objects can still be modified, unless they are also frozen. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object to freeze.


### getOwnPropertyDescriptor

Returns a property descriptor for an own property (that is, one directly present on an object, not present by dint of...

**Parameters:** obj : ObjectThe object in which to look for the property.

**Returns:** a property descriptor for an own property (that is, one directly present on an object, not present by dint of being along an object's prototype chain) of a given object. This method permits examination of the precise description of a property. A property in JavaScript consists of a string-valued name and a property descriptor. Further information about property descriptor types and their attributes can be found in defineProperty. **NOTE:** This method is part of the ECMAScript 5 standard.


### getOwnPropertyNames

Returns an array of all properties (enumerable or not) found directly upon a given object. ...

**Parameters:** obj : ObjectThe object whose enumerable and non-enumerable own properties are to be returned.

**Returns:** an array of all properties (enumerable or not) found directly upon a given object. Rreturns an array whose elements are strings corresponding to the enumerable and non-enumerable properties found directly upon obj. The ordering of the enumerable properties in the array is consistent with the ordering exposed by a for...in loop (or by keys) over the properties of the object. The ordering of the non-enumerable properties in the array, and among the enumerable properties, is not defined. If you want only the enumerable properties, see keys or use a for...in loop (although note that this will return enumerable properties not found directly upon that object but also along the prototype chain for the object unless the latter is filtered with hasOwnProperty). Items on the prototype chain are not listed: **NOTE:** This method is part of the ECMAScript 5 standard.


### getPrototypeOf

Returns the prototype (i.e. ...

**Parameters:** object : ObjectThe object whose prototype is to be returned. Throws a TypeError exception if this parameter isn't an Object.

**Returns:** the prototype (i.e. the internal `[[Prototype]]`) of the specified object. **NOTE:** This method is part of the ECMAScript 5 standard.


### isExtensible

Determines if an object is extensible (whether it can have new properties added to it). ...

Determines if an object is extensible (whether it can have new properties added to it). Objects are extensible by default: they can have new properties added to them, and can be modified. An object can be marked as non-extensible using preventExtensions, seal, or freeze. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object which should be checked.


### isFrozen

Determines if an object is frozen. ...

Determines if an object is frozen. An object is frozen if and only if it is not extensible, all its properties are non-configurable, and all its data properties (that is, properties which are not accessor properties with getter or setter components) are non-writable. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object which should be checked.


### isSealed

Determines if an object is sealed. ...

Determines if an object is sealed. An object is sealed if it is non-extensible and if all its properties are non-configurable and therefore not removable (but not necessarily non-writable). **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object which should be checked.


### keys

Returns an array of a given object's own enumerable properties, in the same order as that provided by a for-in loop (...

**Parameters:** obj : ObjectThe object whose enumerable own properties are to be returned.

**Returns:** an array of a given object's own enumerable properties, in the same order as that provided by a for-in loop (the difference being that a for-in loop enumerates properties in the prototype chain as well). Returns an array whose elements are strings corresponding to the enumerable properties found directly upon object. The ordering of the properties is the same as that given by looping over the properties of the object manually. If you want all properties, even the not enumerable, see getOwnPropertyNames. **NOTE:** This method is part of the ECMAScript 5 standard.


### preventExtensions

Prevents new properties from ever being added to an object (i.e. ...

Prevents new properties from ever being added to an object (i.e. prevents future extensions to the object). An object is extensible if new properties can be added to it. `preventExtensions` marks an object as no longer extensible, so that it will never have properties beyond the ones it had at the time it was marked as non-extensible. Note that the properties of a non-extensible object, in general, may still be deleted. Attempting to add new properties to a non-extensible object will fail, either silently or by throwing a TypeError (most commonly, but not exclusively, when in strict mode). It only prevents addition of own properties. Properties can still be added to the object prototype. If there is a way to turn an extensible object to a non-extensible one, there is no way to do the opposite in ECMAScript 5 **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object which should be made non-extensible.


### seal

Seals an object, preventing new properties from being added to it and marking all existing properties as non-configur...

Seals an object, preventing new properties from being added to it and marking all existing properties as non-configurable. Values of present properties can still be changed as long as they are writable. By default, objects are extensible (new properties can be added to them). Sealing an object prevents new properties from being added and marks all existing properties as non-configurable. This has the effect of making the set of properties on the object fixed and immutable. Making all properties non-configurable also prevents them from being converted from data properties to accessor properties and vice versa, but it does not prevent the values of data properties from being changed. Attempting to delete or add properties to a sealed object, or to convert a data property to accessor or vice versa, will fail, either silently or by throwing a TypeError (most commonly, although not exclusively, when in strict mode code). The prototype chain remains untouched. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** obj : ObjectThe object which should be sealed.


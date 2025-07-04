# Boolean

## Description

The `Boolean` object is an object wrapper for a boolean value.

The value passed as the first parameter is converted to a boolean value, if necessary. If value is omitted or is 0, -0, null, false, `NaN`, undefined, or the empty string (""), the object has an initial value of false. All other values, including any object or the string `"false"`, create an object with an initial value of true.

Do not confuse the primitive Boolean values true and false with the true and false values of the Boolean object.

Any object whose value is not `undefined` or `null`, including a Boolean object whose value is false, evaluates to true when passed to a conditional statement. For example, the condition in the following if statement evaluates to true:

x = new Boolean(false); if (x) { // . . . this code is executed } This behavior does not apply to Boolean primitives. For example, the condition in the following if statement evaluates to `false`:

x = false; if (x) { // . . . this code is not executed } Do not use a `Boolean` object to convert a non-boolean value to a boolean value. Instead, use Boolean as a function to perform this task:

x = Boolean(expression); // preferred x = new Boolean(expression); // don't use If you specify any object, including a Boolean object whose value is false, as the initial value of a Boolean object, the new Boolean object has a value of true.

myFalse = new Boolean(false); // initial value of false g = new Boolean(myFalse); // initial value of true myString = new String("Hello"); // string object s = new Boolean(myString); // initial value of true Do not use a Boolean object in place of a Boolean primitive.

## Methods

### Boolean

Creates a new boolean object. ...

Creates a new boolean object.

**Parameters:** value : ObjectEither a truthy or falsy value to create the corresponding Boolean object.


### toString

Returns a string of either "true" or "false" depending upon the value of the object. ...

**Returns:** a string of either "true" or "false" depending upon the value of the object. Overrides the `Object.prototype.toString` method. The Boolean object overrides the `toString` method of the `Object` object; it does not inherit `Object.toString`. For Boolean objects, the `toString` method returns a string representation of the object. JavaScript calls the `toString` method automatically when a Boolean is to be represented as a text value or when a Boolean is referred to in a string concatenation. For Boolean objects and values, the built-in `toString` method returns the string `"true"` or `"false"` depending on the value of the boolean object. In the following code, `flag.toString` returns `"true"`. ReturnsStringThe boolean value represented as a string.


### valueOf

Returns the primitive value of the Boolean object. ...

**Returns:** the primitive value of the `Boolean` object. Overrides the `Object.prototype.valueOf` method. The `valueOf` method of Boolean returns the primitive value of a Boolean object or literal Boolean as a Boolean data type. This method is usually called internally by JavaScript and not explicitly in code. ReturnsBooleanThe primitive value.


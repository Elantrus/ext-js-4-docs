# Array

## Description

In JavaScript, the `Array` property of the global object is a constructor for array instances.

An array is a JavaScript object. Note that you shouldn't use it as an associative array, use Object instead.

The following example creates an array, msgArray, with a length of 0, then assigns values to msgArray[0] and msgArray[99], changing the length of the array to 100.

var msgArray = new Array(); msgArray[0] = "Hello"; msgArray[99] = "world"; if (msgArray.length == 100) print("The length is 100."); Creating a Two-dimensional Array The following creates chess board as a two dimensional array of strings. The first move is made by copying the 'P' in 6,4 to 4,4. The position 4,4 is left blank.

var board = [ ['R','N','B','Q','K','B','N','R'], ['P','P','P','P','P','P','P','P'], [' ',' ',' ',' ',' ',' ',' ',' '], [' ',' ',' ',' ',' ',' ',' ',' '], [' ',' ',' ',' ',' ',' ',' ',' '], [' ',' ',' ',' ',' ',' ',' ',' '], ['p','p','p','p','p','p','p','p'], ['r','n','b','q','k','b','n','r']]; print(board.join('\n') + '\n\n'); // Move King's Pawn forward 2 board[4][4] = board[6][4]; board[6][4] = ' '; print(board.join('\n')); Here is the output:

R,N,B,Q,K,B,N,R P,P,P,P,P,P,P,P , , , , , , , , , , , , , , , , , , , , , , , , , , , , p,p,p,p,p,p,p,p r,n,b,q,k,b,n,r R,N,B,Q,K,B,N,R P,P,P,P,P,P,P,P , , , , , , , , , , , , , , , , , ,p, , , , , , , , , , p,p,p,p, ,p,p,p r,n,b,q,k,b,n,r Accessing array elements Array elements are nothing less than object properties, so they are accessed as such.

var myArray = new Array("Wind", "Rain", "Fire"); myArray[0]; // "Wind" myArray[1]; // "Rain" // etc. myArray.length; // 3 // Even if indices are properties, the following notation throws a syntax error myArray.2; // It should be noted that in JavaScript, object property names are strings. Consequently, myArray[0] === myArray["0"]; myArray[1] === myArray["1"]; // etc. // However, this should be considered carefully myArray[02]; // "Fire". The number 02 is converted as the "2" string myArray["02"]; // undefined. There is no property named "02" Relationship between length and numerical properties An array's length property and numerical properties are connected. Here is some code explaining how this relationship works.

var a = []; a[0] = 'a'; console.log(a[0]); // 'a' console.log(a.length); // 1 a[1] = 32; console.log(a[1]); // 32 console.log(a.length); // 2 a[13] = 12345; console.log(a[13]); // 12345 console.log(a.length); // 14 a.length = 10; console.log(a[13]); // undefined, when reducing the length elements after length+1 are removed console.log(a.length); // 10 Creating an array using the result of a match The result of a match between a regular expression and a string can create an array. This array has properties and elements that provide information about the match. An array is the return value of RegExp.exec, String.match, and String.replace. To help explain these properties and elements, look at the following example and then refer to the table below:

// Match one d followed by one or more b's followed by one d // Remember matched b's and the following d // Ignore case var myRe = /d(b+)(d)/i; var myArray = myRe.exec("cdbBdbsbz"); The properties and elements returned from this match are as follows:

## Properties

### length

**Type:** Number

Reflects the number of elements in an array. ...

Reflects the number of elements in an array. The value of the `length` property is an integer with a positive sign and a value less than 2 to the 32 power (232). You can set the `length` property to truncate an array at any time. When you extend an array by changing its `length` property, the number of actual elements does not increase; for example, if you set `length` to 3 when it is currently 2, the array still contains only 2 elements. In the following example the array numbers is iterated through by looking at the `length` property to see how many elements it has. Each value is then doubled. The following example shortens the array `statesUS` to a length of 50 if the current `length` is greater than 50.


### Array

Creates new Array object. ...

Creates new Array object.

**Parameters:** items : Number/Object...Either a number that specifies the length of array or any number of items for the array.


### concat

Returns a new array comprised of this array joined with other array(s) and/or value(s). ...

**Parameters:** values : Object...Arrays and/or values to concatenate to the resulting array.

**Returns:** a new array comprised of this array joined with other array(s) and/or value(s). `concat` creates a new array consisting of the elements in the `this` object on which it is called, followed in order by, for each argument, the elements of that argument (if the argument is an array) or the argument itself (if the argument is not an array). `concat` does not alter `this` or any of the arrays provided as arguments but instead returns a "one level deep" copy that contains copies of the same elements combined from the original arrays. Elements of the original arrays are copied into the new array as follows: Object references (and not the actual object): `concat` copies object references into the new array. Both the original and new array refer to the same object. That is, if a referenced object is modified, the changes are visible to both the new and original arrays. Strings and numbers (not String and Number objects): `concat` copies the values of strings and numbers into the new array. Any operation on the new array will have no effect on the original arrays, and vice versa. Concatenating two arrays The following code concatenates two arrays: Concatenating three arrays The following code concatenates three arrays: Concatenating values to an array The following code concatenates three values to an array:


### every

Tests whether all elements in the array pass the test implemented by the provided function. ...

Tests whether all elements in the array pass the test implemented by the provided function. `every` executes the provided `callback` function once for each element present in the array until it finds one where `callback` returns a false value. If such an element is found, the `every` method immediately returns false. Otherwise, if `callback` returned a true value for all elements, `every` will return true. `callback` is invoked only for indexes of the array which have assigned values; it is not invoked for indexes which have been deleted or which have never been assigned values. If a `thisObject` parameter is provided to `every`, it will be used as the `this` for each invocation of the callback. If it is not provided, or is `null`, the global object associated with callback is used instead. `every` does not mutate the array on which it is called. The range of elements processed by `every` is set before the first invocation of callback. Elements which are appended to the array after the call to every begins will not be visited by `callback`. If existing elements of the array are changed, their value as passed to `callback` will be the value at the time `every` visits them; elements that are deleted are not visited. `every` acts like the "for all" quantifier in mathematics. In particular, for an empty array, it returns true. (It is vacuously true that all elements of the empty set satisfy any given condition.) The following example tests whether all elements in the array are bigger than 10. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** callback : FunctionFunction to test for each element. Parametersvalue : MixedThe element value.


### filter

Creates a new array with all elements that pass the test implemented by the provided function. ...

Creates a new array with all elements that pass the test implemented by the provided function. `filter` calls a provided `callback` function once for each element in an array, and constructs a new array of all the values for which `callback` returns a true value. `callback` is invoked only for indexes of the array which have assigned values; it is not invoked for indexes which have been deleted or which have never been assigned values. Array elements which do not pass the `callback` test are simply skipped, and are not included in the new array. If a `thisObject` parameter is provided to `filter`, it will be used as the `this` for each invocation of the `callback`. If it is not provided, or is `null`, the global object associated with callback is used instead. `filter` does not mutate the array on which it is called. The range of elements processed by `filter` is set before the first invocation of `callback`. Elements which are appended to the array after the call to `filter` begins will not be visited by `callback`. If existing elements of the array are changed, or deleted, their value as passed to `callback` will be the value at the time `filter` visits them; elements that are deleted are not visited. The following example uses filter to create a filtered array that has all elements with values less than 10 removed. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** callback : FunctionFunction to test for each element. Parametersvalue : MixedThe element value.


### forEach

Executes a provided function once per array element. ...

Executes a provided function once per array element. `forEach` executes the provided function (`callback`) once for each element present in the array. `callback` is invoked only for indexes of the array which have assigned values; it is not invoked for indexes which have been deleted or which have never been assigned values. If a `thisArg` parameter is provided to `forEach`, it will be used as the `this` value for each `callback` invocation as if `callback.call(thisArg, element, index, array)` was called. If `thisArg` is `undefined` or `null`, the `this` value within the function depends on whether the function is in strict mode or not (passed value if in strict mode, global object if in non-strict mode). The `range` of elements processed by `forEach` is set before the first invocation of `callback`. Elements which are appended to the array after the call to `forEach` begins will not be visited by `callback`. If existing elements of the array are changed, or deleted, their value as passed to callback will be the value at the time `forEach` visits them; elements that are deleted are not visited. The following code logs a line for each element in an array: **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** callback : FunctionFunction to execute for each element. Parametersvalue : MixedThe element value.


### indexOf

Returns the first index at which a given element can be found in the array, or -1 if it is not present. ...

**Parameters:** searchElement : MixedElement to locate in the array.

**Returns:** the first index at which a given element can be found in the array, or -1 if it is not present. `indexOf` compares `searchElement` to elements of the Array using strict equality (the same method used by the `===`, or triple-equals, operator). **NOTE:** This method is part of the ECMAScript 5 standard.


### join

Joins all elements of an array into a string. ...

Joins all elements of an array into a string. The string conversions of all array elements are joined into one string. The following example creates an array, `a`, with three elements, then joins the array three times: using the default separator, then a comma and a space, and then a plus.

**Parameters:** separator : StringSpecifies a string to separate each element of the array. The separator is converted to a string if necessary. If omitted, the array elements are separated with a comma.


### lastIndexOf

Returns the last index at which a given element can be found in the array, or -1 if it is not present. ...

**Parameters:** searchElement : MixedElement to locate in the array.

**Returns:** the last index at which a given element can be found in the array, or -1 if it is not present. The array is searched backwards, starting at `fromIndex`. `lastIndexOf` compares `searchElement` to elements of the Array using strict equality (the same method used by the `===`, or triple-equals, operator). **NOTE:** This method is part of the ECMAScript 5 standard.


### map

Creates a new array with the results of calling a provided function on every element in this array. ...

Creates a new array with the results of calling a provided function on every element in this array. `map` calls a provided `callback` function once for each element in an array, in order, and constructs a new array from the results. `callback` is invoked only for indexes of the array which have assigned values; it is not invoked for indexes which have been deleted or which have never been assigned values. If a `thisArg` parameter is provided to map, it will be used as the `this` for each invocation of the `callback`. If it is not provided, or is `null`, the global object associated with callback is used instead. `map` does not mutate the array on which it is called. The range of elements processed by `map` is set before the first invocation of `callback`. Elements which are appended to the array after the call to `map` begins will not be visited by `callback`. If existing elements of the array are changed, or deleted, their value as passed to `callback` will be the value at the time `map` visits them; elements that are deleted are not visited. The following code creates an array of "plural" forms of nouns from an array of their singular forms. The following code takes an array of numbers and creates a new array containing the square roots of the numbers in the first array. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** callback : FunctionFunction that produces an element of the new Array from an element of the current one. Parametersvalue : MixedThe element value.


### pop

The pop method removes the last element from an array and returns that value to the caller. ...

The pop method removes the last element from an array and returns that value to the caller. `pop` is intentionally generic; this method can be called or applied to objects resembling arrays. Objects which do not contain a length property reflecting the last in a series of consecutive, zero-based numerical properties may not behave in any meaningful manner.

**Returns:** ObjectThe last element in the array


### push

Adds one or more elements to the end of an array and returns the new length of the array. ...

Adds one or more elements to the end of an array and returns the new length of the array. `push` is intentionally generic. This method can be called or applied to objects resembling arrays. The push method relies on a length property to determine where to start inserting the given values. If the length property cannot be converted into a number, the index used is 0. This includes the possibility of length being nonexistent, in which case length will also be created. The only native, array-like objects are strings, although they are not suitable in applications of this method, as strings are immutable. Adding elements to an array The following code creates the sports array containing two elements, then appends two elements to it. After the code executes, sports contains 4 elements: "soccer", "baseball", "football" and "swimming".

**Parameters:** elements : Object...The elements to add to the end of the array.


### reduce

Applies a function against an accumulator and each value of the array (from left-to-right) as to reduce it to a singl...

Applies a function against an accumulator and each value of the array (from left-to-right) as to reduce it to a single value. `reduce` executes the `callback` function once for each element present in the array, excluding holes in the array. The first time the `callback` is called, `previousValue` and `currentValue` can be one of two values. If `initialValue` is provided in the call to `reduce`, then `previousValue` will be equal to `initialValue` and `currentValue` will be equal to the first value in the array. If no `initialValue` was provided, then `previousValue` will be equal to the first value in the array and `currentValue` will be equal to the second. Suppose the following use of reduce occurred: The callback would be invoked four times, with the arguments and return values in each call being as follows: previousValue currentValue index array return value first call 0 1 1 [0,1,2,3,4] 1 second call 1 2 2 [0,1,2,3,4] 3 third call 3 3 3 [0,1,2,3,4] 6 fourth call 6 4 4 [0,1,2,3,4] 10 The value returned by `reduce` would be that of the last callback invocation (10). If you were to provide an initial value as the second argument to reduce, the result would look like this: previousValue currentValue index array return value first call 10 0 0 [0,1,2,3,4] 10 second call 10 1 1 [0,1,2,3,4] 11 third call 11 2 2 [0,1,2,3,4] 13 fourth call 13 3 3 [0,1,2,3,4] 16 fifth call 16 4 4 [0,1,2,3,4] 20 The value returned by `reduce` this time would be, of course, 20. Example: Sum up all values within an array: Example: Flatten an array of arrays: **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** callback : FunctionFunction to execute on each value in the array. ParameterspreviousValue : MixedThe value previously returned in the last invocation of the `callback`, or `initialValue`, if supplied.


### reduceRight

Applies a function simultaneously against two values of the array (from right-to-left) as to reduce it to a single va...

Applies a function simultaneously against two values of the array (from right-to-left) as to reduce it to a single value. `reduceRight` executes the `callback` function once for each element present in the array, excluding holes in the array. The first time the `callback` is called, `previousValue` and `currentValue` can be one of two values. If `initialValue` is provided in the call to `reduceRight`, then `previousValue` will be equal to `initialValue` and `currentValue` will be equal to the last value in the array. If no `initialValue` was provided, then `previousValue` will be equal to the last value in the array and `currentValue` will be equal to the second-to-last value. Some example run-throughs of the function would look like this: And if you were to provide an initialValue, the result would look like this: **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** callback : FunctionFunction to execute on each value in the array. ParameterspreviousValue : MixedThe value previously returned in the last invocation of the `callback`, or `initialValue`, if supplied.


### reverse

Reverses the order of the elements of an array -- the first becomes the last, and the last becomes the first. ...

Reverses the order of the elements of an array -- the first becomes the last, and the last becomes the first. The reverse method transposes the elements of the calling array object in place, mutating the array, and returning a reference to the array. The following example creates an array myArray, containing three elements, then reverses the array. This code changes myArray so that: - myArray[0] is "three" - myArray[1] is "two" - myArray[2] is "one"

**Returns:** ArrayA reference to the array


### shift

Removes the first element from an array and returns that element. ...

Removes the first element from an array and returns that element. The `shift` method removes the element at the zeroeth index and shifts the values at consecutive indexes down, then returns the removed value. `shift` is intentionally generic; this method can be called or applied to objects resembling arrays. Objects which do not contain a `length` property reflecting the last in a series of consecutive, zero-based numerical properties may not behave in any meaningful manner. The following code displays the `myFish` array before and after removing its first element. It also displays the removed element: This example displays the following:

**Returns:** ObjectThe first element of the array prior to shifting.


### slice

Extracts a section of an array and returns a new array. ...

Extracts a section of an array and returns a new array. `slice` does not alter the original array, but returns a new "one level deep" copy that contains copies of the elements sliced from the original array. Elements of the original array are copied into the new array as follows: * For object references (and not the actual object), `slice` copies object references into the new array. Both the original and new array refer to the same object. If a referenced object changes, the changes are visible to both the new and original arrays. * For strings and numbers (not String and Number objects), `slice` copies strings and numbers into the new array. Changes to the string or number in one array does not affect the other array. If a new element is added to either array, the other array is not affected. Using slice In the following example, `slice` creates a new array, `newCar`, from `myCar`. Both include a reference to the object `myHonda`. When the color of `myHonda` is changed to purple, both arrays reflect the change. This script writes:

**Parameters:** begin : NumberZero-based index at which to begin extraction. As a negative index, `start` indicates an offset from the end of the sequence. `slice(-2)` extracts the second-to-last element and the last element in the sequence


### some

Tests whether some element in the array passes the test implemented by the provided function. ...

Tests whether some element in the array passes the test implemented by the provided function. `some` executes the `callback` function once for each element present in the array until it finds one where `callback` returns a true value. If such an element is found, some immediately returns true. Otherwise, some returns false. `callback` is invoked only for indexes of the array which have assigned values; it is not invoked for indexes which have been deleted or which have never been assigned values. If a `thisObject` parameter is provided to some, it will be used as the `this` for each invocation of the `callback`. If it is not provided, or is `null`, the global object associated with callback is used instead. `some` does not mutate the array on which it is called. The range of elements processed by `some` is set before the first invocation of callback. Elements that are appended to the array after the call to some begins will not be visited by `callback`. If an existing, unvisited element of the array is changed by `callback`, its value passed to the visiting callback will be the value at the time that `some` visits that element's index; elements that are deleted are not visited. The following example tests whether some element in the array is bigger than 10. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** callback : FunctionFunction to test for each element. Parametersvalue : MixedThe element value.


### sort

Sorts the elements of an array. ...

Sorts the elements of an array. If `compareFunction` is not supplied, elements are sorted by converting them to strings and comparing strings in lexicographic ("dictionary" or "telephone book," not numerical) order. For example, "80" comes before "9" in lexicographic order, but in a numeric sort 9 comes before 80. If `compareFunction` is supplied, the array elements are sorted according to the return value of the compare function. If a and b are two elements being compared, then: If `compareFunction(a, b)` is less than 0, sort `a` to a lower index than `b`. If `compareFunction(a, b)` returns 0, leave `a` and `b` unchanged with respect to each other, but sorted with respect to all different elements. Note: the ECMAscript standard does not guarantee this behaviour, and thus not all browsers respect this. If `compareFunction(a, b)` is greater than 0, sort `b` to a lower index than `a`. `compareFunction(a, b)` must always returns the same value when given a specific pair of elements a and b as its two arguments. If inconsistent results are returned then the sort order is undefined So, the compare function has the following form: To compare numbers instead of strings, the compare function can simply subtract `b` from `a`: The sort() method can be conveniently used with closures:

**Parameters:** compareFunction : FunctionSpecifies a function that defines the sort order. If omitted, the array is sorted lexicographically (in dictionary order) according to the string conversion of each element.


### splice

Adds and/or removes elements from an array. ...

Adds and/or removes elements from an array. If you specify a different number of elements to insert than the number you're removing, the array will have a different length at the end of the call. This script displays:

**Parameters:** index : NumberIndex at which to start changing the array. If negative, will begin that many elements from the end.


### toString

Returns a string representing the array and its elements. ...

**Returns:** a string representing the array and its elements. Overrides the `Object.prototype.toString` method. The Array object overrides the `toString` method of Object. For Array objects, the `toString` method joins the array and returns one string containing each array element separated by commas. For example, the following code creates an array and uses `toString` to convert the array to a string. JavaScript calls the `toString` method automatically when an array is to be represented as a text value or when an array is referred to in a string concatenation. ReturnsStringThe array as a string.


### unshift

Adds one or more elements to the front of an array and returns the new length of the array. ...

Adds one or more elements to the front of an array and returns the new length of the array. The `unshift` method inserts the given values to the beginning of an array-like object. `unshift` is intentionally generic; this method can be called or applied to objects resembling arrays. Objects which do not contain a `length` property reflecting the last in a series of consecutive, zero-based numerical properties may not behave in any meaningful manner. The following code displays the myFish array before and after adding elements to it. This example displays the following:

**Parameters:** elements : Object...The elements to add to the front of the array.


### isArray

Returns true if an object is an array, false if it is not. ...

**Parameters:** obj : MixedThe object to be checked.

**Returns:** true if an object is an array, false if it is not. **NOTE:** This method is part of the ECMAScript 5 standard.


## Methods

### Array

Creates new Array object. ...

Creates new Array object.

**Parameters:** items : Number/Object...Either a number that specifies the length of array or any number of items for the array.


### concat

Returns a new array comprised of this array joined with other array(s) and/or value(s). ...

**Parameters:** values : Object...Arrays and/or values to concatenate to the resulting array.

**Returns:** a new array comprised of this array joined with other array(s) and/or value(s). `concat` creates a new array consisting of the elements in the `this` object on which it is called, followed in order by, for each argument, the elements of that argument (if the argument is an array) or the argument itself (if the argument is not an array). `concat` does not alter `this` or any of the arrays provided as arguments but instead returns a "one level deep" copy that contains copies of the same elements combined from the original arrays. Elements of the original arrays are copied into the new array as follows: Object references (and not the actual object): `concat` copies object references into the new array. Both the original and new array refer to the same object. That is, if a referenced object is modified, the changes are visible to both the new and original arrays. Strings and numbers (not String and Number objects): `concat` copies the values of strings and numbers into the new array. Any operation on the new array will have no effect on the original arrays, and vice versa. Concatenating two arrays The following code concatenates two arrays: Concatenating three arrays The following code concatenates three arrays: Concatenating values to an array The following code concatenates three values to an array:


### every

Tests whether all elements in the array pass the test implemented by the provided function. ...

Tests whether all elements in the array pass the test implemented by the provided function. `every` executes the provided `callback` function once for each element present in the array until it finds one where `callback` returns a false value. If such an element is found, the `every` method immediately returns false. Otherwise, if `callback` returned a true value for all elements, `every` will return true. `callback` is invoked only for indexes of the array which have assigned values; it is not invoked for indexes which have been deleted or which have never been assigned values. If a `thisObject` parameter is provided to `every`, it will be used as the `this` for each invocation of the callback. If it is not provided, or is `null`, the global object associated with callback is used instead. `every` does not mutate the array on which it is called. The range of elements processed by `every` is set before the first invocation of callback. Elements which are appended to the array after the call to every begins will not be visited by `callback`. If existing elements of the array are changed, their value as passed to `callback` will be the value at the time `every` visits them; elements that are deleted are not visited. `every` acts like the "for all" quantifier in mathematics. In particular, for an empty array, it returns true. (It is vacuously true that all elements of the empty set satisfy any given condition.) The following example tests whether all elements in the array are bigger than 10. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** callback : FunctionFunction to test for each element. Parametersvalue : MixedThe element value.


### filter

Creates a new array with all elements that pass the test implemented by the provided function. ...

Creates a new array with all elements that pass the test implemented by the provided function. `filter` calls a provided `callback` function once for each element in an array, and constructs a new array of all the values for which `callback` returns a true value. `callback` is invoked only for indexes of the array which have assigned values; it is not invoked for indexes which have been deleted or which have never been assigned values. Array elements which do not pass the `callback` test are simply skipped, and are not included in the new array. If a `thisObject` parameter is provided to `filter`, it will be used as the `this` for each invocation of the `callback`. If it is not provided, or is `null`, the global object associated with callback is used instead. `filter` does not mutate the array on which it is called. The range of elements processed by `filter` is set before the first invocation of `callback`. Elements which are appended to the array after the call to `filter` begins will not be visited by `callback`. If existing elements of the array are changed, or deleted, their value as passed to `callback` will be the value at the time `filter` visits them; elements that are deleted are not visited. The following example uses filter to create a filtered array that has all elements with values less than 10 removed. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** callback : FunctionFunction to test for each element. Parametersvalue : MixedThe element value.


### forEach

Executes a provided function once per array element. ...

Executes a provided function once per array element. `forEach` executes the provided function (`callback`) once for each element present in the array. `callback` is invoked only for indexes of the array which have assigned values; it is not invoked for indexes which have been deleted or which have never been assigned values. If a `thisArg` parameter is provided to `forEach`, it will be used as the `this` value for each `callback` invocation as if `callback.call(thisArg, element, index, array)` was called. If `thisArg` is `undefined` or `null`, the `this` value within the function depends on whether the function is in strict mode or not (passed value if in strict mode, global object if in non-strict mode). The `range` of elements processed by `forEach` is set before the first invocation of `callback`. Elements which are appended to the array after the call to `forEach` begins will not be visited by `callback`. If existing elements of the array are changed, or deleted, their value as passed to callback will be the value at the time `forEach` visits them; elements that are deleted are not visited. The following code logs a line for each element in an array: **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** callback : FunctionFunction to execute for each element. Parametersvalue : MixedThe element value.


### indexOf

Returns the first index at which a given element can be found in the array, or -1 if it is not present. ...

**Parameters:** searchElement : MixedElement to locate in the array.

**Returns:** the first index at which a given element can be found in the array, or -1 if it is not present. `indexOf` compares `searchElement` to elements of the Array using strict equality (the same method used by the `===`, or triple-equals, operator). **NOTE:** This method is part of the ECMAScript 5 standard.


### join

Joins all elements of an array into a string. ...

Joins all elements of an array into a string. The string conversions of all array elements are joined into one string. The following example creates an array, `a`, with three elements, then joins the array three times: using the default separator, then a comma and a space, and then a plus.

**Parameters:** separator : StringSpecifies a string to separate each element of the array. The separator is converted to a string if necessary. If omitted, the array elements are separated with a comma.


### lastIndexOf

Returns the last index at which a given element can be found in the array, or -1 if it is not present. ...

**Parameters:** searchElement : MixedElement to locate in the array.

**Returns:** the last index at which a given element can be found in the array, or -1 if it is not present. The array is searched backwards, starting at `fromIndex`. `lastIndexOf` compares `searchElement` to elements of the Array using strict equality (the same method used by the `===`, or triple-equals, operator). **NOTE:** This method is part of the ECMAScript 5 standard.


### map

Creates a new array with the results of calling a provided function on every element in this array. ...

Creates a new array with the results of calling a provided function on every element in this array. `map` calls a provided `callback` function once for each element in an array, in order, and constructs a new array from the results. `callback` is invoked only for indexes of the array which have assigned values; it is not invoked for indexes which have been deleted or which have never been assigned values. If a `thisArg` parameter is provided to map, it will be used as the `this` for each invocation of the `callback`. If it is not provided, or is `null`, the global object associated with callback is used instead. `map` does not mutate the array on which it is called. The range of elements processed by `map` is set before the first invocation of `callback`. Elements which are appended to the array after the call to `map` begins will not be visited by `callback`. If existing elements of the array are changed, or deleted, their value as passed to `callback` will be the value at the time `map` visits them; elements that are deleted are not visited. The following code creates an array of "plural" forms of nouns from an array of their singular forms. The following code takes an array of numbers and creates a new array containing the square roots of the numbers in the first array. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** callback : FunctionFunction that produces an element of the new Array from an element of the current one. Parametersvalue : MixedThe element value.


### pop

The pop method removes the last element from an array and returns that value to the caller. ...

The pop method removes the last element from an array and returns that value to the caller. `pop` is intentionally generic; this method can be called or applied to objects resembling arrays. Objects which do not contain a length property reflecting the last in a series of consecutive, zero-based numerical properties may not behave in any meaningful manner.

**Returns:** ObjectThe last element in the array


### push

Adds one or more elements to the end of an array and returns the new length of the array. ...

Adds one or more elements to the end of an array and returns the new length of the array. `push` is intentionally generic. This method can be called or applied to objects resembling arrays. The push method relies on a length property to determine where to start inserting the given values. If the length property cannot be converted into a number, the index used is 0. This includes the possibility of length being nonexistent, in which case length will also be created. The only native, array-like objects are strings, although they are not suitable in applications of this method, as strings are immutable. Adding elements to an array The following code creates the sports array containing two elements, then appends two elements to it. After the code executes, sports contains 4 elements: "soccer", "baseball", "football" and "swimming".

**Parameters:** elements : Object...The elements to add to the end of the array.


### reduce

Applies a function against an accumulator and each value of the array (from left-to-right) as to reduce it to a singl...

Applies a function against an accumulator and each value of the array (from left-to-right) as to reduce it to a single value. `reduce` executes the `callback` function once for each element present in the array, excluding holes in the array. The first time the `callback` is called, `previousValue` and `currentValue` can be one of two values. If `initialValue` is provided in the call to `reduce`, then `previousValue` will be equal to `initialValue` and `currentValue` will be equal to the first value in the array. If no `initialValue` was provided, then `previousValue` will be equal to the first value in the array and `currentValue` will be equal to the second. Suppose the following use of reduce occurred: The callback would be invoked four times, with the arguments and return values in each call being as follows: previousValue currentValue index array return value first call 0 1 1 [0,1,2,3,4] 1 second call 1 2 2 [0,1,2,3,4] 3 third call 3 3 3 [0,1,2,3,4] 6 fourth call 6 4 4 [0,1,2,3,4] 10 The value returned by `reduce` would be that of the last callback invocation (10). If you were to provide an initial value as the second argument to reduce, the result would look like this: previousValue currentValue index array return value first call 10 0 0 [0,1,2,3,4] 10 second call 10 1 1 [0,1,2,3,4] 11 third call 11 2 2 [0,1,2,3,4] 13 fourth call 13 3 3 [0,1,2,3,4] 16 fifth call 16 4 4 [0,1,2,3,4] 20 The value returned by `reduce` this time would be, of course, 20. Example: Sum up all values within an array: Example: Flatten an array of arrays: **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** callback : FunctionFunction to execute on each value in the array. ParameterspreviousValue : MixedThe value previously returned in the last invocation of the `callback`, or `initialValue`, if supplied.


### reduceRight

Applies a function simultaneously against two values of the array (from right-to-left) as to reduce it to a single va...

Applies a function simultaneously against two values of the array (from right-to-left) as to reduce it to a single value. `reduceRight` executes the `callback` function once for each element present in the array, excluding holes in the array. The first time the `callback` is called, `previousValue` and `currentValue` can be one of two values. If `initialValue` is provided in the call to `reduceRight`, then `previousValue` will be equal to `initialValue` and `currentValue` will be equal to the last value in the array. If no `initialValue` was provided, then `previousValue` will be equal to the last value in the array and `currentValue` will be equal to the second-to-last value. Some example run-throughs of the function would look like this: And if you were to provide an initialValue, the result would look like this: **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** callback : FunctionFunction to execute on each value in the array. ParameterspreviousValue : MixedThe value previously returned in the last invocation of the `callback`, or `initialValue`, if supplied.


### reverse

Reverses the order of the elements of an array -- the first becomes the last, and the last becomes the first. ...

Reverses the order of the elements of an array -- the first becomes the last, and the last becomes the first. The reverse method transposes the elements of the calling array object in place, mutating the array, and returning a reference to the array. The following example creates an array myArray, containing three elements, then reverses the array. This code changes myArray so that: - myArray[0] is "three" - myArray[1] is "two" - myArray[2] is "one"

**Returns:** ArrayA reference to the array


### shift

Removes the first element from an array and returns that element. ...

Removes the first element from an array and returns that element. The `shift` method removes the element at the zeroeth index and shifts the values at consecutive indexes down, then returns the removed value. `shift` is intentionally generic; this method can be called or applied to objects resembling arrays. Objects which do not contain a `length` property reflecting the last in a series of consecutive, zero-based numerical properties may not behave in any meaningful manner. The following code displays the `myFish` array before and after removing its first element. It also displays the removed element: This example displays the following:

**Returns:** ObjectThe first element of the array prior to shifting.


### slice

Extracts a section of an array and returns a new array. ...

Extracts a section of an array and returns a new array. `slice` does not alter the original array, but returns a new "one level deep" copy that contains copies of the elements sliced from the original array. Elements of the original array are copied into the new array as follows: * For object references (and not the actual object), `slice` copies object references into the new array. Both the original and new array refer to the same object. If a referenced object changes, the changes are visible to both the new and original arrays. * For strings and numbers (not String and Number objects), `slice` copies strings and numbers into the new array. Changes to the string or number in one array does not affect the other array. If a new element is added to either array, the other array is not affected. Using slice In the following example, `slice` creates a new array, `newCar`, from `myCar`. Both include a reference to the object `myHonda`. When the color of `myHonda` is changed to purple, both arrays reflect the change. This script writes:

**Parameters:** begin : NumberZero-based index at which to begin extraction. As a negative index, `start` indicates an offset from the end of the sequence. `slice(-2)` extracts the second-to-last element and the last element in the sequence


### some

Tests whether some element in the array passes the test implemented by the provided function. ...

Tests whether some element in the array passes the test implemented by the provided function. `some` executes the `callback` function once for each element present in the array until it finds one where `callback` returns a true value. If such an element is found, some immediately returns true. Otherwise, some returns false. `callback` is invoked only for indexes of the array which have assigned values; it is not invoked for indexes which have been deleted or which have never been assigned values. If a `thisObject` parameter is provided to some, it will be used as the `this` for each invocation of the `callback`. If it is not provided, or is `null`, the global object associated with callback is used instead. `some` does not mutate the array on which it is called. The range of elements processed by `some` is set before the first invocation of callback. Elements that are appended to the array after the call to some begins will not be visited by `callback`. If an existing, unvisited element of the array is changed by `callback`, its value passed to the visiting callback will be the value at the time that `some` visits that element's index; elements that are deleted are not visited. The following example tests whether some element in the array is bigger than 10. **NOTE:** This method is part of the ECMAScript 5 standard.

**Parameters:** callback : FunctionFunction to test for each element. Parametersvalue : MixedThe element value.


### sort

Sorts the elements of an array. ...

Sorts the elements of an array. If `compareFunction` is not supplied, elements are sorted by converting them to strings and comparing strings in lexicographic ("dictionary" or "telephone book," not numerical) order. For example, "80" comes before "9" in lexicographic order, but in a numeric sort 9 comes before 80. If `compareFunction` is supplied, the array elements are sorted according to the return value of the compare function. If a and b are two elements being compared, then: If `compareFunction(a, b)` is less than 0, sort `a` to a lower index than `b`. If `compareFunction(a, b)` returns 0, leave `a` and `b` unchanged with respect to each other, but sorted with respect to all different elements. Note: the ECMAscript standard does not guarantee this behaviour, and thus not all browsers respect this. If `compareFunction(a, b)` is greater than 0, sort `b` to a lower index than `a`. `compareFunction(a, b)` must always returns the same value when given a specific pair of elements a and b as its two arguments. If inconsistent results are returned then the sort order is undefined So, the compare function has the following form: To compare numbers instead of strings, the compare function can simply subtract `b` from `a`: The sort() method can be conveniently used with closures:

**Parameters:** compareFunction : FunctionSpecifies a function that defines the sort order. If omitted, the array is sorted lexicographically (in dictionary order) according to the string conversion of each element.


### splice

Adds and/or removes elements from an array. ...

Adds and/or removes elements from an array. If you specify a different number of elements to insert than the number you're removing, the array will have a different length at the end of the call. This script displays:

**Parameters:** index : NumberIndex at which to start changing the array. If negative, will begin that many elements from the end.


### toString

Returns a string representing the array and its elements. ...

**Returns:** a string representing the array and its elements. Overrides the `Object.prototype.toString` method. The Array object overrides the `toString` method of Object. For Array objects, the `toString` method joins the array and returns one string containing each array element separated by commas. For example, the following code creates an array and uses `toString` to convert the array to a string. JavaScript calls the `toString` method automatically when an array is to be represented as a text value or when an array is referred to in a string concatenation. ReturnsStringThe array as a string.


### unshift

Adds one or more elements to the front of an array and returns the new length of the array. ...

Adds one or more elements to the front of an array and returns the new length of the array. The `unshift` method inserts the given values to the beginning of an array-like object. `unshift` is intentionally generic; this method can be called or applied to objects resembling arrays. Objects which do not contain a `length` property reflecting the last in a series of consecutive, zero-based numerical properties may not behave in any meaningful manner. The following code displays the myFish array before and after adding elements to it. This example displays the following:

**Parameters:** elements : Object...The elements to add to the front of the array.


### isArray

Returns true if an object is an array, false if it is not. ...

**Parameters:** obj : MixedThe object to be checked.

**Returns:** true if an object is an array, false if it is not. **NOTE:** This method is part of the ECMAScript 5 standard.


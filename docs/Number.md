# Number

## Description

Creates a wrapper object to allow you to work with numerical values.

The primary uses for the `Number` object are:

If the argument cannot be converted into a number, it returns `NaN`.

In a non-constructor context (i.e., without the `new` operator), `Number` can be used to perform a type conversion.

The following example uses the `Number` object's properties to assign values to several numeric variables:

biggestNum = Number.MAX_VALUE; smallestNum = Number.MIN_VALUE; infiniteNum = Number.POSITIVE_INFINITY; negInfiniteNum = Number.NEGATIVE_INFINITY; notANum = Number.NaN; Using `Number` to convert a `Date` object The following example converts the `Date` object to a numerical value using `Number` as a function:

var d = new Date("December 17, 1995 03:24:00"); print(Number(d)); This displays "819199440000".

The following example converts the Date object to a numerical value using `Number` as a function:

## Properties

### NEGATIVE_INFINITY

**Type:** Number

Special value representing negative infinity; returned on overflow. ...

Special value representing negative infinity; returned on overflow. The value of `Number.NEGATIVE_INFINITY` is the same as the negative value of the global object's Infinity property. This value behaves slightly differently than mathematical infinity: - Any positive value, including POSITIVE_INFINITY, multiplied by NEGATIVE_INFINITY is NEGATIVE_INFINITY. - Any negative value, including NEGATIVE_INFINITY, multiplied by NEGATIVE_INFINITY is POSITIVE_INFINITY. - Zero multiplied by NEGATIVE_INFINITY is NaN. - NaN multiplied by NEGATIVE_INFINITY is NaN. - NEGATIVE_INFINITY, divided by any negative value except NEGATIVE_INFINITY, is POSITIVE_INFINITY. - NEGATIVE_INFINITY, divided by any positive value except POSITIVE_INFINITY, is NEGATIVE_INFINITY. - NEGATIVE_INFINITY, divided by either NEGATIVE_INFINITY or POSITIVE_INFINITY, is NaN. - Any number divided by NEGATIVE_INFINITY is Zero. Several JavaScript methods (such as the `Number` constructor, `parseFloat`, and `parseInt`) return `NaN` if the value specified in the parameter is significantly lower than `Number.MIN_VALUE`. You might use the `Number.NEGATIVE_INFINITY` property to indicate an error condition that returns a finite number in case of success. Note, however, that `isFinite` would be more appropriate in such a case. In the following example, the variable smallNumber is assigned a value that is smaller than the minimum value. When the `if` statement executes, `smallNumber` has the value `"-Infinity"`, so `smallNumber` is set to a more manageable value before continuing.


### POSITIVE_INFINITY

**Type:** Number

Special value representing infinity; returned on overflow. ...

Special value representing infinity; returned on overflow. The value of `Number.POSITIVE_INFINITY` is the same as the value of the global object's Infinity property. This value behaves slightly differently than mathematical infinity: - Any positive value, including POSITIVE_INFINITY, multiplied by POSITIVE_INFINITY is POSITIVE_INFINITY. - Any negative value, including NEGATIVE_INFINITY, multiplied by POSITIVE_INFINITY is NEGATIVE_INFINITY. - Zero multiplied by POSITIVE_INFINITY is NaN. - NaN multiplied by POSITIVE_INFINITY is NaN. - POSITIVE_INFINITY, divided by any negative value except NEGATIVE_INFINITY, is NEGATIVE_INFINITY. - POSITIVE_INFINITY, divided by any positive value except POSITIVE_INFINITY, is POSITIVE_INFINITY. - POSITIVE_INFINITY, divided by either NEGATIVE_INFINITY or POSITIVE_INFINITY, is NaN. - Any number divided by POSITIVE_INFINITY is Zero. Several JavaScript methods (such as the `Number` constructor, `parseFloat`, and `parseInt`) return `NaN` if the value specified in the parameter is significantly higher than `Number.MAX_VALUE`. You might use the `Number.POSITIVE_INFINITY` property to indicate an error condition that returns a finite number in case of success. Note, however, that `isFinite` would be more appropriate in such a case. In the following example, the variable `bigNumber` is assigned a value that is larger than the maximum value. When the if statement executes, `bigNumber` has the value "Infinity", so `bigNumber` is set to a more manageable value before continuing.


### MAX_VALUE

**Type:** Number

The largest positive representable number. ...

The largest positive representable number. The largest negative representable number is `-MAX_VALUE`. The `MAX_VALUE` property has a value of approximately 1.79E+308. Values larger than `MAX_VALUE` are represented as `"Infinity"`. Because `MAX_VALUE` is a static property of `Number`, you always use it as `Number.MAX_VALUE`, rather than as a property of a `Number` object you created. The following code multiplies two numeric values. If the result is less than or equal to `MAX_VALUE`, the `func1` function is called; otherwise, the `func2` function is called.


### MIN_VALUE

**Type:** Number

The smallest positive representable number -- that is, the positive number closest to zero (without actually being ze...

The smallest positive representable number -- that is, the positive number closest to zero (without actually being zero). The smallest negative representable number is `-MIN_VALUE`. The `MIN_VALUE` property is the number closest to 0, not the most negative number, that JavaScript can represent. `MIN_VALUE` has a value of approximately 5e-324. Values smaller than `MIN_VALUE` ("underflow values") are converted to 0. Because `MIN_VALUE` is a static property of `Number`, you always use it as `Number.MIN_VALUE`, rather than as a property of a `Number` object you created. The following code divides two numeric values. If the result is greater than or equal to `MIN_VALUE`, the `func1` function is called; otherwise, the `func2` function is called.


### NaN

**Type:** Number

Special "not a number" value.


### Number

Creates new Number object. ...

Creates new Number object.

**Parameters:** value : ObjectThe numeric value of the object being created.


### toExponential

Returns a string representing the number in exponential notation. ...

**Parameters:** fractionDigits : NumberAn integer specifying the number of digits after the decimal point. Defaults to as many digits as necessary to specify the number.

**Returns:** a string representing the number in exponential notation. A string representing a `Number` object in exponential notation with one digit before the decimal point, rounded to `fractionDigits` digits after the decimal point. If the `fractionDigits` argument is omitted, the number of digits after the decimal point defaults to the number of digits necessary to represent the value uniquely. If you use the `toExponential` method for a numeric literal and the numeric literal has no exponent and no decimal point, leave a space before the dot that precedes the method call to prevent the dot from being interpreted as a decimal point. If a number has more digits that requested by the `fractionDigits` parameter, the number is rounded to the nearest number represented by `fractionDigits` digits. See the discussion of rounding in the description of the `toFixed` method, which also applies to `toExponential`.


### toFixed

Returns a string representing the number in fixed-point notation. ...

**Parameters:** digits : NumberThe number of digits to appear after the decimal point; this may be a value between 0 and 20, inclusive, and implementations may optionally support a larger range of values. If this argument is omitted, it is treated as 0.

**Returns:** a string representing the number in fixed-point notation.


### toLocaleString

Returns a human readable string representing the number using the locale of the environment. ...

**Returns:** a human readable string representing the number using the locale of the environment. Overrides the `Object.prototype.toLocaleString` method. This method available to numbers will convert the number into a string which is suitable for presentation in the given locale. ReturnsStringString representing the number.


### toPrecision

Returns a string representing the number to a specified precision in fixed- point or exponential notation. ...

**Parameters:** precision : NumberAn integer specifying the number of significant digits.

**Returns:** a string representing the number to a specified precision in fixed- point or exponential notation. A string representing a `Number` object in fixed-point or exponential notation rounded to precision significant digits. See the discussion of rounding in the description of the `toFixed` method, which also applies to `toPrecision`. If the precision argument is omitted, behaves as Number.toString. If it is a non-integer value, it is rounded to the nearest integer. After rounding, if that value is not between 1 and 100 (inclusive), a RangeError is thrown.


### toString

Returns a string representing the specified object. ...

**Parameters:** radix : NumberAn integer between 2 and 36 specifying the base to use for representing numeric values.

**Returns:** a string representing the specified object. Overrides the `Object.prototype.toString` method. The `Number` object overrides the `toString` method of the `Object` object; it does not inherit `Object.toString`. For `Number` objects, the toString method returns a string representation of the object in the specified radix. The `toString` method parses its first argument, and attempts to return a string representation in the specified radix (base). For radixes above 10, the letters of the alphabet indicate numerals greater than 9. For example, for hexadecimal numbers (base 16), A through F are used. If `toString` is given a radix not between 2 and 36, an exception is thrown. If the radix is not specified, JavaScript assumes the preferred radix is 10.


### valueOf

Returns the primitive value of the specified object. ...

**Returns:** the primitive value of the specified object. Overrides the `Object.prototype.valueOf` method. The `valueOf` method of `Number` returns the primitive value of a `Number` object as a number data type. This method is usually called internally by JavaScript and not explicitly in code. ReturnsNumberThe primitive value of the number.


## Methods

### Number

Creates new Number object. ...

Creates new Number object.

**Parameters:** value : ObjectThe numeric value of the object being created.


### toExponential

Returns a string representing the number in exponential notation. ...

**Parameters:** fractionDigits : NumberAn integer specifying the number of digits after the decimal point. Defaults to as many digits as necessary to specify the number.

**Returns:** a string representing the number in exponential notation. A string representing a `Number` object in exponential notation with one digit before the decimal point, rounded to `fractionDigits` digits after the decimal point. If the `fractionDigits` argument is omitted, the number of digits after the decimal point defaults to the number of digits necessary to represent the value uniquely. If you use the `toExponential` method for a numeric literal and the numeric literal has no exponent and no decimal point, leave a space before the dot that precedes the method call to prevent the dot from being interpreted as a decimal point. If a number has more digits that requested by the `fractionDigits` parameter, the number is rounded to the nearest number represented by `fractionDigits` digits. See the discussion of rounding in the description of the `toFixed` method, which also applies to `toExponential`.


### toFixed

Returns a string representing the number in fixed-point notation. ...

**Parameters:** digits : NumberThe number of digits to appear after the decimal point; this may be a value between 0 and 20, inclusive, and implementations may optionally support a larger range of values. If this argument is omitted, it is treated as 0.

**Returns:** a string representing the number in fixed-point notation.


### toLocaleString

Returns a human readable string representing the number using the locale of the environment. ...

**Returns:** a human readable string representing the number using the locale of the environment. Overrides the `Object.prototype.toLocaleString` method. This method available to numbers will convert the number into a string which is suitable for presentation in the given locale. ReturnsStringString representing the number.


### toPrecision

Returns a string representing the number to a specified precision in fixed- point or exponential notation. ...

**Parameters:** precision : NumberAn integer specifying the number of significant digits.

**Returns:** a string representing the number to a specified precision in fixed- point or exponential notation. A string representing a `Number` object in fixed-point or exponential notation rounded to precision significant digits. See the discussion of rounding in the description of the `toFixed` method, which also applies to `toPrecision`. If the precision argument is omitted, behaves as Number.toString. If it is a non-integer value, it is rounded to the nearest integer. After rounding, if that value is not between 1 and 100 (inclusive), a RangeError is thrown.


### toString

Returns a string representing the specified object. ...

**Parameters:** radix : NumberAn integer between 2 and 36 specifying the base to use for representing numeric values.

**Returns:** a string representing the specified object. Overrides the `Object.prototype.toString` method. The `Number` object overrides the `toString` method of the `Object` object; it does not inherit `Object.toString`. For `Number` objects, the toString method returns a string representation of the object in the specified radix. The `toString` method parses its first argument, and attempts to return a string representation in the specified radix (base). For radixes above 10, the letters of the alphabet indicate numerals greater than 9. For example, for hexadecimal numbers (base 16), A through F are used. If `toString` is given a radix not between 2 and 36, an exception is thrown. If the radix is not specified, JavaScript assumes the preferred radix is 10.


### valueOf

Returns the primitive value of the specified object. ...

**Returns:** the primitive value of the specified object. Overrides the `Object.prototype.valueOf` method. The `valueOf` method of `Number` returns the primitive value of a `Number` object as a number data type. This method is usually called internally by JavaScript and not explicitly in code. ReturnsNumberThe primitive value of the number.


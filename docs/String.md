# String

## Description

`String` is a global object that may be used to construct String instances.

String objects may be created by calling the constructor `new String()`. The `String` object wraps JavaScript's string primitive data type with the methods described below. The global function `String()` can also be called without new in front to create a primitive string. String literals in JavaScript are primitive strings.

Because JavaScript automatically converts between string primitives and String objects, you can call any of the methods of the `String` object on a string primitive. JavaScript automatically converts the string primitive to a temporary `String` object, calls the method, then discards the temporary String object. For example, you can use the `String.length` property on a string primitive created from a string literal:

s_obj = new String(s_prim = s_also_prim = "foo"); s_obj.length; // 3 s_prim.length; // 3 s_also_prim.length; // 3 'foo'.length; // 3 "foo".length; // 3 (A string literal is denoted with single or double quotation marks.)

String objects can be converted to primitive strings with the `valueOf` method.

String primitives and String objects give different results when evaluated as JavaScript. Primitives are treated as source code; String objects are treated as a character sequence object. For example:

s1 = "2 + 2"; // creates a string primitive s2 = new String("2 + 2"); // creates a String object eval(s1); // returns the number 4 eval(s2); // returns the string "2 + 2" eval(s2.valueOf()); // returns the number 4 Character access There are two ways to access an individual character in a string. The first is the `charAt` method:

return 'cat'.charAt(1); // returns "a" The other way is to treat the string as an array, where each index corresponds to an individual character:

return 'cat'[1]; // returns "a" The second way (treating the string as an array) is not part of ECMAScript 3. It is a JavaScript and ECMAScript 5 feature.

In both cases, attempting to set an individual character won't work. Trying to set a character through `charAt` results in an error, while trying to set a character via indexing does not throw an error, but the string itself is unchanged.

C developers have the `strcmp()` function for comparing strings. In JavaScript, you just use the less- than and greater-than operators:

var a = "a"; var b = "b"; if (a < b) // true print(a + " is less than " + b); else if (a > b) print(a + " is greater than " + b); else print(a + " and " + b + " are equal."); A similar result can be achieved using the `localeCompare` method inherited by `String` instances.

## Properties

### length

**Type:** Number

Reflects the length of the string. ...

Reflects the length of the string. This property returns the number of code units in the string. UTF-16, the string format used by JavaScript, uses a single 16-bit code unit to represent the most common characters, but needs to use two code units for less commonly-used characters, so it's possible for the value returned by `length` to not match the actual number of characters in the string. For an empty string, `length` is 0.


### String

Creates new String object. ...

Creates new String object.

**Parameters:** value : ObjectThe value to wrap into String object.


### charAt

Returns the character at the specified index. ...

**Parameters:** index : NumberAn integer between 0 and 1 less than the length of the string.

**Returns:** the character at the specified index. Characters in a string are indexed from left to right. The index of the first character is 0, and the index of the last character in a string called `stringName` is `stringName.length - 1`. If the index you supply is out of range, JavaScript returns an empty string. The following example displays characters at different locations in the string "Brave new world": These lines display the following: The following provides a means of ensuring that going through a string loop always provides a whole character, even if the string contains characters that are not in the Basic Multi-lingual Plane. each loop, passing in the whole string and the current iteration and returning a variable to represent the individual character to treat high private surrogates as single characters) surrogates as single characters) have already processed } While the second example may be more frequently useful for those wishing to support non-BMP characters (since the above does not require the caller to know where any non-BMP character might appear), in the event that one *does* wish, in choosing a character by index, to treat the surrogate pairs within a string as the single characters they represent, one can use the following: surrogate pair


### charCodeAt

Returns a number indicating the Unicode value of the character at the given index. ...

**Parameters:** index : NumberAn integer greater than 0 and less than the length of the string; if it is not a number, it defaults to 0.

**Returns:** a number indicating the Unicode value of the character at the given index. Unicode code points range from 0 to 1,114,111. The first 128 Unicode code points are a direct match of the ASCII character encoding. Note that `charCodeAt` will always return a value that is less than 65,536. This is because the higher code points are represented by a pair of (lower valued) "surrogate" pseudo-characters which are used to comprise the real character. Because of this, in order to examine or reproduce the full character for individual characters of value 65,536 and above, for such characters, it is necessary to retrieve not only `charCodeAt(i)`, but also `charCodeAt(i+1)` (as if examining/reproducing a string with two letters). See example 2 and 3 below. `charCodeAt` returns `NaN` if the given index is not greater than 0 or is greater than the length of the string. Backward Compatibility with JavaScript 1.2 The `charCodeAt` method returns a number indicating the ISO-Latin-1 codeset value of the character at the given index. The ISO-Latin-1 codeset ranges from 0 to 255. The first 0 to 127 are a direct match of the ASCII character set. Example 1: Using `charCodeAt` The following example returns 65, the Unicode value for A. "ABC".charCodeAt(0) // returns 65 Example 2: Fixing `charCodeAt` to handle non-Basic-Multilingual-Plane characters if their presence earlier in the string is unknown This version might be used in for loops and the like when it is unknown whether non-BMP characters exist before the specified index position. high surrogate above in the previous iteration Example 3: Fixing `charCodeAt` to handle non-Basic-Multilingual-Plane characters if their presence earlier in the string is known a surrogate pair


### concat

Combines the text of two strings and returns a new string. ...

Combines the text of two strings and returns a new string. `concat` combines the text from one or more strings and returns a new string. Changes to the text in one string do not affect the other string. The following example combines strings into a new string.

**Parameters:** string2 : String...stringN


### fromCharCode

Returns a string created by using the specified sequence of Unicode values. ...

**Parameters:** num1 : Number, ..., numN A sequence of numbers that are Unicode values.

**Returns:** a string created by using the specified sequence of Unicode values. This method returns a string and not a `String` object. Because `fromCharCode` is a static method of `String`, you always use it as `String.fromCharCode()`, rather than as a method of a `String` object you created. Although most common Unicode values can be represented in a fixed width system/with one number (as expected early on during JavaScript standardization) and `fromCharCode()` can be used to return a single character for the most common values (i.e., UCS-2 values which are the subset of UTF-16 with the most common characters), in order to deal with ALL legal Unicode values, `fromCharCode()` alone is inadequate. Since the higher code point characters use two (lower value) "surrogate" numbers to form a single character, `fromCharCode()` can be used to return such a pair and thus adequately represent these higher valued characters. Be aware, therefore, that the following utility function to grab the accurate character even for higher value code points, may be returning a value which is rendered as a single character, but which has a string count of two (though usually the count will be one). The following example returns the string "ABC".


### indexOf

Returns the index within the calling String object of the first occurrence of the specified value, or -1 if not found. ...

**Parameters:** searchValue : StringA string representing the value to search for.

**Returns:** the index within the calling `String` object of the first occurrence of the specified value, or -1 if not found. Characters in a string are indexed from left to right. The index of the first character is 0, and the index of the last character of a string called `stringName` is `stringName.length - 1`. The `indexOf` method is case sensitive. For example, the following expression returns -1: Note that '0' doesn't evaluate to true and '-1' doesn't evaluate to false. Therefore, when checking if a specific string exists within another string the correct way to check would be: The following example uses indexOf and lastIndexOf to locate values in the string "Brave new world". The following example defines two string variables. The variables contain the same string except that the second string contains uppercase letters. The first `writeln` method displays 19. But because the `indexOf` method is case sensitive, the string "cheddar" is not found in `myCapString`, so the second `writeln` method displays -1. The following example sets count to the number of occurrences of the letter x in the string str:


### lastIndexOf

Returns the index within the calling String object of the last occurrence of the specified value, or -1 if not found. ...

**Parameters:** searchValue : StringA string representing the value to search for.

**Returns:** the index within the calling String object of the last occurrence of the specified value, or -1 if not found. The calling string is searched backward, starting at fromIndex. Characters in a string are indexed from left to right. The index of the first character is 0, and the index of the last character is `stringName.length - 1`. The `lastIndexOf` method is case sensitive. For example, the following expression returns -1: The following example uses `indexOf` and `lastIndexOf` to locate values in the string "`Brave new world`".


### localeCompare

Returns a number indicating whether a reference string comes before or after or is the same as the given string in so...

**Parameters:** compareString : StringThe string against which the referring string is comparing.

**Returns:** a number indicating whether a reference string comes before or after or is the same as the given string in sort order. Returns a number indicating whether a reference string comes before or after or is the same as the given string in sort order. Returns -1 if the string occurs earlier in a sort than `compareString`, returns 1 if the string occurs afterwards in such a sort, and returns 0 if they occur at the same level. The following example demonstrates the different potential results for a string occurring before, after, or at the same level as another:


### match

Used to match a regular expression against a string. ...

Used to match a regular expression against a string. If the regular expression does not include the `g` flag, returns the same result as `regexp.exec(string)`. If the regular expression includes the `g` flag, the method returns an Array containing all matches. If there were no matches, the method returns `null`. The returned Array has an extra `input` property, which contains the regexp that generated it as a result. In addition, it has an `index` property, which represents the zero-based index of the match in the string. In the following example, `match` is used to find "Chapter" followed by 1 or more numeric characters followed by a decimal point and numeric character 0 or more times. The regular expression includes the `i` flag so that case will be ignored. This returns the array containing Chapter 3.4.5.1,Chapter 3.4.5.1,.1 "`Chapter 3.4.5.1`" is the first match and the first value remembered from `(Chapter \d+(\.\d)*)`. "`.1`" is the second value remembered from `(\.\d)`. The following example demonstrates the use of the global and ignore case flags with `match`. All letters A through E and a through e are returned, each its own element in the array `matches_array` now equals `['A', 'B', 'C', 'D', 'E', 'a', 'b', 'c', 'd', 'e']`.

**Parameters:** regexp : RegExpA RegExp object. If a non-RegExp object `obj` is passed, it is implicitly converted to a RegExp by using `new RegExp(obj)`.


### replace

Used to find a match between a regular expression and a string, and to replace the matched substring with a new subst...

Used to find a match between a regular expression and a string, and to replace the matched substring with a new substring. This method does not change the `String` object it is called on. It simply returns a new string. To perform a global search and replace, either include the `g` flag in the regular expression or if the first parameter is a string, include `g` in the flags parameter. The replacement string can include the following special replacement patterns: Pattern Inserts `$$` Inserts a `$`. `$&` Inserts the matched substring. `$`` Inserts the portion of the string that precedes the matched substring. `$'` Inserts the portion of the string that follows the matched substring. `$n` or `$nn` Where `n` or `nn` are decimal digits, inserts the _n_th parenthesized submatch string, provided the first argument was a `RegExp` object. You can specify a function as the second parameter. In this case, the function will be invoked after the match has been performed. The function's result (return value) will be used as the replacement string. (Note: the above-mentioned special replacement patterns do not apply in this case.) Note that the function will be invoked multiple times for each full match to be replaced if the regular expression in the first parameter is global. The arguments to the function are as follows: Possible Name Supplied Value `str` The matched substring. (Corresponds to `$&` above.) `p1, p2, ...` The _n_th parenthesized submatch string, provided the first argument to replace was a `RegExp` object. (Correspond to $1, $2, etc. above.) `offset` The offset of the matched substring within the total string being examined. (For example, if the total string was "`abcd`", and the matched substring was "`bc`", then this argument will be 1.) `s` The total string being examined. (The exact number of arguments will depend on whether the first argument was a `RegExp` object and, if so, how many parenthesized submatches it specifies.) The following example will set `newString` to "`XXzzzz - XX , zzzz`": In the following example, the regular expression includes the global and ignore case flags which permits replace to replace each occurrence of 'apples' in the string with 'oranges'. In this version, a string is used as the first parameter and the global and ignore case flags are specified in the flags parameter. Both of these examples print "oranges are round, and oranges are juicy." In the following example, the regular expression is defined in replace and includes the ignore case flag. This prints "Twas the night before Christmas..." The following script switches the words in the string. For the replacement text, the script uses the $1 and $2 replacement patterns. This prints "Smith, John". In this example, all occurrences of capital letters in the string are converted to lower case, and a hyphen is inserted just before the match location. The important thing here is that additional operations are needed on the matched item before it is given back as a replacement. The replacement function accepts the matched snippet as its parameter, and uses it to transform the case and concatenate the hyphen before returning. Given `styleHyphenFormat('borderTop')`, this returns 'border-top'. Because we want to further transform the *result* of the match before the final substitution is made, we must use a function. This forces the evaluation of the match prior to the `toLowerCase()` method. If we had tried to do this using the match without a function, the `toLowerCase()` would have no effect. This is because `'$&'.toLowerCase()` would be evaluated first as a string literal (resulting in the same `'$&'`) before using the characters as a pattern. The following example replaces a Fahrenheit degree with its equivalent Celsius degree. The Fahrenheit degree should be a number ending with F. The function returns the Celsius number ending with C. For example, if the input number is 212F, the function returns 100C. If the number is 0F, the function returns -17.77777777777778C. The regular expression `test` checks for any number that ends with F. The number of Fahrenheit degree is accessible to the function through its second parameter, `p1`. The function sets the Celsius number based on the Fahrenheit degree passed in a string to the `f2c` function. `f2c` then returns the Celsius number. This function approximates Perl's `s///e` flag.

**Parameters:** pattern : String/RegExpEither a string or regular expression pattern to search for.


### search

Executes the search for a match between a regular expression and a specified string. ...

Executes the search for a match between a regular expression and a specified string. If successful, search returns the index of the regular expression inside the string. Otherwise, it returns -1. When you want to know whether a pattern is found in a string use search (similar to the regular expression `test` method); for more information (but slower execution) use `match` (similar to the regular expression `exec` method). The following example prints a message which depends on the success of the test.

**Parameters:** regexp : RegExpA regular expression object. If a non-RegExp object obj is passed, it is implicitly converted to a RegExp by using `new RegExp(obj)`.


### slice

Extracts a section of a string and returns a new string. ...

Extracts a section of a string and returns a new string. `slice` extracts the text from one string and returns a new string. Changes to the text in one string do not affect the other string. `slice` extracts up to but not including `endSlice`. `string.slice(1,4)` extracts the second character through the fourth character (characters indexed 1, 2, and 3). As a negative index, `endSlice` indicates an offset from the end of the string. `string.slice(2,-1)` extracts the third character through the second to last character in the string. The following example uses slice to create a new string. This writes:

**Parameters:** beginSlice : NumberThe zero-based index at which to begin extraction.


### split

Splits a String object into an array of strings by separating the string into substrings. ...

Splits a `String` object into an array of strings by separating the string into substrings. The `split` method returns the new array. When found, `separator` is removed from the string and the substrings are returned in an array. If `separator` is omitted, the array contains one element consisting of the entire string. If `separator` is a regular expression that contains capturing parentheses, then each time separator is matched the results (including any undefined results) of the capturing parentheses are spliced into the output array. However, not all browsers support this capability. Note: When the string is empty, `split` returns an array containing one empty string, rather than an empty array. The following example defines a function that splits a string into an array of strings using the specified separator. After splitting the string, the function displays messages indicating the original string (before the split), the separator used, the number of elements in the array, and the individual array elements. This example produces the following output: The original string is: "Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec" The separator is: "," The array has 12 elements: Jan / Feb / Mar / Apr / May / Jun / Jul / Aug / Sep / Oct / Nov / Dec / In the following example, `split` looks for 0 or more spaces followed by a semicolon followed by 0 or more spaces and, when found, removes the spaces from the string. nameList is the array returned as a result of split. This prints two lines; the first line prints the original string, and the second line prints the resulting array. In the following example, split looks for 0 or more spaces in a string and returns the first 3 splits that it finds. This script displays the following: If `separator` contains capturing parentheses, matched results are returned in the array. This script displays the following:

**Parameters:** seperator : StringSpecifies the character to use for separating the string. The separator is treated as a string or a regular expression. If separator is omitted, the array returned contains one element consisting of the entire string.


### substr

Returns the characters in a string beginning at the specified location through the specified number of characters. ...

**Parameters:** start : NumberLocation at which to begin extracting characters.

**Returns:** the characters in a string beginning at the specified location through the specified number of characters. `start` is a character index. The index of the first character is 0, and the index of the last character is 1 less than the length of the string. `substr` begins extracting characters at start and collects length characters (unless it reaches the end of the string first, in which case it will return fewer). If `start` is positive and is greater than or equal to the length of the string, `substr` returns an empty string. If `start` is negative, `substr` uses it as a character index from the end of the string. If start is negative and abs(start) is larger than the length of the string, `substr` uses 0 as the start index. Note: the described handling of negative values of the start argument is not supported by Microsoft JScript. If length is 0 or negative, `substr` returns an empty string. If length is omitted, `substr` extracts characters to the end of the string. Consider the following script: This script displays:


### substring

Returns the characters in a string between two indexes into the string. ...

**Parameters:** indexA : NumberAn integer between 0 and one less than the length of the string.

**Returns:** the characters in a string between two indexes into the string. substring extracts characters from indexA up to but not including indexB. In particular: * If `indexA` equals `indexB`, `substring` returns an empty string. * If `indexB` is omitted, substring extracts characters to the end of the string. * If either argument is less than 0 or is `NaN`, it is treated as if it were 0. * If either argument is greater than `stringName.length`, it is treated as if it were `stringName.length`. If `indexA` is larger than `indexB`, then the effect of substring is as if the two arguments were swapped; for example, `str.substring(1, 0) == str.substring(0, 1)`. The following example uses substring to display characters from the string "Sencha": The following example replaces a substring within a string. It will replace both individual characters and `substrings`. The function call at the end of the example changes the string "Brave New World" into "Brave New Web". fullS.length);


### toLocaleLowerCase

The characters within a string are converted to lower case while respecting the current locale. ...

The characters within a string are converted to lower case while respecting the current locale. For most languages, this will return the same as `toLowerCase`. The `toLocaleLowerCase` method returns the value of the string converted to lower case according to any locale-specific case mappings. `toLocaleLowerCase` does not affect the value of the string itself. In most cases, this will produce the same result as `toLowerCase()`, but for some locales, such as Turkish, whose case mappings do not follow the default case mappings in Unicode, there may be a different result. The following example displays the string "sencha":

**Returns:** StringReturns value of the string in lowercase.


### toLocaleUpperCase

The characters within a string are converted to upper case while respecting the current locale. ...

The characters within a string are converted to upper case while respecting the current locale. For most languages, this will return the same as `toUpperCase`. The `toLocaleUpperCase` method returns the value of the string converted to upper case according to any locale-specific case mappings. `toLocaleUpperCase` does not affect the value of the string itself. In most cases, this will produce the same result as `toUpperCase()`, but for some locales, such as Turkish, whose case mappings do not follow the default case mappings in Unicode, there may be a different result. The following example displays the string "SENCHA":

**Returns:** StringReturns value of the string in uppercase.


### toLowerCase

Returns the calling string value converted to lower case. ...

**Returns:** the calling string value converted to lower case. The `toLowerCase` method returns the value of the string converted to lowercase. `toLowerCase` does not affect the value of the string itself. The following example displays the lowercase string "sencha": ReturnsStringReturns value of the string in lowercase.


### toString

Returns a string representing the specified object. ...

**Returns:** a string representing the specified object. Overrides the `Object.toString` method. The `String` object overrides the `toString` method of the `Object` object; it does not inherit `Object.toString`. For `String` objects, the `toString` method returns a string representation of the object. The following example displays the string value of a String object: ReturnsStringA string representation of the object.


### toUpperCase

Returns the calling string value converted to uppercase. ...

**Returns:** the calling string value converted to uppercase. The `toUpperCase` method returns the value of the string converted to uppercase. `toUpperCase` does not affect the value of the string itself. The following example displays the string "SENCHA": ReturnsStringReturns value of the string in uppercase.


### trim

Removes whitespace from both ends of the string. ...

Removes whitespace from both ends of the string. Does not affect the value of the string itself. The following example displays the lowercase string `"foo"`: **NOTE:** This method is part of the ECMAScript 5 standard.

**Returns:** StringA string stripped of whitespace on both ends.


### valueOf

Returns the primitive value of the specified object. ...

**Returns:** the primitive value of the specified object. Overrides the `Object.valueOf` method. The `valueOf` method of String returns the primitive value of a `String` object as a string data type. This value is equivalent to `String.toString`. This method is usually called internally by JavaScript and not explicitly in code. ReturnsStringReturns value of string.


## Methods

### String

Creates new String object. ...

Creates new String object.

**Parameters:** value : ObjectThe value to wrap into String object.


### charAt

Returns the character at the specified index. ...

**Parameters:** index : NumberAn integer between 0 and 1 less than the length of the string.

**Returns:** the character at the specified index. Characters in a string are indexed from left to right. The index of the first character is 0, and the index of the last character in a string called `stringName` is `stringName.length - 1`. If the index you supply is out of range, JavaScript returns an empty string. The following example displays characters at different locations in the string "Brave new world": These lines display the following: The following provides a means of ensuring that going through a string loop always provides a whole character, even if the string contains characters that are not in the Basic Multi-lingual Plane. each loop, passing in the whole string and the current iteration and returning a variable to represent the individual character to treat high private surrogates as single characters) surrogates as single characters) have already processed } While the second example may be more frequently useful for those wishing to support non-BMP characters (since the above does not require the caller to know where any non-BMP character might appear), in the event that one *does* wish, in choosing a character by index, to treat the surrogate pairs within a string as the single characters they represent, one can use the following: surrogate pair


### charCodeAt

Returns a number indicating the Unicode value of the character at the given index. ...

**Parameters:** index : NumberAn integer greater than 0 and less than the length of the string; if it is not a number, it defaults to 0.

**Returns:** a number indicating the Unicode value of the character at the given index. Unicode code points range from 0 to 1,114,111. The first 128 Unicode code points are a direct match of the ASCII character encoding. Note that `charCodeAt` will always return a value that is less than 65,536. This is because the higher code points are represented by a pair of (lower valued) "surrogate" pseudo-characters which are used to comprise the real character. Because of this, in order to examine or reproduce the full character for individual characters of value 65,536 and above, for such characters, it is necessary to retrieve not only `charCodeAt(i)`, but also `charCodeAt(i+1)` (as if examining/reproducing a string with two letters). See example 2 and 3 below. `charCodeAt` returns `NaN` if the given index is not greater than 0 or is greater than the length of the string. Backward Compatibility with JavaScript 1.2 The `charCodeAt` method returns a number indicating the ISO-Latin-1 codeset value of the character at the given index. The ISO-Latin-1 codeset ranges from 0 to 255. The first 0 to 127 are a direct match of the ASCII character set. Example 1: Using `charCodeAt` The following example returns 65, the Unicode value for A. "ABC".charCodeAt(0) // returns 65 Example 2: Fixing `charCodeAt` to handle non-Basic-Multilingual-Plane characters if their presence earlier in the string is unknown This version might be used in for loops and the like when it is unknown whether non-BMP characters exist before the specified index position. high surrogate above in the previous iteration Example 3: Fixing `charCodeAt` to handle non-Basic-Multilingual-Plane characters if their presence earlier in the string is known a surrogate pair


### concat

Combines the text of two strings and returns a new string. ...

Combines the text of two strings and returns a new string. `concat` combines the text from one or more strings and returns a new string. Changes to the text in one string do not affect the other string. The following example combines strings into a new string.

**Parameters:** string2 : String...stringN


### fromCharCode

Returns a string created by using the specified sequence of Unicode values. ...

**Parameters:** num1 : Number, ..., numN A sequence of numbers that are Unicode values.

**Returns:** a string created by using the specified sequence of Unicode values. This method returns a string and not a `String` object. Because `fromCharCode` is a static method of `String`, you always use it as `String.fromCharCode()`, rather than as a method of a `String` object you created. Although most common Unicode values can be represented in a fixed width system/with one number (as expected early on during JavaScript standardization) and `fromCharCode()` can be used to return a single character for the most common values (i.e., UCS-2 values which are the subset of UTF-16 with the most common characters), in order to deal with ALL legal Unicode values, `fromCharCode()` alone is inadequate. Since the higher code point characters use two (lower value) "surrogate" numbers to form a single character, `fromCharCode()` can be used to return such a pair and thus adequately represent these higher valued characters. Be aware, therefore, that the following utility function to grab the accurate character even for higher value code points, may be returning a value which is rendered as a single character, but which has a string count of two (though usually the count will be one). The following example returns the string "ABC".


### indexOf

Returns the index within the calling String object of the first occurrence of the specified value, or -1 if not found. ...

**Parameters:** searchValue : StringA string representing the value to search for.

**Returns:** the index within the calling `String` object of the first occurrence of the specified value, or -1 if not found. Characters in a string are indexed from left to right. The index of the first character is 0, and the index of the last character of a string called `stringName` is `stringName.length - 1`. The `indexOf` method is case sensitive. For example, the following expression returns -1: Note that '0' doesn't evaluate to true and '-1' doesn't evaluate to false. Therefore, when checking if a specific string exists within another string the correct way to check would be: The following example uses indexOf and lastIndexOf to locate values in the string "Brave new world". The following example defines two string variables. The variables contain the same string except that the second string contains uppercase letters. The first `writeln` method displays 19. But because the `indexOf` method is case sensitive, the string "cheddar" is not found in `myCapString`, so the second `writeln` method displays -1. The following example sets count to the number of occurrences of the letter x in the string str:


### lastIndexOf

Returns the index within the calling String object of the last occurrence of the specified value, or -1 if not found. ...

**Parameters:** searchValue : StringA string representing the value to search for.

**Returns:** the index within the calling String object of the last occurrence of the specified value, or -1 if not found. The calling string is searched backward, starting at fromIndex. Characters in a string are indexed from left to right. The index of the first character is 0, and the index of the last character is `stringName.length - 1`. The `lastIndexOf` method is case sensitive. For example, the following expression returns -1: The following example uses `indexOf` and `lastIndexOf` to locate values in the string "`Brave new world`".


### localeCompare

Returns a number indicating whether a reference string comes before or after or is the same as the given string in so...

**Parameters:** compareString : StringThe string against which the referring string is comparing.

**Returns:** a number indicating whether a reference string comes before or after or is the same as the given string in sort order. Returns a number indicating whether a reference string comes before or after or is the same as the given string in sort order. Returns -1 if the string occurs earlier in a sort than `compareString`, returns 1 if the string occurs afterwards in such a sort, and returns 0 if they occur at the same level. The following example demonstrates the different potential results for a string occurring before, after, or at the same level as another:


### match

Used to match a regular expression against a string. ...

Used to match a regular expression against a string. If the regular expression does not include the `g` flag, returns the same result as `regexp.exec(string)`. If the regular expression includes the `g` flag, the method returns an Array containing all matches. If there were no matches, the method returns `null`. The returned Array has an extra `input` property, which contains the regexp that generated it as a result. In addition, it has an `index` property, which represents the zero-based index of the match in the string. In the following example, `match` is used to find "Chapter" followed by 1 or more numeric characters followed by a decimal point and numeric character 0 or more times. The regular expression includes the `i` flag so that case will be ignored. This returns the array containing Chapter 3.4.5.1,Chapter 3.4.5.1,.1 "`Chapter 3.4.5.1`" is the first match and the first value remembered from `(Chapter \d+(\.\d)*)`. "`.1`" is the second value remembered from `(\.\d)`. The following example demonstrates the use of the global and ignore case flags with `match`. All letters A through E and a through e are returned, each its own element in the array `matches_array` now equals `['A', 'B', 'C', 'D', 'E', 'a', 'b', 'c', 'd', 'e']`.

**Parameters:** regexp : RegExpA RegExp object. If a non-RegExp object `obj` is passed, it is implicitly converted to a RegExp by using `new RegExp(obj)`.


### replace

Used to find a match between a regular expression and a string, and to replace the matched substring with a new subst...

Used to find a match between a regular expression and a string, and to replace the matched substring with a new substring. This method does not change the `String` object it is called on. It simply returns a new string. To perform a global search and replace, either include the `g` flag in the regular expression or if the first parameter is a string, include `g` in the flags parameter. The replacement string can include the following special replacement patterns: Pattern Inserts `$$` Inserts a `$`. `$&` Inserts the matched substring. `$`` Inserts the portion of the string that precedes the matched substring. `$'` Inserts the portion of the string that follows the matched substring. `$n` or `$nn` Where `n` or `nn` are decimal digits, inserts the _n_th parenthesized submatch string, provided the first argument was a `RegExp` object. You can specify a function as the second parameter. In this case, the function will be invoked after the match has been performed. The function's result (return value) will be used as the replacement string. (Note: the above-mentioned special replacement patterns do not apply in this case.) Note that the function will be invoked multiple times for each full match to be replaced if the regular expression in the first parameter is global. The arguments to the function are as follows: Possible Name Supplied Value `str` The matched substring. (Corresponds to `$&` above.) `p1, p2, ...` The _n_th parenthesized submatch string, provided the first argument to replace was a `RegExp` object. (Correspond to $1, $2, etc. above.) `offset` The offset of the matched substring within the total string being examined. (For example, if the total string was "`abcd`", and the matched substring was "`bc`", then this argument will be 1.) `s` The total string being examined. (The exact number of arguments will depend on whether the first argument was a `RegExp` object and, if so, how many parenthesized submatches it specifies.) The following example will set `newString` to "`XXzzzz - XX , zzzz`": In the following example, the regular expression includes the global and ignore case flags which permits replace to replace each occurrence of 'apples' in the string with 'oranges'. In this version, a string is used as the first parameter and the global and ignore case flags are specified in the flags parameter. Both of these examples print "oranges are round, and oranges are juicy." In the following example, the regular expression is defined in replace and includes the ignore case flag. This prints "Twas the night before Christmas..." The following script switches the words in the string. For the replacement text, the script uses the $1 and $2 replacement patterns. This prints "Smith, John". In this example, all occurrences of capital letters in the string are converted to lower case, and a hyphen is inserted just before the match location. The important thing here is that additional operations are needed on the matched item before it is given back as a replacement. The replacement function accepts the matched snippet as its parameter, and uses it to transform the case and concatenate the hyphen before returning. Given `styleHyphenFormat('borderTop')`, this returns 'border-top'. Because we want to further transform the *result* of the match before the final substitution is made, we must use a function. This forces the evaluation of the match prior to the `toLowerCase()` method. If we had tried to do this using the match without a function, the `toLowerCase()` would have no effect. This is because `'$&'.toLowerCase()` would be evaluated first as a string literal (resulting in the same `'$&'`) before using the characters as a pattern. The following example replaces a Fahrenheit degree with its equivalent Celsius degree. The Fahrenheit degree should be a number ending with F. The function returns the Celsius number ending with C. For example, if the input number is 212F, the function returns 100C. If the number is 0F, the function returns -17.77777777777778C. The regular expression `test` checks for any number that ends with F. The number of Fahrenheit degree is accessible to the function through its second parameter, `p1`. The function sets the Celsius number based on the Fahrenheit degree passed in a string to the `f2c` function. `f2c` then returns the Celsius number. This function approximates Perl's `s///e` flag.

**Parameters:** pattern : String/RegExpEither a string or regular expression pattern to search for.


### search

Executes the search for a match between a regular expression and a specified string. ...

Executes the search for a match between a regular expression and a specified string. If successful, search returns the index of the regular expression inside the string. Otherwise, it returns -1. When you want to know whether a pattern is found in a string use search (similar to the regular expression `test` method); for more information (but slower execution) use `match` (similar to the regular expression `exec` method). The following example prints a message which depends on the success of the test.

**Parameters:** regexp : RegExpA regular expression object. If a non-RegExp object obj is passed, it is implicitly converted to a RegExp by using `new RegExp(obj)`.


### slice

Extracts a section of a string and returns a new string. ...

Extracts a section of a string and returns a new string. `slice` extracts the text from one string and returns a new string. Changes to the text in one string do not affect the other string. `slice` extracts up to but not including `endSlice`. `string.slice(1,4)` extracts the second character through the fourth character (characters indexed 1, 2, and 3). As a negative index, `endSlice` indicates an offset from the end of the string. `string.slice(2,-1)` extracts the third character through the second to last character in the string. The following example uses slice to create a new string. This writes:

**Parameters:** beginSlice : NumberThe zero-based index at which to begin extraction.


### split

Splits a String object into an array of strings by separating the string into substrings. ...

Splits a `String` object into an array of strings by separating the string into substrings. The `split` method returns the new array. When found, `separator` is removed from the string and the substrings are returned in an array. If `separator` is omitted, the array contains one element consisting of the entire string. If `separator` is a regular expression that contains capturing parentheses, then each time separator is matched the results (including any undefined results) of the capturing parentheses are spliced into the output array. However, not all browsers support this capability. Note: When the string is empty, `split` returns an array containing one empty string, rather than an empty array. The following example defines a function that splits a string into an array of strings using the specified separator. After splitting the string, the function displays messages indicating the original string (before the split), the separator used, the number of elements in the array, and the individual array elements. This example produces the following output: The original string is: "Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec" The separator is: "," The array has 12 elements: Jan / Feb / Mar / Apr / May / Jun / Jul / Aug / Sep / Oct / Nov / Dec / In the following example, `split` looks for 0 or more spaces followed by a semicolon followed by 0 or more spaces and, when found, removes the spaces from the string. nameList is the array returned as a result of split. This prints two lines; the first line prints the original string, and the second line prints the resulting array. In the following example, split looks for 0 or more spaces in a string and returns the first 3 splits that it finds. This script displays the following: If `separator` contains capturing parentheses, matched results are returned in the array. This script displays the following:

**Parameters:** seperator : StringSpecifies the character to use for separating the string. The separator is treated as a string or a regular expression. If separator is omitted, the array returned contains one element consisting of the entire string.


### substr

Returns the characters in a string beginning at the specified location through the specified number of characters. ...

**Parameters:** start : NumberLocation at which to begin extracting characters.

**Returns:** the characters in a string beginning at the specified location through the specified number of characters. `start` is a character index. The index of the first character is 0, and the index of the last character is 1 less than the length of the string. `substr` begins extracting characters at start and collects length characters (unless it reaches the end of the string first, in which case it will return fewer). If `start` is positive and is greater than or equal to the length of the string, `substr` returns an empty string. If `start` is negative, `substr` uses it as a character index from the end of the string. If start is negative and abs(start) is larger than the length of the string, `substr` uses 0 as the start index. Note: the described handling of negative values of the start argument is not supported by Microsoft JScript. If length is 0 or negative, `substr` returns an empty string. If length is omitted, `substr` extracts characters to the end of the string. Consider the following script: This script displays:


### substring

Returns the characters in a string between two indexes into the string. ...

**Parameters:** indexA : NumberAn integer between 0 and one less than the length of the string.

**Returns:** the characters in a string between two indexes into the string. substring extracts characters from indexA up to but not including indexB. In particular: * If `indexA` equals `indexB`, `substring` returns an empty string. * If `indexB` is omitted, substring extracts characters to the end of the string. * If either argument is less than 0 or is `NaN`, it is treated as if it were 0. * If either argument is greater than `stringName.length`, it is treated as if it were `stringName.length`. If `indexA` is larger than `indexB`, then the effect of substring is as if the two arguments were swapped; for example, `str.substring(1, 0) == str.substring(0, 1)`. The following example uses substring to display characters from the string "Sencha": The following example replaces a substring within a string. It will replace both individual characters and `substrings`. The function call at the end of the example changes the string "Brave New World" into "Brave New Web". fullS.length);


### toLocaleLowerCase

The characters within a string are converted to lower case while respecting the current locale. ...

The characters within a string are converted to lower case while respecting the current locale. For most languages, this will return the same as `toLowerCase`. The `toLocaleLowerCase` method returns the value of the string converted to lower case according to any locale-specific case mappings. `toLocaleLowerCase` does not affect the value of the string itself. In most cases, this will produce the same result as `toLowerCase()`, but for some locales, such as Turkish, whose case mappings do not follow the default case mappings in Unicode, there may be a different result. The following example displays the string "sencha":

**Returns:** StringReturns value of the string in lowercase.


### toLocaleUpperCase

The characters within a string are converted to upper case while respecting the current locale. ...

The characters within a string are converted to upper case while respecting the current locale. For most languages, this will return the same as `toUpperCase`. The `toLocaleUpperCase` method returns the value of the string converted to upper case according to any locale-specific case mappings. `toLocaleUpperCase` does not affect the value of the string itself. In most cases, this will produce the same result as `toUpperCase()`, but for some locales, such as Turkish, whose case mappings do not follow the default case mappings in Unicode, there may be a different result. The following example displays the string "SENCHA":

**Returns:** StringReturns value of the string in uppercase.


### toLowerCase

Returns the calling string value converted to lower case. ...

**Returns:** the calling string value converted to lower case. The `toLowerCase` method returns the value of the string converted to lowercase. `toLowerCase` does not affect the value of the string itself. The following example displays the lowercase string "sencha": ReturnsStringReturns value of the string in lowercase.


### toString

Returns a string representing the specified object. ...

**Returns:** a string representing the specified object. Overrides the `Object.toString` method. The `String` object overrides the `toString` method of the `Object` object; it does not inherit `Object.toString`. For `String` objects, the `toString` method returns a string representation of the object. The following example displays the string value of a String object: ReturnsStringA string representation of the object.


### toUpperCase

Returns the calling string value converted to uppercase. ...

**Returns:** the calling string value converted to uppercase. The `toUpperCase` method returns the value of the string converted to uppercase. `toUpperCase` does not affect the value of the string itself. The following example displays the string "SENCHA": ReturnsStringReturns value of the string in uppercase.


### trim

Removes whitespace from both ends of the string. ...

Removes whitespace from both ends of the string. Does not affect the value of the string itself. The following example displays the lowercase string `"foo"`: **NOTE:** This method is part of the ECMAScript 5 standard.

**Returns:** StringA string stripped of whitespace on both ends.


### valueOf

Returns the primitive value of the specified object. ...

**Returns:** the primitive value of the specified object. Overrides the `Object.valueOf` method. The `valueOf` method of String returns the primitive value of a `String` object as a string data type. This value is equivalent to `String.toString`. This method is usually called internally by JavaScript and not explicitly in code. ReturnsStringReturns value of string.


# Date

## Description

Creates `Date` instances which let you work with dates and times.

If you supply no arguments, the constructor creates a `Date` object for today's date and time according to local time. If you supply some arguments but not others, the missing arguments are set to 0. If you supply any arguments, you must supply at least the year, month, and day. You can omit the hours, minutes, seconds, and milliseconds.

The date is measured in milliseconds since midnight 01 January, 1970 UTC. A day holds 86,400,000 milliseconds. The `Date` object range is -100,000,000 days to 100,000,000 days relative to 01 January, 1970 UTC.

The `Date` object provides uniform behavior across platforms.

The `Date` object supports a number of UTC (universal) methods, as well as local time methods. UTC, also known as Greenwich Mean Time (GMT), refers to the time as set by the World Time Standard. The local time is the time known to the computer where JavaScript is executed.

Invoking `Date` in a non-constructor context (i.e., without the `new` operator) will return a string representing the current time.

Note that `Date` objects can only be instantiated by calling `Date` or using it as a constructor; unlike other JavaScript object types, `Date` objects have no literal syntax.

The following example shows several ways to assign dates:

today = new Date(); birthday = new Date("December 19, 1989 03:24:00"); birthday = new Date(1989,11,19); birthday = new Date(1989,11,17,3,24,0); Calculating elapsed time The following examples show how to determine the elapsed time between two dates:

// using static methods var start = Date.now(); // the event you'd like to time goes here: doSomethingForALongTime(); var end = Date.now(); var elapsed = end - start; // time in milliseconds // if you have Date objects var start = new Date(); // the event you'd like to time goes here: doSomethingForALongTime(); var end = new Date(); var elapsed = end.getTime() - start.getTime(); // time in milliseconds // if you want to test a function and get back its return function printElapsedTime (fTest) { var nStartTime = Date.now(), vReturn = fTest(), nEndTime = Date.now(); alert("Elapsed time: " + String(nEndTime - nStartTime) + " milliseconds"); return vReturn; } yourFunctionReturn = printElapsedTime(yourFunction); ISO 8601 formatted dates The following example shows how to formate a date in an ISO 8601 format using UTC:

## Methods

### Date

Creates new Date object. ...

Creates new Date object.

**Parameters:** - year : Number/String (optional)Either UNIX timestamp, date string, or year (when month and day parameters also provided): Integer value representing the number of milliseconds since 1 January 1970 00:00:00 UTC (Unix Epoch). - String value representing a date. The string should be in a format recognized by the parse method (IETF-compliant RFC 1123 timestamps). - Integer value representing the year. For compatibility (in order to avoid the Y2K problem), you should always specify the year in full; use 1998, rather than 98.


### getDate

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The second statement below assigns the value 25 to the variable `day`, based on the value of the `Date` object `Xmas95`. ReturnsNumberValue between 1 and 31.


### getDay

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The value returned by `getDay` is an integer corresponding to the day of the week: 0 for Sunday, 1 for Monday, 2 for Tuesday, and so on. The second statement below assigns the value 1 to `weekday`, based on the value of the `Date` object `Xmas95`. December 25, 1995, is a Monday. ReturnsNumberA numeric representation of the day from Sunday (0) to Saturday (6).


### getFullYear

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The value returned by `getFullYear` is an absolute number. For dates between the years 1000 and 9999, `getFullYear` returns a four-digit number, for example, 1995. Use this function to make sure a year is compliant with years after 2000. Use this method instead of the `getYear` method. The following example assigns the four-digit value of the current year to the variable yr. ReturnsNumberFour digit representation of the year.


### getHours

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The second statement below assigns the value 23 to the variable `hours`, based on the value of the `Date` object `Xmas95`. ReturnsNumberValue between 0 and 23, using 24-hour clock.


### getMilliseconds

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The following example assigns the milliseconds portion of the current time to the variable ms. ReturnsNumberA number between 0 and 999.


### getMinutes

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The second statement below assigns the value 15 to the variable `minutes`, based on the value of the `Date` object `Xmas95`. ReturnsNumberValue between 0 and 59.


### getMonth

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The second statement below assigns the value 11 to the variable `month`, based on the value of the `Date` object `Xmas95`. ReturnsNumberAn integer between 0 and 11. 0 corresponds to January, 1 to February, and so on.


### getSeconds

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The second statement below assigns the value 30 to the variable `secs`, based on the value of the `Date` object `Xmas95`. ReturnsNumberValue between 0 and 59.


### getTime

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The value returned by the `getTime` method is the number of milliseconds since 1 January 1970 00:00:00 UTC. You can use this method to help assign a date and time to another `Date` object. This method is functionally equivalent to the `valueOf` method. Using getTime for copying dates Constructing a date object with the identical time value. Measuring execution time Subtracting two subsequent getTime calls on newly generated Date objects, give the time span between these two calls. This can be used to calculate the executing time of some operations. ReturnsNumberNumber of milliseconds since 1/1/1970 (GMT).


### getTimezoneOffset

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The time-zone offset is the difference, in minutes, between UTC and local time. Note that this means that the offset is positive if the local timezone is behind UTC and negative if it is ahead. For example, if your time zone is UTC+10 (Australian Eastern Standard Time), -600 will be returned. Daylight savings time prevents this value from being a constant even for a given locale ReturnsNumberMinutes between GMT and local time.


### getUTCDate

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The following example assigns the day portion of the current date to the variable `d`. ReturnsNumberInteger between 1 and 31 representing the day.


### getUTCDay

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The following example assigns the weekday portion of the current date to the variable `weekday`. ReturnsNumberA numeric representation of the day from Sunday (0) to Saturday (6).


### getUTCFullYear

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The following example assigns the four-digit value of the current year to the variable `yr`. ReturnsNumberFour digit representation of the year.


### getUTCHours

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The following example assigns the hours portion of the current time to the variable `hrs`. ReturnsNumberValue between 0 and 23.


### getUTCMilliseconds

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The following example assigns the milliseconds portion of the current time to the variable `ms`. ReturnsNumberMilliseconds portion of the Date.


### getUTCMinutes

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The following example assigns the minutes portion of the current time to the variable `min`. ReturnsNumberValue between 0 and 59.


### getUTCMonth

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The following example assigns the month portion of the current date to the variable `mon`. ReturnsNumberValue between 0 (January) and 11 (December).


### getUTCSeconds

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The following example assigns the seconds portion of the current time to the variable `sec`. ReturnsNumberValue between 0 and 59.


### setDate

Sets the day of the month (1-31) for a specified date according to local time. ...

Sets the day of the month (1-31) for a specified date according to local time. If the parameter you specify is outside of the expected range, `setDate` attempts to update the date information in the `Date` object accordingly. For example, if you use 0 for `dayValue`, the date will be set to the last day of the previous month. The second statement below changes the day for theBigDay to July 24 from its original value.

**Parameters:** dayValue : NumberAn integer from 1 to 31, representing the day of the month.


### setFullYear

Sets the full year (4 digits for 4-digit years) for a specified date according to local time. ...

Sets the full year (4 digits for 4-digit years) for a specified date according to local time. If you do not specify the `monthValue` and `dayValue` parameters, the values returned from the `getMonth` and `getDate` methods are used. If a parameter you specify is outside of the expected range, `setFullYear` attempts to update the other parameters and the date information in the `Date` object accordingly. For example, if you specify 15 for monthValue, the year is incremented by 1 (year + 1), and 3 is used for the month. theBigDay = new Date(); theBigDay.setFullYear(1997);

**Parameters:** yearValue : NumberAn integer specifying the numeric value of the year, for example, 1995.


### setHours

Sets the hours (0-23) for a specified date according to local time. ...

Sets the hours (0-23) for a specified date according to local time. If you do not specify the `minutesValue`, `secondsValue`, and `msValue` parameters, the values returned from the `getUTCMinutes`, `getUTCSeconds`, and `getMilliseconds` methods are used. If a parameter you specify is outside of the expected range, setHours attempts to update the date information in the `Date` object accordingly. For example, if you use 100 for `secondsValue`, the minutes will be incremented by 1 (min + 1), and 40 will be used for seconds.

**Parameters:** hoursValue : NumberAn integer between 0 and 23, representing the hour.


### setMilliseconds

Sets the milliseconds (0-999) for a specified date according to local time. ...

Sets the milliseconds (0-999) for a specified date according to local time. If you specify a number outside the expected range, the date information in the `Date` object is updated accordingly. For example, if you specify 1005, the number of seconds is incremented by 1, and 5 is used for the milliseconds.

**Parameters:** millisecondsValue : NumberA number between 0 and 999, representing the milliseconds.


### setMinutes

Sets the minutes (0-59) for a specified date according to local time. ...

Sets the minutes (0-59) for a specified date according to local time. If you do not specify the `secondsValue` and `msValue` parameters, the values returned from `getSeconds` and `getMilliseconds` methods are used. If a parameter you specify is outside of the expected range, `setMinutes` attempts to update the date information in the `Date` object accordingly. For example, if you use 100 for `secondsValue`, the minutes (`minutesValue`) will be incremented by 1 (minutesValue + 1), and 40 will be used for seconds.

**Parameters:** minutesValue : NumberAn integer between 0 and 59, representing the minutes.


### setMonth

Sets the month (0-11) for a specified date according to local time. ...

Sets the month (0-11) for a specified date according to local time. If you do not specify the `dayValue` parameter, the value returned from the `getDate` method is used. If a parameter you specify is outside of the expected range, `setMonth` attempts to update the date information in the `Date` object accordingly. For example, if you use 15 for `monthValue`, the year will be incremented by 1 (year + 1), and 3 will be used for month.

**Parameters:** monthValue : NumberAn integer between 0 and 11 (representing the months January through December).


### setSeconds

Sets the seconds (0-59) for a specified date according to local time. ...

Sets the seconds (0-59) for a specified date according to local time. If you do not specify the `msValue` parameter, the value returned from the `getMilliseconds` method is used. If a parameter you specify is outside of the expected range, `setSeconds` attempts to update the date information in the `Date` object accordingly. For example, if you use 100 for `secondsValue`, the minutes stored in the `Date` object will be incremented by 1, and 40 will be used for seconds.

**Parameters:** secondsValue : NumberAn integer between 0 and 59.


### setTime

Sets the Date object to the time represented by a number of milliseconds since January 1, 1970, 00:00:00 UTC, allowin...

Sets the Date object to the time represented by a number of milliseconds since January 1, 1970, 00:00:00 UTC, allowing for negative numbers for times prior. Use the `setTime` method to help assign a date and time to another `Date` object.

**Parameters:** timeValue : NumberAn integer representing the number of milliseconds since 1 January 1970, 00:00:00 UTC.


### setUTCDate

Sets the day of the month (1-31) for a specified date according to universal time. ...

Sets the day of the month (1-31) for a specified date according to universal time. If a parameter you specify is outside of the expected range, `setUTCDate` attempts to update the date information in the `Date` object accordingly. For example, if you use 40 for `dayValue`, and the month stored in the `Date` object is June, the day will be changed to 10 and the month will be incremented to July.

**Parameters:** dayValue : NumberAn integer from 1 to 31, representing the day of the month.


### setUTCFullYear

Sets the full year (4 digits for 4-digit years) for a specified date according to universal time. ...

Sets the full year (4 digits for 4-digit years) for a specified date according to universal time. If you do not specify the `monthValue` and `dayValue` parameters, the values returned from the `getMonth` and `getDate` methods are used. If a parameter you specify is outside of the expected range, `setUTCFullYear` attempts to update the other parameters and the date information in the `Date` object accordingly. For example, if you specify 15 for `monthValue`, the year is incremented by 1 (year + 1), and 3 is used for the month.

**Parameters:** yearValue : NumberAn integer specifying the numeric value of the year, for example, 1995.


### setUTCHours

Sets the hour (0-23) for a specified date according to universal time. ...

Sets the hour (0-23) for a specified date according to universal time. If you do not specify the `minutesValue`, `secondsValue`, and `msValue` parameters, the values returned from the `getUTCMinutes`, `getUTCSeconds`, and `getUTCMilliseconds` methods are used. If a parameter you specify is outside of the expected range, `setUTCHours` attempts to update the date information in the `Date` object accordingly. For example, if you use 100 for `secondsValue`, the minutes will be incremented by 1 (min + 1), and 40 will be used for seconds.

**Parameters:** hoursValue : NumberAn integer between 0 and 23, representing the hour.


### setUTCMilliseconds

Sets the milliseconds (0-999) for a specified date according to universal time. ...

Sets the milliseconds (0-999) for a specified date according to universal time. If a parameter you specify is outside of the expected range, `setUTCMilliseconds` attempts to update the date information in the `Date` object accordingly. For example, if you use 1100 for `millisecondsValue`, the seconds stored in the Date object will be incremented by 1, and 100 will be used for milliseconds.

**Parameters:** millisecondsValue : NumberA number between 0 and 999, representing the milliseconds.


### setUTCMinutes

Sets the minutes (0-59) for a specified date according to universal time. ...

Sets the minutes (0-59) for a specified date according to universal time. If you do not specify the `secondsValue` and `msValue` parameters, the values returned from `getUTCSeconds` and `getUTCMilliseconds` methods are used. If a parameter you specify is outside of the expected range, `setUTCMinutes` attempts to update the date information in the `Date` object accordingly. For example, if you use 100 for `secondsValue`, the minutes (`minutesValue`) will be incremented by 1 (`minutesValue` + 1), and 40 will be used for seconds.

**Parameters:** minutesValue : NumberAn integer between 0 and 59, representing the minutes.


### setUTCMonth

Sets the month (0-11) for a specified date according to universal time. ...

Sets the month (0-11) for a specified date according to universal time. If you do not specify the `dayValue` parameter, the value returned from the `getUTCDate` method is used. If a parameter you specify is outside of the expected range, `setUTCMonth` attempts to update the date information in the `Date` object accordingly. For example, if you use 15 for `monthValue`, the year will be incremented by 1 (year + 1), and 3 will be used for month.

**Parameters:** monthValue : NumberAn integer between 0 and 11, representing the months January through December.


### setUTCSeconds

Sets the seconds (0-59) for a specified date according to universal time. ...

Sets the seconds (0-59) for a specified date according to universal time. If you do not specify the `msValue` parameter, the value returned from the `getUTCMilliseconds` methods is used. If a parameter you specify is outside of the expected range, `setUTCSeconds` attempts to update the date information in the `Date` object accordingly. For example, if you use 100 for `secondsValue`, the minutes stored in the `Date` object will be incremented by 1, and 40 will be used for seconds.

**Parameters:** secondsValue : NumberAn integer between 0 and 59.


### toDateString

Returns the "date" portion of the Date as a human-readable string in American English. ...

**Returns:** the "date" portion of the Date as a human-readable string in American English. Date instances refer to a specific point in time. Calling `toString` will return the date formatted in a human readable form in American English. In SpiderMonkey, this consists of the date portion (day, month, and year) followed by the time portion (hours, minutes, seconds, and time zone). Sometimes it is desirable to obtain a string of the date portion; such a thing can be accomplished with the `toDateString` method. The `toDateString` method is especially useful because compliant engines implementing ECMA-262 may differ in the string obtained from `toString` for `Date` objects, as the format is implementation- dependent and simple string slicing approaches may not produce consistent results across multiple engines. ReturnsStringHuman-readable string, in local time.


### toJSON

Returns a JSON representation of the Date object. ...

**Returns:** a JSON representation of the Date object. Date instances refer to a specific point in time. Calling `toJSON()` returns a JSON formatted string representing the Date object's value. This method is generally intended to, by default, usefully serialize Date objects during JSON serialization. **NOTE:** This method is part of the ECMAScript 5 standard. ReturnsStringDate value in `YYYY-MM-DDTHH-MM-SS.MMMZ` format.


### toLocaleDateString

Returns the "date" portion of the Date as a string, using the current locale's conventions. ...

**Returns:** the "date" portion of the Date as a string, using the current locale's conventions. The `toLocaleDateString` method relies on the underlying operating system in formatting dates. It converts the date to a string using the formatting convention of the operating system where the script is running. For example, in the United States, the month appears before the date (04/15/98), whereas in Germany the date appears before the month (15.04.98). If the operating system is not year-2000 compliant and does not use the full year for years before 1900 or over 2000, `toLocaleDateString` returns a string that is not year-2000 compliant. `toLocaleDateString` behaves similarly to `toString` when converting a year that the operating system does not properly format. Methods such as `getDate`, `getMonth`, and `getFullYear` give more portable results than `toLocaleDateString`. Use `toLocaleDateString` when the intent is to display to the user a string formatted using the regional format chosen by the user. Be aware that this method, due to its nature, behaves differently depending on the operating system and on the user's settings. In the following example, `today` is a `Date` object: In this example, `toLocaleDateString` returns a string value that is similar to the following form. The exact format depends on the platform, locale and user's settings. You shouldn't use this method in contexts where you rely on a particular format or locale. ReturnsStringHuman-readable string that may be formatted differently depending on the country.


### toLocaleString

Converts a date to a string, using the current locale's conventions. ...

Converts a date to a string, using the current locale's conventions. Overrides the `Object.toLocaleString` method. The `toLocaleString` method relies on the underlying operating system in formatting dates. It converts the date to a string using the formatting convention of the operating system where the script is running. For example, in the United States, the month appears before the date (04/15/98), whereas in Germany the date appears before the month (15.04.98). If the operating system is not year-2000 compliant and does not use the full year for years before 1900 or over 2000, `toLocaleString` returns a string that is not year-2000 compliant. `toLocaleString` behaves similarly to `toString` when converting a year that the operating system does not properly format. Methods such as `getDate`, `getMonth`, `getFullYear`, `getHours`, `getMinutes`, and `getSeconds` give more portable results than `toLocaleString`. Use `toLocaleString` when the intent is to display to the user a string formatted using the regional format chosen by the user. Be aware that this method, due to its nature, behaves differently depending on the operating system and on the user's settings. In the following example, `today` is a `Date` object: In this example, `toLocaleString` returns a string value that is similar to the following form. The exact format depends on the platform, locale and user's settings. You shouldn't use this method in contexts where you rely on a particular format or locale.

**Returns:** StringHuman-readable string that may be formatted differently depending on the country.


### toLocaleTimeString

Returns the "time" portion of the Date as a string, using the current locale's conventions. ...

**Returns:** the "time" portion of the Date as a string, using the current locale's conventions. The `toLocaleTimeString` method relies on the underlying operating system in formatting dates. It converts the date to a string using the formatting convention of the operating system where the script is running. For example, in the United States, the month appears before the date (04/15/98), whereas in Germany the date appears before the month (15.04.98). Methods such as `getHours`, `getMinutes`, and `getSeconds` give more consistent results than `toLocaleTimeString`. Use `toLocaleTimeString` when the intent is to display to the user a string formatted using the regional format chosen by the user. Be aware that this method, due to its nature, behaves differently depending on the operating system and on the user's settings. In the following example, `today` is a `Date` object: In this example, `toLocaleTimeString` returns a string value that is similar to the following form. The exact format depends on the platform. You shouldn't use this method in contexts where you rely on a particular format or locale. ReturnsStringHuman-readable string that may be formatted differently depending on the country.


### toString

Returns a string representing the specified Date object. ...

**Returns:** a string representing the specified Date object. Overrides the `Object.prototype.toString` method. The `Date` object overrides the toString method of the Object object; it does not inherit `Object.toString`. For `Date` objects, the `toString` method returns a string representation of the object. `toString` always returns a string representation of the date in American English. JavaScript calls the `toString` method automatically when a date is to be represented as a text value or when a date is referred to in a string concatenation. The following assigns the `toString` value of a `Date` object to `myVar`: ReturnsStringHuman-readable string of the date in local time.


### toTimeString

Returns the "time" portion of the Date as a human-readable string. ...

**Returns:** the "time" portion of the Date as a human-readable string. Date instances refer to a specific point in time. Calling `toString` will return the date formatted in a human readable form in American English. In SpiderMonkey, this consists of the date portion (day, month, and year) followed by the time portion (hours, minutes, seconds, and time zone). Sometimes it is desirable to obtain a string of the time portion; such a thing can be accomplished with the `toTimeString` method. The `toTimeString` method is especially useful because compliant engines implementing ECMA-262 may differ in the string obtained from `toString` for `Date` objects, as the format is implementation- dependent; simple string slicing approaches may not produce consistent results across multiple engines. ReturnsStringHuman-readable string of the date in local time.


### toUTCString

Converts a date to a string, using the universal time convention. ...

Converts a date to a string, using the universal time convention. The value returned by `toUTCString` is a readable string in American English in the UTC time zone. The format of the return value may vary according to the platform.

**Returns:** StringString of the date in UTC.


### valueOf

Returns the primitive value of a Date object. ...

**Returns:** the primitive value of a Date object. Overrides the Object.prototype.valueOf method. The `valueOf` method returns the primitive value of a `Date` object as a number data type, the number of milliseconds since midnight 01 January, 1970 UTC. This method is functionally equivalent to the `getTime` method. This method is usually called internally by JavaScript and not explicitly in code. ReturnsNumberDate represented as milliseconds.


### UTC

Accepts the same parameters as the longest form of the constructor, and returns the number of milliseconds in a Date ...

Accepts the same parameters as the longest form of the constructor, and returns the number of milliseconds in a `Date` object since January 1, 1970, 00:00:00, universal time. `UTC` takes comma-delimited date parameters and returns the number of milliseconds between January 1, 1970, 00:00:00, universal time and the time you specified. You should specify a full year for the year; for example, 1998. If a year between 0 and 99 is specified, the method converts the year to a year in the 20th century (1900 + year); for example, if you specify 95, the year 1995 is used. The `UTC` method differs from the `Date` constructor in two ways. * `Date.UTC` uses universal time instead of the local time. * `Date.UTC` returns a time value as a number instead of creating a `Date` object. If a parameter you specify is outside of the expected range, the `UTC` method updates the other parameters to allow for your number. For example, if you use 15 for month, the year will be incremented by 1 (year + 1), and 3 will be used for the month. Because `UTC` is a static method of `Date`, you always use it as `Date.UTC()`, rather than as a method of a `Date` object you created. The following statement creates a `Date` object using GMT instead of local time:

**Parameters:** year : NumberA year after 1900.


### now

Returns the numeric value corresponding to the current time. ...

**Returns:** the numeric value corresponding to the current time. The `now` method returns the milliseconds elapsed since 1 January 1970 00:00:00 UTC up until now as a number. When using `now` to create timestamps or unique IDs, keep in mind that the resolution may be 15 milliseconds on Windows, so you could end up with several equal values if `now` is called multiple times within a short time span. ReturnsNumberReturns the number of milliseconds elapsed since 1 January 1970 00:00:00 UTC.


### parse

Parses a string representation of a date, and returns the number of milliseconds since January 1, 1970, 00:00:00, loc...

Parses a string representation of a date, and returns the number of milliseconds since January 1, 1970, 00:00:00, local time. The `parse` method takes a date string (such as `"Dec 25, 1995"`) and returns the number of milliseconds since January 1, 1970, 00:00:00 UTC. The local time zone is used to interpret arguments that do not contain time zone information. This function is useful for setting date values based on string values, for example in conjunction with the `setTime` method and the Date object. Given a string representing a time, parse returns the time value. It accepts the IETF standard (RFC 1123 Section 5.2.14 and elsewhere) date syntax: `"Mon, 25 Dec 1995 13:30:00 GMT"`. It understands the continental US time-zone abbreviations, but for general use, use a time-zone offset, for example, `"Mon, 25 Dec 1995 13:30:00 GMT+0430"` (4 hours, 30 minutes east of the Greenwich meridian). If you do not specify a time zone, the local time zone is assumed. GMT and UTC are considered equivalent. Using parse If `IPOdate` is an existing `Date` object, then you can set it to August 9, 1995 (local time) as follows: Some other examples:

**Parameters:** dateString : StringA string representing a date.


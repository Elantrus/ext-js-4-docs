# Ext.Version

## Descrição

A utility class that wrap around a string version number and provide convenient
method to perform comparison. See also: compare. Example:

## Methods

### Ext.Version

...

Parametersversion : String/NumberThe version number in the following standard format:

major[.minor[.patch[.build[release]]]]


Examples:

1.0
1.2.3beta
1.2.3.4RC


### equals

Returns whether this version equals to the supplied argument ...

Returns whether this version equals to the supplied argument
Parameterstarget : String/NumberThe version to compare with


### getBuild

Returns the build component value ...

Returns the build component value
ReturnsNumberbuild


### getMajor

Returns the major component value ...

Returns the major component value
ReturnsNumbermajor


### getMinor

Returns the minor component value ...

Returns the minor component value
ReturnsNumberminor


### getPatch

Returns the patch component value ...

Returns the patch component value
ReturnsNumberpatch


### getRelease

Returns the release component value ...

Returns the release component value
ReturnsNumberrelease


### getShortVersion

Returns shortVersion version without dots and release ...

Returns shortVersion version without dots and release
ReturnsString


### gt

Convenient alias to isGreaterThan ...

Convenient alias to isGreaterThan
Parameterstarget : String/Number


### gtEq

Convenient alias to isGreaterThanOrEqual ...

Convenient alias to isGreaterThanOrEqual
Parameterstarget : String/Number


### isGreaterThan

Returns whether this version if greater than the supplied argument ...

Returns whether this version if greater than the supplied argument
Parameterstarget : String/NumberThe version to compare with


### isGreaterThanOrEqual

Returns whether this version if greater than or equal to the supplied argument ...

Returns whether this version if greater than or equal to the supplied argument
Parameterstarget : String/NumberThe version to compare with


### isLessThan

Returns whether this version if smaller than the supplied argument ...

Returns whether this version if smaller than the supplied argument
Parameterstarget : String/NumberThe version to compare with


### isLessThanOrEqual

Returns whether this version if less than or equal to the supplied argument ...

Returns whether this version if less than or equal to the supplied argument
Parameterstarget : String/NumberThe version to compare with


### lt

Convenient alias to isLessThan ...

Convenient alias to isLessThan
Parameterstarget : String/Number


### ltEq

Convenient alias to isLessThanOrEqual ...

Convenient alias to isLessThanOrEqual
Parameterstarget : String/Number


### match

Returns whether this version matches the supplied argument. ...

Returns whether this version matches the supplied argument. Example:

var version = new Ext.Version('1.0.2beta');
console.log(version.match(1)); // True
console.log(version.match(1.0)); // True
console.log(version.match('1.0.2')); // True
console.log(version.match('1.0.2RC')); // False

Parameterstarget : String/NumberThe version to compare with


### toArray

Returns this format: [major, minor, patch, build, release]. ...

Returns this format: [major, minor, patch, build, release]. Useful for comparison
ReturnsNumber[]


### toString

Override the native toString method ...

Override the native toString method
ReturnsStringversion


### valueOf

Override the native valueOf method ...

Override the native valueOf method
ReturnsStringversion


### compare

Compare 2 specified versions, starting from left to right. ...

Compare 2 specified versions, starting from left to right. If a part contains special version strings,
they are handled in the following order:
'dev' < 'alpha' = 'a' < 'beta' = 'b' < 'RC' = 'rc' < '#' < 'pl' = 'p' < 'anything else'
Parameterscurrent : StringThe current version to compare to


### getComponentValue

Converts a version component to a comparable value ...

Converts a version component to a comparable value
Parametersvalue : ObjectThe value to convert


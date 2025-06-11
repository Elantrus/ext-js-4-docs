# Ext.Version

## Description

A utility class that wrap around a string version number and provide convenient method to perform comparison. See also: compare. Example:

## Methods

### Ext.Version

...

**Parameters:** version : String/NumberThe version number in the following standard format: Examples:


### equals

Returns whether this version equals to the supplied argument ...

**Parameters:** target : String/NumberThe version to compare with

**Returns:** whether this version equals to the supplied argument


### getBuild

Returns the build component value ...

**Returns:** the build component value ReturnsNumberbuild


### getMajor

Returns the major component value ...

**Returns:** the major component value ReturnsNumbermajor


### getMinor

Returns the minor component value ...

**Returns:** the minor component value ReturnsNumberminor


### getPatch

Returns the patch component value ...

**Returns:** the patch component value ReturnsNumberpatch


### getRelease

Returns the release component value ...

**Returns:** the release component value ReturnsNumberrelease


### getShortVersion

Returns shortVersion version without dots and release ...

**Returns:** shortVersion version without dots and release ReturnsString


### gt

Convenient alias to isGreaterThan ...

Convenient alias to isGreaterThan

**Parameters:** target : String/Number


### gtEq

Convenient alias to isGreaterThanOrEqual ...

Convenient alias to isGreaterThanOrEqual

**Parameters:** target : String/Number


### isGreaterThan

Returns whether this version if greater than the supplied argument ...

**Parameters:** target : String/NumberThe version to compare with

**Returns:** whether this version if greater than the supplied argument


### isGreaterThanOrEqual

Returns whether this version if greater than or equal to the supplied argument ...

**Parameters:** target : String/NumberThe version to compare with

**Returns:** whether this version if greater than or equal to the supplied argument


### isLessThan

Returns whether this version if smaller than the supplied argument ...

**Parameters:** target : String/NumberThe version to compare with

**Returns:** whether this version if smaller than the supplied argument


### isLessThanOrEqual

Returns whether this version if less than or equal to the supplied argument ...

**Parameters:** target : String/NumberThe version to compare with

**Returns:** whether this version if less than or equal to the supplied argument


### lt

Convenient alias to isLessThan ...

Convenient alias to isLessThan

**Parameters:** target : String/Number


### ltEq

Convenient alias to isLessThanOrEqual ...

Convenient alias to isLessThanOrEqual

**Parameters:** target : String/Number


### match

Returns whether this version matches the supplied argument. ...

**Parameters:** target : String/NumberThe version to compare with

**Returns:** whether this version matches the supplied argument. Example:


### toArray

Returns this format: [major, minor, patch, build, release]. ...

**Returns:** this format: [major, minor, patch, build, release]. Useful for comparison ReturnsNumber[]


### toString

Override the native toString method ...

Override the native toString method

**Returns:** Stringversion


### valueOf

Override the native valueOf method ...

Override the native valueOf method

**Returns:** Stringversion


### compare

Compare 2 specified versions, starting from left to right. ...

Compare 2 specified versions, starting from left to right. If a part contains special version strings, they are handled in the following order: 'dev' < 'alpha' = 'a' < 'beta' = 'b' < 'RC' = 'rc' < '#' < 'pl' = 'p' < 'anything else'

**Parameters:** current : StringThe current version to compare to


### getComponentValue

Converts a version component to a comparable value ...

Converts a version component to a comparable value

**Parameters:** value : ObjectThe value to convert


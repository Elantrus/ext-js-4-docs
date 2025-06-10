# Ext.JSON

## Descrição

Modified version of Douglas Crockford's JSON.js that doesn't
mess with the Object prototype.

## Methods

### decode

Decodes (parses) a JSON string to an object. ...

Decodes (parses) a JSON string to an object. If the JSON is invalid, this function throws
a SyntaxError unless the safe option is set.
Parametersjson : StringThe JSON string


### encode

Encodes an Object, Array or other value. ...

Encodes an Object, Array or other value.

If the environment's native JSON encoding is not being used (Ext.USE_NATIVE_JSON is not set,
or the environment does not support it), then ExtJS's encoding will be used. This allows the developer
to add a `toJSON` method to their classes which need serializing to return a valid JSON representation
of the object.
Parameterso : ObjectThe variable to encode


### encodeDate

Encodes a Date. ...

Encodes a Date. This returns the actual string which is inserted into the JSON string as the literal
expression. **The returned value includes enclosing double quotation marks.**

The default return format is `"yyyy-mm-ddThh:mm:ss"`.

To override this:

Ext.JSON.encodeDate = function(d) {
    return Ext.Date.format(d, '"Y-m-d"');
};

Parametersd : DateThe Date to encode


### encodeString

Encodes a String. ...

Encodes a String. This returns the actual string which is inserted into the JSON string as the literal
expression. **The returned value includes enclosing double quotation marks.**

To override this:

Ext.JSON.encodeString = function(s) {
    return 'Foo' + s;
};

Parameterss : StringThe String to encode


### encodeValue

The function which encode uses to encode all javascript values to their JSON representations
when Ext.USE_NATIVE_JSON...

The function which encode uses to encode all javascript values to their JSON representations
when Ext.USE_NATIVE_JSON is `false`.

This is made public so that it can be replaced with a custom implementation.
Parameterso : ObjectAny javascript value to be converted to its JSON representation


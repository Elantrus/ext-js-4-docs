# Global_CSS

## CSS Variables

### $base-color

**Tipo:** color

The base color to be used throughout the theme. ...

The base color to be used throughout the theme.
Defaults to: `#808080`


### $base-gradient

**Tipo:** string

The base gradient to be used throughout the theme. ...

The base gradient to be used throughout the theme.
Defaults to: `'matte'`


### $body-background-color

**Tipo:** color

Background color to apply to the body element ...

Background color to apply to the body element
Defaults to: `transparent`


### $color

**Tipo:** color

The default text color to be used throughout the theme. ...

The default text color to be used throughout the theme.
Defaults to: `#000`


### $css-shadow-border-radius

**Tipo:** measurement

The border radius for CSS shadows ...

The border radius for CSS shadows
Defaults to: `5px`


### $font-family

**Tipo:** string

The default font-family to be used throughout the theme. ...

The default font-family to be used throughout the theme.
Defaults to: `helvetica , arial , verdana , sans-serif`


### $font-size

**Tipo:** string

The default font-family to be used throughout the theme. ...

The default font-family to be used throughout the theme.
Defaults to: `13px`


### $image-extension

**Tipo:** string

default file extension to use for images (defaults to 'png'). ...

default file extension to use for images (defaults to 'png').
Defaults to: `'png'`


### $image-search-path

**Tipo:** string

Default search path for images ...

Default search path for images
Defaults to: `'.'`


### $include-chrome

**Tipo:** boolean

True to include Chrome specific rules ...

True to include Chrome specific rules
Defaults to: `true`


### $include-content-box

**Tipo:** boolean

True to include rules for browsers that do not support the border-box model
(IE6 strict and IE7 strict) ...

True to include rules for browsers that do not support the border-box model
(IE6 strict and IE7 strict)
Defaults to: `$include-ie`


### $include-default-uis

**Tipo:** boolean

True to include the default UI for each component. ...

True to include the default UI for each component.
Defaults to: `true`


### $include-ff

**Tipo:** boolean

True to include Firefox specific rules ...

True to include Firefox specific rules
Defaults to: `true`


### $include-ie

**Tipo:** boolean

True to include Internet Explorer specific rules ...

True to include Internet Explorer specific rules
Defaults to: `true`


### $include-not-found-images

**Tipo:** boolean

True to include files which are not found when compiling your SASS


### $include-opera

**Tipo:** boolean

True to include Opera specific rules ...

True to include Opera specific rules
Defaults to: `true`


### $include-safari

**Tipo:** boolean

True to include Safari specific rules ...

True to include Safari specific rules
Defaults to: `true`


### $include-shadow-images

**Tipo:** color

True to include all shadow images. ...

True to include all shadow images.
Defaults to: `true`


### $include-webkit

**Tipo:** boolean

True to include Webkit specific rules ...

True to include Webkit specific rules
Defaults to: `true`


### $neutral-color

**Tipo:** color

The neutral color to be used throughout the theme. ...

The neutral color to be used throughout the theme.
Defaults to: `#dcdcdc`


### $prefix

**Tipo:** string

The prefix to be applied to all CSS selectors. ...

The prefix to be applied to all CSS selectors. If this is changed, it must also be changed in your
JavaScript application.
Defaults to: `'x-'`


### $relative-image-path-for-uis

**Tipo:** boolean/string

True to use a relative image path for all new UIs. ...

True to use a relative image path for all new UIs. If true, the path will be "../images/".
It can also be a string of the path value.
It defaults to false, which means it will look for the images in the ExtJS SDK folder.
Defaults to: `false`


### $slicer-image-extension

**Tipo:** string

default file extension to use for slicer images (defaults to 'gif'). ...

default file extension to use for slicer images (defaults to 'gif').
Defaults to: `'gif'`


### $theme-resource-path

**Tipo:** string

The base path relative to the CSS output directory to use for theme resources. ...

The base path relative to the CSS output directory to use for theme resources.  For example
if the theme's images live one directory up from the generated CSS output in a directory
named 'foo/images/', you would need to set this variable to '../foo/' in order for the image
paths in the CSS output to be generated correctly. By default this is the same as the
CSS output directory.
Defaults to: `''`


### background-gradient

Creates a background gradient. ...

Creates a background gradient.

Example usage:

.foo {
     @include background-gradient(#808080, matte, left);
}

$bg-color : ColorThe background color of the gradient


## CSS Mixins

### background-gradient

Creates a background gradient. ...

Creates a background gradient.

Example usage:

.foo {
     @include background-gradient(#808080, matte, left);
}

$bg-color : ColorThe background color of the gradient


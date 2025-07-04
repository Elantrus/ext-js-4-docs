# Ext.supports

## Description

Determines information about features are supported in the current environment

## Properties

### ArraySort

**Type:** Boolean

True if the Array sort native method isn't bugged.


### AudioTag

**Type:** Boolean

True if the device supports the HTML5 audio tag


### BoundingClientRect

**Type:** Boolean

True if the browser supports the getBoundingClientRect method on elements


### CSS3BorderRadius

**Type:** Boolean

True if the device supports CSS3 border radius


### CSS3BoxShadow

**Type:** Boolean

True if document environment supports the CSS3 box-shadow style.


### CSS3DTransform

**Type:** Boolean

True if the device supports CSS3DTransform


### CSS3LinearGradient

**Type:** Boolean

True if the device supports CSS3 linear gradients


### Canvas

**Type:** Boolean

True if the device supports Canvas


### ClassList

**Type:** Boolean

True if document environment supports the HTML5 classList API.


### ComputedStyle

**Type:** Boolean

True if the browser supports document.defaultView.getComputedStyle()


### CreateContextualFragment

**Type:** Boolean

True if browser support CreateContextualFragment range native methods.


### DeviceMotion

**Type:** Boolean

True if the device supports device motion (acceleration and rotation rate)


### Direct2DBug

**Type:** Boolean

True if when asking for an element's dimension via offsetWidth or offsetHeight, getBoundingClientRect, etc. ...

True if when asking for an element's dimension via offsetWidth or offsetHeight, getBoundingClientRect, etc. the browser returns the subpixel width rounded to the nearest pixel.


### DisplayChangeInputSelectionBug

**Type:** Object

True if INPUT elements lose their selection when their display style is changed. ...

True if INPUT elements lose their selection when their display style is changed. Essentially, if a text input has focus and its display style is changed, the I-beam disappears. This bug is encountered due to the work around in place for the RightMargin bug. This has been observed in Safari 4.0.4 and older, and appears to be fixed in Safari 5. It's not clear if Safari 4.1 has the bug, but it has the same WebKit version number as Safari 5 (according to http://unixpapa.com/js/gecko.html).


### DisplayChangeTextAreaSelectionBug

**Type:** Object

True if TEXTAREA elements lose their selection when their display style is changed. ...

True if TEXTAREA elements lose their selection when their display style is changed. Essentially, if a text area has focus and its display style is changed, the I-beam disappears. This bug is encountered due to the work around in place for the RightMargin bug. This has been observed in Chrome 10 and Safari 5 and older, and appears to be fixed in Chrome 11.


### Float

**Type:** Boolean

True if the device supports CSS float


### GeoLocation

**Type:** Boolean

True if the device supports GeoLocation


### GetPositionPercentage

**Type:** Boolean

True if the browser will return the left/top/right/bottom position as a percentage when explicitly set as a percentag...

True if the browser will return the left/top/right/bottom position as a percentage when explicitly set as a percentage value.


### History

**Type:** Boolean

True if the device supports HTML5 history


### LocalStorage

**Type:** Object

True if localStorage is supported


### MouseEnterLeave

**Type:** Boolean

True if the browser supports mouseenter and mouseleave events


### MouseWheel

**Type:** Boolean

True if the browser supports the mousewheel event


### Opacity

**Type:** Boolean

True if the browser supports normal css opacity


### OrientationChange

**Type:** Boolean

True if the device supports orientation change


### PercentageHeightOverflowBug

**Type:** Boolean

In some browsers (IE quirks, IE6, IE7, IE9, chrome, safari and opera at the time of this writing) a percentage-height...

In some browsers (IE quirks, IE6, IE7, IE9, chrome, safari and opera at the time of this writing) a percentage-height element ignores the horizontal scrollbar of its parent element. This method returns true if the browser is affected by this bug.


### Placeholder

**Type:** Boolean

True if the browser supports the HTML5 placeholder attribute on inputs


### PointerEvents

**Type:** Boolean

True if document environment supports the CSS3 pointer-events style.


### Range

**Type:** Boolean

True if browser support document.createRange native method.


### RightMargin

**Type:** Boolean

True if the device supports right margin. ...

True if the device supports right margin. See https://bugs.webkit.org/show_bug.cgi?id=13343 for why this is needed.


### RotatedBoundingClientRect

**Type:** Boolean

True if the BoundingClientRect is rotated when the element is rotated using a CSS transform.


### ScrollWidthInlinePaddingBug

**Type:** Boolean

In some browsers the right padding of an overflowing element is not accounted for in its scrollWidth. ...

In some browsers the right padding of an overflowing element is not accounted for in its scrollWidth. The result can vary depending on whether or not The element contains block-level children. This method tests the effect of padding on scrollWidth when there are no block-level children inside the overflowing element. This method returns true if the browser is affected by this bug.


### Svg

**Type:** Boolean

True if the device supports SVG


### TextAreaMaxLength

**Type:** Boolean

True if the browser supports maxlength on textareas.


### TimeoutActualLateness

**Type:** Boolean

True if the browser passes the "actualLateness" parameter to setTimeout. ...

True if the browser passes the "actualLateness" parameter to setTimeout. See: https://developer.mozilla.org/en/DOM/window.setTimeout


### Touch

**Type:** Boolean

True if the device supports touch


### Transitions

**Type:** Boolean

True if the device supports CSS3 Transitions


### TransparentColor

**Type:** Boolean

True if the device supports transparent color


### Vml

**Type:** Boolean

True if the device supports VML


### WindowOnError

**Type:** Boolean

True if browser supports window.onerror.


### xOriginBug

**Type:** Boolean

In Chrome 24.0, an RTL element which has vertical overflow positions its right X origin incorrectly. ...

In Chrome 24.0, an RTL element which has vertical overflow positions its right X origin incorrectly. It skips a non-existent scrollbar which has been moved to the left edge due to the RTL setting. http://code.google.com/p/chromium/issues/detail?id=174656 This method returns true if the browser is affected by this bug.


### generateVector

Generates a support vector for the current browser/mode. ...

Generates a support vector for the current browser/mode. The result can be added to supportsVectors to eliminate feature detection at startup time.


### init

Runs feature detection routines and sets the various flags. ...

Runs feature detection routines and sets the various flags. This is called when the scripts loads (very early) and again at Ext.onReady. Some detections are flagged as `early` and run immediately. Others that require the document body will not run until ready. Each test is run only once, so calling this method from an onReady function is safe and ensures that all flags have been set.


## Methods

### generateVector

Generates a support vector for the current browser/mode. ...

Generates a support vector for the current browser/mode. The result can be added to supportsVectors to eliminate feature detection at startup time.


### init

Runs feature detection routines and sets the various flags. ...

Runs feature detection routines and sets the various flags. This is called when the scripts loads (very early) and again at Ext.onReady. Some detections are flagged as `early` and run immediately. Others that require the document body will not run until ready. Each test is run only once, so calling this method from an onReady function is safe and ensures that all flags have been set.


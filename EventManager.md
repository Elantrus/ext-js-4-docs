# Ext.EventManager

## Descrição

Registers event handlers that want to receive a normalized EventObject instead of the standard browser event and provides
several useful events directly.

See Ext.EventObject for more details on normalized event objects.

## Properties

### deferReadyEvent

**Tipo:** Number

Additionally, allow the 'DOM' listener thread to complete (usually desirable with mobWebkit, Gecko)
before firing the...

Additionally, allow the 'DOM' listener thread to complete (usually desirable with mobWebkit, Gecko)
before firing the entire onReady chain (high stack load on Loader) by specifying a delay value.
Defaults to 1ms.
Defaults to: `1`


### hasBoundOnReady

**Tipo:** Boolean

Check if we have bound our global onReady listener ...

Check if we have bound our global onReady listener
Defaults to: `false`


### hasFiredReady

**Tipo:** Boolean

Check if fireDocReady has been called ...

Check if fireDocReady has been called
Defaults to: `false`


### idleEvent

**Tipo:** Object

Fires when an event handler finishes its run, just before returning to browser control. ...

Fires when an event handler finishes its run, just before returning to browser control.

This includes DOM event handlers, Ajax (including JSONP) event handlers, and TaskRunners

This can be useful for performing cleanup, or update tasks which need to happen only
after all code in an event handler has been run, but which should not be executed in a timer
due to the intervening browser reflow/repaint which would take place.


### propRe

**Tipo:** RegExp

Options to parse for the 4th argument to addListener. ...

Options to parse for the 4th argument to addListener.
Defaults to: `/^(?:scope|delay|buffer|single|stopEvent|preventDefault|stopPropagation|normalized|args|delegate|freezeEvent)$/`


### readyEvent

**Tipo:** Object

Holds references to any onReady functions


### scrollTimeout

**Tipo:** Object

Timer for doScroll polling


### stoppedMouseDownEvent

**Tipo:** Object

Contains a list of all document mouse downs, so we can ensure they fire even when stopEvent is called.


### useKeyDown

**Tipo:** Object

note 1: IE fires ONLY the keydown event on specialkey autorepeat
note 2: Safari < 3.1, Gecko (Mac/Linux) & Ope...

note 1: IE fires ONLY the keydown event on specialkey autorepeat
note 2: Safari < 3.1, Gecko (Mac/Linux) & Opera fire only the keypress event on specialkey autorepeat
(research done by Jan Wolter at http://unixpapa.com/js/key.html)


### addListener

Appends an event handler to an element. ...

Appends an event handler to an element.  The shorthand version on is equivalent.
Typically you will use Ext.Element.addListener directly on an Element in favor of
calling this version.

on is an alias for addListener.
Parametersel : String/Ext.Element/HTMLElement/WindowThe html element or id to assign the event handler to.


### bindReadyEvent

Binds the appropriate browser event for checking if the DOM has loaded. ...

Binds the appropriate browser event for checking if the DOM has loaded.


### cloneEventListenerCache

Clones the event cache for a particular element for a particular event ...

Clones the event cache for a particular element for a particular event
Parameterselement : HTMLElementThe element


### contains

Checks whether the event's relatedTarget is contained inside (or is) the element. ...

Checks whether the event's relatedTarget is contained inside (or is) the element.
Parametersevent : Object


### createListenerWrap

Create the wrapper function for the event ...

Create the wrapper function for the event
Parametersdom : HTMLElementThe dom element


### fireDocReady

We know the document is loaded, so trigger any onReady events. ...

We know the document is loaded, so trigger any onReady events.


### fireReadyEvent

Fires the ready event ...

Fires the ready event


### fireResize

Fire the resize event. ...

Fire the resize event.


### fireUnload

Fires the unload event for items bound with onWindowUnload ...

Fires the unload event for items bound with onWindowUnload


### getEventCache

Gets the event cache object for a particular element ...

Gets the event cache object for a particular element
Parameterselement : HTMLElementThe element


### getEventListenerCache

Get the event cache for a particular element for a particular event ...

Get the event cache for a particular element for a particular event
Parameterselement : HTMLElementThe element


### getId

Get the id of the element. ...

Get the id of the element. If one has not been assigned, automatically assign it.
Parameterselement : HTMLElement/Ext.ElementThe element to get the id for.


### getKeyEvent

Indicates which event to use for getting key presses. ...

Indicates which event to use for getting key presses.
ReturnsStringThe appropriate event name.


### getPageX

Gets the x coordinate from the event ...

Gets the x coordinate from the event
Parametersevent : ObjectThe event


### getPageXY

Gets the x & y coordinate from the event ...

Gets the x & y coordinate from the event
Parametersevent : ObjectThe event


### getPageY

Gets the y coordinate from the event ...

Gets the y coordinate from the event
Parametersevent : ObjectThe event


### getRelatedTarget

Gets the related target from the event. ...

Gets the related target from the event.
Parametersevent : ObjectThe event


### getTarget

Gets the target of the event. ...

Gets the target of the event.
Parametersevent : ObjectThe event


### isReadyPaused

detects whether the EventManager has been placed in a paused state for synchronization
with external debugging / perf...

detects whether the EventManager has been placed in a paused state for synchronization
with external debugging / perf tools (PageAnalyzer)


### normalizeEvent

Normalize cross browser event differences ...

Normalize cross browser event differences
ParameterseventName : ObjectThe event name


### on

Appends an event handler to an element. ...

Appends an event handler to an element.  The shorthand version on is equivalent.
Typically you will use Ext.Element.addListener directly on an Element in favor of
calling this version.

on is an alias for addListener.
Parametersel : String/Ext.Element/HTMLElement/WindowThe html element or id to assign the event handler to.


### onDocumentReady

Adds a listener to be notified when the document is ready (before onload and before images are loaded). ...

Adds a listener to be notified when the document is ready (before onload and before images are loaded).

Ext.onDocumentReady is an alias for onDocumentReady.
Parametersfn : FunctionThe method the event invokes.


### onWindowResize

Adds a listener to be notified when the browser window is resized and provides resize event buffering (100 millisecon...

Adds a listener to be notified when the browser window is resized and provides resize event buffering (100 milliseconds),
passes new viewport width and height to handlers.
Parametersfn : FunctionThe handler function the window resize event invokes.


### onWindowUnload

Adds a listener to be notified when the browser window is unloaded. ...

Adds a listener to be notified when the browser window is unloaded.
Parametersfn : FunctionThe handler function the window unload event invokes.


### pollScroll

This strategy has minimal benefits for Sencha solutions that build themselves (ie. ...

This strategy has minimal benefits for Sencha solutions that build themselves (ie. minimal initial page markup).
However, progressively-enhanced pages (with image content and/or embedded frames) will benefit the most from it.
Browser timer resolution is too poor to ensure a doScroll check more than once on a page loaded with minimal
assets (the readystatechange event 'complete' usually beats the doScroll timer on a 'lightly-loaded' initial document).


### prepareListenerConfig

Convert a "config style" listener into a set of flat arguments so they can be passed to addListener ...

Convert a "config style" listener into a set of flat arguments so they can be passed to addListener
Parameterselement : ObjectThe element the event is for


### preventDefault

Prevents the browsers default handling of the event. ...

Prevents the browsers default handling of the event.
Parametersevent : EventThe event to prevent the default


### purgeElement

Recursively removes all previous added listeners from an element and its children. ...

Recursively removes all previous added listeners from an element and its children. Typically you will use Ext.Element.purgeAllListeners
directly on an Element in favor of calling this version.
Parametersel : String/Ext.Element/HTMLElement/WindowThe id or html element from which to remove all event handlers.


### removeAll

Removes all event handers from an element. ...

Removes all event handers from an element.  Typically you will use Ext.Element.removeAllListeners
directly on an Element in favor of calling this version.
Parametersel : String/Ext.Element/HTMLElement/WindowThe id or html element from which to remove all event handlers.


### removeListener

Removes an event handler from an element. ...

Removes an event handler from an element.  The shorthand version un is equivalent.  Typically
you will use Ext.Element.removeListener directly on an Element in favor of calling this version.

on is an alias for addListener.
Parametersel : String/Ext.Element/HTMLElement/WindowThe id or html element from which to remove the listener.


### removeResizeListener

Removes the passed window resize listener. ...

Removes the passed window resize listener.
Parametersfn : FunctionThe method the event invokes


### removeUnloadListener

Removes the passed window unload listener. ...

Removes the passed window unload listener.
Parametersfn : FunctionThe method the event invokes


### resolveTextNode

Resolve any text nodes accounting for browser differences. ...

Resolve any text nodes accounting for browser differences.
Parametersnode : HTMLElementThe node


### stopEvent

Stop the event (preventDefault and stopPropagation) ...

Stop the event (preventDefault and stopPropagation)
Parametersevent : EventThe event to stop


### stopPropagation

Cancels bubbling of the event. ...

Cancels bubbling of the event.
Parametersevent : EventThe event to stop bubbling.


### un

Removes an event handler from an element. ...

Removes an event handler from an element.  The shorthand version un is equivalent.  Typically
you will use Ext.Element.removeListener directly on an Element in favor of calling this version.

on is an alias for addListener.
Parametersel : String/Ext.Element/HTMLElement/WindowThe id or html element from which to remove the listener.


## Methods

### addListener

Appends an event handler to an element. ...

Appends an event handler to an element.  The shorthand version on is equivalent.
Typically you will use Ext.Element.addListener directly on an Element in favor of
calling this version.

on is an alias for addListener.
Parametersel : String/Ext.Element/HTMLElement/WindowThe html element or id to assign the event handler to.


### bindReadyEvent

Binds the appropriate browser event for checking if the DOM has loaded. ...

Binds the appropriate browser event for checking if the DOM has loaded.


### cloneEventListenerCache

Clones the event cache for a particular element for a particular event ...

Clones the event cache for a particular element for a particular event
Parameterselement : HTMLElementThe element


### contains

Checks whether the event's relatedTarget is contained inside (or is) the element. ...

Checks whether the event's relatedTarget is contained inside (or is) the element.
Parametersevent : Object


### createListenerWrap

Create the wrapper function for the event ...

Create the wrapper function for the event
Parametersdom : HTMLElementThe dom element


### fireDocReady

We know the document is loaded, so trigger any onReady events. ...

We know the document is loaded, so trigger any onReady events.


### fireReadyEvent

Fires the ready event ...

Fires the ready event


### fireResize

Fire the resize event. ...

Fire the resize event.


### fireUnload

Fires the unload event for items bound with onWindowUnload ...

Fires the unload event for items bound with onWindowUnload


### getEventCache

Gets the event cache object for a particular element ...

Gets the event cache object for a particular element
Parameterselement : HTMLElementThe element


### getEventListenerCache

Get the event cache for a particular element for a particular event ...

Get the event cache for a particular element for a particular event
Parameterselement : HTMLElementThe element


### getId

Get the id of the element. ...

Get the id of the element. If one has not been assigned, automatically assign it.
Parameterselement : HTMLElement/Ext.ElementThe element to get the id for.


### getKeyEvent

Indicates which event to use for getting key presses. ...

Indicates which event to use for getting key presses.
ReturnsStringThe appropriate event name.


### getPageX

Gets the x coordinate from the event ...

Gets the x coordinate from the event
Parametersevent : ObjectThe event


### getPageXY

Gets the x & y coordinate from the event ...

Gets the x & y coordinate from the event
Parametersevent : ObjectThe event


### getPageY

Gets the y coordinate from the event ...

Gets the y coordinate from the event
Parametersevent : ObjectThe event


### getRelatedTarget

Gets the related target from the event. ...

Gets the related target from the event.
Parametersevent : ObjectThe event


### getTarget

Gets the target of the event. ...

Gets the target of the event.
Parametersevent : ObjectThe event


### isReadyPaused

detects whether the EventManager has been placed in a paused state for synchronization
with external debugging / perf...

detects whether the EventManager has been placed in a paused state for synchronization
with external debugging / perf tools (PageAnalyzer)


### normalizeEvent

Normalize cross browser event differences ...

Normalize cross browser event differences
ParameterseventName : ObjectThe event name


### on

Appends an event handler to an element. ...

Appends an event handler to an element.  The shorthand version on is equivalent.
Typically you will use Ext.Element.addListener directly on an Element in favor of
calling this version.

on is an alias for addListener.
Parametersel : String/Ext.Element/HTMLElement/WindowThe html element or id to assign the event handler to.


### onDocumentReady

Adds a listener to be notified when the document is ready (before onload and before images are loaded). ...

Adds a listener to be notified when the document is ready (before onload and before images are loaded).

Ext.onDocumentReady is an alias for onDocumentReady.
Parametersfn : FunctionThe method the event invokes.


### onWindowResize

Adds a listener to be notified when the browser window is resized and provides resize event buffering (100 millisecon...

Adds a listener to be notified when the browser window is resized and provides resize event buffering (100 milliseconds),
passes new viewport width and height to handlers.
Parametersfn : FunctionThe handler function the window resize event invokes.


### onWindowUnload

Adds a listener to be notified when the browser window is unloaded. ...

Adds a listener to be notified when the browser window is unloaded.
Parametersfn : FunctionThe handler function the window unload event invokes.


### pollScroll

This strategy has minimal benefits for Sencha solutions that build themselves (ie. ...

This strategy has minimal benefits for Sencha solutions that build themselves (ie. minimal initial page markup).
However, progressively-enhanced pages (with image content and/or embedded frames) will benefit the most from it.
Browser timer resolution is too poor to ensure a doScroll check more than once on a page loaded with minimal
assets (the readystatechange event 'complete' usually beats the doScroll timer on a 'lightly-loaded' initial document).


### prepareListenerConfig

Convert a "config style" listener into a set of flat arguments so they can be passed to addListener ...

Convert a "config style" listener into a set of flat arguments so they can be passed to addListener
Parameterselement : ObjectThe element the event is for


### preventDefault

Prevents the browsers default handling of the event. ...

Prevents the browsers default handling of the event.
Parametersevent : EventThe event to prevent the default


### purgeElement

Recursively removes all previous added listeners from an element and its children. ...

Recursively removes all previous added listeners from an element and its children. Typically you will use Ext.Element.purgeAllListeners
directly on an Element in favor of calling this version.
Parametersel : String/Ext.Element/HTMLElement/WindowThe id or html element from which to remove all event handlers.


### removeAll

Removes all event handers from an element. ...

Removes all event handers from an element.  Typically you will use Ext.Element.removeAllListeners
directly on an Element in favor of calling this version.
Parametersel : String/Ext.Element/HTMLElement/WindowThe id or html element from which to remove all event handlers.


### removeListener

Removes an event handler from an element. ...

Removes an event handler from an element.  The shorthand version un is equivalent.  Typically
you will use Ext.Element.removeListener directly on an Element in favor of calling this version.

on is an alias for addListener.
Parametersel : String/Ext.Element/HTMLElement/WindowThe id or html element from which to remove the listener.


### removeResizeListener

Removes the passed window resize listener. ...

Removes the passed window resize listener.
Parametersfn : FunctionThe method the event invokes


### removeUnloadListener

Removes the passed window unload listener. ...

Removes the passed window unload listener.
Parametersfn : FunctionThe method the event invokes


### resolveTextNode

Resolve any text nodes accounting for browser differences. ...

Resolve any text nodes accounting for browser differences.
Parametersnode : HTMLElementThe node


### stopEvent

Stop the event (preventDefault and stopPropagation) ...

Stop the event (preventDefault and stopPropagation)
Parametersevent : EventThe event to stop


### stopPropagation

Cancels bubbling of the event. ...

Cancels bubbling of the event.
Parametersevent : EventThe event to stop bubbling.


### un

Removes an event handler from an element. ...

Removes an event handler from an element.  The shorthand version un is equivalent.  Typically
you will use Ext.Element.removeListener directly on an Element in favor of calling this version.

on is an alias for addListener.
Parametersel : String/Ext.Element/HTMLElement/WindowThe id or html element from which to remove the listener.


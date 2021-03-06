Scrollable
==========

Small and quick implementation of a CSS-customizable Scrollbar for use in situations where a div with a fixed height contains content that overflows past its boundaries.
This implementation is based off of the scrollbar designs found in various places on Facebook, GMail, and Trello.

1. One-line instantiation means you are up and running in no time.
2. Mousewheel and click-and-drag support
3. All aspects of the scrollbar container and knob are controlled via CSS
4. Automatically detects browser resizing and adjusts all positioning and sizing accordingly.
5. Automatically adjusts for changes in content

***New**: Scrollable now accepts the [$$](http://mootools.net/docs/core/Element/Element#Window:dollars) selector in addition to the regular [$](http://mootools.net/docs/core/Element/Element#Window:dollar)*

How to Use
----------

### Syntax

	var myScrollable = new Scrollable(element/elements, options);

### Arguments

1. element - ([element/elements](http://mootools.net/docs/core/Element/Element)) The element to make scrollable. Can be selected via $ or $$
2. options - ([object](http://mootools.net/docs/core/Types/Object), optional) See below.

### Options
* autoHide (truthy: defaults to true) If set to true, hides the scrollbar when the mouse is not over the target element. Otherwise, the scrollbar will stay visible at all times.
* fade (truthy: defaults to true) If set to true, a fade effect will be applied to the showing and hiding of the scrollbar.

### Example

Given a div element with a fixed height and proper overflow (that is, anything besides "scroll"/"auto"):

	var myScrollable = new Scrollable( $('elem-id') );

Given more than one element, by passing in a CSS selector:

	var myScrollables = new Scrollable( $('.class') );

A more complex example (an unordered list with multiple `li` elements):

	var myScrollables = new Scrollable( $('list').getElements('li') );

Changelog
---------

### v0.2.6
* Fixed [issue #5](https://github.com/julianlam/Scrollable/issues/5), regarding incorrect positioning in certain circumstances involving instantiation and the page scrollbar
* Fixed bug where scrollbar was visible for a fraction of a second before being hidden/repositioned.
* Fixed issue where scrolling of the page was always blocked by a Scrollable instance, even if the target element has been scrolled to the top/bottom already
* Added "terminate();", which should be called to remove any existing instances of Scrollable

### v0.2.5
* Updated Scrollable to support target elements like `<textarea>`

### v0.2.4
* Added ability to define a custom class in the event "scrollbar" is already taken

### v0.2.3
* Added documentation regarding the fade and autoHide options, which were already present in v0.2.2
* Added ability to pass in elements selected via [getElements](http://mootools.net/docs/core/Element/Element#Element:getElements)
* Fixed [issue #2](https://github.com/julianlam/Scrollable/issues/2), regarding incorrect fading behaviour when scrollbar is in use

Screenshots
-----------

![Screenshot 1](http://i.imgur.com/ZKXbK.png)

Tappy! 
=====

Tappy is a minimal normalized tap event that works with touch, mouse, keyboard, and probably other inputs too.

Copyright 2013 @scottjehl, Filament Group, Inc. Licensed MIT

Why
===

Tappy allows you to bind to a `tap` event like you would any other user interaction, like `click`. The advantage of usting Tappy's  `tap` event over `click` is that it will allow you to execute code immediately on touch devices, eliminating the 300ms delay that click events have on platforms like iOS. Once bound to an element, Tappy's `tap` event will fire upon touch or other traditional interactions like mouse click, pressing the enter key, and more. 


How-to
===

Tappy requires jQuery, or a similar framework of matching API conventions. 

To use, include `tappy.js` in your page, select an element and bind to a `tap` event. 

``` js
$( "a.my-link" ).bind( "tap", function( e ){ 
  alert( "tap!" );
}); 
```
In binding to the `tap` event, you'll be automatically preventing the browser's default click handling on the element, so be sure to handle that tap responsibly.

To use tappy to create fast-click navigation, you could do something like this:

``` js
$( "a.my-link" ).bind( "tap", function( e ){ 
  // go to the e.target.href URL
}); 
```


Notes:
===

This plugin makes several assumptions that may not work well for your project, but we've found them easy enough to work around.

Tappy works best when bound directly to a tappable element. In its current state, we don't recommend using it with event delegation due to the way it prevents default event behavior. That might change in a future update.

This plugin is built using a very limited portion of jQuery's API in attempt to be compatible with slimmer libraries that share jQuery's syntax. That's why it monkey-patches `bind` for example, rather than using the Special Events API. That said, we could make those changes, but this is working pretty well for our admittedly specific needs at the moment.


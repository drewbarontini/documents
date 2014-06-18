jQuery Plugin
=============

CoffeeScript
------------

```coffeescript
# --------------------
#   Plugin Name
#   Author Name
#   Version
# --------------------

# Reference jQuery
$ = jQuery

# Adds plugin object to jQuery
$.fn.extend
  # Change pluginName to your plugin's name.
  pluginName: (options) ->
    # Default settings
    settings =
      option1: true
      option2: false
      debug: false

    # Merge default settings with options.
    settings = $.extend settings, options

    # Simple logger.
    log = (msg) ->
      console?.log msg if settings.debug

    # _Insert magic here._
    return @each () ->
      log "Preparing magic show."
      # You can use your settings in here now.
      log "Option 1 value: #{settings.option1}"
```

JavaScript
----------

```javascript
/** --------------------
*   Plugin Name
*   Author Name
*   Version
-------------------- **/

(function($) {
  
  $.fn.pluginName = function(options) {

  // Defaults
  var defaults = {
    // ...
  };

  // Merge defaults and options
  var settings = $.extend({}, defaults, options);
    
  // Initialize
  this.each(function() {
    // ...
  });

  // Object
  var object = {};

  // Object method
  object.method = function() {
    // ...
  };

  // Return this (to make chainable)
  return this;

})(jQuery);
```

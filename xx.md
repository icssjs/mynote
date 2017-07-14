```javascfipt 
use strict";

(function ($) {
    $.attrFn = $.attrFn || {};

    // navigator.userAgent.toLowerCase() isn't reliable for Chrome installs
    // on mobile devices. As such, we will create a boolean isChromeDesktop
    // The reason that we need to do this is because Chrome annoyingly
    // purports support for touch events even if the underlying hardware
    // does not!
    var touchCapable = ('ontouchstart' in window),
	
        settings = {
            tap_pixel_range: 5,
            swipe_h_threshold: 50,
            swipe_v_threshold: 50,
            taphold_threshold: 750,
            doubletap_int: 500,

            touch_capable: touchCapable,
            orientation_support: ('orientation' in window && 'onorientationchange' in window),

            startevent:  (touchCapable) ? 'touchstart' : 'mousedown',
            endevent:    (touchCapable) ? 'touchend' : 'mouseup',
            moveevent:   (touchCapable) ? 'touchmove' : 'mousemove',
            tapevent:    (touchCapable) ? 'tap' : 'click',
            scrollevent: (touchCapable) ? 'touchmove' : 'scroll',

            hold_timer: null,
            tap_timer: null
        };
```
# Klipper Config stuff

* neopixel.cfg - klipper config and gcode macros for controlling neopixel leds.

## Base macro for shared information
**[gcode_macro global_light_setting]**<br >
Central place for storing the current state of the light strip

## Fade out/in
Instead of just switching the light on and off i wanted it to fade on and off.

**[gcode_macro fade_light]**<br >
The control macro for switching(fading) on or of a light.
Call: "fade_light red={redColor} green={greenColor} blue={blueColor}" to switch light on to the desired color.
Call: "fade_light red={redColor} green={greenColor} blue={blueColor} count=100 fade_mode=0" to switch off.

**[delayed_gcode fade_light_delayed]**<br >
The delayed gcode macro that does the actual fading.

## Change color

**[gcode_macro change_light]**<br >
The control macro for changing the color.
Call: "change_light red=0 green=1 blue=0" or "change_light red=0.5 green=1 blue=0.3"
Each color needs to be between 0 and 1.
Note: change_light is not designed to be called when leds are off. Use  the fade_light macro to switch on to the desired color.

**[delayed_gcode change_light_delayed]**<br >
The delayed gcode macro that does the actual color change.

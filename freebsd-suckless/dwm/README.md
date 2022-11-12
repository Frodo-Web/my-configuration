# DWM - dynamic window manager, [Original source](https://github.com/Digital-Chaos/dwm/tree/freebsd)
dwm is an extremely fast, small, and dynamic window manager for X.


## Requirements
In order to build dwm you need the Xlib header files.


## Installation
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):
````
make clean install
````
## #define MODKEY Mod4Mask
The default MODKEY is left Alt key, it's defined in config.def.h as:
````
#define MODKEY Mod1Mask
````
We switch to Win key to make use of it:
````
#define MODKEY Mod4Mask
````
## Install fonts
Font Awesome 6 are required for this configuration
````
// config.h
#define FONT_AWESOME_BRANDS     "Font Awesome 6 Brands-9"
#define FONT_AWESOME_FREE       "Font Awesome 6 Free Solid-9"
````
To install these fonts follow this guide - [Custom xorg fonts in FreeBSD](https://github.com/Frodo-Web/frodo-tips/blob/main/FreeBSD-tips-by-Frodo/custom-fonts.md)
## Running DWM
Add the following lines to your .xinitrc to start dwm using startx:
````
#!/bin/sh
exec dwm
````
In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:
````
DISPLAY=foo.bar:1 exec dwm
````
(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:
````
while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
do
    sleep 1
done &
exec dwm
````
### But better use slstatus, [Check this out](https://github.com/Frodo-Web/my-configuration/tree/main/freebsd-suckless/slstatus)
## Configuration
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.

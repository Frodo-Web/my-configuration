# slstatus - suckless status, [Original source](https://github.com/Digital-Chaos/slstatus)
slstatus is a suckless status monitor for window managers that use WM_NAME
(e.g. dwm) or stdin to fill the status bar.


## Features
- Battery percentage/power/state
- CPU usage
- CPU frequency
- CPU iowait
- Custom shell commands
- Date and time
- Disk status (free storage, percentage, total storage and used storage)
- Available entropy
- Username/GID/UID
- Hostname
- IP address (IPv4 and IPv6)
- Kernel version
- Keyboard indicators
- Load average
- Number of files in a directory (hint: Maildir)
- Memory status (free memory, percentage, total memory and used memory)
- Swap status (free swap, percentage, total swap and used swap)
- Temperature
- Uptime
- Volume percentage (OSS/ALSA)
- WiFi signal percentage and ESSID


## Requirements
In order to build slstatus you need the Xlib header files and optionally ALSA
for volume percentage. PulseAudio is not supported for various reasons.


## Installation
Edit config.mk to match your local setup (slstatus is installed into the
/usr/local namespace by default).

Afterwards enter the following command to build and install slstatus (if
necessary as root):

    make clean install


## Running slstatus with DWM
See the man page for details.
### Add slstatus execution to your .xinitrc file like this:
````
#!/bin/sh
feh --no-fehbg --bg-fill /home/sega/background.jpg
slstatus &
exec dwm
````
## Configuration
slstatus can be customized by creating a custom config.h and (re)compiling the
source code. This keeps it fast, secure and simple.

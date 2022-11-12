# ST is a simple terminal implementation for X
## Copy / Paste
#### Paste with mouse wheel
````
// config.h
static MouseShortcut mshortcuts[] = {
	/* mask                 button   function        argument       release */
  ...
	{ XK_ANY_MOD,           Button2, selpaste,       {.i = 0},      1 },
  ...
};
````
#### Copy / Paste with Ctrl+Shift + C / V / Y and Shift + Insert
````
...
#define TERMMOD (ControlMask|ShiftMask)

...
static Shortcut shortcuts[] = {
	/* mask                 keysym          function        argument */
      ...
	{ TERMMOD,              XK_C,           clipcopy,       {.i =  0} },
	{ TERMMOD,              XK_V,           clippaste,      {.i =  0} },
	{ TERMMOD,              XK_Y,           selpaste,       {.i =  0} },
	{ ShiftMask,            XK_Insert,      selpaste,       {.i =  0} },
      ...
};
````

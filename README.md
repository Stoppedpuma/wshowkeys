# wshowkeys

Displays keypresses on screen on supported Wayland compositors (requires
`wlr_layer_shell_v1` support).

![](https://sr.ht/xGs2.png)

Originally Forked from https://git.sr.ht/~sircmpwn/wshowkeys as Drew has moved onto other things.

This fork is from https://github.com/ammgws/wshowkeys and contains small improvements such as unicode icons, and readability improvements

## Known issues / Issues to be aware of prior to usage

- Delete is shown as a missing unicode.
- The first PgUp / PgDown not having a space after normal typing

## Installation

Dependencies:

- cairo
- libinput
- pango
- udev 
- wayland 
- xkbcommon 

```
$ meson build
$ ninja -C build
# ninja -C build install
# chmod a+s /usr/bin/wshowkeys (or chmod a+s /usr/local/bin/wshowkeys in some cases)
```

wshowkeys must be configured as setuid during installation. It requires root
permissions to read input events. These permissions are dropped after startup.

## Usage

```
wshowkeys [-b|-f|-s #RRGGBB[AA]] [-F font] [-t timeout]
    [-a top|left|right|bottom] [-m margin] [-o output]
```

- *-b #RRGGBB[AA]*: set background color
- *-f #RRGGBB[AA]*: set foreground color
- *-s #RRGGBB[AA]*: set color for special keys
- *-F font*: set font (Pango format, e.g. 'monospace 24')
- *-t timeout*: set timeout before clearing old keystrokes
- *-a top|left|right|bottom*: anchor the keystrokes to an edge. May be specified
  twice.
- *-m margin*: set a margin (in pixels) from the nearest edge
- *-o output*: request wshowkeys is shown on the specified output
  (unimplemented)

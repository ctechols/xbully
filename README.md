# xbully: Push your windows around

xbully gives you the ability to manipulate windows from the command line. 
Unlike similar commands such as wmctrl or xdotool, xbully takes into account 
your existing window layout, and lets you move or resize a window relative to 
other windows on your screen.

Some window managers, like openbox or sawfish, have rich sets of commands for 
moving windows around using the keyboard.  xbully attempts to make those 
features available in more window managers.

# Getting Started

## Dependencies

xbully has the following list of dependencies on an Ubuntu system:

* ruby
* ruby-dev
* bundler
* build-essential
* libx11-dev
* libglib2.0-dev
* libxmu-dev

xbully also requires a window manager with good support for the Extended Window 
Manager Hints (EWMH) specification 
http://standards.freedesktop.org/wm-spec/wm-spec-latest.html.  

It is tested under the following window managers:

* openbox
* marco

The following window managers are known not to work well:

* sawfish - Sawfish doesn't report the \_NET\_FRAME\_EXTENTS property, so xbully 
  cannot calculate window sizes correctly.

## Installing

1. Clone the repo http://github.com/ctechols/xbully
2. Change into the xbully root directory
3. Run `bundle install --path ./gems`
4. Add the xbully root directory to your `$PATH`
5. Run 'xbully'

# Window manipulation commands

Run xbully commands using the following syntax:

`xbully <command_name>`

## `pack_<direction>`

These commands will move a window in the named direction until they are 
immediately adjacent to the nearest window or monitor edge:

* pack_left
* pack_right
* pack_up
* pack_down

# Known Issues

marco (The MATE window manager) prevents windows from being placed across the 
boundary between two monitors.  This causes issues when using the 
`pack_<direction>` commands.

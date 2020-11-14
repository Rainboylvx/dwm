dwm - dynamic window manager
============================
dwm is an extremely fast, small, and dynamic window manager for X.


Requirements
------------
In order to build dwm you need the Xlib header files.


Installation
------------
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

    make clean install


## pathes

- [dwm-alpha-20201019-61bb8b2.diff](./patches/dwm-alpha-20201019-61bb8b2.diff)
- [dwm-autostart-20200610-cb3f58a.diff](./patches/dwm-autostart-20200610-cb3f58a.diff)
- [dwm-fullscreen-6.2.diff](./patches/dwm-fullscreen-6.2.diff)
- [dwm-hide_vacant_tags-6.2.diff](./patches/dwm-hide_vacant_tags-6.2.diff)
- [dwm-noborder-6.2.diff](./patches/dwm-noborder-6.2.diff)
- [dwm-scratchpad-6.2.diff](./patches/dwm-scratchpad-6.2.diff)
- [dwm-vanitygaps-20200610-f09418b.diff](./patches/dwm-vanitygaps-20200610-f09418b.diff)
- [dwm-focusadjacenttag-6.0.diff](./patches/dwm-focusadjacenttag-6.0.diff) 
- [我自制的补丁，第二次按tag会回到上一个tag](./patches/0001-my-patch-press-tag-again-will-toggle.patch)

autostart 的脚本在`~/.dwm/autostart.sh `

使用的字体：[Yahei-Fira-Icon-Hybrid-Font](https://github.com/HanleyLee/Yahei-Fira-Icon-Hybrid-Font);wq

## 我的快捷键

| 快捷键                                                 | 说明                                     |
|--------------------------------------------------------|------------------------------------------|
| <kbd>MODKEY</kbd> +<kbd>d</kbd>                        | dmenu                                    |
| <kbd>MODKEY</kbd> +<kbd>Return</kbd>                   | st terminal                              |
| <kbd>MODKEY</kbd> +<kbd>'</kbd>                        | st scratchpad                            |
| <kbd>MODKEY</kbd> +<kbd>b</kbd>                        | google-chrome-stable                     |
| <kbd>MODKEY</kbd> +<kbd>j</kbd>                        | focusstack next                          |
| <kbd>MODKEY</kbd> +<kbd>k</kbd>                        | focusstack pre                           |
| <kbd>MODKEY</kbd> +<kbd>l</kbd>                        | inc master size                          |
| <kbd>MODKEY</kbd> +<kbd>h</kbd>                        | dec master size                          |
| <kbd>MODKEY</kbd> +<kbd>Tab</kbd>                      | toggle pre view                          |
| <kbd>MODKEY</kbd> +<kbd>q</kbd>                        | kill client                              |
| <kbd>MODKEY</kbd> +<kbd>f</kbd>                        | fullscreen                               |
| <kbd>MODKEY</kbd> +<kbd>space</kbd>                    | toggle pre layout                        |
| <kbd>MODKEY</kbd> +<kbd>0</kbd>                        | view all window                          |
| <kbd>MODKEY</kbd> +<kbd>left</kbd>                     | view to left                             |
| <kbd>MODKEY</kbd> +<kbd>right</kbd>                    | view to right                            |
| <kbd>MODKEY</kbd>+<kbd>Shift</kbd> +<kbd>left</kbd>    | move window to left                      |
| <kbd>MODKEY</kbd>+<kbd>Shift</kbd> +<kbd>right</kbd>   | move window to right                     |
| <kbd>MODKEY</kbd>+<kbd>Shift</kbd> +<kbd>i</kbd>       | increase number of master                |
| <kbd>MODKEY</kbd>+<kbd>Shift</kbd> +<kbd>d</kbd>       | decrease number of master                |
| <kbd>MODKEY</kbd>+<kbd>Shift</kbd> +<kbd>b</kbd>       | toggle show status bar                   |
| <kbd>MODKEY</kbd>+<kbd>Shift</kbd> +<kbd>Return</kbd>  | swap stack master                        |
| <kbd>MODKEY</kbd>+<kbd>Shift</kbd> +<kbd>t</kbd>       | set tiled layout                         |
| <kbd>MODKEY</kbd>+<kbd>Shift</kbd> +<kbd>f</kbd>       | set floating layout                      |
| <kbd>MODKEY</kbd>+<kbd>Shift</kbd> +<kbd>monocle</kbd> | set monocle(单片全屏) layout             |
| <kbd>MODKEY</kbd>+<kbd>Shift</kbd> +<kbd>space</kbd>   | toggle window floating                   |
| <kbd>MODKEY</kbd>+<kbd>Shift</kbd> +<kbd>0</kbd>       | set window at all tag                    |
| <kbd>MODKEY</kbd>+<kbd>Ctrl</kbd> +<kbd>[0-9]</kbd>    | view this tag at same time               |
| [Mod]+[R M B]                                          | to resize the floating window.           |
| [Mod]+[L M B]                                          | to move the floating window around.      |
| [Mod]+[Space]                                          | to change the layout into floating mode. |
| [Mod]+[Shift]+[Space]                                  | to make an individual window float.      |
| [Mod]+[M M B]                                          | to make an individual window un-float.   |
| [Shift]+[Mod]+[, / .]                                  | move active window to different screen.  |
| [Shift]+[Mod]+[q]                                      | quit dwm cleanly.                        |

Running dwm
-----------
Add the following line to your .xinitrc to start dwm using startx:

    exec dwm

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm


Configuration
-------------
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.

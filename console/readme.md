Console
=======

The "true console" (not a terminal on a GUI that is) is mostly accessible by \<alt\>-\<ctrl\>-\<F1-F6\> (there are many).

clear screen (buffer)
---------------------

Ctrl-l

or

`clear`

Keyboard-Layout
---------------

* `dpkg-reconfigure keyboard-configuration`
* `service keyboard-setup restart`

and see [Debian: Keyboard](https://wiki.debian.org/Keyboard)

or change:

/etc/default/keyboard

XKBLAYOUT="ch"

and `reboot`

Note: Live-USB/CD environments may override this by the readonly rootfs.

Language Settings
-----------------

* `dpkg-reconfigure locales`
* `export LANG=us_US.UTF-8`

see [Debian: Language Change](https://wiki.debian.org/ChangeLanguage)

Console font
------------

* edit /etc/default/console-setup
* read `man console-setup`
* you may use:
	* Fontface: "Fixed"
	* Codeset: "Lat15"
	* Fontsize: "8x16"
* or
	* Fontface: "TerminusBold"
	* Codeset: "Lat15"
	* Fontsize: "16x32"
	

[back](../)


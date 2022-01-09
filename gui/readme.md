GUI
===

* cinnamon
* mint
* KDE
* gnome

How to enable/disable graphical environment
-------------------------------------------

[systemd](/boot/systemd.md)

How to autologin a user (without password)
------------------------------------------

for lightdm:

`nano /etc/lightdm/lightdm.conf`
uncomment and change the following line:

autologin-user=<user-name>

Start menu items
----------------

are stored in `/usr/share/applications` and `~/.local/share/applications`. But this may well depend on
the menu in use (eg. Default Cinnamon menu applet and Cinnamenu and others).

[back](../)


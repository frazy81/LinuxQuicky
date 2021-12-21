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

[back](../)


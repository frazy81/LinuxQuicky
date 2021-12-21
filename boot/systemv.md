System V
========

Init scripts
------------

Most distros have changed to [systemd](systemd.md) init!

https://www.linux.com/news/introduction-services-runlevels-and-rcd-scripts

`/etc/rc.local` is called after every other rcX.d, but before the logon prompts. So I use this script to execute any after reboot tasks (just enter the script-file before exit). And remember: init script may - just like cron - not set PATH to the common sence dir names. So: expect that commands like mount/rm/touch etc. need an absolute path. You may get the absolute path of a system command by typing `which <command>`. This will return the path the program is situated at.

A "K" in front of the symlink means: the service should be killed in this runlevel (service stop)

A "S" in front of the symlink means: the service should be started in this runlevel (service start)
The number gives the order.

add a service for a certain runlevel
`cd /etc/rc2.d/`			# rc2.d is - for raspbian/debian - the normal multi-user runlevel.
`ln -s ../init.d/rpcbind S05rpcbind`

[back](./)


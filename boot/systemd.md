systemd
=======

systemd unit-files are stored in /etc/systemd/system

if you "systemctl enable name.service", a symlink is created in /etc/systemd/system/multi-user.target or any other target.

the symlink can be removed by "systemctl disable name.service".

Be AWARE that: if you change the [Install] WantedBy, that you remove the symlink first by disabling the service and make sure the symlink is away!

Be AWARE that you reload the daemon by "systemctl daemon-reload" after each change to a unit-file!

Be AWARE to never use Before/After multi-user.target when [Install] is multi-user.target! This is a dependency cycle!

Be AWARE to always use absolut path's, since there's no ENV!

Be AWARE to use sleep ONLY in ExecStartPre=/bin/sleep 15, but NOT inside ExecStart

Fruther explanation: [systemd](https://www.digitalocean.com/community/tutorials/understanding-systemd-units-and-unit-files)

Debugging:

`systemctl status name.service`	# if only roughly 5 lines and loaded (dead), the service kind of interrupted, debugging with next command:

`journalctl -xe | grep name -A 5 -B 5`

Boot time analysis
------------------

`systemd-analyze plot >temp.xml`

then open the temp.xml in a browser

[back](./)


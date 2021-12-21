Debug Shutdown
==============

make journals persistent:

`mkdir -p /var/log/journal`

`systemd-tmpfiles --create --prefix /var/log/journal`

`nano /etc/systemd/journald.conf`

	add/change the line to: Storage=persistent
	
`systemctl restart systemd-journald`

to show last boot/shutdown:

	`journalctl -b -1`	# scroll down

[back](./)

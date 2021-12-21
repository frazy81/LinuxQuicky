NFS - Network File System
=========================

network file system works without passwords. Only Samba/SMB/Microsoft/cifs network do need a credential.

Mounting:

`mount 192.168.192.4:/folder /mnt -o nolock`

`cd /etc/rc2.d/`			# rc2.d is - for raspbian/debian - the normal multi-user runlevel.
`ln -s ../init.d/rpcbind S05rpcbind`

to start rpcbind for runlevel 2 (the default multi user runlevel).

You may need to assign MOUNTD (sub process of NFS) to have a static Port, so that you can handle the ufw firewall:

in /etc/default/nfs-kernel-server I added --port 592 for MOUNDOPTS and enabled the port by "ufw enable 592" on the server

[back](./)


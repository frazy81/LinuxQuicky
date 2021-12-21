ExFAT
=====

Windows file system which is often used for multi platform file interchange (USB sticks, SD cards etc.).

initialize exfat volume
-----------------------

`sudo mkfs.exfat -n <LABEL> /dev/sdb1`

Check an exfat volume
---------------------

`sudo fsck.exfat /dev/sdb1`

linux kernel<5.4
----------------

`sudo apt install exfat-fuse exfat-utils`
`ln -s /sbin/mount.exfat-fuse /sbin/mount.exfat`	# for automount
or mount with fuse: `mount.exfat-fuse /dev/sdb1 /mnt2`

[back](./)


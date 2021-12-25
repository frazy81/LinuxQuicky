NTFS
====

Windows default file system.

initialize ntfs volume
----------------------

`apt install ntfs-3g`	# get ntfs support

`mkntfs -f -L <LABEL> /dev/sdb1`

or

`mkfs -t ntfs -f -U -L <LABEL> /dev/sdb1`

-f: fast (otherwise 0-ed, takes long)
-U: Make UUID, good for /etc/fstab

name a volume
-------------

ntfslabel /dev/sda9 my_label

partitioning
------------

in a [partitioning](../drives/) tool (such as cfdisk, fdisk, gnome-disks) select partition type 7 (HPFS/NTFS/exFAT) for NTFS.

[back](./)


wearout - SD/SSD
================

how to decrease the wearout of SD-cards/SSD-disks:

* disable swap (remove swap partitions, delete line of swap in /etc/fstab)
* `sudo tune2fs -O ^has_journal /dev/sdaX`, disable journaling
* in /etc/fstab:
	* `/dev/mapper/linux--root	/               ext4    noatime,errors=remount-ro 0       1`
	* add the mount option `noatime` to the root partition
* mount /var as a read-only filesystem, so that logs can't be written.

[back](./)


Loop devices
============

virtual drives or files can be treated like a block device.

`losetup -P /dev/loop0 ./image-rescue-disk.img`		# loop0p1 is now also populated due to -P (populate)

so we can do:

`dd if=/dev/loop0p1 bs=4M | pv -s 8G | dd of=/dev/mmcblk0p1 bs=4M`

`losetup -d /dev/loop0`		# detach assignment of /dev/loop0 to ./image-rescue-disk.img

[back](./)


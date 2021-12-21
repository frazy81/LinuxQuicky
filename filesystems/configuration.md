/etc/fstab
==========

on the [console](/console/) type in `man fstab`

use "auto" for automount only if disks are installed fix. Otherwise the computer won't boot if the disks are not available.
Use static UUID in fstab (get the id through blkid or cfdisk)

`ls -lrt /dev/disk/by-uuid`	# which uuid for which drive/volume?

[back](./)


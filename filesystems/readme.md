Filesystems
===========

* [How to configure](./configuration.md)

Common linux filesystems
------------------------

* [ext4](ext4.md)
* [ntfs](ntfs.md)
* [nfs network file system](nfs.md)
* [btrfs](btrfs.md)
* [samba/cifs](samba.md)
* [tmpfs - in memory file system - ramdisk](tmpfs.md)
* linux swap (todo)
* [wearout considerations for SD/SSD](wearout.md)
* and many others (including support for NTFS/FAT16/32/exFAT)

which filesystem
----------------

Windows XP and higher use NTFS, exFAT and FAT32. MacOS can read/write exFAT/NTFS
(NTFS write not per default!). Linux Kernel 5.4+ supports exFAT out of the box,
kernels <5.4 need: "sudo apt install exfat-fuse exfat-utils".
Linux and NTFS: apt install ntfs-3g

to share data on multiple platforms: exFAT (>32GB, files>4GB possible) and vfat (alias for FAT32, only works up to 32GB and files smaller than 4GB)!

FAT32=vfat (in linux)

Linux only: ext4 is a good choice.

fixing filesystem issues
------------------------

[fixing](fixing.md)

What is mounted?
----------------

* mount				# show all mounted filesystems
* findmnt -l --target /		# what is mounted at '/'
* findmnt			# show all mounted filesystems

Which process accesses a certain file
-------------------------------------

* fuser -v /path/to/file
* fuser -v /mnt			# is /mnt still being used (and by which processes)

[back](../)

Partitioning
============

`fdisk /dev/sda -l`			gives a nice overview over all partitions and where they start/end

`cfdisk /dev/sda`

`lsblk`		# list block devices
`blkid -o list`	# with UUID, only root

Using old MBR, you can only use 2TB per disk. When installing linux, try GUID GPT. GRUB has some problems with GPT, if you boot with
EFI you need an EFI System partition, without EFI you need an extra Bootloader-Partition. Both described in [external](https://wiki.ubuntuusers.de/GRUB_2/Grundlagen/#MBR-mit-GUID-Partitionstabelle-GPT)
So: when installing a new system: make sure you have one of these partitions setup! Or you never can run GRUB on the GPT. I tried and failed.

Always have at least 200 MB for the /boot partition (if it's a partition)! 100MB is used by a kernel (actually roughly 65MB), but I need space for apt upgrade setting up a new kernel! Neptun had such a problem.

NEW: When using GPT and EFI: use a 64-bit OS (amd64), otherwise you can't install in UEFI mode.

partitioning:
make GTP:
sgdisk -g /dev/sda
back to MBR:
sgdisk -m 1,2,3,4 /dev/sda	then reboot, then use cfdisk /dev/sda and toggle the partition bootable with "b".

to reinstall GRUB:
grub-install /dev/sda

[back](./)


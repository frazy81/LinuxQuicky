VirtualBox
==========

Mount VirtualBox drives
-----------------------

apt install qemu (for reading VMDK VirtualBox virtual drives)
sudo qemu-nbd -c /dev/nbd0 -f vmdk linux-debian-baremetal-base-conf-disk001.vmdk
sudo mount /dev/nbd0p1 /mnt2
sudo umount /mnt2
sudo qemu-nbd -d /dev/nbd0

[back](./)


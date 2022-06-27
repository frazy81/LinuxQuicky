UEFI / BIOS
===========

Old computers used BIOS "firmware" (BIOS=Basic Input/Output System). New computers use UEFI (=Unified Extensible Firmware Interface), how ever
the computer can still run using BIOS with legacy mode.

How to see which one is in use?

/sys/firmware/efi

if this directory exists, the system is booted in UEFI. If it efi does not exist, then the system is booted in BIOS.

EFI Grub Boot recovery
======================

[Recovery-Process](https://ictsolved.github.io/recover-efi-grub-in-linux/)

``
 sudo mount /dev/sda7 /mnt

 sudo mount /dev/sda2 /mnt/boot/efi

 sudo for i in /dev /dev/pts /proc /sys /run; do sudo mount -B $i /mnt$i; done

 sudo cp /etc/resolv.conf /mnt/etc/

 sudo modprobe efivars

 sudo chroot /mnt

 sudo apt-get update

 sudo apt-get install --reinstall grub-efi-amd64

 sudo update-grub

 sudo umount /mnt/boot/efi

 sudo umount /mnt

 exit

 sudo reboot
 
``

[back](./)


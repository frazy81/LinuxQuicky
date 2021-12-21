Encrypt Filesystems
===================

Single encrypted image file
---------------------------

Setup:

`apt install lvm2 cryptsetup e2fsprogs`

`dd if=/dev/urandom of=crypto.img bs=1M count=50`	# 50 MB image file

`losetup /dev/loop0 crypto.img`	# assign the image to the special block device /dev/loop0

`cryptsetup -y luksFormat -c aes /dev/loop0`	# format the loop device (and thus the image file)

`cryptsetup luksOpen /dev/loop0 crypto`	# open the loop device and give it the mapper name "crypto"

`mkfs.ext4 /dev/mapper/crypto`	# format the image with [ext4](ext4.md) filesystem
`fsck -f /dev/mapper/crypto`	# check for integrity

Use after setup:

mounting the fs:
`losetup /dev/loop0 crypto.img`	# assign special loop block device 0 (/dev/loop0) the image file.
`cryptsetup luksOpen /dev/loop0 crypto`	# let loop0 be handled by cryptsetup => device /dev/mapper/crypto
`mount /dev/mapper/crypto /mnt2`	# mount it to /mnt2

unmount the fs:
`umount /mnt2`	# umount filesystem
`cryptsetup luksClose crypto`	# free it from being decrypted
`losetup -d /dev/loop0`	# not assigned to loop0 anymore.

Encrypted LVM
-------------

`vgscan --mknodes`
`vgchange -ay linux-lvm`	# -a activate, y yes, n no, per default active
`lvdisplay`
`lvs`
`mount /dev/mapper/<linux-root> /mnt2`

umount first
`vgchange -an linux-lvm`
`cryptsetup luksClose linux-root`
`losetup -d /dev/loop0`

[back](./)


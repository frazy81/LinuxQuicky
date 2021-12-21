Fixing corrupt filesystems
==========================

apt-get install ntfs-3g
ntfsfix /dev/sdb
    # unfortunately ntfsfix can't fix all problems, sometimes you need to run 'chkdsk d: /F' on windows itself

testdisk and follow screen instructions

cryptsetup luksOpen /dev/sda1 linux-root
vgscan --mknodes
mount /dev/mapper/linux--lvm-linux--root /mnt2
cryptsetup luksOpen -d /mnt2/root/luks_homekey.key /dev/sda1 linux-home
mount /dev/mapper/linux-home /mnt3
fsck.ext4 -v -f -D -c /dev/mapper/linux--lvm-linux--root        # -c very slow, checks for badblocks, see /srv/manage/mond-backup_check_filesystems
fsck.ext4 -v -f -D -c /dev/mapper/linux-home

todo: umount stuff? not sure how to vgscan delete, umount shows device busy

[back](./)


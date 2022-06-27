# btrfs

### create a new btrfs filesystem

`mkfs.btrfs -L mylabel /dev/sdb1`

or use the whole disk (without partitions)

`mkfs.btrfs -L mylabel /dev/sdb`

### mounting a btrfs filesystem

`mount -t btrfs /dev/sdb1 /mnt2`

### create subvolume and snapshots

create a subvolume "new_subvol"

`btrfs subvolume create /mnt2/new_subvol`

make a snapshot of that subvolume

`btrfs subvolume snapshot /mnt2/new_subvol /mnt2/snapshot_of_subvol`

or 

`btrfs subv snapshop /home /home/.snapshots/2022-02-01`		# if /home is a btrfs subvolume

### mounting a subvolume only

`mount -t btrfs -o subvol=new_subvol /dev/sdb1 /new_subvol`

`mount -t btrfs -o subvol=snapshot_of_subvol /dev/sdb1 /mnt/snapshot`

`mount -o subvolid=258 /dev/sdb1 /mnt3`		# use btrfs subv list /mnt2 to show subvolids

or in /etc/fstab:

`UUID=<UUID>	/mnt3	btrfs	rw,exec,subvolid=258	0	0`		# UUID by `blkid`

### checking and maintenance

`btrfsck /dev/sdb1`

`btrfs scrub start /mnt2`

`btrfs scrub status /mnt2`

`btrfs scrub cancel /mnt2`

`btrfs scrub resume /mnt2`

### info

`btrfs fi show`

diskusage:

`btrfs fi du /mnt3 -s`

`btrfs fi df /mnt3 -h`

listing:

`btrfs subv list /mnt2`

do not use btrfs RAID 5.

for btrfs as root filesystem: do NOT use top level! Create a subvolume "@" and mount this subvolume as root,
so that snapshots and fs-expansion works.

When snapshots are active, removing a lot or big files costs time due to CoW (Copy on Write). If a lot of copy and remove operations are
due it might make sence to use a ext4 filesystem or use a subvolume with no snapshots.

A good tool to keep track of used storage space by snapshots is:

[btrfs-du](https://github.com/nachoparker/btrfs-du/blob/master/btrfs-du)

[back](./)


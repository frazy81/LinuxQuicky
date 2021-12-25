ext4
====

very common linux file format.

Resize volume
-------------

`cfdisk /dev/sda`	# filesystems unmounted!
`e2fsck -f /dev/sda2`	# check filesystem
`resize2fs /dev/sda2 32G` # resize to 32G
`cfdisk /dev/sda`	# resize partition to 32G (RESIZE BUTTON)

label
-----

`e2label /dev/sda1 name-of-the-filesystem`

[back](./)


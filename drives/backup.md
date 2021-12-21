Backup
======

dd (disk dump) is your friend (and worst nightmare if you don't crosscheck what you do).

Always double check if you write to (or read from) the correct block device! Sometimes the letters change.

make backup:

`dd if=/dev/sda bs=4M of=./image-of-sda.img`

`dd if=/dev/sda bs=4M | pv -s 1T | dd of=./image-of-sda.img bs=4M`	# with progress, -s 1T = one terrabyte

restore a backup: (be sure what you do and double check!)

`dd if=./image-of-sda.img bs=4M of=/dev/sda`

`dd if=./image-of-sda.img bs=4M | pv -s 1T | dd of=/dev/sda bs=4M`	# with progress

[external](http://www.adick.at/2012/02/11/festplatten-klonen-mit-dd/)

`with killall -USR1 dd`

dd will output the current status. The output looks like:

53+0 records in
53+0 records out
222298112 bytes (222 MB) copied, 52.1263 s, 4.3 MB/s

but you can also use `dd if=XXX bs=4M | pv -s 1666M | dd of=YYY bs=4M`

pv will show the status and progressbar

[back](./)


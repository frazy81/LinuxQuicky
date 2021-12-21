Delete a Drive
==============

to randomly overwrite a drive

`dd if=/dev/urandom bs=4M | pv -s 1T | dd of=/dev/device bs=4M`

Note: urandom! not random (random is real entropy and slow, urandom is pseudo-random and fast)

[back](./)


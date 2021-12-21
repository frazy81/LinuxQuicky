Encrypted Harddrive
===================

When using encrypted harddrive: make a non-encrypted boot partition (>150MB), then make an encrypted partition (as crypt). Enable it later (after initialization) as an LVM partition. Then create a root and a swap partition in LVM. This way you only  need to type in the password once for both root and swap. And you can still use Hybernation. Without having LVM, you can't use a keyfile to decrypt the swap because the swap will need to be loaded before root, because of hybernation.

make it -s 512. 512 bits key! not 256. Use sha256 instead of sha1.

`dd if=/dev/random of=/root/homedrive_luks.key bs=1 count=256`	# make a key for encrypted home drive

`cryptsetup luksAddKey /dev/sda1 /root/homedrive_luks.key`	# add key file for /home on /dev/sda1

`cryptsetup luksDump /dev/sda1`

`cryptsetup luksChangeKey /dev/sda1 -S 0`	# change key 0 passphrase to the complex stored one), -S is Slot (0-7)

`cryptsetup luksAddKey /dev/<homedrive>`	# add the complex stored key

modify /etc/crypttab:

	sda1_crypt UUID=xyz /root/homedrive_luks.key luks

so that "none" get's exchanged to the keyfile /root/homedrive_luks.key

reboot & try
now /home will only be accessible by the complex key and the keyfile /root/homedrive_luks.key
/ will be accessible with the password defined.

[back](./)


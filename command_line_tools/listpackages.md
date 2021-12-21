List installed packages
=======================

# from https://linuxize.com/post/how-to-list-installed-packages-on-ubuntu/
apt list --installed
sudo dpkg-query -l
sudo dpkg-query -f '${binary:Package}\n' -W > packages_list.txt
	# install the very same packages on an other server:
	sudo xargs -a ./packages_list.txt apt install
# count packages installed:
sudo dpkg-query -f '${binary:Package}\n' -W | wc -l

[back](./)


Command line tools
==================

* [rsync](rsync.md)
* [find test](text.md)
* xxd - show file in hexadecimals
* [list installed packages](listpackages.md)
* screen -d -m -S <name> -h 8192 <command>

System information
------------------

lscpu
lsmod
lshw
lspci
modinfo
rpcinfo -p | grep nfs		# which ports for nfs?
uname -a
lsb_release -a		# which linux version

System performance
------------------

strace, trace a program and see file IO/network IO
vmstat -S M (megabytes)
mpstat -P all 1
iostat
top

System temperatures
-------------------

apt install lm-sensors
sudo sensors-detect		# YES to all

watch -n 0.05 sensors

Audio
-----

* audacity

Screenshots
-----------

* screengrab

[back](../)


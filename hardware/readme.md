Hardware
========

How to list installed hardware?
-------------------------------

* `inxi -Fx`
* `cat /proc/cpuinfo` or `lscpu`
* `cat /proc/meminfo`
* `hwinfo --short`
* `lshw -short`
* `lshw`
* `lsblk`
* `lspci` or concretely for graphics card: `lspci -v | grep "VGA" -A 15ls`
* `dmidecode -t processor`
  * -t:
    * bios
    * processor
    * memory
    * system
    * baseboard
    * chassis
    * cache
    * connector
    * slot
* `lsusb` - list USB
* `hdparm -i /dev/sdb`

[back](../)


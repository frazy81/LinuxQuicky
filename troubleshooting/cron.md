Cron
====

often not the same environment variables (especially default path to lookup programs). Therefore you may need to use the full path.

How to find the full path of a program? - `which <program>`

For a program that should start after *reboot*, you may want to include a delay `/bin/sleep 30` for some ressources to come up (eg. networking, NFS).

[back](./)


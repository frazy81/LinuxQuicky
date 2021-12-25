Troubleshooting
===============

 * normally it's your mistake! Take a step back and think it over.
 * normally it's easy to fix!
 
The problem is normally somewhere between chair and keyboard.
 
See logs
--------

they are all located in `/var/log`.

useful:

`tail -n 1000 /var/log/syslog`	# see the last 1000 lines of the syslog file

See logs change
---------------

`watch tail -n 100 /var/log/syslog`

or

`watch -n 0.1 tail -n 100 /var/log/syslog`

to check for changes every 0.1s.

Cancel/Abort with Ctrl-C
 
My typicals
-----------

* [cron](cron.md)
* [webserver](webserver.md)

[back](../)


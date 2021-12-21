ufw - Uncomplicated Firewall
============================

Install
-------

`apt install ufw`	# install the uncomplicated firewall

Work with ufw
-------------


Enabling the firewall:
`ufw enable`			# or `ufw disable` to disable it

this defaults to: allow all outgoing traffic, block all incoming traffic and deny routing.

Enable incoming 80:

`ufw allow HTTP`

Enable incoming 734, from Class-C network on 192.168.192.0/8:

`ufw allow proto tcp from 192.168.192.0/8 to any port 734`

IMPORTANT is the order! If for example you allow to port 80 and later deactivate an IP completely,
this has now effect! Since you allowed to port 80 before, so the IP is not deactivated! If you
completely want to disallow an IP, you need to do that in `/etc/ufw/before.rules`.

LOGGING
-------

rsyslogd logs ufw in /var/log/ufw.log* by /etc/rsyslog.d/20-ufw.conf

if console spitts out lots of messages: turn off logging by

`ufw logging off`

reenable with

`ufw logging low`		# default

there's no way around it, as dmesg prints the whole Kernel Ring Buffer and messages are intercepted
by rsyslog and put into the log. So: either you want logging, or not. No way to just put them into
log-files but keep the console clean. To me such a feature would be appreciated.

[back](./)


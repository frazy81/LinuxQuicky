Periodic Tasks
==============

cronjobs
--------

tasks that get executed depending on a specific time. Often implemented is: Vixie Cron (see `man cron`).

define and edit tasks using

```bash
crontab -e
```

there may be a specific crontab file *for each user*, the above command brings up the file for the current active user.

see:

/var/spool/cron/crontabs/<user>         # cronjob files

```bash
man crontab
man 5 crontab
```

*important*
the crontab PATH is usually not the same as if you're in a console! Either include PATH into the crontab file OR add them explicitely in crontabs, such as:

```bash
@reboot           /bin/sleep 30
20 6 15 3 1-5     /bin/sleep 25 && <command>
```

which will execute a 25s sleep and a command at:

06:20 at the 15th March Monday to Friday.

anacron
-------

another cronjob that executes tasks after a period of time (such as every hour). Useful for systems that do not operate 24/7.

see:

```bash
/etc/anacrontab
man 8 anacron
systemctl status anacron
```

[back](../)

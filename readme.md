LinuxQuicky
===========

contents
--------

* [about](about/)
* [boot process](boot/)
* [drives](drives/)
* [filesystems](filesystems/)
* [editors](editors/)
* [console](console/)
* [command line tools](command_line_tools/)
* [networking](networking/)
* [ssh](ssh/)
* [monitoring](monitoring/)
* [user and group management](usergroupmanagement/)
* [troubleshooting](troubleshooting/)
* [periodic tasks](periodictasks/)
* [some hacks assorti](some_hacks_assorti/)
* [further software details](others/)
* [links](links/)

how to use
----------

These .md markdown scripts can be converted to html with for example grib (https://github.com/joeyespo/grip/). Checkout out the script at https://gist.github.com/frazy81/52a0111919002df080092a9e34e33861 to automatically convert all files (including sub-directories) to html.

```bash
git clone https://gist.github.com/52a0111919002df080092a9e34e33861.git
cd 52a0111919002df080092a9e34e33861
./create_docs.py -d /path/to/LinuxQuicky -riHeb

# or

# use grip directly (as webserver):

grip -b

```


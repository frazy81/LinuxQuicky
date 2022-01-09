User and Group Management
=========================

`groupadd <groupname>`			# add a new group

`useradd <username> -g <groupname> -d /home/<username> -m`

	# adds a new user to group <groupname> with home-directory /home/<username>
	# -m: create home dir
	
`passwd username`

	# change the password for user `username
	
Permissions
-----------

`ls test*`

-rwxr-xr-x  1 default users       259 Mar 27  2019  test

drwxr-xr-x  5 default users      4096 Oct 15 15:35  testdir

permissions, # of hard links to file, user, group, filesize, date&time, name

-rwxr-xr-x

first character is '-': normal file, if 'd': directory. After that:

user, group and everyone permissions as (rwx: read, write, execute).

Change permissions
------------------

`chmod +x test`		# make executable by user

`chmod u+x test`	# make executable by user (same as above)

`chmod g+x test`	# make executable by group

`chmod g-x test`	# make Non-executable by group

`chmod 0644 test`	# make test: "rw-r--r--"

`chmod 0755 test`	# make test: "rwxr-xr-x"
	
[back](../)


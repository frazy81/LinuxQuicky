SSH
===

Secure Shell. Via ssh you can access to a shell on a remote server (if sshd - the SSH daemon is running there).

create new "credentials", an RSA keys:

RSA 2048 (-t rsa, which is RSA2) is recommended (and the standard) and still sufficient. 1024 is not good enough! (source: man ssh-keygen). Use -b 4096 to increase bit size to 4096.

SSH Keys:

`ssh-keygen -t rsa -b 4096`		# create 4096 bit long ssh key
`ssh-add`				# add keys to authentication agend (or restart /etc/init.d/ssh restart)
`ssh-copy-id user@192.168.1.XXX`	# copies id_rsa.pub of current computer to the other, so that this computer can connect to the other specified

[back](../)


rsync
=====

rsync -avt --delete /home/user /backup/

rsync -arvh --progress source destination	# one file
rsync -arvh --info=progress2 source destination	# many files
rsync -arvh --info=progress2 --delete --exclude-from=backup_home_exclude . /backup_home/

Using rsync to create backups: http://www.mikerubel.org/computers/rsync_snapshots/, https://www.ostechnix.com/backup-entire-linux-system-using-rsync/

remember: wild cards (*) are expanded by the shell. This means rsync will be in 'file' mode and --delete won't work because of that. If --delete shall work, don't use wild cards...

REMARK with using rsync on WD Cloud:
 - timestamps are not safed, therefore files will always be copied (even if not changed), so we need the -c (checksum based) to actually detect changes and copy over if changed.

[back](./)


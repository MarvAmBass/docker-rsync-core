# docker-rsync-core
rsync 3.1.2 - freshly complied from official stable releases on ubuntu 16.04

# Source Code
Check the following link for a new version: https://www.samba.org/ftp/rsync/src/

# Example Config

    # sample rsyncd.conf configuration file

    # GLOBAL OPTIONS

    #motd file=/etc/motd
    log file=/var/log/rsyncd
    # for pid file, do not use /var/run/rsync.pid if
    # you are going to run rsync out of the init.d script.
    # The init.d script does its own pid file handling,
    # so omit the "pid file" line completely in that case.
    # pid file=/var/run/rsyncd.pid
    #syslog facility=daemon
    #socket options=

    # MODULE OPTIONS

    #[ftp]
    #	comment = public archive
    #	path = /var/www/pub
    #	use chroot = yes
    #	max connections=10
    #	lock file = /var/lock/rsyncd
    # the default for read only is yes...
    #	read only = yes
    #	list = yes
    #	uid = nobody
    #	gid = nogroup
    #	exclude = 
    #	exclude from = 
    #	include =
    #	include from =
    #	auth users = 
    #	secrets file = /etc/rsyncd.secrets
    #	strict modes = yes
    #	hosts allow =
    #	hosts deny =
    #	ignore errors = no
    #	ignore nonreadable = yes
    #	transfer logging = no
    #	log format = %t: host %h (%a) %o %f (%l bytes). Total %b bytes.
    #	timeout = 600
    #	refuse options = checksum dry-run
    #	dont compress = *.gz *.tgz *.zip *.z *.rpm *.deb *.iso *.bz2 *.tbz

    [flac]
      comment = music - flac files
      path = /mnt/flac
      use chroot = yes
      lock file = /var/lock/rsyncd
      read only = yes
      list = yes
      uid = nobody
      gid = nogroup
      strict modes = yes
      ignore errors = no
      ignore nonreadable = yes
      transfer logging = no
      timeout = 600
      refuse options = checksum dry-run
      dont compress = *.gz *.tgz *.zip *.z *.rpm *.deb *.iso *.bz2 *.tbz

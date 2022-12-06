## Adding option x-systemd.automount to FSTAB


* Having trouble getting my cifs to mount on reboots . Added x-systemd.automount
as an option in fstab. Waht it does is doesn't mount it right away but only when
you access it. For example cd to /mnt/whatver.

* Here is an example entry in fstab

`//192.168.1.100/data	/mnt/data	cifs	uid=0,credentials=/home/dude/.smb,
iocharset=utf8,x-systemd.automount	0	2`


    #zettle #fstab #systemd #linux

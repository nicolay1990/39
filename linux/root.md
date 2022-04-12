```
# rw init=/sysroot/bin/sh

chroot /sysroot
passwd root
touch /.autorelabel
exit
reboot
```
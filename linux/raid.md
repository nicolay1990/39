```
apt-get install mdadm
mdadm --zero-superblock /dev/sda /dev/sdc
mdadm --create /dev/md0 --level=1 --raid-devices=2 /dev/sda1 /dev/sdc1

mkfs.ext4 /dev/md0

#/etc/fstab
/dev/md0 /home ext4 noatime,rw 0 0

#config
mdadm --detail --scan /dev/md0 >> /etc/mdadm/mdadm.conf

update-initramfs -u
```
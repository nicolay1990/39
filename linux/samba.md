```
[global]
   interfaces = enp0s3
#   passdb backend = tdbsam
   log file = /var/log/samba/log.%m
   max log size = 1000
   logging = file
   panic action = /usr/share/samba/panic-action %d
   workgroup = WORKGROUP
[smb_share]
path = /mnt/storage
read only = no
security = share
public = yes
guest ok = yes
browsable = yes
writable = yes
create mask = 666
directory mask = 777


#smb.conf
[global]
workgroup = WORKGROUP
security = user
map to guest = bad user
wins support = no
dns proxy = no

[public]
path = /samba/public
guest ok = yes
force user = nobody
browsable = yes
writable = yes

[private]
path = /samba/private
valid users = @smbgrp
guest ok = no
browsable = yes
writable = yes
```

```
#fstab
//server/share /pathto/mountpoint cifs credentials=/home/username/.smbcredentials 0 0
```

```
#.smbcredentials
username=shareuser
password=sharepassword
domain=domain_or_workgroupname
```
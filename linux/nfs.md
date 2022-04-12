```
#server
apt install nfs-kernel-server nfs-common portmap
#/etc/exports
/mnt 192.168.0.0/24(ro, fsid=0, async, no_subtree_check)
/mnt/movie 192.168.0.0/24(rw, async, no_subtree_check)
/mnt/user 192.168.0.41(rw, async, no_subtree_check)


#client
apt install nfs-common portmap
mount -t nfs 192.168.0.2:/mnt/movie /home/movie

#/etc/fstab
192.168.0.2:/mnt/movie /home/movie nfs rw,async
```
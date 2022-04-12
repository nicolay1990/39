```
#dd if=/dev/zero of=/storage/lun0.img bs=1M count=2048
#tgtadm --mode target --op show
```

\#/etc/tgt/conf.d/example.conf

```
<target iqn.2009-02.lab.interface31:debian-test-target> 
backing-store /storage/lunO.img 
initiator-address 192.168.111.150
#incominguser user secretpass12
</target>
```
```
#/etc/ufw/sysctl.conf net.ipv4.ip_forward = 1
#/etc/default/ufw DEFAULT_FORWARD_POLICY="ACCEPT"
#/etc/ufw/before.rules #NAT table rules *nat :POSTROUTING ACCEPT [0:0]
-A POSTROUTING -s 10.8.0.0/16 -o eth0 -j MASQUERADE
COMMIT
```
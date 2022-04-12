```
set interfaces ethernet eth0 vrrp vrrp-group 2 advertise-interval '1'
set interfaces ethernet eth0 vrrp vrrp-group 2 preempt 'true'
set interfaces ethernet eth0 vrrp vrrp-group 2 priority '100'
set interfaces ethernet eth0 vrrp vrrp-group 2 sync-group 'PublicSync'
set interfaces ethernet eth0 vrrp vrrp-group 2 virtual-address '172.16.1.20'

set interfaces ethernet eth1 vrrp vrrp-group 3 advertise-interval '1'
set interfaces ethernet eth1 vrrp vrrp-group 3 preempt 'true'
set interfaces ethernet eth1 vrrp vrrp-group 3 priority '100'
set interfaces ethernet eth1 vrrp vrrp-group 3 virtual-address '192.168.5.20/24'
set interfaces ethernet eth1 vrrp vrrp-group 3 sync-group 'LanSync'
```
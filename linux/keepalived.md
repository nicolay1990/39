```
#keepalived.conf
vrrp_instance vrrp0 {
	state <MASTER|BACKUP>
	virtual_router_id 1
	priority <1-254>
	virtual_ipaddress {
		x.x.x.x/x
	}
}
```
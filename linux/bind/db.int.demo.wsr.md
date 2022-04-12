```
$TTL	86400
@	IN	SOA	int.demo.wsr. int.demo.wsr (
			      1		; Serial
			 604800		; Refresh
			  86400		; Retry
			2419200		; Expire
			  86400 )	; Negative Cache TTL
;
@	IN	NS	ns.int.demo.wsr.
ns	IN	A	4.4.4.100
	
web-l	IN	A	192.168.100.100
web-r	IN	A	172.16.100.100
srv	IN	A	192.168.100.200
rtr-l	IN	A	192.168.100.254
rtr-r	IN	A	172.16.100.254
;webapp	IN	CNAME	web-l
webapp	IN	CNAME	web-r
ntp	IN	CNAME	srv
dns	IN	CNAME	srv
```
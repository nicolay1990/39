```
$TTL 38400
$ORIGIN demo.wsr.
@	IN	SOA	ns.demo.wsr.	demo.wsr. (1 604800 86400 2419200 604800)

@	IN	NS	ns.demo.wsr.
ns	IN	A	3.3.3.1
ns	IN	A	4.4.4.1
ns	IN	A	5.5.5.1	


isp	IN	A	3.3.3.1
www	IN	A	4.4.4.100
www	IN	A	5.5.5.100

internet	IN	CNAME	isp

; int.demo.wsr

$ORIGIN int.demo.wsr.
@	IN	NS	ns.int.demo.wsr.
	IN	NS 	ns.demo.wsr.
ns.int.demo.wsr.	IN	A	4.4.4.100
```
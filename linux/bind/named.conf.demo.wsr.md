```
zone "demo.wsr" {
	type master;
	file "/etc/bind/db.demo.wsr";
//	allow-transfer { any; };
	forwarders { };
};

//zone "int.demo.wsr" {
//	type master;
//	file "/etc/bind/db.int.demo.wsr";
//	masters {4.4.4.100;};
//};
//zone "0.in-addr.arpa" {
//	file "/etc/bind/db.0";
//};
```
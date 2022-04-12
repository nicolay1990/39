```
# ipser.conf
conn "ipsec"
	auto=start
	type=tunnel
	authby=secret
	ike=3des-sha1;dh14
	esp=aes-sha2
	left=<local>
	right=<remote>
	leftprotoport=gre
	rightprotoport=gre
	pfs=no
# ipsec.secret
<localaddr> <remoteaddr> : PSK "<key>"
```
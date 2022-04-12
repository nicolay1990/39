```
network:
    ethernets:
        ens3:
            dhcp4: false
            dhcp6: false
            accept-ra: false
            match:
                macaddress: xx:xx:xx:xx:xx:xx
            set-name: ens3
            addresses:
                - 10.0.0.233/24
                - ::/128
            gateway4: 10.0.0.1
            gateway6: fe80::2c5b:30d1:1e14:f5ed 
            nameservers:
                addresses:
                        - 8.8.8.8
                        - 8.8.4.4
                        - 2001:4860:4860::8888
	                - 2001:4860:4860::8844
#            routes:
#                    - to: default
#                      via: 10.0.0.1
#                    - to: ::/0
#                      via: "fe80::200:17ff:fe5a:2487"                        
    version: 2
```
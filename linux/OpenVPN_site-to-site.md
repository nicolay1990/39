```
openvpn --genkey --secert /etc/openvpn/server.key

# /etc/openvpn/server.conf
local 4.4.4.100
remote 5.5.5.100
float
port 1194
dev tun
ifconfig 10.0.0.1 10.0.0.2
persist-tun
cipher AES-256-CBC
persist-local-ip
#persist-remote-ip
ping 15
secter /etc/openvpn/server/server.key
route 172.16.100.0 255.255.255.0
log /var/log/tunnel.log
verb 3
```
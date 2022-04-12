```
#yum install xinetd tftp-server tftp vim
#vim /etc/xinetd.d/tftp

service tftp { socket_type = dgram protocol = udp wait = yes user = root server = /usr/sbin/in.tftpd server_args = -v -s /var/lib/tftpboot disable = no per_source = 11 cps = 100 2 flags = IPv4 }

#sudo systemctl start xinetd sudo systemctl enable xinetd sudo firewall-cmd --permanent --zone=public --add-service=tftp && sudo firewall-cmd --reload

###test### echo passed > ~/test.txt sudo mv ~/test.txt /var/lib/tftpboot tftp 127.0.0.1 -c get test.txt cat test.txt
```
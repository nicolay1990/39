```
ufw allow from any to 169.254.0.2/32 port 3260 proto tcp
ufw allow from any to 169.254.0.2/32 port 80 proto tcp
ufw allow from any to 169.254.2.0/24 port 3260 proto tcp
ufw allow from any to 169.254.4.0/24 port 3260 proto tcp
ufw allow from any to 169.254.5.0/24 port 3260 proto tcp
ufw allow from any to 169.254.169.254/32 port 53 proto tcp
ufw allow from any to 169.254.169.254/32 port 53 proto udp
ufw allow from any to 169.254.169.254/32 port 80 proto tcp
ufw allow from any to 169.254.0.3/32 port 80 proto tcp
ufw allow from any to 169.254.0.4/32 port 80 proto tcp
ufw allow from any to 169.254.169.254/32 port 67 proto udp
ufw allow from any to 169.254.169.254/32 port 69 proto udp
ufw allow from any to 169.254.169.254/32 port 123 proto udp
```
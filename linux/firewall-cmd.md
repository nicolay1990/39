```
firewall-cmd --permanent --zone=internal --add-forward
firewall-cmd --zone=public --add-forward-port=port=6666:proto=tcp:toport=22:toaddr=IP --permanent
```
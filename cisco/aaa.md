```
aaa new-model

radius server <name> address ipv4 <ipaddr> auth-port 1812 acct-port 1813 key <key> exit

aaa authentification login default group radius local

aaa authorization exec default group radius local
```
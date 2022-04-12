int f0/0

```
  ip add 10.10.10.1 255.255.255.0
  no sh
```

int f1/0

```
 ip add 100.100.100.1 255.255.255.252
 no sh
```

int f1/1

```
ip add 200.200.200.1 255.255.255.252
no sh
```

ip access-list standard ACL-DNAT

```
 permit 10.10.10.0 0.0.0.255
```

route-map RM-NAT-ISP01 10

```
match ip add ACL-DNAT
match int f1/0
```

route-map RM-NAT-ISP02 10

```
match ip add ACL-DNAT
match int f1/1
```

int f0/0

```
ip nat inside
```

int f1/0

```
ip nat outside
```

int f1/1

```
ip nat outside

ip nat inside source route-map RM-NAT-ISP01 int f1/0 overload

ip nat inside source route-map RM-NAT-ISP02 int f1/1 overload
ip sla 20
 icmp-echo 100.100.100.2 source-interface f1/0
 timeout 1000
 frequency 10
ip sla schedule 20 life forever start-time now
track 1 rtr 20 reachability
ip route 0.0.0.0 0.0.0.0 100.100.100.2 track 1
ip route 0.0.0.0 0.0.0.0 200.200.200.2 2
```

# 

# 
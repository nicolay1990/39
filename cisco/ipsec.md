```
sakmp policy 10 encryption 3des hash sha authe pre-share group 2
crypto isakmp key <key> address <remote address>

crypto ipsec transform-set <TSET> esp-3des esp-sha-hmac

ip access-list ex IPsec permit ip <private-local-subnet> <private-remote-subnet>

crypto map <IPsec> 10 ipsec-isakmp set peer <remote-address> set transform-set <TSET> match address IPsec

interface <Outgoing-interface> crypto map <IPsec>
```
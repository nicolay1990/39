```
crypto ikev1 enable OUTSIDE crypto isakmp identity address tunnel-group 10.10.10.2 type ipsec-l2l

tunnel-group 10.10.10.2 ipsec-attributes ikev1 pre-shared-key MY_SHARED_KEY

crypto ikev1 policy 10

authentication pre-share encryption aes hash sha group 2 lifetime 3600

access-list LAN1_LAN2 extended permit ip 192.168.1.0 255.255.255.0 192.168.2.0 255.255.255.0

crypto ipsec ikev1 transform-set MY_TRANSFORM_SET esp-aes-256 esp-sha-hmac

crypto map MY_CRYPTO_MAP 10 match address LAN1_LAN2 crypto map MY_CRYPTO_MAP 10 set peer 10.10.10.2 crypto map MY_CRYPTO_MAP 10 set ikev1 transform-set MY_TRANSFORM_SET crypto map MY_CRYPTO_MAP 10 set security-association lifetime seconds 3600 crypto map MY_CRYPTO_MAP interface OUTSIDE
```
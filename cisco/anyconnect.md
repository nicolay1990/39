\#Self-Signed Certificate

Configure a trustpoint for the self-signed certificate, and apply this RSA Keypair:

```
crypto pki trustpoint anyconnectvpn enrollment selfsigned subject-name CN=108.1.220.132 revocation-check none rsakeypair anyconnect
```

Once the trustpoint is configured, enroll the self-signed certificate

```
crypto pki enroll anyconnectvpn 
```

% Include the router serial number in the subject name? [yes/no]: no

% Include an IP address in the subject name? [no]: no

Generate Self Signed Router Certificate? [yes/no]: yes

Router Self Signed Certificate successfully created

```
#Client image crypto vpn anyconnect flash:/anyconnect-win-3.1.05160-k9.pkg sequence 1
```

\#Users

```
aaa new-model aaa authentication login sslvpn local aaa authorization network sslvpn local username Anyconnect password Anyconnect123
```

```
#VPN pool ip local pool SSL_Client 192.168.10.1 192.168.100.20
```

```
#Ciphers 

crypto ssl proposal sslvpn-proposal protection rsa-3des-ede-sha1 rsa-rc4128-md5 rsa-aes128-sha1 rsa-aes256-sha1
```

```
#Route 
ip access-list standard sslvpn-tunnel permit 10.0.0.0 0.255.255.255
```

\#SSL Policy

```
crypto ssl policy sslvpn-policy ssl proposal ssl_proposal pki trustpoint anyconnectvpn sign ip address local 108.1.220.132 port 443 no shut
```

\#SSL Authorization Policy

```
crypto ssl authorization policy sslvpn-auth-policy pool SSL_Client dns 10.0.0.120 def-domain cisco.comroute set access-list sslvpn-tunnel
```

\#SSL Profile

```
crypto ssl profile sslvpn-profile match policy sslvpn-policy aaa authentication user-pass list sslvpn aaa authorization group user-pass list sslvpn sslvpn-auth-policy authentication remote user-pass max-users 100
```
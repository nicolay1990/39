```
auth_param basic program /usr/lib/squid/basic_ncsa_auth /etc/squid/htpasswd
acl auth_users  proxy_auth REQUIRED
http_access allow auth_users

http_access deny all

http_port 8080

cache_dir ufs /var/spool/squid 100 16 256
coredump_dir /var/spool/squid

refresh_pattern ^ftp:           1440    20%     10080
refresh_pattern ^gopher:        1440    0%      1440
refresh_pattern -i (/cgi-bin/|\?) 0     0%      0
refresh_pattern .               0       20%     4320
cache_effective_user proxy
cache_effective_group proxy
check_hostnames off
visible_hostname localhost
httpd_suppress_version_string on
connect_timeout 60 second
access_log none
cache_store_log none
```
```
apt-get install freeradius freeradius-ldap

# /etc/freeradius/3.0/sites-available/default

#    Auth-Type LDAP {
#        ldap
#     }

# /etc/freeradius/3.0/mods-available/ldap

server = 'ldap.home.clintonmetu.com'
identity = 'cn=admin,dc=home,dc=clintonmetu,dc=com'
password = <admin_password>
base_dn = 'dc=home,dc=clintonmetu,dc=com'

ln -s /etc/freeradius/3.0/mods-available/ldap /etc/freeradius/3.0/mods-enabled/ldap


systemctl restart freeradius


radtest <ldap user> <pass> 127.0.0.1 1 testing123

# /etc/freeradius/3.0/sites-available/default
```
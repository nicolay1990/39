```
dnf config-manager --set-enabled powertools
yum install -y openldap openldap-clients openldap-servers
apt-get install slapd ldap-utils
dpkg-reconfigure slapd - - +

olcRootDN: cn=ramesh,dc=thegeekstuff,dc=com
# slappasswd

# vi /etc/openldap/slapd.d/cn=config/olcDatabase={2}bdb.ldif
olcSuffix: dc=thegeekstuff,dc=com

# slaptest -u

ldapsearch -x -LLL -b dc=home,dc=clintonmetu,dc=com

#newuser.ldif
dn: ou=Groups,dc=home,dc=clintonmetu,dc=com
ou: Groups
objectClass: organizationalUnit
objectClass: top

dn: ou=People,dc=home,dc=clintonmetu,dc=com
objectClass: organizationalUnit
ou: People

dn: cn=net-device-users,ou=Groups,dc=home,dc=clintonmetu,dc=com
gidNumber: 500
objectClass: posixGroup
objectClass: top
memberUid: clint
cn: net-device-users

dn: uid=clint,ou=People,dc=home,dc=clintonmetu,dc=com
objectClass: inetOrgPerson
objectClass: posixAccount
objectClass: shadowAccount
uid: clint
sn: Metu
givenName: Clinton
cn: Clinton Metu
displayName: Clinton Metu
uidNumber: 10000
gidNumber: 10000
gecos: Clinton Metu
loginShell: /bin/bash
homeDirectory: /home/clinton
userPassword: clinton123

ldapadd -x -W -D cn=admin,dc=home,dc=clintonmetu,dc=com -f newuser.ldif

#disable_anon_bind.ldif

dn: cn=config
changetype: modify
add: olcDisallows
olcDisallows: bind_anon

dn: cn=config
changetype: modify
add: olcRequires
olcRequires: authc

dn: olcDatabase={-1}frontend,cn=config
changetype: modify
add: olcRequires
olcRequires: authc

ldapmodify -H ldapi:/// -Y EXTERNAL -f disable_anon_bind.ldif
```
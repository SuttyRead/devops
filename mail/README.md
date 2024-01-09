#!/bin/bash
# Зупинка всіх Docker контейнерів
docker stop $(docker ps -aq)

#!/bin/bash
# Видалення всіх Docker контейнерів
docker rm $(docker ps -aq)

#!/bin/bash
# Видалення всіх Docker об'ємів (volumes)
docker volume rm $(docker volume ls -q)

docker exec -ti mailserver setup email add sutty1@sutty.shop

docker exec -it mailserver /bin/bash

listmailuser


ldapsearch -x -H ldap://authentik.sutty.shop -D 'cn=sutty1,ou=users,DC=ldap,DC=goauthentik,DC=io' -w 'sutty1sutty1' -b 'DC=ldap,DC=goauthentik,DC=io' 

ldapsearch -x -H ldap://authentik.sutty.shop -D 'cn=ldapservice,ou=users,DC=ldap,DC=goauthentik,DC=io' -w 'ldapservice' -b 'DC=ldap,DC=goauthentik,DC=io' '(objectClass=group)'
ldapsearch -x -H ldap://authentik.sutty.shop -D 'cn=ldapservice,ou=users,DC=ldap,DC=goauthentik,DC=io' -w 'ldapservice' -b 'DC=ldap,DC=goauthentik,DC=io' '(objectClass=alias)'


ldapsearch -x -H ldap://authentik.sutty.shop -D 'cn=ldapservice,ou=users,DC=ldap,DC=goauthentik,DC=io' -w 'ldapservice' -b 'DC=ldap,DC=goauthentik,DC=io' '(objectClass=organizationalPerson)'

ldapsearch -x -H ldap://authentik.sutty.shop -D 'cn=ldapservice,ou=users,DC=ldap,DC=goauthentik,DC=io' -w 'ldapservice' -b 'DC=ldap,DC=goauthentik,DC=io' '(&(objectClass=user)(mail=sutty30@sutty.shop))'


ldapsearch -x -H ldap://authentik.sutty.shop -D 'cn=akadmin,ou=users,DC=ldap,DC=goauthentik,DC=io' -w 'Komfort@1a' -b 'DC=ldap,DC=goauthentik,DC=io'
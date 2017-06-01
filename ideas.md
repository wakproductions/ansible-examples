# Run Security Updates

https://www.digitalocean.com/community/questions/updating-ubuntu-14-04-security-updates

https://askubuntu.com/questions/578761/how-to-only-install-security-updates

https://tecadmin.net/install-security-updates-ubuntu-debian/

# Setup postgres

https://www.postgresql.org/message-id/4D958A35.8030501@hogranch.com

````
 $ sudo -u postgres psql

     postgres=> alter user postgres password 'apassword';
     postgres=> create user yerusername createdb createuser password 
'somepass';
     postgres=> create database yerusername owner yerusername;
     postgres=> \q

     $ ...
```


https://stackoverflow.com/questions/18664074/getting-error-peer-authentication-failed-for-user-postgres-when-trying-to-ge
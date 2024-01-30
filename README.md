# CYBORG

### IP: 10.10.165.148

### PORTS
- 80
- 22

### 80
- /admin, /etc
- /admin : music-archive-tar
- /etc/squid/: passwd, squid.conf
- passwd: `music_archive:$apr1$BpZ.Q.1m$F0qqPwHSOG50URuOVQTTn.`
- squid.conf
```
auth_param basic program /usr/lib64/squid/basic_ncsa_auth /etc/squid/passwd
auth_param basic children 5
auth_param basic realm Squid Basic Authentication
auth_param basic credentialsttl 2 hours
acl auth_users proxy_auth REQUIRED
http_access allow auth_users

```
### JOHN
- password: squidward

### music archive
- used borg to mount the archive
- found password for alex
- pass: S3cretP@s3
- found user.txt

### LINPEAS
- found backup.sh cronjob per minute
- backup has -c "command" setup
- ran chmod +s /bin/bash
- got root access with sudo -p
- found /root/root.txt


# mailx-centos
Configuration for sending mail using mailx in CentOS

**2 ways:** (1) Set environment in global-config(*mail.rc*) file, or (2) Set inline environment 

### (1) Copy and paste the snippet in mailx config file 
> location: ***/etc/mail.rc***

```
set smtp-use-starttls
set smtp=smtp://smtp.gmail.com:587
set smtp-auth=login
set smtp-auth-user='AUTH_USER_MAIL'
set smtp-auth-password='AUTH_USER_PASSWORD'
set ssl-verify=ignore
set nss-config-dir=/etc/pki/nssdb/
```

### To send mail:

```
cat -v /file/path/ | mail -v -s 'Mail-Subject' -a /attached/file/path/ example@example.com
```

---
### (2) To send inline mail:

```
cat -v /file/path/ | mail -v -S smtp-use-starttls -S ssl-verify=ignore -S smtp-auth=login -S smtp=smtp://smtp.gmail.com:587 -S nss-config-dir=/etc/pki/nssdb/ -S smtp-auth-user='AUTH_USER_MAIL' -S smtp-auth-password='AUTH_USER_PASSWORD' -s 'Mail-Subject' -a /attached/file/path/ example@example.com
```

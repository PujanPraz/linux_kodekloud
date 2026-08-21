```
To accommodate the backup agent tool's specifications, the system admin team at `xFusionCorp Industries` requires the creation of a user with a non-interactive shell. Here's your task:  
  
Create a user named `rose` with a non-interactive shell on `App Server 3`.
```

thor@jump-host ~$ ssh banner@stapp03

[banner@stapp03 ~]$ sudo useradd rose -s /sbin/nologin 

[banner@stapp03 ~]$ tail /etc/passwd
rose:x:1001:1001::/home/rose:/sbin/nologin
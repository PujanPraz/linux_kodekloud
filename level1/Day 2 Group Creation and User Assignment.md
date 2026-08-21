```
Task:

The system admin team at `xFusionCorp Industries` has streamlined access management by implementing group-based access control. Here's what you need to do:  
  
a. Create a group named `nautilus_admin_users` across all App servers within the `Stratos Datacenter`.  
  
b. Add the user `jarod` into the `nautilus_admin_users` group on all App servers. If the user doesn't exist, create it as well.
```

solution:

-> First, ssh to the app server 1
```
thor@jump-host ~$ ssh tony@stapp01
```

it will ask for password, then create a group nautilus_admin_users
```
[tony@stapp01 ~]$ sudo groupadd nautilus_admin_users
```

After successfully creating group verify it
```
[tony@stapp01 ~]$ tail /etc/group
nautilus_admin_users:x:1001:
```

Then, create a user named jarod and add it to supplementary group nautilus_admin_users group
```
[tony@stapp01 ~]$ sudo useradd jarod -G nautilus_admin_users
```

Again, verfiy it
```
[tony@stapp01 ~]$ id jarod
uid=1001(jarod) gid=1002(jarod) groups=1002(jarod),1001(nautilus_admin_users)
```

do the same for other app servers.

```
Task:

In response to heightened security concerns, the `xFusionCorp Industries` security team has opted for custom Apache users for their web applications. Each user is tailored specifically for an application, enhancing security measures. Your task is to create a custom Apache user according to the outlined specifications:  

a. Create a user named `javed` on `App server 2` within the Stratos Datacenter.  
  
b. Assign a unique UID `1623` and designate the home directory as `/var/www/javed`.
```

solution:
-> Firstly, ssh to the app server 2 as below.
```
thor@jump-host ~$ ssh steve@stapp02
```

Then, create the user named javed with user id 1623 with home directory /var/www/javed. Don't forget to verify it. Additionally, you can also check the passwd file if you want to verfiy the home directory too.

```
[steve@stapp02 ~]$ sudo useradd javed -u 1623 -d /var/www/javed
[steve@stapp02 ~]$ id javed
uid=1623(javed) gid=1623(javed) groups=1623(javed)
```

```
Task:

Following a security audit, the xFusionCorp Industries security team has opted to enhance application and server security with SELinux. To initiate testing, the following requirements have been established for `App server 3` in the `Stratos Datacenter:`  
  
1. Install the required `SELinux` packages.
    
2. Permanently disable SELinux for the time being; it will be re-enabled after necessary configuration changes.
    
3. No need to reboot the server, as a scheduled maintenance reboot is already planned for tonight.
    
4. Disregard the current status of SELinux via the command line; the final status after the reboot should be `disabled`.
```

solutions:
thor@jump-host ~$ ssh banner@stapp03

[banner@stapp03 ~]$ sudo yum install -y selinux-policy selinux-policy-targeted

[banner@stapp03 ~]$ vim /etc/selinux/config 
SELINUX=disable
[banner@stapp03 ~]$ getenforce
Disabled

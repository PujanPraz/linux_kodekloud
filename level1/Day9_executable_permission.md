### Task:
In a bid to automate backup processes, the xFusionCorp Industries sysadmin team has developed a new bash script named xfusioncorp.sh. While the script has been distributed to all necessary servers, it lacks executable permissions on App Server 2 within the Stratos Datacenter.

Your task is to grant executable permissions to the /tmp/xfusioncorp.sh script on App Server 2. Additionally, ensure that all users have the capability to execute it.

-> Solutions,

```
thor@jump-host ~$ ssh steve@stapp02
The authenticity of host 'stapp02 (10.244.164.60)' can't be established.
ED25519 key fingerprint is SHA256:JuTD3FcEy5CUEkRKcWEMQXS2egZz/fK6uzCO3ydxmH4.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'stapp02' (ED25519) to the list of known hosts.
steve@stapp02's password:
```

```
[steve@stapp02 ~]$ ls -l /tmp/xfusioncorp.sh 
---------- 1 root root 40 Aug 24 08:41 /tmp/xfusioncorp.sh
```

```
[steve@stapp02 ~]$ sudo chmod 555 /tmp/xfusioncorp.sh
```

```
[steve@stapp02 ~]$ ls -l /tmp/xfusioncorp.sh 
-r-xr-xr-x 1 root root 40 Aug 24 08:46 xfusioncorp.sh
```

```
[steve@stapp02 ~]$ sh xfusioncorp.sh
Welcome To KodeKloud
```

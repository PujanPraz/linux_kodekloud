### Task

Following security audits, the xFusionCorp Industries security team has rolled out new protocols, including the restriction of direct root SSH login.

Your task is to disable direct SSH root login on all app servers within the Stratos Datacenter.

-> Solution,

```
thor@jump-host ~$ ssh tony@stapp01 
The authenticity of host 'stapp01 (10.244.81.35)' can't be established.
ED25519 key fingerprint is SHA256:F7kBUPKaBcCagfA74oJsjOuDfBxkJgndfWuxAZ3a9Ww.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'stapp01' (ED25519) to the list of known hosts.
tony@stapp01's password:
```

```
[tony@stapp01 ~]$ sudo vim /etc/ssh/sshd_config
PermitRootLogin no
```

```
[tony@stapp01 ~]$ sudo sshd -t
```

```
[tony@stapp01 ~]$ sudo systemctl restart sshd
```

```
[steve@stapp02 ~]$ sudo sshd -T | grep permitrootlogin
permitrootlogin no
```

Do the same for other app server







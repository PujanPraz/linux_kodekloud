### Task:
After conducting a security audit within the Stratos DC, the Nautilus security team discovered misconfigured permissions on critical files. To address this, corrective actions are being taken by the production support team. Specifically, the file named /etc/hosts on Nautilus App 3 server requires adjustments to its Access Control Lists (ACLs) as follows:

1. The file's user owner and group owner should be set to root.

2. Others should possess read only permissions on the file.

3. User javed must not have any permissions on the file.

4. User ryan should be granted read only permission on the file.

-> Solution,

```
[banner@stapp03 ~]$ ls -l /etc/hosts
-rw-r--r-- 1 root root 285 Aug 25 03:28 /etc/hosts
```

```
[banner@stapp03 ~]$ getfacl /etc/hosts
```

```
[banner@stapp03 ~]$ sudo setfacl -m u:javed:--- /etc/hosts
```

```
[banner@stapp03 ~]$ sudo setfacl -m u:ryan:r-- /etc/hosts
```

```
[banner@stapp03 ~]$ getfacl /etc/hosts
```

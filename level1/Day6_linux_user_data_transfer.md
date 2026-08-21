### Task
Due to an accidental data mix-up, user data was unintentionally mingled on Nautilus App Server 2 at the /home/usersdata location by the Nautilus production support team in Stratos DC. To rectify this, specific user data needs to be filtered and relocated. Here are the details:

Locate all files (excluding directories) owned by user javed within the /home/usersdata directory on App Server 2. Copy these files while preserving the directory structure to the /ecommerce directory.

-> Solutions,

```
thor@jump-host ~$ ssh steve@stapp02
The authenticity of host 'stapp02 (10.244.240.154)' can't be established.
ED25519 key fingerprint is SHA256:tD38TVsp3N5SeC9iX7DwKAZ/fSrQ8ODzMV5w0KPrvSY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'stapp02' (ED25519) to the list of known hosts.
steve@stapp02's password: 
[steve@stapp02 ~]$
```

```
[steve@stapp02 ~]$ find /home/usersdata/ -type f -user javed -exec cp --parents {} /ecommerce/ \;
```

```
[steve@stapp02 ~]$ ls -l /ecommerce/
total 4
drwxr-xr-x 3 steve steve 4096 Aug 21 14:48 home
[steve@stapp02 ~]$ cd /ecommerce/
[steve@stapp02 ecommerce]$ ls
home
[steve@stapp02 ecommerce]$ cd home/
[steve@stapp02 home]$ ls
usersdata
[steve@stapp02 home]$ cd usersdata/
[steve@stapp02 usersdata]$ ls
index.php        wp-blog-header.php    wp-content   wp-links-opml.php  wp-mail.php      wp-trackback.php
wp-activate.php  wp-comments-post.php  wp-cron.php  wp-load.php        wp-settings.php  xmlrpc.php
wp-admin         wp-config-sample.php  wp-includes  wp-login.php       wp-signup.php
[steve@stapp02 usersdata]$
```

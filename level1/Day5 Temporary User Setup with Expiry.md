```
Task:

As part of the temporary assignment to the `Nautilus` project, a developer named `siva` requires access for a limited duration. To ensure smooth access management, a temporary user account with an expiry date is needed. Here's what you need to do:  

Create a user named `siva` on `App Server 2` in Stratos Datacenter. Set the expiry date to `2027-02-17`, ensuring the user is created in lowercase as per standard protocol.
```

solution:
thor@jump-host ~$ ssh steve@stapp02

[steve@stapp02 ~]$ sudo useradd -e 2027-02-17 siva

[steve@stapp02 ~]$ tail /etc/passwd
siva:x:1001:1001::/home/siva:/bin/bash

[steve@stapp02 ~]$ sudo chage -l siva
Last password change                                    : Aug 20, 2026
Password expires                                        : never
Password inactive                                       : never
Account expires                                         : Feb 17, 2027
Minimum number of days between password change          : 0
Maximum number of days between password change          : 99999
Number of days of warning before password expires       : 7
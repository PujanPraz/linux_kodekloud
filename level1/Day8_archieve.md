### Task
The jump host server hosts a directory named /data, serving as a repository for various developers non-confidential data. Developer javed has requested a copy of their data stored in /data/javed. The System Admin team has provided the following steps to fulfill this request:

a. Create a compressed archive named javed.tar.gz of the /data/javed directory.

b. Transfer the archive to the /home directory on the Jump Host Server.

-> Solution,

```
thor@jump-host /data/javed$ ls
nautilus1.txt  nautilus2.txt  nautilus3.txt
```

```
thor@jump-host ~$ tar -zcvf javed.tar.gz /data/javed/
tar: Removing leading `/' from member names
/data/javed/
/data/javed/nautilus2.txt
/data/javed/nautilus3.txt
/data/javed/nautilus1.txt
```

```
thor@jump-host ~$ ls
javed.tar.gz
```

```
thor@jump-host ~$ sudo mv javed.tar.gz /home
```

```
thor@jump-host ~$ cd /home
thor@jump-host /home$ ls
ansible  javed.tar.gz  thor
```

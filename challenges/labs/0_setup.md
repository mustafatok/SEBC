## List the cloud provider you are using (AWS, GCE, Azure, other)
AWS

## List the nodes you are using by IP address and name
| Public IPs     | Private IPs   |
| -------------- |:-------------:|
| 35.156.47.209  | 172.31.19.108 |
| 35.156.174.131 | 172.31.29.137 |
| 35.157.16.1    | 172.31.22.5   |
| 35.157.188.163 | 172.31.17.25  |
| 35.157.199.104 | 172.31.23.114 |

## List the Linux release you are using
Red Hat 7.2

## Demonstrate the disk capacity available on each node is >= 30 GB
```
[ec2-user@ip-172-31-19-108 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2      100G  1,2G   99G   2% /
devtmpfs        7,3G     0  7,3G   0% /dev
tmpfs           7,2G     0  7,2G   0% /dev/shm
tmpfs           7,2G   17M  7,2G   1% /run
tmpfs           7,2G     0  7,2G   0% /sys/fs/cgroup
tmpfs           1,5G     0  1,5G   0% /run/user/1000
tmpfs           1,5G     0  1,5G   0% /run/user/0

```

```
[ec2-user@ip-172-31-29-137 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2      100G  1,2G   99G   2% /
devtmpfs        7,3G     0  7,3G   0% /dev
tmpfs           7,2G     0  7,2G   0% /dev/shm
tmpfs           7,2G   17M  7,2G   1% /run
tmpfs           7,2G     0  7,2G   0% /sys/fs/cgroup
tmpfs           1,5G     0  1,5G   0% /run/user/1000
tmpfs           1,5G     0  1,5G   0% /run/user/0

```

```
[ec2-user@ip-172-31-22-5 ~]$  df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2      100G  1,2G   99G   2% /
devtmpfs        7,3G     0  7,3G   0% /dev
tmpfs           7,2G     0  7,2G   0% /dev/shm
tmpfs           7,2G   17M  7,2G   1% /run
tmpfs           7,2G     0  7,2G   0% /sys/fs/cgroup
tmpfs           1,5G     0  1,5G   0% /run/user/1000
tmpfs           1,5G     0  1,5G   0% /run/user/0

```

```
[ec2-user@ip-172-31-17-25 ~]$  df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2      100G  1,2G   99G   2% /
devtmpfs        7,3G     0  7,3G   0% /dev
tmpfs           7,2G     0  7,2G   0% /dev/shm
tmpfs           7,2G   17M  7,2G   1% /run
tmpfs           7,2G     0  7,2G   0% /sys/fs/cgroup
tmpfs           1,5G     0  1,5G   0% /run/user/1000
tmpfs           1,5G     0  1,5G   0% /run/user/0

```

```
[ec2-user@ip-172-31-23-114 ~]$  df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2      100G  1,2G   99G   2% /
devtmpfs        7,3G     0  7,3G   0% /dev
tmpfs           7,2G     0  7,2G   0% /dev/shm
tmpfs           7,2G   17M  7,2G   1% /run
tmpfs           7,2G     0  7,2G   0% /sys/fs/cgroup
tmpfs           1,5G     0  1,5G   0% /run/user/1000
tmpfs           1,5G     0  1,5G   0% /run/user/0

```

## List the command and output for yum repolist enabled

```
[ec2-user@ip-172-31-19-108 ~]$ sudo yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                                 repo name                                                             status
!rhui-REGION-client-config-server-7/x86_64              Red Hat Update Infrastructure 2.0 Client Configuration Server 7            4
!rhui-REGION-rhel-server-releases/7Server/x86_64        Red Hat Enterprise Linux Server 7 (RPMs)                              14.038
!rhui-REGION-rhel-server-rh-common/7Server/x86_64       Red Hat Enterprise Linux Server 7 RH Common (RPMs)                       209
repolist: 14.251
```

```
[ec2-user@ip-172-31-29-137 ~]$ sudo yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                                 repo name                                                             status
!rhui-REGION-client-config-server-7/x86_64              Red Hat Update Infrastructure 2.0 Client Configuration Server 7            4
!rhui-REGION-rhel-server-releases/7Server/x86_64        Red Hat Enterprise Linux Server 7 (RPMs)                              14.038
!rhui-REGION-rhel-server-rh-common/7Server/x86_64       Red Hat Enterprise Linux Server 7 RH Common (RPMs)                       209
repolist: 14.251

```

```
[ec2-user@ip-172-31-22-5 ~]$ sudo yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                                 repo name                                                             status
!rhui-REGION-client-config-server-7/x86_64              Red Hat Update Infrastructure 2.0 Client Configuration Server 7            4
!rhui-REGION-rhel-server-releases/7Server/x86_64        Red Hat Enterprise Linux Server 7 (RPMs)                              14.038
!rhui-REGION-rhel-server-rh-common/7Server/x86_64       Red Hat Enterprise Linux Server 7 RH Common (RPMs)                       209
repolist: 14.251

```

```
[ec2-user@ip-172-31-17-25 ~]$ sudo yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                                 repo name                                                             status
!rhui-REGION-client-config-server-7/x86_64              Red Hat Update Infrastructure 2.0 Client Configuration Server 7            4
!rhui-REGION-rhel-server-releases/7Server/x86_64        Red Hat Enterprise Linux Server 7 (RPMs)                              14.038
!rhui-REGION-rhel-server-rh-common/7Server/x86_64       Red Hat Enterprise Linux Server 7 RH Common (RPMs)                       209
repolist: 14.251

```

```
[ec2-user@ip-172-31-23-114 ~]$ sudo yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                                 repo name                                                             status
!rhui-REGION-client-config-server-7/x86_64              Red Hat Update Infrastructure 2.0 Client Configuration Server 7            4
!rhui-REGION-rhel-server-releases/7Server/x86_64        Red Hat Enterprise Linux Server 7 (RPMs)                              14.038
!rhui-REGION-rhel-server-rh-common/7Server/x86_64       Red Hat Enterprise Linux Server 7 RH Common (RPMs)                       209
repolist: 14.251

```

## Add the following Linux accounts to all nodes
```
sudo useradd -u 2010 neymar
sudo useradd -u 2016 ronaldo
sudo groupadd barca
sudo usermod -aG barca ronaldo
sudo groupadd merengues
sudo usermod -aG merengues neymar
```

## List the /etc/passwd entries for neymar and ronaldo
```
[ec2-user@ip-172-31-19-108 ~]$ cat /etc/passwd | grep neymar
neymar:x:2010:2010::/home/neymar:/bin/bash
[ec2-user@ip-172-31-19-108 ~]$ cat /etc/passwd | grep ronaldo
ronaldo:x:2016:2016::/home/ronaldo:/bin/bash

```

## List the /etc/group entries for barca and merengues
```
[ec2-user@ip-172-31-19-108 ~]$ cat /etc/group | grep barca
barca:x:2017:ronaldo
[ec2-user@ip-172-31-19-108 ~]$ cat /etc/group | grep merengues
merengues:x:2018:neymar
```
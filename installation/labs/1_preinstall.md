1. Check `vm.swappiness` on all your nodes
    * Set the value to `1` if necessary
```
[ec2-user@ip-172-31-26-193 ~]$ sysctl vm.swappiness
vm.swappiness = 30
[ec2-user@ip-172-31-26-193 ~]$ sudo sysctl vm.swappiness=1
vm.swappiness = 1
```

2. Show the mount attributes of all volumes
```
[ec2-user@ip-172-31-26-193 ~]$ mount | column -t
sysfs       on  /sys                        type  sysfs       (rw,nosuid,nodev,noexec,relatime,seclabel)
proc        on  /proc                       type  proc        (rw,nosuid,nodev,noexec,relatime)
devtmpfs    on  /dev                        type  devtmpfs    (rw,nosuid,seclabel,size=7599360k,nr_inodes=1899840,mode=755)
securityfs  on  /sys/kernel/security        type  securityfs  (rw,nosuid,nodev,noexec,relatime)
tmpfs       on  /dev/shm                    type  tmpfs       (rw,nosuid,nodev,seclabel)
devpts      on  /dev/pts                    type  devpts      (rw,nosuid,noexec,relatime,seclabel,gid=5,mode=620,ptmxmode=000)
tmpfs       on  /run                        type  tmpfs       (rw,nosuid,nodev,seclabel,mode=755)
tmpfs       on  /sys/fs/cgroup              type  tmpfs       (ro,nosuid,nodev,noexec,seclabel,mode=755)
cgroup      on  /sys/fs/cgroup/systemd      type  cgroup      (rw,nosuid,nodev,noexec,relatime,xattr,release_agent=/usr/lib/systemd/systemd-cgroups-agent,name=systemd)
pstore      on  /sys/fs/pstore              type  pstore      (rw,nosuid,nodev,noexec,relatime)
cgroup      on  /sys/fs/cgroup/cpuset       type  cgroup      (rw,nosuid,nodev,noexec,relatime,cpuset)
cgroup      on  /sys/fs/cgroup/perf_event   type  cgroup      (rw,nosuid,nodev,noexec,relatime,perf_event)
cgroup      on  /sys/fs/cgroup/memory       type  cgroup      (rw,nosuid,nodev,noexec,relatime,memory)
cgroup      on  /sys/fs/cgroup/cpu,cpuacct  type  cgroup      (rw,nosuid,nodev,noexec,relatime,cpuacct,cpu)
cgroup      on  /sys/fs/cgroup/devices      type  cgroup      (rw,nosuid,nodev,noexec,relatime,devices)
cgroup      on  /sys/fs/cgroup/hugetlb      type  cgroup      (rw,nosuid,nodev,noexec,relatime,hugetlb)
cgroup      on  /sys/fs/cgroup/net_cls      type  cgroup      (rw,nosuid,nodev,noexec,relatime,net_cls)
cgroup      on  /sys/fs/cgroup/blkio        type  cgroup      (rw,nosuid,nodev,noexec,relatime,blkio)
cgroup      on  /sys/fs/cgroup/freezer      type  cgroup      (rw,nosuid,nodev,noexec,relatime,freezer)
configfs    on  /sys/kernel/config          type  configfs    (rw,relatime)
/dev/xvda2  on  /                           type  xfs         (rw,relatime,seclabel,attr2,inode64,noquota)
selinuxfs   on  /sys/fs/selinux             type  selinuxfs   (rw,relatime)
debugfs     on  /sys/kernel/debug           type  debugfs     (rw,relatime)
mqueue      on  /dev/mqueue                 type  mqueue      (rw,relatime,seclabel)
hugetlbfs   on  /dev/hugepages              type  hugetlbfs   (rw,relatime,seclabel)
systemd-1   on  /proc/sys/fs/binfmt_misc    type  autofs      (rw,relatime,fd=29,pgrp=1,timeout=300,minproto=5,maxproto=5,direct)
tmpfs       on  /run/user/1000              type  tmpfs       (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700,uid=1000,gid=1000)
```

3. Show the reserve space of any non-root, `ext`-based volumes
    * XFS volumes do not maintain reserve space
```
[ec2-user@ip-172-31-26-193 ~]$ df -H
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       33G  972M   32G   4% /
devtmpfs        7,8G     0  7,8G   0% /dev
tmpfs           7,7G     0  7,7G   0% /dev/shm
tmpfs           7,7G   18M  7,7G   1% /run
tmpfs           7,7G     0  7,7G   0% /sys/fs/cgroup
tmpfs           1,6G     0  1,6G   0% /run/user/1000


[ec2-user@ip-172-31-26-193 ~]$ sudo fdisk -l /dev/xvda2

Disk /dev/xvda2: 32.2 GB, 32210140672 bytes, 62910431 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
```

4. Disable transparent hugepage support
```
[ec2-user@ip-172-31-26-193 ~]$ sudo -s
[root@ip-172-31-26-193 ec2-user]# echo never > /sys/kernel/mm/transparent_hugepage/enabled
[root@ip-172-31-26-193 ec2-user]# cat /sys/kernel/mm/transparent_hugepage/enabled
always madvise [never]
[root@ip-172-31-26-193 ec2-user]# reboot
```

5. List your network interface configuration
```
[ec2-user@ip-172-31-26-193 ~]$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.26.193  netmask 255.255.240.0  broadcast 172.31.31.255
        inet6 fe80::473:a5ff:febe:3a35  prefixlen 64  scopeid 0x20<link>
        ether 06:73:a5:be:3a:35  txqueuelen 1000  (Ethernet)
        RX packets 211  bytes 25404 (24.8 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 253  bytes 25711 (25.1 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 0  (Local Loopback)
        RX packets 4  bytes 340 (340.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4  bytes 340 (340.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

6. List forward and reverse host lookups using `getent` or `nslookup`
```
[ec2-user@ip-172-31-26-193 ~]$ getent hosts ec2-35-157-157-148.eu-central-1.compute.amazonaws.com
172.31.20.157   ec2-35-157-157-148.eu-central-1.compute.amazonaws.com
[ec2-user@ip-172-31-26-193 ~]$ getent hosts 172.31.20.157
172.31.20.157   ip-172-31-20-157.eu-central-1.compute.internal
[ec2-user@ip-172-31-26-193 ~]$ getent hosts 35.157.157.148
35.157.157.148  ec2-35-157-157-148.eu-central-1.compute.amazonaws.com
```

7. Show the <code>nscd</code> service is running
```
[ec2-user@ip-172-31-26-193 ~]$ sudo systemctl status nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; disabled; vendor preset: disabled)
   Active: active (running) since Mo 2017-03-06 10:20:57 EST; 4s ago
  Process: 9231 ExecStop=/usr/sbin/nscd --shutdown (code=exited, status=0/SUCCESS)
  Process: 9234 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 9235 (nscd)
   CGroup: /system.slice/nscd.service
           └─9235 /usr/sbin/nscd
```

8. Show the <code>ntpd</code> service is running<br>
```
[ec2-user@ip-172-31-26-193 ~]$ sudo systemctl status ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; disabled; vendor preset: disabled)
   Active: active (running) since Mo 2017-03-06 10:22:59 EST; 5s ago
  Process: 9313 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 9314 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─9314 /usr/sbin/ntpd -u ntp:ntp -g
```
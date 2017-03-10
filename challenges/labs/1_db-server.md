## The hostname of your db server node
```
[ec2-user@ip-172-31-19-108 ~]$ hostname
ip-172-31-19-108.eu-central-1.compute.internal
```

## The command and output for display your database server's version
```
[ec2-user@ip-172-31-19-108 ~]$ mysqladmin -u root -p version
Enter password: 
mysqladmin  Ver 8.42 Distrib 5.6.35, for Linux on x86_64
Copyright (c) 2000, 2016, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Server version		5.6.35
Protocol version	10
Connection		Localhost via UNIX socket
UNIX socket		/var/lib/mysql/mysql.sock
Uptime:			2 min 23 sec

Threads: 1  Questions: 47  Slow queries: 0  Opens: 67  Flush tables: 1  Open tables: 60  Queries per second avg: 0.328
```

## The command and output for listing your created databases
```
[ec2-user@ip-172-31-19-108 ~]$ sudo mysql -u root -p -e "SHOW DATABASES;"
Enter password: 
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
```

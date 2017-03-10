## List the command and output for ls /etc/yum.repos.d in challenges/labs/2_cm.md

```
[ec2-user@ip-172-31-29-137 ~]$ sudo ls /etc/yum.repos.d
cloudera-manager.repo  mysql-community-source.repo  redhat-rhui-client-config.repo  rhui-load-balancers.conf
mysql-community.repo   redhat.repo		    redhat-rhui.repo
```

## Use the scm_prepare_database.sh script to write your db.properties file

```
[ec2-user@ip-172-31-29-137 ~]$ sudo /usr/share/cmf/schema/scm_prepare_database.sh -h ip-172-31-19-108.eu-central-1.compute.internal mysql scm scm
Enter SCM password: 
JAVA_HOME=/usr/java/jdk1.8.0_111
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.8.0_111/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
```
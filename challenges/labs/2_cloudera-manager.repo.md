## Copy the cloudera-manager.repo file to challenges/labs/2_cloudera-manager.repo.md

```
[ec2-user@ip-172-31-29-137 ~]$ cat /etc/yum.repos.d/cloudera-manager.repo 
[cloudera-manager]
# Packages for Cloudera Manager, Version 5, on RedHat or CentOS 7 x86_64           	  
name=Cloudera Manager
baseurl=https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/5.9/
gpgkey =https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/RPM-GPG-KEY-cloudera    
gpgcheck = 1

```
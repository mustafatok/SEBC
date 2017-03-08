* What is ubertask optimization?

	It is also known as small-jobs optimization, which runs "sufficiently small" jobs sequentially within a single JVM. "Small" is basically defined by mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings.

* Where in CM is the Kerberos Security Realm value displayed?

	It is displayed in Administraton / Settings / Kerberos Security Realm ( default_realm ).

* Which CDH service(s) host a property for enabling Kerberos authentication?

	All core services in CDH host a property for enabling Kerberos: HDFS, Hive, Hue, Oozie, YARN (MR2 Included), ZooKeeper, Cloudera Management Services

* How do you upgrade the CM agents?

	In order to upgrade CM Agents we can use an upgrade wizard that is invoked when you connect to the Admin Console or manually install the Cloudera Manager Agent packages.

* Give the `tsquery` statement used to chart Hue's CPU utilization?

	select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME

* Name all the roles that make up the Hive service

	Role Types : Gateway, Hive Metastore Server, HiveServer2
	Role Groups : Gateway Default Group, Hive Metastore Server Default Group, HiveServer2 Default Group

* What steps must be completed before integrating Cloudera Manager with Kerberos?
	Prerequisites - you already have a working Kerberos key distribution center (KDC) and realm setup, and that you've installed the following Kerberos client packages on all cluster hosts and hosts that will be used to access the cluster, depending on the OS in use.

	These prerequisites for integrating Kerberos are taken from : https://www.cloudera.com/documentation/enterprise/5-8-x/topics/cm_sg_intro_kerb.html

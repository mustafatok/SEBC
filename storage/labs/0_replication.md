Choose a partner in class

Name a source directory after your GitHub handle
Name a target directory after your partner's GitHub handle


	I created 2 users from hue; one for myself ( mustafatok ) one for my partner ( msmarnaoui ). In order to perform commands in hdfs, I created the same users in linux as well. Then, I created source and target folders by using:
	```
	[mustafatok@ip-172-31-26-193 ec2-user]$ hdfs dfs -mkdir /user/mustafatok/source
	[msmarnaoui@ip-172-31-26-193 ec2-user]$ hdfs dfs -mkdir /user/msmarnaoui/target
	```

Use teragen to create a 500 MB file
```
[mustafatok@ip-172-31-26-193 ec2-user]$ hadoop jar /opt/cloudera/parcels/CDH-5.8.4-1.cdh5.8.4.p0.5/jars/hadoop-examples.jar teragen 5242880 /user/mustafatok/source/teragen_data
```

Copy your partner's file to your target directory
Let one partner use distcp on the command line

The command is stuck all the time because of the connection problem in the other cluster. I will try it again when the other cluster is up again!
```
[mustafatok@ip-172-31-26-193 ec2-user]$ hadoop distcp hftp://52.10.0.80:50070/user/msmarnaoui/msmarnaoui/part-m-00000 /user/mustafatok/target/17/03/07 11:23:51 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, append=false, useDiff=false, useRdiff=false, fromSnapshot=null, toSnapshot=null, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[hftp://52.10.0.80:50070/user/msmarnaoui/msmarnaoui/part-m-00000], targetPath=/user/mustafatok/target, targetPathExists=true, filtersFile='null'}
17/03/07 11:23:51 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-26-193.eu-central-1.compute.internal/172.31.26.193:8032
17/03/07 11:23:52 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 1; dirCnt = 0
17/03/07 11:23:52 INFO tools.SimpleCopyListing: Build file listing completed.
17/03/07 11:23:52 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb
17/03/07 11:23:52 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor
17/03/07 11:23:52 INFO tools.DistCp: Number of paths in the copy list: 1
17/03/07 11:23:52 INFO tools.DistCp: Number of paths in the copy list: 1
17/03/07 11:23:52 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-26-193.eu-central-1.compute.internal/172.31.26.193:8032
17/03/07 11:23:53 INFO mapreduce.JobSubmitter: number of splits:1
17/03/07 11:23:53 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1488901699669_0005
17/03/07 11:23:53 INFO impl.YarnClientImpl: Submitted application application_1488901699669_0005
17/03/07 11:23:53 INFO mapreduce.Job: The url to track the job: http://ip-172-31-26-193.eu-central-1.compute.internal:8088/proxy/application_1488901699669_0005/
17/03/07 11:23:53 INFO tools.DistCp: DistCp job-id: job_1488901699669_0005
17/03/07 11:23:53 INFO mapreduce.Job: Running job: job_1488901699669_0005
17/03/07 11:23:58 INFO mapreduce.Job: Job job_1488901699669_0005 running in uber mode : false
17/03/07 11:23:58 INFO mapreduce.Job:  map 0% reduce 0%

```


Browse the results
Use hdfs fsck <path> -files -blocks on your source and target directories





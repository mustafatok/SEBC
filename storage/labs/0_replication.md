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

Copy your partner's file to your target directory (I used the user `msmarnaoui` to get file from his cluster)
Let one partner use distcp on the command line

```
[msmarnaoui@ip-172-31-26-193 ec2-user]$ hadoop distcp hftp://35.167.64.53:50070/user/msmarnaoui/msmarnaoui /user/msmarnaoui/target
17/03/08 09:53:59 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, append=false, useDiff=false, useRdiff=false, fromSnapshot=null, toSnapshot=null, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[hftp://35.167.64.53:50070/user/msmarnaoui/msmarnaoui], targetPath=/user/msmarnaoui/target, targetPathExists=true, filtersFile='null'}
17/03/08 09:53:59 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-26-193.eu-central-1.compute.internal/172.31.26.193:8032
17/03/08 09:54:01 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 4; dirCnt = 1
17/03/08 09:54:01 INFO tools.SimpleCopyListing: Build file listing completed.
17/03/08 09:54:01 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb
17/03/08 09:54:01 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor
17/03/08 09:54:01 INFO tools.DistCp: Number of paths in the copy list: 4
17/03/08 09:54:01 INFO tools.DistCp: Number of paths in the copy list: 4
17/03/08 09:54:01 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-26-193.eu-central-1.compute.internal/172.31.26.193:8032
17/03/08 09:54:01 INFO mapreduce.JobSubmitter: number of splits:3
17/03/08 09:54:01 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1488973979967_0020
17/03/08 09:54:02 INFO impl.YarnClientImpl: Submitted application application_1488973979967_0020
17/03/08 09:54:02 INFO mapreduce.Job: The url to track the job: http://ip-172-31-26-193.eu-central-1.compute.internal:8088/proxy/application_1488973979967_0020/
17/03/08 09:54:02 INFO tools.DistCp: DistCp job-id: job_1488973979967_0020
17/03/08 09:54:02 INFO mapreduce.Job: Running job: job_1488973979967_0020
17/03/08 09:54:08 INFO mapreduce.Job: Job job_1488973979967_0020 running in uber mode : false
17/03/08 09:54:08 INFO mapreduce.Job:  map 0% reduce 0%
17/03/08 09:54:14 INFO mapreduce.Job:  map 33% reduce 0%
17/03/08 09:54:25 INFO mapreduce.Job:  map 100% reduce 0%
17/03/08 09:54:43 INFO mapreduce.Job: Job job_1488973979967_0020 completed successfully
17/03/08 09:54:43 INFO mapreduce.Job: Counters: 40
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=389211
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=1762
		HDFS: Number of bytes written=500000068
		HDFS: Number of read operations=39
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=11
		HFTP: Number of bytes read=0
		HFTP: Number of bytes written=0
		HFTP: Number of read operations=0
		HFTP: Number of large read operations=0
		HFTP: Number of write operations=0
	Job Counters 
		Launched map tasks=3
		Other local map tasks=3
		Total time spent by all maps in occupied slots (ms)=69952
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=69952
		Total vcore-seconds taken by all map tasks=69952
		Total megabyte-seconds taken by all map tasks=71630848
	Map-Reduce Framework
		Map input records=4
		Map output records=1
		Input split bytes=366
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=183
		CPU time spent (ms)=13940
		Physical memory (bytes) snapshot=708722688
		Virtual memory (bytes) snapshot=4769325056
		Total committed heap usage (bytes)=842530816
	File Input Format Counters 
		Bytes Read=1396
	File Output Format Counters 
		Bytes Written=68
	DistCp Counters
		Bytes Copied=500000000
		Bytes Expected=500000000
		Bytes Skipped=0
		Files Copied=3
		Files Skipped=1

```

Browse the results
Use hdfs fsck <path> -files -blocks on your source and target directories
```
[msmarnaoui@ip-172-31-26-193 ec2-user]$ hdfs fsck /user/msmarnaoui/target -files -blocks
Connecting to namenode via http://ip-172-31-26-193.eu-central-1.compute.internal:50070
FSCK started by msmarnaoui (auth:SIMPLE) from /172.31.26.193 for path /user/msmarnaoui/target at Wed Mar 08 09:56:25 EST 2017
/user/msmarnaoui/target <dir>
/user/msmarnaoui/target/msmarnaoui <dir>
/user/msmarnaoui/target/msmarnaoui/_SUCCESS 0 bytes, 0 block(s):  OK

/user/msmarnaoui/target/msmarnaoui/part-m-00000 250000000 bytes, 2 block(s):  OK
0. BP-786418985-172.31.26.193-1488824081450:blk_1073747438_6616 len=134217728 Live_repl=3
1. BP-786418985-172.31.26.193-1488824081450:blk_1073747441_6619 len=115782272 Live_repl=3

/user/msmarnaoui/target/msmarnaoui/part-m-00001 250000000 bytes, 2 block(s):  OK
0. BP-786418985-172.31.26.193-1488824081450:blk_1073747439_6617 len=134217728 Live_repl=3
1. BP-786418985-172.31.26.193-1488824081450:blk_1073747442_6620 len=115782272 Live_repl=3

Status: HEALTHY
 Total size:	500000000 B
 Total dirs:	2
 Total files:	3
 Total symlinks:		0
 Total blocks (validated):	4 (avg. block size 125000000 B)
 Minimally replicated blocks:	4 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Wed Mar 08 09:56:25 EST 2017 in 2 milliseconds


The filesystem under path '/user/msmarnaoui/target' is HEALTHY
```
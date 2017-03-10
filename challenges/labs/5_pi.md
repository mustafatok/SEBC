## Run the Hadoop pi program as the user ronaldo

```
[ec2-user@ip-172-31-17-25 ~]$ kinit ronaldo
Password for ronaldo@MUSTAFATOK.ES: 
```

```
[ec2-user@ip-172-31-17-25 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1000
Default principal: ronaldo@MUSTAFATOK.ES

Valid starting       Expires              Service principal
10.03.2017 05:24:53  11.03.2017 05:24:53  krbtgt/MUSTAFATOK.ES@MUSTAFATOK.ES
	renew until 17.03.2017 06:24:53
```

```
[ec2-user@ip-172-31-17-25 ~]$ hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar pi 10 100
Number of Maps  = 10
Samples per Map = 100
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Wrote input for Map #4
Wrote input for Map #5
Wrote input for Map #6
Wrote input for Map #7
Wrote input for Map #8
Wrote input for Map #9
Starting Job
17/03/10 05:25:07 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-17-25.eu-central-1.compute.internal/172.31.17.25:8032
17/03/10 05:25:07 INFO hdfs.DFSClient: Created token for ronaldo: HDFS_DELEGATION_TOKEN owner=ronaldo@MUSTAFATOK.ES, renewer=yarn, realUser=, issueDate=1489141507255, maxDate=1489746307255, sequenceNumber=2, masterKeyId=2 on 172.31.17.25:8020
17/03/10 05:25:07 INFO security.TokenCache: Got dt for hdfs://ip-172-31-17-25.eu-central-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.17.25:8020, Ident: (token for ronaldo: HDFS_DELEGATION_TOKEN owner=ronaldo@MUSTAFATOK.ES, renewer=yarn, realUser=, issueDate=1489141507255, maxDate=1489746307255, sequenceNumber=2, masterKeyId=2)
17/03/10 05:25:07 INFO input.FileInputFormat: Total input paths to process : 10
17/03/10 05:25:07 INFO mapreduce.JobSubmitter: number of splits:10
17/03/10 05:25:07 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1489140600809_0002
17/03/10 05:25:07 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.17.25:8020, Ident: (token for ronaldo: HDFS_DELEGATION_TOKEN owner=ronaldo@MUSTAFATOK.ES, renewer=yarn, realUser=, issueDate=1489141507255, maxDate=1489746307255, sequenceNumber=2, masterKeyId=2)
17/03/10 05:25:08 INFO impl.YarnClientImpl: Submitted application application_1489140600809_0002
17/03/10 05:25:08 INFO mapreduce.Job: The url to track the job: http://ip-172-31-17-25.eu-central-1.compute.internal:8088/proxy/application_1489140600809_0002/
17/03/10 05:25:08 INFO mapreduce.Job: Running job: job_1489140600809_0002
17/03/10 05:25:16 INFO mapreduce.Job: Job job_1489140600809_0002 running in uber mode : false
17/03/10 05:25:16 INFO mapreduce.Job:  map 0% reduce 0%
17/03/10 05:25:22 INFO mapreduce.Job:  map 10% reduce 0%
17/03/10 05:25:23 INFO mapreduce.Job:  map 20% reduce 0%
17/03/10 05:25:26 INFO mapreduce.Job:  map 40% reduce 0%
17/03/10 05:25:29 INFO mapreduce.Job:  map 100% reduce 0%
17/03/10 05:25:35 INFO mapreduce.Job:  map 100% reduce 100%
17/03/10 05:25:35 INFO mapreduce.Job: Job job_1489140600809_0002 completed successfully
17/03/10 05:25:35 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=99
		FILE: Number of bytes written=1369048
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=3020
		HDFS: Number of bytes written=215
		HDFS: Number of read operations=43
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=3
	Job Counters 
		Launched map tasks=10
		Launched reduce tasks=1
		Data-local map tasks=10
		Total time spent by all maps in occupied slots (ms)=92776
		Total time spent by all reduces in occupied slots (ms)=3358
		Total time spent by all map tasks (ms)=92776
		Total time spent by all reduce tasks (ms)=3358
		Total vcore-seconds taken by all map tasks=92776
		Total vcore-seconds taken by all reduce tasks=3358
		Total megabyte-seconds taken by all map tasks=95002624
		Total megabyte-seconds taken by all reduce tasks=3438592
	Map-Reduce Framework
		Map input records=10
		Map output records=20
		Map output bytes=180
		Map output materialized bytes=340
		Input split bytes=1840
		Combine input records=0
		Combine output records=0
		Reduce input groups=2
		Reduce shuffle bytes=340
		Reduce input records=20
		Reduce output records=0
		Spilled Records=40
		Shuffled Maps =10
		Failed Shuffles=0
		Merged Map outputs=10
		GC time elapsed (ms)=345
		CPU time spent (ms)=7600
		Physical memory (bytes) snapshot=4807503872
		Virtual memory (bytes) snapshot=17462599680
		Total committed heap usage (bytes)=5577375744
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=1180
	File Output Format Counters 
		Bytes Written=97
Job Finished in 28.553 seconds
Estimated value of Pi is 3.14800000000000000000
```
## Run the terasort program as neymar using the output target /user/neymar/tsort640m
```
[ec2-user@ip-172-31-17-25 ~]$ kinit neymar
Password for neymar@MUSTAFATOK.ES: 

```

```
[ec2-user@ip-172-31-17-25 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1000
Default principal: neymar@MUSTAFATOK.ES

Valid starting       Expires              Service principal
10.03.2017 05:15:59  11.03.2017 05:15:59  krbtgt/MUSTAFATOK.ES@MUSTAFATOK.ES
	renew until 17.03.2017 06:15:59
```

```
[ec2-user@ip-172-31-17-25 ~]$ hdfs dfs -ls
Found 2 items
drwx------   - neymar neymar          0 2017-03-10 04:37 .staging
drwxr-xr-x   - neymar neymar          0 2017-03-10 04:37 tgen640
```

```
[ec2-user@ip-172-31-17-25 ~]$  time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/neymar/tgen640 /user/neymar/tsort640m
17/03/10 05:16:50 INFO terasort.TeraSort: starting
17/03/10 05:16:51 INFO hdfs.DFSClient: Created token for neymar: HDFS_DELEGATION_TOKEN owner=neymar@MUSTAFATOK.ES, renewer=yarn, realUser=, issueDate=1489141011564, maxDate=1489745811564, sequenceNumber=1, masterKeyId=2 on 172.31.17.25:8020
17/03/10 05:16:51 INFO security.TokenCache: Got dt for hdfs://ip-172-31-17-25.eu-central-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.17.25:8020, Ident: (token for neymar: HDFS_DELEGATION_TOKEN owner=neymar@MUSTAFATOK.ES, renewer=yarn, realUser=, issueDate=1489141011564, maxDate=1489745811564, sequenceNumber=1, masterKeyId=2)
17/03/10 05:16:51 INFO input.FileInputFormat: Total input paths to process : 8
Spent 490ms computing base-splits.
Spent 8ms computing TeraScheduler splits.
Computing input splits took 498ms
Sampling 10 splits of 392
Making 8 from 100000 sampled records
Computing parititions took 967ms
Spent 1468ms computing partitions.
17/03/10 05:16:52 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-17-25.eu-central-1.compute.internal/172.31.17.25:8032
17/03/10 05:16:53 INFO mapreduce.JobSubmitter: number of splits:392
17/03/10 05:16:53 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1489140600809_0001
17/03/10 05:16:53 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.17.25:8020, Ident: (token for neymar: HDFS_DELEGATION_TOKEN owner=neymar@MUSTAFATOK.ES, renewer=yarn, realUser=, issueDate=1489141011564, maxDate=1489745811564, sequenceNumber=1, masterKeyId=2)
17/03/10 05:16:54 INFO impl.YarnClientImpl: Submitted application application_1489140600809_0001
17/03/10 05:16:54 INFO mapreduce.Job: The url to track the job: http://ip-172-31-17-25.eu-central-1.compute.internal:8088/proxy/application_1489140600809_0001/
17/03/10 05:16:54 INFO mapreduce.Job: Running job: job_1489140600809_0001
17/03/10 05:17:03 INFO mapreduce.Job: Job job_1489140600809_0001 running in uber mode : false
17/03/10 05:17:03 INFO mapreduce.Job:  map 0% reduce 0%
17/03/10 05:17:12 INFO mapreduce.Job:  map 1% reduce 0%
17/03/10 05:17:20 INFO mapreduce.Job:  map 2% reduce 0%
17/03/10 05:17:24 INFO mapreduce.Job:  map 4% reduce 0%
17/03/10 05:17:28 INFO mapreduce.Job:  map 5% reduce 0%
17/03/10 05:17:34 INFO mapreduce.Job:  map 6% reduce 0%
17/03/10 05:17:36 INFO mapreduce.Job:  map 8% reduce 0%
17/03/10 05:17:41 INFO mapreduce.Job:  map 9% reduce 0%
17/03/10 05:17:48 INFO mapreduce.Job:  map 12% reduce 0%
17/03/10 05:17:54 INFO mapreduce.Job:  map 13% reduce 0%
17/03/10 05:17:57 INFO mapreduce.Job:  map 14% reduce 0%
17/03/10 05:17:59 INFO mapreduce.Job:  map 15% reduce 0%
17/03/10 05:18:00 INFO mapreduce.Job:  map 16% reduce 0%
17/03/10 05:18:06 INFO mapreduce.Job:  map 17% reduce 0%
17/03/10 05:18:12 INFO mapreduce.Job:  map 19% reduce 0%
17/03/10 05:18:13 INFO mapreduce.Job:  map 20% reduce 0%
17/03/10 05:18:17 INFO mapreduce.Job:  map 21% reduce 0%
17/03/10 05:18:24 INFO mapreduce.Job:  map 23% reduce 0%
17/03/10 05:18:25 INFO mapreduce.Job:  map 24% reduce 0%
17/03/10 05:18:31 INFO mapreduce.Job:  map 25% reduce 0%
17/03/10 05:18:34 INFO mapreduce.Job:  map 26% reduce 0%
17/03/10 05:18:37 INFO mapreduce.Job:  map 28% reduce 0%
17/03/10 05:18:43 INFO mapreduce.Job:  map 29% reduce 0%
17/03/10 05:18:45 INFO mapreduce.Job:  map 30% reduce 0%
17/03/10 05:18:49 INFO mapreduce.Job:  map 32% reduce 0%
17/03/10 05:18:53 INFO mapreduce.Job:  map 33% reduce 0%
17/03/10 05:18:59 INFO mapreduce.Job:  map 34% reduce 0%
17/03/10 05:19:00 INFO mapreduce.Job:  map 35% reduce 0%
17/03/10 05:19:02 INFO mapreduce.Job:  map 36% reduce 0%
17/03/10 05:19:06 INFO mapreduce.Job:  map 37% reduce 0%
17/03/10 05:19:10 INFO mapreduce.Job:  map 38% reduce 0%
17/03/10 05:19:13 INFO mapreduce.Job:  map 40% reduce 0%
17/03/10 05:19:19 INFO mapreduce.Job:  map 41% reduce 0%
17/03/10 05:19:21 INFO mapreduce.Job:  map 42% reduce 0%
17/03/10 05:19:25 INFO mapreduce.Job:  map 43% reduce 0%
17/03/10 05:19:26 INFO mapreduce.Job:  map 44% reduce 0%
17/03/10 05:19:29 INFO mapreduce.Job:  map 45% reduce 0%
17/03/10 05:19:34 INFO mapreduce.Job:  map 46% reduce 0%
17/03/10 05:19:38 INFO mapreduce.Job:  map 48% reduce 0%
17/03/10 05:19:42 INFO mapreduce.Job:  map 49% reduce 0%
17/03/10 05:19:47 INFO mapreduce.Job:  map 50% reduce 0%
17/03/10 05:19:49 INFO mapreduce.Job:  map 51% reduce 0%
17/03/10 05:19:50 INFO mapreduce.Job:  map 52% reduce 0%
17/03/10 05:19:54 INFO mapreduce.Job:  map 53% reduce 0%
17/03/10 05:19:57 INFO mapreduce.Job:  map 54% reduce 0%
17/03/10 05:20:02 INFO mapreduce.Job:  map 56% reduce 0%
17/03/10 05:20:06 INFO mapreduce.Job:  map 57% reduce 0%
17/03/10 05:20:08 INFO mapreduce.Job:  map 58% reduce 0%
17/03/10 05:20:14 INFO mapreduce.Job:  map 59% reduce 0%
17/03/10 05:20:15 INFO mapreduce.Job:  map 60% reduce 0%
17/03/10 05:20:16 INFO mapreduce.Job:  map 61% reduce 0%
17/03/10 05:20:23 INFO mapreduce.Job:  map 62% reduce 0%
17/03/10 05:20:24 INFO mapreduce.Job:  map 63% reduce 0%
17/03/10 05:20:25 INFO mapreduce.Job:  map 64% reduce 0%
17/03/10 05:20:29 INFO mapreduce.Job:  map 65% reduce 0%
17/03/10 05:20:32 INFO mapreduce.Job:  map 66% reduce 0%
17/03/10 05:20:35 INFO mapreduce.Job:  map 67% reduce 0%
17/03/10 05:20:37 INFO mapreduce.Job:  map 68% reduce 0%
17/03/10 05:20:42 INFO mapreduce.Job:  map 69% reduce 0%
17/03/10 05:20:43 INFO mapreduce.Job:  map 70% reduce 0%
17/03/10 05:20:50 INFO mapreduce.Job:  map 72% reduce 0%
17/03/10 05:20:53 INFO mapreduce.Job:  map 73% reduce 0%
17/03/10 05:20:57 INFO mapreduce.Job:  map 74% reduce 0%
17/03/10 05:21:01 INFO mapreduce.Job:  map 75% reduce 0%
17/03/10 05:21:02 INFO mapreduce.Job:  map 76% reduce 0%
17/03/10 05:21:04 INFO mapreduce.Job:  map 77% reduce 0%
17/03/10 05:21:09 INFO mapreduce.Job:  map 78% reduce 0%
17/03/10 05:21:10 INFO mapreduce.Job:  map 79% reduce 0%
17/03/10 05:21:14 INFO mapreduce.Job:  map 80% reduce 0%
17/03/10 05:21:16 INFO mapreduce.Job:  map 81% reduce 0%
17/03/10 05:21:19 INFO mapreduce.Job:  map 82% reduce 0%
17/03/10 05:21:26 INFO mapreduce.Job:  map 84% reduce 0%
17/03/10 05:21:28 INFO mapreduce.Job:  map 84% reduce 3%
17/03/10 05:21:30 INFO mapreduce.Job:  map 84% reduce 5%
17/03/10 05:21:31 INFO mapreduce.Job:  map 84% reduce 6%
17/03/10 05:21:32 INFO mapreduce.Job:  map 84% reduce 14%
17/03/10 05:21:33 INFO mapreduce.Job:  map 84% reduce 15%
17/03/10 05:21:34 INFO mapreduce.Job:  map 84% reduce 17%
17/03/10 05:21:35 INFO mapreduce.Job:  map 84% reduce 19%
17/03/10 05:21:38 INFO mapreduce.Job:  map 85% reduce 20%
17/03/10 05:21:40 INFO mapreduce.Job:  map 85% reduce 24%
17/03/10 05:21:41 INFO mapreduce.Job:  map 86% reduce 24%
17/03/10 05:21:47 INFO mapreduce.Job:  map 86% reduce 25%
17/03/10 05:21:50 INFO mapreduce.Job:  map 87% reduce 25%
17/03/10 05:21:52 INFO mapreduce.Job:  map 88% reduce 25%
17/03/10 05:21:55 INFO mapreduce.Job:  map 88% reduce 26%
17/03/10 05:22:02 INFO mapreduce.Job:  map 90% reduce 26%
17/03/10 05:22:12 INFO mapreduce.Job:  map 91% reduce 26%
17/03/10 05:22:14 INFO mapreduce.Job:  map 92% reduce 26%
17/03/10 05:22:15 INFO mapreduce.Job:  map 92% reduce 27%
17/03/10 05:22:22 INFO mapreduce.Job:  map 93% reduce 27%
17/03/10 05:22:26 INFO mapreduce.Job:  map 94% reduce 27%
17/03/10 05:22:32 INFO mapreduce.Job:  map 95% reduce 28%
17/03/10 05:22:39 INFO mapreduce.Job:  map 96% reduce 28%
17/03/10 05:22:43 INFO mapreduce.Job:  map 97% reduce 28%
17/03/10 05:22:51 INFO mapreduce.Job:  map 98% reduce 28%
17/03/10 05:22:53 INFO mapreduce.Job:  map 99% reduce 29%
17/03/10 05:23:03 INFO mapreduce.Job:  map 100% reduce 33%
17/03/10 05:23:05 INFO mapreduce.Job:  map 100% reduce 40%
17/03/10 05:23:06 INFO mapreduce.Job:  map 100% reduce 57%
17/03/10 05:23:07 INFO mapreduce.Job:  map 100% reduce 61%
17/03/10 05:23:08 INFO mapreduce.Job:  map 100% reduce 63%
17/03/10 05:23:09 INFO mapreduce.Job:  map 100% reduce 70%
17/03/10 05:23:11 INFO mapreduce.Job:  map 100% reduce 72%
17/03/10 05:23:12 INFO mapreduce.Job:  map 100% reduce 75%
17/03/10 05:23:13 INFO mapreduce.Job:  map 100% reduce 77%
17/03/10 05:23:14 INFO mapreduce.Job:  map 100% reduce 79%
17/03/10 05:23:15 INFO mapreduce.Job:  map 100% reduce 82%
17/03/10 05:23:16 INFO mapreduce.Job:  map 100% reduce 84%
17/03/10 05:23:17 INFO mapreduce.Job:  map 100% reduce 85%
17/03/10 05:23:18 INFO mapreduce.Job:  map 100% reduce 87%
17/03/10 05:23:21 INFO mapreduce.Job:  map 100% reduce 88%
17/03/10 05:23:22 INFO mapreduce.Job:  map 100% reduce 89%
17/03/10 05:23:24 INFO mapreduce.Job:  map 100% reduce 92%
17/03/10 05:23:25 INFO mapreduce.Job:  map 100% reduce 94%
17/03/10 05:23:26 INFO mapreduce.Job:  map 100% reduce 96%
17/03/10 05:23:27 INFO mapreduce.Job:  map 100% reduce 98%
17/03/10 05:23:28 INFO mapreduce.Job:  map 100% reduce 99%
17/03/10 05:23:29 INFO mapreduce.Job:  map 100% reduce 100%
17/03/10 05:23:29 INFO mapreduce.Job: Job job_1489140600809_0001 completed successfully
17/03/10 05:23:29 INFO mapreduce.Job: Counters: 50
	File System Counters
		FILE: Number of bytes read=2906452846
		FILE: Number of bytes written=5799732948
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=6553660760
		HDFS: Number of bytes written=6553600000
		HDFS: Number of read operations=1200
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters 
		Launched map tasks=392
		Launched reduce tasks=8
		Data-local map tasks=391
		Rack-local map tasks=1
		Total time spent by all maps in occupied slots (ms)=3457966
		Total time spent by all reduces in occupied slots (ms)=904127
		Total time spent by all map tasks (ms)=3457966
		Total time spent by all reduce tasks (ms)=904127
		Total vcore-seconds taken by all map tasks=3457966
		Total vcore-seconds taken by all reduce tasks=904127
		Total megabyte-seconds taken by all map tasks=3540957184
		Total megabyte-seconds taken by all reduce tasks=925826048
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Map output bytes=6684672000
		Map output materialized bytes=2843186996
		Input split bytes=60760
		Combine input records=0
		Combine output records=0
		Reduce input groups=65536000
		Reduce shuffle bytes=2843186996
		Reduce input records=65536000
		Reduce output records=65536000
		Spilled Records=131072000
		Shuffled Maps =3136
		Failed Shuffles=0
		Merged Map outputs=3136
		GC time elapsed (ms)=42020
		CPU time spent (ms)=1464800
		Physical memory (bytes) snapshot=191514480640
		Virtual memory (bytes) snapshot=630454005760
		Total committed heap usage (bytes)=224901726208
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=6553600000
	File Output Format Counters 
		Bytes Written=6553600000
17/03/10 05:23:29 INFO terasort.TeraSort: done

real	6m40.268s
user	0m9.300s
sys	0m0.355s

```
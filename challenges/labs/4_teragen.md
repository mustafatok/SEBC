## The full teragen command and job output and The result of the time command

```
[neymar@ip-172-31-17-25 ec2-user]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Dmapreduce.job.maps=8 -Ddfs.block.size=16777216 65536000 tgen640
17/03/10 04:36:13 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-17-25.eu-central-1.compute.internal/172.31.17.25:8032
17/03/10 04:36:14 INFO terasort.TeraSort: Generating 65536000 using 8
17/03/10 04:36:14 INFO mapreduce.JobSubmitter: number of splits:8
17/03/10 04:36:14 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/03/10 04:36:14 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1489137340676_0001
17/03/10 04:36:14 INFO impl.YarnClientImpl: Submitted application application_1489137340676_0001
17/03/10 04:36:14 INFO mapreduce.Job: The url to track the job: http://ip-172-31-17-25.eu-central-1.compute.internal:8088/proxy/application_1489137340676_0001/
17/03/10 04:36:14 INFO mapreduce.Job: Running job: job_1489137340676_0001
17/03/10 04:36:22 INFO mapreduce.Job: Job job_1489137340676_0001 running in uber mode : false
17/03/10 04:36:22 INFO mapreduce.Job:  map 0% reduce 0%
17/03/10 04:36:35 INFO mapreduce.Job:  map 5% reduce 0%
17/03/10 04:36:37 INFO mapreduce.Job:  map 15% reduce 0%
17/03/10 04:36:38 INFO mapreduce.Job:  map 18% reduce 0%
17/03/10 04:36:40 INFO mapreduce.Job:  map 23% reduce 0%
17/03/10 04:36:41 INFO mapreduce.Job:  map 25% reduce 0%
17/03/10 04:36:43 INFO mapreduce.Job:  map 28% reduce 0%
17/03/10 04:36:44 INFO mapreduce.Job:  map 30% reduce 0%
17/03/10 04:36:46 INFO mapreduce.Job:  map 31% reduce 0%
17/03/10 04:36:50 INFO mapreduce.Job:  map 32% reduce 0%
17/03/10 04:36:52 INFO mapreduce.Job:  map 33% reduce 0%
17/03/10 04:36:55 INFO mapreduce.Job:  map 34% reduce 0%
17/03/10 04:36:59 INFO mapreduce.Job:  map 35% reduce 0%
17/03/10 04:37:01 INFO mapreduce.Job:  map 43% reduce 0%
17/03/10 04:37:02 INFO mapreduce.Job:  map 46% reduce 0%
17/03/10 04:37:04 INFO mapreduce.Job:  map 50% reduce 0%
17/03/10 04:37:05 INFO mapreduce.Job:  map 52% reduce 0%
17/03/10 04:37:07 INFO mapreduce.Job:  map 56% reduce 0%
17/03/10 04:37:08 INFO mapreduce.Job:  map 57% reduce 0%
17/03/10 04:37:13 INFO mapreduce.Job:  map 59% reduce 0%
17/03/10 04:37:17 INFO mapreduce.Job:  map 60% reduce 0%
17/03/10 04:37:20 INFO mapreduce.Job:  map 61% reduce 0%
17/03/10 04:37:22 INFO mapreduce.Job:  map 65% reduce 0%
17/03/10 04:37:23 INFO mapreduce.Job:  map 67% reduce 0%
17/03/10 04:37:25 INFO mapreduce.Job:  map 72% reduce 0%
17/03/10 04:37:26 INFO mapreduce.Job:  map 73% reduce 0%
17/03/10 04:37:28 INFO mapreduce.Job:  map 76% reduce 0%
17/03/10 04:37:29 INFO mapreduce.Job:  map 77% reduce 0%
17/03/10 04:37:31 INFO mapreduce.Job:  map 80% reduce 0%
17/03/10 04:37:32 INFO mapreduce.Job:  map 82% reduce 0%
17/03/10 04:37:34 INFO mapreduce.Job:  map 86% reduce 0%
17/03/10 04:37:37 INFO mapreduce.Job:  map 87% reduce 0%
17/03/10 04:37:40 INFO mapreduce.Job:  map 89% reduce 0%
17/03/10 04:37:44 INFO mapreduce.Job:  map 90% reduce 0%
17/03/10 04:37:46 INFO mapreduce.Job:  map 91% reduce 0%
17/03/10 04:37:49 INFO mapreduce.Job:  map 92% reduce 0%
17/03/10 04:37:51 INFO mapreduce.Job:  map 93% reduce 0%
17/03/10 04:37:52 INFO mapreduce.Job:  map 97% reduce 0%
17/03/10 04:37:53 INFO mapreduce.Job:  map 100% reduce 0%
17/03/10 04:37:54 INFO mapreduce.Job: Job job_1489137340676_0001 completed successfully
17/03/10 04:37:54 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=983672
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=682
		HDFS: Number of bytes written=6553600000
		HDFS: Number of read operations=32
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters 
		Launched map tasks=8
		Other local map tasks=8
		Total time spent by all maps in occupied slots (ms)=679737
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=679737
		Total vcore-seconds taken by all map tasks=679737
		Total megabyte-seconds taken by all map tasks=696050688
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Input split bytes=682
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1789
		CPU time spent (ms)=138610
		Physical memory (bytes) snapshot=2666258432
		Virtual memory (bytes) snapshot=12612087808
		Total committed heap usage (bytes)=2736783360
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=140750829423462787
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=6553600000

real	1m43.678s
user	0m5.712s
sys	0m0.244s

```

## The command and output of hdfs dfs -ls /user/neymar/tgen640

```
[neymar@ip-172-31-17-25 ec2-user]$ hdfs dfs -ls /user/neymar/tgen640
Found 9 items
-rw-r--r--   3 neymar neymar          0 2017-03-10 04:37 /user/neymar/tgen640/_SUCCESS
-rw-r--r--   3 neymar neymar  819200000 2017-03-10 04:37 /user/neymar/tgen640/part-m-00000
-rw-r--r--   3 neymar neymar  819200000 2017-03-10 04:37 /user/neymar/tgen640/part-m-00001
-rw-r--r--   3 neymar neymar  819200000 2017-03-10 04:37 /user/neymar/tgen640/part-m-00002
-rw-r--r--   3 neymar neymar  819200000 2017-03-10 04:37 /user/neymar/tgen640/part-m-00003
-rw-r--r--   3 neymar neymar  819200000 2017-03-10 04:37 /user/neymar/tgen640/part-m-00004
-rw-r--r--   3 neymar neymar  819200000 2017-03-10 04:37 /user/neymar/tgen640/part-m-00005
-rw-r--r--   3 neymar neymar  819200000 2017-03-10 04:37 /user/neymar/tgen640/part-m-00006
-rw-r--r--   3 neymar neymar  819200000 2017-03-10 04:37 /user/neymar/tgen640/part-m-00007

```

## The command and output to show how many blocks are stored under this directory

```
[neymar@ip-172-31-17-25 ec2-user]$ hdfs fsck /user/neymar/tgen640
Connecting to namenode via http://ip-172-31-17-25.eu-central-1.compute.internal:50070
FSCK started by neymar (auth:SIMPLE) from /172.31.17.25 for path /user/neymar/tgen640 at Fri Mar 10 04:40:50 EST 2017
.........Status: HEALTHY
 Total size:	6553600000 B
 Total dirs:	1
 Total files:	9
 Total symlinks:		0
 Total blocks (validated):	392 (avg. block size 16718367 B)
 Minimally replicated blocks:	392 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Fri Mar 10 04:40:50 EST 2017 in 13 milliseconds


The filesystem under path '/user/neymar/tgen640' is HEALTHY
```

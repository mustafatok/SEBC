
Create an end-user Linux account named with your GitHub handle
```
sudo useradd mustafatok
```

Create a home HDFS directory for this user as well

	I added a user in hue. It created directory when I added user.

Run the following exercises as this user
Create a 10 GB file using teragen
Set the number of mappers to four
Limit the block size to 32 MB
Land the result under your user's home directory
Use the time command to report the job's duration

	First, I tried creating the file but it got stuck because of the space issue, then I increased the volume size from 30g to 100g from AWS console.

```
[mustafatok@ip-172-31-26-193 ec2-user]$ time hadoop jar /opt/cloudera/parcels/CDH-5.8.4-1.cdh5.8.4.p0.5/jars/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=33554432 107374182 /user/mustafatok/teragen_data_10GB
17/03/07 07:24:45 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-26-193.eu-central-1.compute.internal/172.31.26.193:8032
17/03/07 07:24:45 INFO terasort.TeraSort: Generating 107374182 using 4
17/03/07 07:24:45 INFO mapreduce.JobSubmitter: number of splits:4
17/03/07 07:24:45 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/03/07 07:24:45 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/03/07 07:24:46 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1488889251693_0001
17/03/07 07:24:46 INFO impl.YarnClientImpl: Submitted application application_1488889251693_0001
17/03/07 07:24:46 INFO mapreduce.Job: The url to track the job: http://ip-172-31-26-193.eu-central-1.compute.internal:8088/proxy/application_1488889251693_0001/
17/03/07 07:24:46 INFO mapreduce.Job: Running job: job_1488889251693_0001
17/03/07 07:24:52 INFO mapreduce.Job: Job job_1488889251693_0001 running in uber mode : false
17/03/07 07:24:52 INFO mapreduce.Job:  map 0% reduce 0%
17/03/07 07:25:03 INFO mapreduce.Job:  map 3% reduce 0%
17/03/07 07:25:04 INFO mapreduce.Job:  map 12% reduce 0%
17/03/07 07:25:06 INFO mapreduce.Job:  map 13% reduce 0%
17/03/07 07:25:07 INFO mapreduce.Job:  map 16% reduce 0%
17/03/07 07:25:09 INFO mapreduce.Job:  map 17% reduce 0%
17/03/07 07:25:11 INFO mapreduce.Job:  map 19% reduce 0%
17/03/07 07:25:13 INFO mapreduce.Job:  map 20% reduce 0%
17/03/07 07:25:14 INFO mapreduce.Job:  map 21% reduce 0%
17/03/07 07:25:22 INFO mapreduce.Job:  map 22% reduce 0%
17/03/07 07:25:26 INFO mapreduce.Job:  map 23% reduce 0%
17/03/07 07:25:28 INFO mapreduce.Job:  map 24% reduce 0%
17/03/07 07:25:29 INFO mapreduce.Job:  map 29% reduce 0%
17/03/07 07:25:31 INFO mapreduce.Job:  map 30% reduce 0%
17/03/07 07:25:32 INFO mapreduce.Job:  map 33% reduce 0%
17/03/07 07:25:35 INFO mapreduce.Job:  map 34% reduce 0%
17/03/07 07:25:44 INFO mapreduce.Job:  map 35% reduce 0%
17/03/07 07:25:47 INFO mapreduce.Job:  map 37% reduce 0%
17/03/07 07:25:49 INFO mapreduce.Job:  map 38% reduce 0%
17/03/07 07:25:50 INFO mapreduce.Job:  map 39% reduce 0%
17/03/07 07:25:53 INFO mapreduce.Job:  map 40% reduce 0%
17/03/07 07:26:02 INFO mapreduce.Job:  map 41% reduce 0%
17/03/07 07:26:04 INFO mapreduce.Job:  map 42% reduce 0%
17/03/07 07:26:05 INFO mapreduce.Job:  map 43% reduce 0%
17/03/07 07:26:07 INFO mapreduce.Job:  map 44% reduce 0%
17/03/07 07:26:08 INFO mapreduce.Job:  map 50% reduce 0%
17/03/07 07:26:10 INFO mapreduce.Job:  map 51% reduce 0%
17/03/07 07:26:11 INFO mapreduce.Job:  map 53% reduce 0%
17/03/07 07:26:13 INFO mapreduce.Job:  map 54% reduce 0%
17/03/07 07:26:14 INFO mapreduce.Job:  map 55% reduce 0%
17/03/07 07:26:26 INFO mapreduce.Job:  map 57% reduce 0%
17/03/07 07:26:28 INFO mapreduce.Job:  map 58% reduce 0%
17/03/07 07:26:29 INFO mapreduce.Job:  map 62% reduce 0%
17/03/07 07:26:31 INFO mapreduce.Job:  map 63% reduce 0%
17/03/07 07:26:32 INFO mapreduce.Job:  map 67% reduce 0%
17/03/07 07:26:35 INFO mapreduce.Job:  map 69% reduce 0%
17/03/07 07:26:38 INFO mapreduce.Job:  map 71% reduce 0%
17/03/07 07:26:41 INFO mapreduce.Job:  map 72% reduce 0%
17/03/07 07:26:43 INFO mapreduce.Job:  map 73% reduce 0%
17/03/07 07:26:50 INFO mapreduce.Job:  map 74% reduce 0%
17/03/07 07:26:56 INFO mapreduce.Job:  map 75% reduce 0%
17/03/07 07:26:59 INFO mapreduce.Job:  map 79% reduce 0%
17/03/07 07:27:01 INFO mapreduce.Job:  map 81% reduce 0%
17/03/07 07:27:02 INFO mapreduce.Job:  map 83% reduce 0%
17/03/07 07:27:05 INFO mapreduce.Job:  map 85% reduce 0%
17/03/07 07:27:14 INFO mapreduce.Job:  map 86% reduce 0%
17/03/07 07:27:16 INFO mapreduce.Job:  map 88% reduce 0%
17/03/07 07:27:17 INFO mapreduce.Job:  map 92% reduce 0%
17/03/07 07:27:20 INFO mapreduce.Job:  map 94% reduce 0%
17/03/07 07:27:22 INFO mapreduce.Job:  map 95% reduce 0%
17/03/07 07:27:23 INFO mapreduce.Job:  map 96% reduce 0%
17/03/07 07:27:25 INFO mapreduce.Job:  map 97% reduce 0%
17/03/07 07:27:35 INFO mapreduce.Job:  map 100% reduce 0%
17/03/07 07:27:39 INFO mapreduce.Job: Job job_1488889251693_0001 completed successfully
17/03/07 07:27:40 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=491172
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=344
		HDFS: Number of bytes written=10737418200
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=632511
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=632511
		Total vcore-seconds taken by all map tasks=632511
		Total megabyte-seconds taken by all map tasks=647691264
	Map-Reduce Framework
		Map input records=107374182
		Map output records=107374182
		Input split bytes=344
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1241
		CPU time spent (ms)=166890
		Physical memory (bytes) snapshot=702537728
		Virtual memory (bytes) snapshot=6277226496
		Total committed heap usage (bytes)=853540864
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=230593859918397906
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=10737418200

real	2m57.288s
user	0m6.128s
sys	0m0.265s

```

Run the terasort command on this file
Use the time command to report the job's duration
Land the result under your user's home directory
```
[mustafatok@ip-172-31-26-193 ec2-user]$ time hadoop jar /opt/cloudera/parcels/CDH-5.8.4-1.cdh5.8.4.p0.5/jars/hadoop-examples.jar terasort /user/mustafatok/teragen_data_10GB /user/mustafatok/terasort_data_10GB
17/03/07 07:45:29 INFO terasort.TeraSort: starting
17/03/07 07:45:31 INFO input.FileInputFormat: Total input paths to process : 4
Spent 290ms computing base-splits.
Spent 5ms computing TeraScheduler splits.
Computing input splits took 295ms
Sampling 10 splits of 320
Making 8 from 100000 sampled records
Computing parititions took 1126ms
Spent 1424ms computing partitions.
17/03/07 07:45:32 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-26-193.eu-central-1.compute.internal/172.31.26.193:8032
17/03/07 07:45:33 INFO mapreduce.JobSubmitter: number of splits:320
17/03/07 07:45:33 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1488889251693_0002
17/03/07 07:45:33 INFO impl.YarnClientImpl: Submitted application application_1488889251693_0002
17/03/07 07:45:33 INFO mapreduce.Job: The url to track the job: http://ip-172-31-26-193.eu-central-1.compute.internal:8088/proxy/application_1488889251693_0002/
17/03/07 07:45:33 INFO mapreduce.Job: Running job: job_1488889251693_0002
17/03/07 07:45:39 INFO mapreduce.Job: Job job_1488889251693_0002 running in uber mode : false
17/03/07 07:45:39 INFO mapreduce.Job:  map 0% reduce 0%
17/03/07 07:45:47 INFO mapreduce.Job:  map 1% reduce 0%
17/03/07 07:45:49 INFO mapreduce.Job:  map 2% reduce 0%
17/03/07 07:45:50 INFO mapreduce.Job:  map 3% reduce 0%
17/03/07 07:45:52 INFO mapreduce.Job:  map 4% reduce 0%
17/03/07 07:46:00 INFO mapreduce.Job:  map 6% reduce 0%
17/03/07 07:46:01 INFO mapreduce.Job:  map 7% reduce 0%
17/03/07 07:46:05 INFO mapreduce.Job:  map 8% reduce 0%
17/03/07 07:46:09 INFO mapreduce.Job:  map 9% reduce 0%
17/03/07 07:46:10 INFO mapreduce.Job:  map 11% reduce 0%
17/03/07 07:46:16 INFO mapreduce.Job:  map 12% reduce 0%
17/03/07 07:46:17 INFO mapreduce.Job:  map 13% reduce 0%
17/03/07 07:46:20 INFO mapreduce.Job:  map 14% reduce 0%
17/03/07 07:46:22 INFO mapreduce.Job:  map 15% reduce 0%
17/03/07 07:46:27 INFO mapreduce.Job:  map 16% reduce 0%
17/03/07 07:46:28 INFO mapreduce.Job:  map 17% reduce 0%
17/03/07 07:46:29 INFO mapreduce.Job:  map 19% reduce 0%
17/03/07 07:46:36 INFO mapreduce.Job:  map 20% reduce 0%
17/03/07 07:46:37 INFO mapreduce.Job:  map 21% reduce 0%
17/03/07 07:46:38 INFO mapreduce.Job:  map 22% reduce 0%
17/03/07 07:46:44 INFO mapreduce.Job:  map 23% reduce 0%
17/03/07 07:46:47 INFO mapreduce.Job:  map 24% reduce 0%
17/03/07 07:46:48 INFO mapreduce.Job:  map 25% reduce 0%
17/03/07 07:46:51 INFO mapreduce.Job:  map 26% reduce 0%
17/03/07 07:46:52 INFO mapreduce.Job:  map 27% reduce 0%
17/03/07 07:46:56 INFO mapreduce.Job:  map 28% reduce 0%
17/03/07 07:46:57 INFO mapreduce.Job:  map 29% reduce 0%
17/03/07 07:47:01 INFO mapreduce.Job:  map 30% reduce 0%
17/03/07 07:47:04 INFO mapreduce.Job:  map 31% reduce 0%
17/03/07 07:47:05 INFO mapreduce.Job:  map 32% reduce 0%
17/03/07 07:47:06 INFO mapreduce.Job:  map 33% reduce 0%
17/03/07 07:47:12 INFO mapreduce.Job:  map 34% reduce 0%
17/03/07 07:47:14 INFO mapreduce.Job:  map 35% reduce 0%
17/03/07 07:47:15 INFO mapreduce.Job:  map 36% reduce 0%
17/03/07 07:47:16 INFO mapreduce.Job:  map 37% reduce 0%
17/03/07 07:47:19 INFO mapreduce.Job:  map 38% reduce 0%
17/03/07 07:47:23 INFO mapreduce.Job:  map 39% reduce 0%
17/03/07 07:47:25 INFO mapreduce.Job:  map 40% reduce 0%
17/03/07 07:47:27 INFO mapreduce.Job:  map 41% reduce 0%
17/03/07 07:47:30 INFO mapreduce.Job:  map 42% reduce 0%
17/03/07 07:47:34 INFO mapreduce.Job:  map 43% reduce 0%
17/03/07 07:47:35 INFO mapreduce.Job:  map 44% reduce 0%
17/03/07 07:47:39 INFO mapreduce.Job:  map 45% reduce 0%
17/03/07 07:47:40 INFO mapreduce.Job:  map 46% reduce 0%
17/03/07 07:47:41 INFO mapreduce.Job:  map 47% reduce 0%
17/03/07 07:47:46 INFO mapreduce.Job:  map 48% reduce 0%
17/03/07 07:47:48 INFO mapreduce.Job:  map 49% reduce 0%
17/03/07 07:47:49 INFO mapreduce.Job:  map 50% reduce 0%
17/03/07 07:47:51 INFO mapreduce.Job:  map 51% reduce 0%
17/03/07 07:47:54 INFO mapreduce.Job:  map 52% reduce 0%
17/03/07 07:47:59 INFO mapreduce.Job:  map 53% reduce 0%
17/03/07 07:48:00 INFO mapreduce.Job:  map 54% reduce 0%
17/03/07 07:48:01 INFO mapreduce.Job:  map 55% reduce 0%
17/03/07 07:48:03 INFO mapreduce.Job:  map 56% reduce 0%
17/03/07 07:48:07 INFO mapreduce.Job:  map 57% reduce 0%
17/03/07 07:48:09 INFO mapreduce.Job:  map 58% reduce 0%
17/03/07 07:48:11 INFO mapreduce.Job:  map 59% reduce 0%
17/03/07 07:48:16 INFO mapreduce.Job:  map 60% reduce 0%
17/03/07 07:48:17 INFO mapreduce.Job:  map 61% reduce 0%
17/03/07 07:48:20 INFO mapreduce.Job:  map 62% reduce 0%
17/03/07 07:48:23 INFO mapreduce.Job:  map 63% reduce 0%
17/03/07 07:48:25 INFO mapreduce.Job:  map 64% reduce 0%
17/03/07 07:48:26 INFO mapreduce.Job:  map 65% reduce 0%
17/03/07 07:48:29 INFO mapreduce.Job:  map 66% reduce 0%
17/03/07 07:48:31 INFO mapreduce.Job:  map 67% reduce 0%
17/03/07 07:48:35 INFO mapreduce.Job:  map 68% reduce 0%
17/03/07 07:48:37 INFO mapreduce.Job:  map 69% reduce 0%
17/03/07 07:48:38 INFO mapreduce.Job:  map 70% reduce 0%
17/03/07 07:48:43 INFO mapreduce.Job:  map 71% reduce 0%
17/03/07 07:48:44 INFO mapreduce.Job:  map 72% reduce 0%
17/03/07 07:48:46 INFO mapreduce.Job:  map 73% reduce 0%
17/03/07 07:48:47 INFO mapreduce.Job:  map 74% reduce 0%
17/03/07 07:48:51 INFO mapreduce.Job:  map 75% reduce 0%
17/03/07 07:48:53 INFO mapreduce.Job:  map 76% reduce 0%
17/03/07 07:48:56 INFO mapreduce.Job:  map 77% reduce 0%
17/03/07 07:48:58 INFO mapreduce.Job:  map 78% reduce 0%
17/03/07 07:49:02 INFO mapreduce.Job:  map 79% reduce 0%
17/03/07 07:49:05 INFO mapreduce.Job:  map 80% reduce 0%
17/03/07 07:49:06 INFO mapreduce.Job:  map 81% reduce 0%
17/03/07 07:49:09 INFO mapreduce.Job:  map 82% reduce 0%
17/03/07 07:49:13 INFO mapreduce.Job:  map 83% reduce 0%
17/03/07 07:49:14 INFO mapreduce.Job:  map 84% reduce 0%
17/03/07 07:49:15 INFO mapreduce.Job:  map 85% reduce 0%
17/03/07 07:49:20 INFO mapreduce.Job:  map 85% reduce 2%
17/03/07 07:49:22 INFO mapreduce.Job:  map 85% reduce 3%
17/03/07 07:49:23 INFO mapreduce.Job:  map 85% reduce 6%
17/03/07 07:49:24 INFO mapreduce.Job:  map 86% reduce 11%
17/03/07 07:49:25 INFO mapreduce.Job:  map 86% reduce 12%
17/03/07 07:49:26 INFO mapreduce.Job:  map 86% reduce 14%
17/03/07 07:49:28 INFO mapreduce.Job:  map 86% reduce 17%
17/03/07 07:49:29 INFO mapreduce.Job:  map 86% reduce 19%
17/03/07 07:49:30 INFO mapreduce.Job:  map 86% reduce 20%
17/03/07 07:49:31 INFO mapreduce.Job:  map 87% reduce 20%
17/03/07 07:49:32 INFO mapreduce.Job:  map 87% reduce 21%
17/03/07 07:49:33 INFO mapreduce.Job:  map 87% reduce 22%
17/03/07 07:49:34 INFO mapreduce.Job:  map 88% reduce 23%
17/03/07 07:49:35 INFO mapreduce.Job:  map 88% reduce 24%
17/03/07 07:49:38 INFO mapreduce.Job:  map 88% reduce 26%
17/03/07 07:49:43 INFO mapreduce.Job:  map 89% reduce 26%
17/03/07 07:49:44 INFO mapreduce.Job:  map 90% reduce 26%
17/03/07 07:49:50 INFO mapreduce.Job:  map 91% reduce 26%
17/03/07 07:49:53 INFO mapreduce.Job:  map 91% reduce 27%
17/03/07 07:49:54 INFO mapreduce.Job:  map 92% reduce 27%
17/03/07 07:50:00 INFO mapreduce.Job:  map 93% reduce 27%
17/03/07 07:50:07 INFO mapreduce.Job:  map 94% reduce 27%
17/03/07 07:50:09 INFO mapreduce.Job:  map 95% reduce 27%
17/03/07 07:50:11 INFO mapreduce.Job:  map 95% reduce 28%
17/03/07 07:50:14 INFO mapreduce.Job:  map 96% reduce 28%
17/03/07 07:50:19 INFO mapreduce.Job:  map 97% reduce 28%
17/03/07 07:50:23 INFO mapreduce.Job:  map 98% reduce 28%
17/03/07 07:50:26 INFO mapreduce.Job:  map 98% reduce 29%
17/03/07 07:50:28 INFO mapreduce.Job:  map 99% reduce 29%
17/03/07 07:50:32 INFO mapreduce.Job:  map 100% reduce 29%
17/03/07 07:50:38 INFO mapreduce.Job:  map 100% reduce 38%
17/03/07 07:50:39 INFO mapreduce.Job:  map 100% reduce 46%
17/03/07 07:50:40 INFO mapreduce.Job:  map 100% reduce 49%
17/03/07 07:50:41 INFO mapreduce.Job:  map 100% reduce 61%
17/03/07 07:50:42 INFO mapreduce.Job:  map 100% reduce 62%
17/03/07 07:50:44 INFO mapreduce.Job:  map 100% reduce 65%
17/03/07 07:50:45 INFO mapreduce.Job:  map 100% reduce 67%
17/03/07 07:50:47 INFO mapreduce.Job:  map 100% reduce 70%
17/03/07 07:50:48 INFO mapreduce.Job:  map 100% reduce 72%
17/03/07 07:50:49 INFO mapreduce.Job:  map 100% reduce 75%
17/03/07 07:50:50 INFO mapreduce.Job:  map 100% reduce 78%
17/03/07 07:50:51 INFO mapreduce.Job:  map 100% reduce 80%
17/03/07 07:50:52 INFO mapreduce.Job:  map 100% reduce 81%
17/03/07 07:50:53 INFO mapreduce.Job:  map 100% reduce 84%
17/03/07 07:50:54 INFO mapreduce.Job:  map 100% reduce 86%
17/03/07 07:50:55 INFO mapreduce.Job:  map 100% reduce 87%
17/03/07 07:50:56 INFO mapreduce.Job:  map 100% reduce 89%
17/03/07 07:50:57 INFO mapreduce.Job:  map 100% reduce 91%
17/03/07 07:50:58 INFO mapreduce.Job:  map 100% reduce 92%
17/03/07 07:50:59 INFO mapreduce.Job:  map 100% reduce 93%
17/03/07 07:51:01 INFO mapreduce.Job:  map 100% reduce 94%
17/03/07 07:51:02 INFO mapreduce.Job:  map 100% reduce 95%
17/03/07 07:51:03 INFO mapreduce.Job:  map 100% reduce 96%
17/03/07 07:51:05 INFO mapreduce.Job:  map 100% reduce 97%
17/03/07 07:51:08 INFO mapreduce.Job:  map 100% reduce 98%
17/03/07 07:51:11 INFO mapreduce.Job:  map 100% reduce 100%
17/03/07 07:51:13 INFO mapreduce.Job: Job job_1488889251693_0002 completed successfully
17/03/07 07:51:14 INFO mapreduce.Job: Counters: 50
	File System Counters
		FILE: Number of bytes read=4775423707
		FILE: Number of bytes written=9479070044
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=10737472600
		HDFS: Number of bytes written=10737418200
		HDFS: Number of read operations=984
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters 
		Launched map tasks=320
		Launched reduce tasks=8
		Data-local map tasks=319
		Rack-local map tasks=1
		Total time spent by all maps in occupied slots (ms)=2568359
		Total time spent by all reduces in occupied slots (ms)=815290
		Total time spent by all map tasks (ms)=2568359
		Total time spent by all reduce tasks (ms)=815290
		Total vcore-seconds taken by all map tasks=2568359
		Total vcore-seconds taken by all reduce tasks=815290
		Total megabyte-seconds taken by all map tasks=2629999616
		Total megabyte-seconds taken by all reduce tasks=834856960
	Map-Reduce Framework
		Map input records=107374182
		Map output records=107374182
		Map output bytes=10952166564
		Map output materialized bytes=4662863455
		Input split bytes=54400
		Combine input records=0
		Combine output records=0
		Reduce input groups=107374182
		Reduce shuffle bytes=4662863455
		Reduce input records=107374182
		Reduce output records=107374182
		Spilled Records=214748364
		Shuffled Maps =2560
		Failed Shuffles=0
		Merged Map outputs=2560
		GC time elapsed (ms)=36758
		CPU time spent (ms)=1469090
		Physical memory (bytes) snapshot=161684701184
		Virtual memory (bytes) snapshot=517166759936
		Total committed heap usage (bytes)=184145149952
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=10737418200
	File Output Format Counters 
		Bytes Written=10737418200
17/03/07 07:51:14 INFO terasort.TeraSort: done

real	5m45.159s
user	0m9.827s
sys	0m0.338s
```
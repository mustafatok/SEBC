##Create a precious directory in HDFS; copy the ZIP course file into it.

I created precious directory via command line.

```
[mustafatok@ip-172-31-26-193 ec2-user]$ hdfs dfs -mkdir /user/mustafatok/precious
[mustafatok@ip-172-31-26-193 ec2-user]$ hdfs dfs -ls /user/mustafatok/
Found 8 items
drwx------   - mustafatok mustafatok          0 2017-03-07 10:15 /user/mustafatok/.Trash
-rw-r--r--   3 mustafatok mustafatok          0 2017-03-07 10:10 /user/mustafatok/.distcp.tmp.attempt_1488889251693_0006_m_000000_0
drwx------   - mustafatok mustafatok          0 2017-03-07 10:10 /user/mustafatok/.staging
drwxr-xr-x   - mustafatok mustafatok          0 2017-03-07 10:16 /user/mustafatok/precious
drwxr-xr-x   - mustafatok mustafatok          0 2017-03-07 05:25 /user/mustafatok/source
drwxr-xr-x   - mustafatok mustafatok          0 2017-03-07 10:10 /user/mustafatok/target
drwxr-xr-x   - mustafatok mustafatok          0 2017-03-07 07:27 /user/mustafatok/teragen_data_10GB
drwxr-xr-x   - mustafatok mustafatok          0 2017-03-07 07:51 /user/mustafatok/terasort_data_10GB
```

I uploaded zip file using hue. 

```
[mustafatok@ip-172-31-26-193 ec2-user]$ hdfs dfs -ls /user/mustafatok/precious
Found 1 items
-rw-r--r--   3 mustafatok mustafatok     415069 2017-03-07 10:21 /user/mustafatok/precious/SEBC.zip
```

##Enable snapshots for precious

From Cloudera Manager, I went into Clusters/HDFS/File Browser and found /user/mustafatok/precious. Then clicked Enable Snapshots.

##Create a snapshot called sebc-hdfs-test

The same page in previous step, I clicked on take Snapshot and gave the name sebc-hdfs-test

##Delete the directory
##Delete the ZIP file

I managed to delete zip file, but I couldn't delete directory because directory is snapshottable and already has snapshots. Here are the commands and outputs:

```
[mustafatok@ip-172-31-26-193 ec2-user]$ hdfs dfs -rm -r /user/mustafatok/precious
rm: Failed to move to trash: hdfs://ip-172-31-26-193.eu-central-1.compute.internal:8020/user/mustafatok/precious: The directory /user/mustafatok/precious cannot be deleted since /user/mustafatok/precious is snapshottable and already has snapshots
[mustafatok@ip-172-31-26-193 ec2-user]$ hdfs dfs -rm -r /user/mustafatok/precious/SEBC.zip
17/03/07 10:27:57 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-26-193.eu-central-1.compute.internal:8020/user/mustafatok/precious/SEBC.zip' to trash at: hdfs://ip-172-31-26-193.eu-central-1.compute.internal:8020/user/mustafatok/.Trash/Current/user/mustafatok/precious/SEBC.zip1488900477892
[mustafatok@ip-172-31-26-193 ec2-user]$ hdfs dfs -ls /user/mustafatok/precious
[mustafatok@ip-172-31-26-193 ec2-user]$ hdfs dfs -rm -r /user/mustafatok/precious
rm: Failed to move to trash: hdfs://ip-172-31-26-193.eu-central-1.compute.internal:8020/user/mustafatok/precious: The directory /user/mustafatok/precious cannot be deleted since /user/mustafatok/precious is snapshottable and already has snapshots
```

##Restore the deleted file

Again from Clusters/HDFS/File Browser and found /user/mustafatok/precious, I clicked restore from snapshot.
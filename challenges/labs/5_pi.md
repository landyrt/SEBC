Run the Hadoop pi program as user haley
Copy the command and full output to challenges/labs/5_pi.md

```sh

[ec2-user@ip-172-31-19-21 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar pi 2 1000
Number of Maps  = 2
Samples per Map = 1000
Wrote input for Map #0
Wrote input for Map #1
Starting Job
17/12/01 13:26:16 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-30-64.ec2.internal/172.31.30.64:8032
17/12/01 13:26:16 INFO hdfs.DFSClient: Created token for haley: HDFS_DELEGATION_TOKEN owner=haley@LANDYRT.HQ, renewer=yarn, realUser=, issueDate=1512156376607, maxDate=1512761176607, sequenceNumber=5, masterKeyId=2 on 172.31.30.64:8020
17/12/01 13:26:16 INFO security.TokenCache: Got dt for hdfs://ip-172-31-30-64.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.30.64:8020, Ident: (token for haley: HDFS_DELEGATION_TOKEN owner=haley@LANDYRT.HQ, renewer=yarn, realUser=, issueDate=1512156376607, maxDate=1512761176607, sequenceNumber=5, masterKeyId=2)
17/12/01 13:26:16 INFO input.FileInputFormat: Total input paths to process : 2
17/12/01 13:26:16 INFO mapreduce.JobSubmitter: number of splits:2
17/12/01 13:26:16 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512154664706_0005
17/12/01 13:26:16 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.30.64:8020, Ident: (token for haley: HDFS_DELEGATION_TOKEN owner=haley@LANDYRT.HQ, renewer=yarn, realUser=, issueDate=1512156376607, maxDate=1512761176607, sequenceNumber=5, masterKeyId=2)
17/12/01 13:26:17 INFO impl.YarnClientImpl: Submitted application application_1512154664706_0005
17/12/01 13:26:17 INFO mapreduce.Job: The url to track the job: http://ip-172-31-30-64.ec2.internal:8088/proxy/application_1512154664706_0005/
17/12/01 13:26:17 INFO mapreduce.Job: Running job: job_1512154664706_0005
17/12/01 13:26:24 INFO mapreduce.Job: Job job_1512154664706_0005 running in uber mode : false
17/12/01 13:26:24 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 13:26:30 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 13:26:37 INFO mapreduce.Job:  map 100% reduce 100%
17/12/01 13:26:37 INFO mapreduce.Job: Job job_1512154664706_0005 completed successfully
17/12/01 13:26:37 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=50
		FILE: Number of bytes written=372246
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=564
		HDFS: Number of bytes written=215
		HDFS: Number of read operations=11
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=3
	Job Counters 
		Launched map tasks=2
		Launched reduce tasks=1
		Data-local map tasks=2
		Total time spent by all maps in occupied slots (ms)=6997
		Total time spent by all reduces in occupied slots (ms)=4807
		Total time spent by all map tasks (ms)=6997
		Total time spent by all reduce tasks (ms)=4807
		Total vcore-seconds taken by all map tasks=6997
		Total vcore-seconds taken by all reduce tasks=4807
		Total megabyte-seconds taken by all map tasks=7164928
		Total megabyte-seconds taken by all reduce tasks=4922368
	Map-Reduce Framework
		Map input records=2
		Map output records=4
		Map output bytes=36
		Map output materialized bytes=68
		Input split bytes=328
		Combine input records=0
		Combine output records=0
		Reduce input groups=2
		Reduce shuffle bytes=68
		Reduce input records=4
		Reduce output records=0
		Spilled Records=8
		Shuffled Maps =2
		Failed Shuffles=0
		Merged Map outputs=2
		GC time elapsed (ms)=39
		CPU time spent (ms)=2280
		Physical memory (bytes) snapshot=1261576192
		Virtual memory (bytes) snapshot=4821204992
		Total committed heap usage (bytes)=1509949440
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=236
	File Output Format Counters 
		Bytes Written=97
Job Finished in 21.343 seconds
Estimated value of Pi is 3.14400000000000000000

real	0m23.774s
user	0m4.567s
sys	0m0.268s

```

Copy the configuration files in /var/kerberos/krb5kdc/ to your repo:
Add the prefix 5_ and the suffix .md to the original file name
Example: 5_kdc.conf.md

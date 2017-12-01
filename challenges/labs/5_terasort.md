
Run the terasort program as user saturn with the output target /user/saturn/tsort
Generate 10,000,000 records

```sh

[ec2-user@ip-172-31-19-21 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=33554432 10000000 /user/saturn/tgen2
17/12/01 13:16:57 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-30-64.ec2.internal/172.31.30.64:8032
17/12/01 13:16:57 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@LANDYRT.HQ, renewer=yarn, realUser=, issueDate=1512155817722, maxDate=1512760617722, sequenceNumber=3, masterKeyId=2 on 172.31.30.64:8020
17/12/01 13:16:57 INFO security.TokenCache: Got dt for hdfs://ip-172-31-30-64.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.30.64:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@LANDYRT.HQ, renewer=yarn, realUser=, issueDate=1512155817722, maxDate=1512760617722, sequenceNumber=3, masterKeyId=2)
17/12/01 13:16:58 INFO terasort.TeraSort: Generating 10000000 using 4
17/12/01 13:16:58 INFO mapreduce.JobSubmitter: number of splits:4
17/12/01 13:16:58 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/12/01 13:16:58 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/12/01 13:16:58 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512154664706_0003
17/12/01 13:16:58 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.30.64:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@LANDYRT.HQ, renewer=yarn, realUser=, issueDate=1512155817722, maxDate=1512760617722, sequenceNumber=3, masterKeyId=2)
17/12/01 13:16:58 INFO impl.YarnClientImpl: Submitted application application_1512154664706_0003
17/12/01 13:16:58 INFO mapreduce.Job: The url to track the job: http://ip-172-31-30-64.ec2.internal:8088/proxy/application_1512154664706_0003/
17/12/01 13:16:58 INFO mapreduce.Job: Running job: job_1512154664706_0003
17/12/01 13:17:05 INFO mapreduce.Job: Job job_1512154664706_0003 running in uber mode : false
17/12/01 13:17:05 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 13:17:20 INFO mapreduce.Job:  map 60% reduce 0%
17/12/01 13:17:21 INFO mapreduce.Job:  map 79% reduce 0%
17/12/01 13:17:22 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 13:17:23 INFO mapreduce.Job: Job job_1512154664706_0003 completed successfully
17/12/01 13:17:23 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=493576
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=337
		HDFS: Number of bytes written=1000000000
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=56320
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=56320
		Total vcore-seconds taken by all map tasks=56320
		Total megabyte-seconds taken by all map tasks=57671680
	Map-Reduce Framework
		Map input records=10000000
		Map output records=10000000
		Input split bytes=337
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=470
		CPU time spent (ms)=28430
		Physical memory (bytes) snapshot=1463070720
		Virtual memory (bytes) snapshot=6365536256
		Total committed heap usage (bytes)=2418016256
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=21472776955442690
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=1000000000

real	0m27.786s
user	0m4.479s
sys	0m0.258s

```

Copy the command and full output to challenges/labs/5_terasort.md

```sh

[ec2-user@ip-172-31-19-21 ~]$ /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/saturn/tgen2 /user/saturn/tsort 
-bash: /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar: Permission denied
[ec2-user@ip-172-31-19-21 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/saturn/tgen2/* /user/saturn/tsort 
17/12/01 13:22:21 INFO terasort.TeraSort: starting
17/12/01 13:22:22 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@LANDYRT.HQ, renewer=yarn, realUser=, issueDate=1512156142221, maxDate=1512760942221, sequenceNumber=4, masterKeyId=2 on 172.31.30.64:8020
17/12/01 13:22:22 INFO security.TokenCache: Got dt for hdfs://ip-172-31-30-64.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.30.64:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@LANDYRT.HQ, renewer=yarn, realUser=, issueDate=1512156142221, maxDate=1512760942221, sequenceNumber=4, masterKeyId=2)
17/12/01 13:22:22 INFO input.FileInputFormat: Total input paths to process : 4
Spent 253ms computing base-splits.
Spent 3ms computing TeraScheduler splits.
Computing input splits took 257ms
Sampling 10 splits of 32
Making 16 from 100000 sampled records
Computing parititions took 531ms
Spent 790ms computing partitions.
17/12/01 13:22:22 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-30-64.ec2.internal/172.31.30.64:8032
17/12/01 13:22:23 INFO mapreduce.JobSubmitter: number of splits:32
17/12/01 13:22:23 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512154664706_0004
17/12/01 13:22:23 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.30.64:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@LANDYRT.HQ, renewer=yarn, realUser=, issueDate=1512156142221, maxDate=1512760942221, sequenceNumber=4, masterKeyId=2)
17/12/01 13:22:23 INFO impl.YarnClientImpl: Submitted application application_1512154664706_0004
17/12/01 13:22:23 INFO mapreduce.Job: The url to track the job: http://ip-172-31-30-64.ec2.internal:8088/proxy/application_1512154664706_0004/
17/12/01 13:22:23 INFO mapreduce.Job: Running job: job_1512154664706_0004
17/12/01 13:22:31 INFO mapreduce.Job: Job job_1512154664706_0004 running in uber mode : false
17/12/01 13:22:31 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 13:22:42 INFO mapreduce.Job:  map 25% reduce 0%
17/12/01 13:22:43 INFO mapreduce.Job:  map 34% reduce 0%
17/12/01 13:22:47 INFO mapreduce.Job:  map 38% reduce 0%
17/12/01 13:22:48 INFO mapreduce.Job:  map 72% reduce 0%
17/12/01 13:22:49 INFO mapreduce.Job:  map 75% reduce 0%
17/12/01 13:22:50 INFO mapreduce.Job:  map 78% reduce 0%
17/12/01 13:22:51 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 13:22:59 INFO mapreduce.Job:  map 100% reduce 38%
17/12/01 13:23:01 INFO mapreduce.Job:  map 100% reduce 50%
17/12/01 13:23:02 INFO mapreduce.Job:  map 100% reduce 100%
17/12/01 13:23:02 INFO mapreduce.Job: Job job_1512154664706_0004 completed successfully
17/12/01 13:23:02 INFO mapreduce.Job: Counters: 50
	File System Counters
		FILE: Number of bytes read=439895400
		FILE: Number of bytes written=879959979
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=1000004352
		HDFS: Number of bytes written=1000000000
		HDFS: Number of read operations=144
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=32
	Job Counters 
		Launched map tasks=32
		Launched reduce tasks=16
		Data-local map tasks=30
		Rack-local map tasks=2
		Total time spent by all maps in occupied slots (ms)=391357
		Total time spent by all reduces in occupied slots (ms)=119403
		Total time spent by all map tasks (ms)=391357
		Total time spent by all reduce tasks (ms)=119403
		Total vcore-seconds taken by all map tasks=391357
		Total vcore-seconds taken by all reduce tasks=119403
		Total megabyte-seconds taken by all map tasks=400749568
		Total megabyte-seconds taken by all reduce tasks=122268672
	Map-Reduce Framework
		Map input records=10000000
		Map output records=10000000
		Map output bytes=1020000000
		Map output materialized bytes=434068551
		Input split bytes=4352
		Combine input records=0
		Combine output records=0
		Reduce input groups=10000000
		Reduce shuffle bytes=434068551
		Reduce input records=10000000
		Reduce output records=10000000
		Spilled Records=20000000
		Shuffled Maps =512
		Failed Shuffles=0
		Merged Map outputs=512
		GC time elapsed (ms)=3576
		CPU time spent (ms)=189620
		Physical memory (bytes) snapshot=22202421248
		Virtual memory (bytes) snapshot=76660572160
		Total committed heap usage (bytes)=25142755328
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=1000000000
	File Output Format Counters 
		Bytes Written=1000000000
17/12/01 13:23:02 INFO terasort.TeraSort: done

real	0m42.266s
user	0m6.410s
sys	0m0.299s

```







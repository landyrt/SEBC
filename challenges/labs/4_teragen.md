The full teragen command and output
The result of the time command

```sh

[saturn@ip-172-31-30-64 cloudera-scm-server]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=12 -Ddfs.block.size=33554432 -Dmapreduce.map.memory.mb=512 65536000 /user/saturn/tgen
17/12/01 12:07:41 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-30-64.ec2.internal/172.31.30.64:8032
17/12/01 12:07:41 INFO terasort.TeraSort: Generating 65536000 using 12
17/12/01 12:07:41 INFO mapreduce.JobSubmitter: number of splits:12
17/12/01 12:07:41 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/12/01 12:07:41 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/12/01 12:07:41 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1512150105336_0002
17/12/01 12:07:42 INFO impl.YarnClientImpl: Submitted application application_1512150105336_0002
17/12/01 12:07:42 INFO mapreduce.Job: The url to track the job: http://ip-172-31-30-64.ec2.internal:8088/proxy/application_1512150105336_0002/
17/12/01 12:07:42 INFO mapreduce.Job: Running job: job_1512150105336_0002
17/12/01 12:07:47 INFO mapreduce.Job: Job job_1512150105336_0002 running in uber mode : false
17/12/01 12:07:47 INFO mapreduce.Job:  map 0% reduce 0%
17/12/01 12:07:58 INFO mapreduce.Job:  map 8% reduce 0%
17/12/01 12:07:59 INFO mapreduce.Job:  map 10% reduce 0%
17/12/01 12:08:00 INFO mapreduce.Job:  map 21% reduce 0%
17/12/01 12:08:01 INFO mapreduce.Job:  map 22% reduce 0%
17/12/01 12:08:03 INFO mapreduce.Job:  map 27% reduce 0%
17/12/01 12:08:04 INFO mapreduce.Job:  map 28% reduce 0%
17/12/01 12:08:05 INFO mapreduce.Job:  map 29% reduce 0%
17/12/01 12:08:06 INFO mapreduce.Job:  map 36% reduce 0%
17/12/01 12:08:07 INFO mapreduce.Job:  map 37% reduce 0%
17/12/01 12:08:09 INFO mapreduce.Job:  map 43% reduce 0%
17/12/01 12:08:10 INFO mapreduce.Job:  map 44% reduce 0%
17/12/01 12:08:12 INFO mapreduce.Job:  map 51% reduce 0%
17/12/01 12:08:13 INFO mapreduce.Job:  map 52% reduce 0%
17/12/01 12:08:15 INFO mapreduce.Job:  map 60% reduce 0%
17/12/01 12:08:16 INFO mapreduce.Job:  map 61% reduce 0%
17/12/01 12:08:18 INFO mapreduce.Job:  map 68% reduce 0%
17/12/01 12:08:19 INFO mapreduce.Job:  map 69% reduce 0%
17/12/01 12:08:21 INFO mapreduce.Job:  map 75% reduce 0%
17/12/01 12:08:22 INFO mapreduce.Job:  map 76% reduce 0%
17/12/01 12:08:24 INFO mapreduce.Job:  map 80% reduce 0%
17/12/01 12:08:27 INFO mapreduce.Job:  map 89% reduce 0%
17/12/01 12:08:29 INFO mapreduce.Job:  map 90% reduce 0%
17/12/01 12:08:30 INFO mapreduce.Job:  map 96% reduce 0%
17/12/01 12:08:32 INFO mapreduce.Job:  map 100% reduce 0%
17/12/01 12:08:32 INFO mapreduce.Job: Job job_1512150105336_0002 completed successfully
17/12/01 12:08:32 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=1471646
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=1025
		HDFS: Number of bytes written=6553600000
		HDFS: Number of read operations=48
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=24
	Job Counters 
		Launched map tasks=12
		Other local map tasks=12
		Total time spent by all maps in occupied slots (ms)=472005
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=472005
		Total vcore-seconds taken by all map tasks=472005
		Total megabyte-seconds taken by all map tasks=483333120
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Input split bytes=1025
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1920
		CPU time spent (ms)=135460
		Physical memory (bytes) snapshot=2420723712
		Virtual memory (bytes) snapshot=13735694336
		Total committed heap usage (bytes)=4467458048
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=140750829423462787
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=6553600000

real	0m53.453s
user	0m4.325s
sys	0m0.275s

```

The command and output of hdfs dfs -ls /user/saturn/tgen

```sh

[saturn@ip-172-31-30-64 cloudera-scm-server]$ hdfs dfs -ls /user/saturn/tgen
Found 13 items
-rw-r--r--   3 saturn supergroup          0 2017-12-01 12:08 /user/saturn/tgen/_SUCCESS
-rw-r--r--   3 saturn supergroup  546133400 2017-12-01 12:08 /user/saturn/tgen/part-m-00000
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:08 /user/saturn/tgen/part-m-00001
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:08 /user/saturn/tgen/part-m-00002
-rw-r--r--   3 saturn supergroup  546133400 2017-12-01 12:08 /user/saturn/tgen/part-m-00003
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:08 /user/saturn/tgen/part-m-00004
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:08 /user/saturn/tgen/part-m-00005
-rw-r--r--   3 saturn supergroup  546133400 2017-12-01 12:08 /user/saturn/tgen/part-m-00006
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:08 /user/saturn/tgen/part-m-00007
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:08 /user/saturn/tgen/part-m-00008
-rw-r--r--   3 saturn supergroup  546133400 2017-12-01 12:08 /user/saturn/tgen/part-m-00009
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:08 /user/saturn/tgen/part-m-00010
-rw-r--r--   3 saturn supergroup  546133300 2017-12-01 12:08 /user/saturn/tgen/part-m-00011

```

The command and output of hadoop fsck -blocks /user/saturn

```sh

[hdfs@ip-172-31-30-64 cloudera-scm-server]$ hadoop fsck -blocks /user/saturn
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-30-64.ec2.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.30.64 for path /user/saturn at Fri Dec 01 18:12:21 UTC 2017
.............Status: HEALTHY
 Total size:	6553600000 B
 Total dirs:	2
 Total files:	13
 Total symlinks:		0
 Total blocks (validated):	204 (avg. block size 32125490 B)
 Minimally replicated blocks:	204 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Fri Dec 01 18:12:21 UTC 2017 in 9 milliseconds


The filesystem under path '/user/saturn' is HEALTHY

```


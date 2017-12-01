
Create an end-user Linux account named with your GitHub handle

    Make sure this Linux account is added to all cluster nodes
    Create an HDFS directory under /user
    Run the following exercises under this user account

Create a 10 GB file using teragen

    Set the number of mappers to four
    Limit the block size to 32 MB
    Land the output in your user's home directory
    Use the time command to report the job's duration

```sh
[landyrt@ip-172-31-30-26 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=33554432 104857600 /user/landyrt/teragen
17/11/28 19:29:27 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-30-26.ec2.internal/172.31.30.26:8032
17/11/28 19:29:27 INFO terasort.TeraGen: Generating 104857600 using 4
17/11/28 19:29:27 INFO mapreduce.JobSubmitter: number of splits:4
17/11/28 19:29:27 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/11/28 19:29:27 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/11/28 19:29:27 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1511911117917_0003
17/11/28 19:29:27 INFO impl.YarnClientImpl: Submitted application application_1511911117917_0003
17/11/28 19:29:27 INFO mapreduce.Job: The url to track the job: http://ip-172-31-30-26.ec2.internal:8088/proxy/application_1511911117917_0003/
17/11/28 19:29:27 INFO mapreduce.Job: Running job: job_1511911117917_0003
17/11/28 19:29:32 INFO mapreduce.Job: Job job_1511911117917_0003 running in uber mode : false
17/11/28 19:29:32 INFO mapreduce.Job:  map 0% reduce 0%
17/11/28 19:29:51 INFO mapreduce.Job:  map 15% reduce 0%
17/11/28 19:29:56 INFO mapreduce.Job:  map 17% reduce 0%
17/11/28 19:29:57 INFO mapreduce.Job:  map 22% reduce 0%
17/11/28 19:30:02 INFO mapreduce.Job:  map 23% reduce 0%
17/11/28 19:30:03 INFO mapreduce.Job:  map 29% reduce 0%
17/11/28 19:30:08 INFO mapreduce.Job:  map 30% reduce 0%
17/11/28 19:30:09 INFO mapreduce.Job:  map 33% reduce 0%
17/11/28 19:30:15 INFO mapreduce.Job:  map 34% reduce 0%
17/11/28 19:30:20 INFO mapreduce.Job:  map 37% reduce 0%
17/11/28 19:30:21 INFO mapreduce.Job:  map 40% reduce 0%
17/11/28 19:30:26 INFO mapreduce.Job:  map 44% reduce 0%
17/11/28 19:30:27 INFO mapreduce.Job:  map 47% reduce 0%
17/11/28 19:30:32 INFO mapreduce.Job:  map 49% reduce 0%
17/11/28 19:30:33 INFO mapreduce.Job:  map 52% reduce 0%
17/11/28 19:30:38 INFO mapreduce.Job:  map 53% reduce 0%
17/11/28 19:30:39 INFO mapreduce.Job:  map 55% reduce 0%
17/11/28 19:30:44 INFO mapreduce.Job:  map 59% reduce 0%
17/11/28 19:30:45 INFO mapreduce.Job:  map 60% reduce 0%
17/11/28 19:30:50 INFO mapreduce.Job:  map 63% reduce 0%
17/11/28 19:30:51 INFO mapreduce.Job:  map 64% reduce 0%
17/11/28 19:30:56 INFO mapreduce.Job:  map 68% reduce 0%
17/11/28 19:30:57 INFO mapreduce.Job:  map 70% reduce 0%
17/11/28 19:31:02 INFO mapreduce.Job:  map 77% reduce 0%
17/11/28 19:31:08 INFO mapreduce.Job:  map 81% reduce 0%
17/11/28 19:31:14 INFO mapreduce.Job:  map 83% reduce 0%
17/11/28 19:31:20 INFO mapreduce.Job:  map 89% reduce 0%
17/11/28 19:31:27 INFO mapreduce.Job:  map 96% reduce 0%
17/11/28 19:31:33 INFO mapreduce.Job:  map 98% reduce 0%
17/11/28 19:31:35 INFO mapreduce.Job:  map 100% reduce 0%
17/11/28 19:31:36 INFO mapreduce.Job: Job job_1511911117917_0003 completed successfully
17/11/28 19:31:36 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=581480
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=344
		HDFS: Number of bytes written=10485760000
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=472173
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=472173
		Total vcore-milliseconds taken by all map tasks=472173
		Total megabyte-milliseconds taken by all map tasks=483505152
	Map-Reduce Framework
		Map input records=104857600
		Map output records=104857600
		Input split bytes=344
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=994
		CPU time spent (ms)=149830
		Physical memory (bytes) snapshot=722481152
		Virtual memory (bytes) snapshot=6352453632
		Total committed heap usage (bytes)=1645740032
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=225186913807133164
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=10485760000

real	2m11.297s
user	0m4.824s
sys	0m0.268s

```

Run the terasort command on this file

    Use the time command to report the job's duration
    Land the result under your user's home directory

```sh

[landyrt@ip-172-31-30-26 ~]$ nohup time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/landyrt/teragen/* /user/landyrt/terasort &
[1] 23811

17/11/28 19:43:35 INFO terasort.TeraSort: starting
17/11/28 19:43:36 INFO input.FileInputFormat: Total input paths to process : 4
Spent 207ms computing base-splits.
Spent 5ms computing TeraScheduler splits.
Computing input splits took 213ms
Sampling 10 splits of 316
Making 16 from 100000 sampled records
Computing parititions took 578ms
Spent 793ms computing partitions.
17/11/28 19:43:37 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-30-26.ec2.internal/172.31.30.26:8032
17/11/28 19:43:37 INFO mapreduce.JobSubmitter: number of splits:316
17/11/28 19:43:37 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1511911117917_0004
17/11/28 19:43:37 INFO impl.YarnClientImpl: Submitted application application_1511911117917_0004
17/11/28 19:43:37 INFO mapreduce.Job: The url to track the job: http://ip-172-31-30-26.ec2.internal:8088/proxy/application_1511911117917_0004/
17/11/28 19:43:37 INFO mapreduce.Job: Running job: job_1511911117917_0004
17/11/28 19:43:43 INFO mapreduce.Job: Job job_1511911117917_0004 running in uber mode : false
17/11/28 19:43:43 INFO mapreduce.Job:  map 0% reduce 0%
17/11/28 19:43:52 INFO mapreduce.Job:  map 1% reduce 0%
17/11/28 19:43:53 INFO mapreduce.Job:  map 2% reduce 0%
17/11/28 19:43:56 INFO mapreduce.Job:  map 5% reduce 0%
17/11/28 19:43:57 INFO mapreduce.Job:  map 8% reduce 0%
17/11/28 19:43:58 INFO mapreduce.Job:  map 9% reduce 0%
17/11/28 19:44:00 INFO mapreduce.Job:  map 10% reduce 0%
17/11/28 19:44:01 INFO mapreduce.Job:  map 11% reduce 0%
17/11/28 19:44:06 INFO mapreduce.Job:  map 12% reduce 0%
17/11/28 19:44:08 INFO mapreduce.Job:  map 16% reduce 0%
17/11/28 19:44:09 INFO mapreduce.Job:  map 19% reduce 0%
17/11/28 19:44:10 INFO mapreduce.Job:  map 20% reduce 0%
17/11/28 19:44:15 INFO mapreduce.Job:  map 21% reduce 0%
17/11/28 19:44:17 INFO mapreduce.Job:  map 22% reduce 0%
17/11/28 19:44:18 INFO mapreduce.Job:  map 23% reduce 0%
17/11/28 19:44:19 INFO mapreduce.Job:  map 25% reduce 0%
17/11/28 19:44:20 INFO mapreduce.Job:  map 26% reduce 0%
17/11/28 19:44:21 INFO mapreduce.Job:  map 29% reduce 0%
17/11/28 19:44:23 INFO mapreduce.Job:  map 30% reduce 0%
17/11/28 19:44:25 INFO mapreduce.Job:  map 31% reduce 0%
17/11/28 19:44:28 INFO mapreduce.Job:  map 32% reduce 0%
17/11/28 19:44:29 INFO mapreduce.Job:  map 33% reduce 0%
17/11/28 19:44:30 INFO mapreduce.Job:  map 35% reduce 0%
17/11/28 19:44:32 INFO mapreduce.Job:  map 37% reduce 0%
17/11/28 19:44:33 INFO mapreduce.Job:  map 40% reduce 0%
17/11/28 19:44:37 INFO mapreduce.Job:  map 41% reduce 0%
17/11/28 19:44:38 INFO mapreduce.Job:  map 42% reduce 0%
17/11/28 19:44:39 INFO mapreduce.Job:  map 43% reduce 0%
17/11/28 19:44:41 INFO mapreduce.Job:  map 45% reduce 0%
17/11/28 19:44:44 INFO mapreduce.Job:  map 46% reduce 0%
17/11/28 19:44:45 INFO mapreduce.Job:  map 50% reduce 0%
17/11/28 19:44:46 INFO mapreduce.Job:  map 51% reduce 0%
17/11/28 19:44:49 INFO mapreduce.Job:  map 52% reduce 0%
17/11/28 19:44:51 INFO mapreduce.Job:  map 53% reduce 0%
17/11/28 19:44:52 INFO mapreduce.Job:  map 55% reduce 0%
17/11/28 19:44:54 INFO mapreduce.Job:  map 56% reduce 0%
17/11/28 19:44:56 INFO mapreduce.Job:  map 57% reduce 0%
17/11/28 19:44:57 INFO mapreduce.Job:  map 60% reduce 0%
17/11/28 19:44:58 INFO mapreduce.Job:  map 61% reduce 0%
17/11/28 19:45:00 INFO mapreduce.Job:  map 62% reduce 0%
17/11/28 19:45:02 INFO mapreduce.Job:  map 64% reduce 0%
17/11/28 19:45:03 INFO mapreduce.Job:  map 65% reduce 0%
17/11/28 19:45:06 INFO mapreduce.Job:  map 66% reduce 0%
17/11/28 19:45:08 INFO mapreduce.Job:  map 69% reduce 0%
17/11/28 19:45:09 INFO mapreduce.Job:  map 70% reduce 0%
17/11/28 19:45:10 INFO mapreduce.Job:  map 71% reduce 0%
17/11/28 19:45:11 INFO mapreduce.Job:  map 72% reduce 0%
17/11/28 19:45:13 INFO mapreduce.Job:  map 73% reduce 0%
17/11/28 19:45:14 INFO mapreduce.Job:  map 75% reduce 0%
17/11/28 19:45:17 INFO mapreduce.Job:  map 76% reduce 0%
17/11/28 19:45:19 INFO mapreduce.Job:  map 78% reduce 0%
17/11/28 19:45:20 INFO mapreduce.Job:  map 80% reduce 0%
17/11/28 19:45:21 INFO mapreduce.Job:  map 81% reduce 0%
17/11/28 19:45:22 INFO mapreduce.Job:  map 82% reduce 0%
17/11/28 19:45:24 INFO mapreduce.Job:  map 83% reduce 0%
17/11/28 19:45:25 INFO mapreduce.Job:  map 84% reduce 0%
17/11/28 19:45:26 INFO mapreduce.Job:  map 85% reduce 0%
17/11/28 19:45:28 INFO mapreduce.Job:  map 86% reduce 0%
17/11/28 19:45:30 INFO mapreduce.Job:  map 87% reduce 0%
17/11/28 19:45:31 INFO mapreduce.Job:  map 88% reduce 0%
17/11/28 19:45:32 INFO mapreduce.Job:  map 90% reduce 0%
17/11/28 19:45:33 INFO mapreduce.Job:  map 91% reduce 0%
17/11/28 19:45:40 INFO mapreduce.Job:  map 91% reduce 4%
17/11/28 19:45:42 INFO mapreduce.Job:  map 92% reduce 6%
17/11/28 19:45:43 INFO mapreduce.Job:  map 93% reduce 11%
17/11/28 19:45:44 INFO mapreduce.Job:  map 96% reduce 13%
17/11/28 19:45:45 INFO mapreduce.Job:  map 96% reduce 19%
17/11/28 19:45:47 INFO mapreduce.Job:  map 96% reduce 27%
17/11/28 19:45:49 INFO mapreduce.Job:  map 96% reduce 28%
17/11/28 19:45:51 INFO mapreduce.Job:  map 97% reduce 30%
17/11/28 19:45:53 INFO mapreduce.Job:  map 98% reduce 30%
17/11/28 19:45:55 INFO mapreduce.Job:  map 100% reduce 30%
17/11/28 19:45:56 INFO mapreduce.Job:  map 100% reduce 31%
17/11/28 19:45:57 INFO mapreduce.Job:  map 100% reduce 32%
17/11/28 19:45:58 INFO mapreduce.Job:  map 100% reduce 37%
17/11/28 19:45:59 INFO mapreduce.Job:  map 100% reduce 48%
17/11/28 19:46:01 INFO mapreduce.Job:  map 100% reduce 51%
17/11/28 19:46:02 INFO mapreduce.Job:  map 100% reduce 57%
17/11/28 19:46:03 INFO mapreduce.Job:  map 100% reduce 66%
17/11/28 19:46:04 INFO mapreduce.Job:  map 100% reduce 69%
17/11/28 19:46:05 INFO mapreduce.Job:  map 100% reduce 76%
17/11/28 19:46:06 INFO mapreduce.Job:  map 100% reduce 77%
17/11/28 19:46:08 INFO mapreduce.Job:  map 100% reduce 82%
17/11/28 19:46:10 INFO mapreduce.Job:  map 100% reduce 86%
17/11/28 19:46:11 INFO mapreduce.Job:  map 100% reduce 91%
17/11/28 19:46:14 INFO mapreduce.Job:  map 100% reduce 93%
17/11/28 19:46:16 INFO mapreduce.Job:  map 100% reduce 95%
17/11/28 19:46:17 INFO mapreduce.Job:  map 100% reduce 96%
17/11/28 19:46:20 INFO mapreduce.Job:  map 100% reduce 97%
17/11/28 19:46:21 INFO mapreduce.Job:  map 100% reduce 98%
17/11/28 19:46:22 INFO mapreduce.Job:  map 100% reduce 99%
17/11/28 19:46:23 INFO mapreduce.Job:  map 100% reduce 100%
17/11/28 19:46:23 INFO mapreduce.Job: Job job_1511911117917_0004 completed successfully
17/11/28 19:46:23 INFO mapreduce.Job: Counters: 50
        File System Counters
                FILE: Number of bytes read=4650969215
                FILE: Number of bytes written=9253381783
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=10485803924
                HDFS: Number of bytes written=10485760000
                HDFS: Number of read operations=996
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=32
        Job Counters 
                Launched map tasks=316
                Launched reduce tasks=16
                Data-local map tasks=314
                Rack-local map tasks=2
                Total time spent by all maps in occupied slots (ms)=2941286
                Total time spent by all reduces in occupied slots (ms)=790948
                Total time spent by all map tasks (ms)=2941286
                Total time spent by all reduce tasks (ms)=790948
                Total vcore-milliseconds taken by all map tasks=2941286
                Total vcore-milliseconds taken by all reduce tasks=790948
                Total megabyte-milliseconds taken by all map tasks=3011876864
                Total megabyte-milliseconds taken by all reduce tasks=809930752
        Map-Reduce Framework
                Map input records=104857600
                Map output records=104857600
                Map output bytes=10695475200
                Map output materialized bytes=4553562572
                Input split bytes=43924
                Combine input records=0
                Combine output records=0
                Reduce input groups=104857600
                Reduce shuffle bytes=4553562572
                Reduce input records=104857600
                Reduce output records=104857600
                Spilled Records=209715200
                Shuffled Maps =5056
                Failed Shuffles=0
                Merged Map outputs=5056
                GC time elapsed (ms)=36157
                CPU time spent (ms)=1580220
                Physical memory (bytes) snapshot=179554742272
                Virtual memory (bytes) snapshot=530587004928
                Total committed heap usage (bytes)=181928984576
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters 
                Bytes Read=10485760000
        File Output Format Counters 
                Bytes Written=10485760000
17/11/28 19:46:23 INFO terasort.TeraSort: done
7.32user 0.35system 2:48.88elapsed 4%CPU (0avgtext+0avgdata 246596maxresident)k
0inputs+1200outputs (0major+78517minor)pagefaults 0swaps

```



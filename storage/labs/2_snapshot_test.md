Create a precious directory in HDFS; copy the ZIP course file into it.

```sh
[landyrt@ip-172-31-30-26 hduser]$ hdfs dfs -mkdir /user/landyrt/precious
[landyrt@ip-172-31-30-26 hduser]$ hdfs dfs -ls /user/landyrt/
Found 5 items
drwx------   - landyrt hadoop          0 2017-11-28 19:46 /user/landyrt/.staging
-rw-r--r--   3 landyrt hadoop          0 2017-11-29 13:11 /user/landyrt/holaMundo
drwxr-xr-x   - landyrt hadoop          0 2017-11-28 20:42 /user/landyrt/precious


[root@ip-172-31-30-26 hduser]# mv SEBC-master.zip /home/landyrt/
[root@ip-172-31-30-26 hduser]# sudo su - landyrt
Last login: Tue Nov 28 19:49:25 CST 2017 on pts/0
[landyrt@ip-172-31-30-26 ~]$ ls
nohup.out  SEBC-master.zip
[landyrt@ip-172-31-30-26 ~]$ hdfs dfs -put SEBC-master.zip /user/landyrt/precious
[landyrt@ip-172-31-30-26 ~]$ exit


```

Enable snapshots for precious

```sh

[root@ip-172-31-30-26 hduser]# sudo -u hdfs hdfs dfsadmin -allowSnapshot /user/landyrt/precious
Allowing snaphot on /user/landyrt/precious succeeded

```

Create a snapshot called sebc-hdfs-test

```sh

[landyrt@ip-172-31-30-26 hduser]$ hdfs dfs -createSnapshot /user/landyrt/precious sebc-hdfs-test
Created snapshot /user/landyrt/precious/.snapshot/sebc-hdfs-test

```

Delete the directory

```sh

[landyrt@ip-172-31-30-26 hduser]$ hdfs dfs -rm -f -R -skipTrash /user/landyrt/precious
rm: The directory /user/landyrt/precious cannot be deleted since /user/landyrt/precious is snapshottable and already has snapshots

```


Delete the ZIP file

```sh

[landyrt@ip-172-31-30-26 hduser]$ hdfs dfs -rm -f -R -skipTrash /user/landyrt/precious/SEBC-master.zip
Deleted /user/landyrt/precious/SEBC-master.zip

```

Restore the deleted file


```sh

[landyrt@ip-172-31-30-26 hduser]$ hdfs dfs -ls /user/landyrt/precious/.snapshot
Found 1 items
drwxr-xr-x   - landyrt hadoop          0 2017-11-28 20:10 /user/landyrt/precious/.snapshot/sebc-hdfs-test
[landyrt@ip-172-31-30-26 hduser]$ hdfs dfs -ls /user/landyrt/precious/.snapshot/sebc-hdfs-test
Found 1 items
-rw-r--r--   3 landyrt hadoop     474833 2017-11-28 19:59 /user/landyrt/precious/.snapshot/sebc-hdfs-test/SEBC-master.zip
[landyrt@ip-172-31-30-26 hduser]$ hdfs dfs -cp /user/landyrt/precious/.snapshot/sebc-hdfs-test/SEBC-master.zip /user/landyrt/precious

```















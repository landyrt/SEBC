SENTRY - Verify user privileges

```sh
beeline> [hduser@ip-172-31-20-150 ~]$ kinit landyrt
Password for landyrt@VINKOS.COM: 
[hduser@ip-172-31-20-150 ~]$ beeline
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-29-75.ec2.internal:10000/default;principal=hive/ip-172-31-29-75.ec2.internal@VINKOS.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-29-75.ec2.internal:10000/default;principal=hive/ip-172-31-29-75.ec2.internal@VINKOS.COM
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-29-75.ec2.internal:> show tables;
INFO  : Compiling command(queryId=hive_20171129210909_c7969800-4799-4c42-b3f8-4bd87344ba94): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129210909_c7969800-4799-4c42-b3f8-4bd87344ba94); Time taken: 0.582 seconds
INFO  : Executing command(queryId=hive_20171129210909_c7969800-4799-4c42-b3f8-4bd87344ba94): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129210909_c7969800-4799-4c42-b3f8-4bd87344ba94); Time taken: 0.254 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.141 seconds)
0: jdbc:hive2://ip-172-31-29-75.ec2.internal:> 

```

SENTRY - kinit as george, then login to beeline

```sh
[root@ip-172-31-30-26 ~]# groupadd selector
[root@ip-172-31-30-26 ~]# groupadd inserters
[root@ip-172-31-30-26 ~]# sudo useradd -u 1100 -g selector george
[root@ip-172-31-30-26 ~]# sudo useradd -u 1200 -g inserters ferdinand

[root@ip-172-31-30-26 ~]# kadmin.local
Authenticating as principal hdfs/admin@VINKOS.COM with password.
kadmin.local:  add_principal george
WARNING: no policy specified for george@VINKOS.COM; defaulting to no policy
Enter password for principal "george@VINKOS.COM": 
Re-enter password for principal "george@VINKOS.COM": 
Principal "george@VINKOS.COM" created.
kadmin.local:  add_principal ferdinand
WARNING: no policy specified for ferdinand@VINKOS.COM; defaulting to no policy
Enter password for principal "ferdinand@VINKOS.COM": 
Re-enter password for principal "ferdinand@VINKOS.COM": 
Principal "ferdinand@VINKOS.COM" created.


[landyrt@ip-172-31-30-26 root]$ kinit george
Password for george@VINKOS.COM: 
[landyrt@ip-172-31-30-26 root]$ beeline
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-29-75.ec2.internal:10000/default;principal=hive/ip-172-31-29-75.ec2.internal@VINKOS.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-29-75.ec2.internal:10000/default;principal=hive/ip-172-31-29-75.ec2.internal@VINKOS.COM
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-29-75.ec2.internal:> show tables;
INFO  : Compiling command(queryId=hive_20171129220707_d86ac1b1-0c85-48be-a0fd-dbd36f44a1a3): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129220707_d86ac1b1-0c85-48be-a0fd-dbd36f44a1a3); Time taken: 0.061 seconds
INFO  : Executing command(queryId=hive_20171129220707_d86ac1b1-0c85-48be-a0fd-dbd36f44a1a3): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129220707_d86ac1b1-0c85-48be-a0fd-dbd36f44a1a3); Time taken: 0.142 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
| sample07  |
| sample08  |
+-----------+--+
2 rows selected (0.288 seconds)
0: jdbc:hive2://ip-172-31-29-75.ec2.internal:> select * from sample07;
INFO  : Compiling command(queryId=hive_20171129220707_083b641e-d798-4d28-9265-d9f29e37a677): select * from sample07
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:sample07.campo1, type:string, comment:null), FieldSchema(name:sample07.campo2, type:int, comment:null), FieldSchema(name:sample07.campo3, type:date, comment:null), FieldSchema(name:sample07.year, type:int, comment:null)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129220707_083b641e-d798-4d28-9265-d9f29e37a677); Time taken: 0.181 seconds
INFO  : Executing command(queryId=hive_20171129220707_083b641e-d798-4d28-9265-d9f29e37a677): select * from sample07
INFO  : Completed executing command(queryId=hive_20171129220707_083b641e-d798-4d28-9265-d9f29e37a677); Time taken: 0.001 seconds
INFO  : OK
+------------------+------------------+------------------+----------------+--+
| sample07.campo1  | sample07.campo2  | sample07.campo3  | sample07.year  |
+------------------+------------------+------------------+----------------+--+
+------------------+------------------+------------------+----------------+--+
No rows selected (0.214 seconds)




[root@ip-172-31-30-26 ~]# kdestroy
[root@ip-172-31-30-26 ~]# kinit ferdinand;
Password for ferdinand@VINKOS.COM: 
[root@ip-172-31-30-26 ~]# beeline
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-29-75.ec2.internal:10000/default;principal=hive/ip-172-31-29-75.ec2.internal@VINKOS.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-29-75.ec2.internal:10000/default;principal=hive/ip-172-31-29-75.ec2.internal@VINKOS.COM
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-29-75.ec2.internal:> show tables;
INFO  : Compiling command(queryId=hive_20171129222020_b199dfb7-65f6-4055-9a04-426c924df57b): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129222020_b199dfb7-65f6-4055-9a04-426c924df57b); Time taken: 0.055 seconds
INFO  : Executing command(queryId=hive_20171129222020_b199dfb7-65f6-4055-9a04-426c924df57b): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171129222020_b199dfb7-65f6-4055-9a04-426c924df57b); Time taken: 0.149 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
| sample07  |
+-----------+--+
1 row selected (0.294 seconds)
0: jdbc:hive2://ip-172-31-29-75.ec2.internal:> select * from sample07;
INFO  : Compiling command(queryId=hive_20171129222020_7bb58618-cc13-4933-824b-d10bedcb9ee8): select * from sample07
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:sample07.campo1, type:string, comment:null), FieldSchema(name:sample07.campo2, type:int, comment:null), FieldSchema(name:sample07.campo3, type:date, comment:null), FieldSchema(name:sample07.year, type:int, comment:null)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171129222020_7bb58618-cc13-4933-824b-d10bedcb9ee8); Time taken: 0.186 seconds
INFO  : Executing command(queryId=hive_20171129222020_7bb58618-cc13-4933-824b-d10bedcb9ee8): select * from sample07
INFO  : Completed executing command(queryId=hive_20171129222020_7bb58618-cc13-4933-824b-d10bedcb9ee8); Time taken: 0.001 seconds
INFO  : OK
+------------------+------------------+------------------+----------------+--+
| sample07.campo1  | sample07.campo2  | sample07.campo3  | sample07.year  |
+------------------+------------------+------------------+----------------+--+
+------------------+------------------+------------------+----------------+--+
No rows selected (0.219 seconds)

```

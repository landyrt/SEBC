
Install MySQL 5.6 or MariaDB 5.5 server on the first node listed in 0_setup.md
Use a YUM repository to install the package
Copy the repo configuration you used to challenges/labs/1_my-database-server.repo.md

	```sh

	[root@ip-172-31-19-21 ~]# less  /etc/yum.repos.d/MariaDB10.repo

	# MariaDB 10.1 CentOS repository list - created 2016-01-18 09:58 UTC
	# http://mariadb.org/mariadb/repositories/
	[mariadb]
	name = MariaDB
	baseurl = http://yum.mariadb.org/10.1/centos7-amd64
	gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
	gpgcheck=1
	enablerepo=1
	/etc/yum.repos.d/MariaDB10.repo (END)

	```

On all cluster nodes
Install the database client package and JDBC connector jar on all nodes
Start the database service and create these databases
scm
rman
hive
oozie
hue
Record the following in challenges/labs/1_db-server.md
A command and output that shows the hostname of your database server

```sh

MariaDB [(none)]> SHOW VARIABLES like 'hostname';
+---------------+------------------------------+
| Variable_name | Value                        |
+---------------+------------------------------+
| hostname      | ip-172-31-19-21.ec2.internal |
+---------------+------------------------------+
1 row in set (0.01 sec)

```

A command and output that reports the database server version

```sh

MariaDB [(none)]> SHOW VARIABLES like 'version';
+---------------+-----------------+
| Variable_name | Value           |
+---------------+-----------------+
| version       | 10.1.29-MariaDB |
+---------------+-----------------+
1 row in set (0.00 sec)

```

A command and output that lists all the databases in the server

```sh

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| hive               |
| hue                |
| information_schema |
| metastore          |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm             |
+--------------------+
12 rows in set (0.00 sec)

```

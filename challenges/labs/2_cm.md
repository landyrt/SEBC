Create the Issue Install CM
Assign yourself and label it started
Install Cloudera Manager on the second node listed in 0_setup.md
List the command and output for ls /etc/yum.repos.d in challenges/labs/2_cm.md

```sh

[root@ip-172-31-30-64 share]# ls /etc/yum.repos.d
cloudera-manager.repo  MariaDB10.repo  redhat.repo  redhat-rhui-client-config.repo  redhat-rhui.repo  rhui-load-balancers.conf

```

Connect Cloudera Manager Server to its database
Use the scm_prepare_database.sh script to create the db.properties file
List the full command and its output in 2_cm.md

```sh

[root@ip-172-31-30-64 share]# /usr/share/cmf/schema/scm_prepare_database.sh mysql -h ip-172-31-19-21.ec2.internal -utemp -ptemp --scm-host ip-172-31-30-64.ec2.internal scm scm scm
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera/
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera//bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!

```



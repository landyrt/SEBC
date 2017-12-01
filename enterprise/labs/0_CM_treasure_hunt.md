
1. What is ubertask optimization?

	Ubertask optimization enable the JVM to run small jobs sequentially in an efficient way. Small jobs are defined by: mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes

2. Where in CM is the Kerberos Security Realm value displayed?

	Administration -> Settings, Category -> kerberos: Kerberos security realm (default_realm): VINKOS.COM

3. Which CDH service(s) host a property for enabling Kerberos authentication?

	Zookeeper, Yarn, HDFS

4. How do you upgrade the CM agents?

	Hosts -> All Hosts -> Re run upgrade wizard

5. Give the tsquery statement used to chart Hue's CPU utilization?

	select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME

6. Name all the roles that make up the Hive service

	Hive Metastore Server, WebHCat Server, HiveServer2

7. What steps must be completed before integrating Cloudera Manager with Kerberos?

	Install Kerberos Server
		Configure & create kdc.conf file ( define [realms] )
	Install kerberos client in all nodes
		Configure & create krb5.conf file (define [realms] y [libdefaults] )
	Create database 
	Create principal to manage accounts 
	Add */admin and cloudera-scm to ACL to give them privileges to add principals
	Adds the password policy to the database
	Start Kerberos
 






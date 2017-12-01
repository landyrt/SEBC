Create the Issue Install CDH
Assign yourself and label it started
Deploy Coreset services + Spark
Rename your cluster after your GitHub handle
Create user directories in HDFS for saturn and haley
Add the following to 3_cm.md:

The command and output for hdfs dfs -ls /user

```sh

[hdfs@ip-172-31-19-21 root]$ hdfs dfs -ls /user
Found 9 items
drwxr-xr-x   - admin  admin               0 2017-12-01 11:50 /user/admin
drwxr-xr-x   - hdfs   supergroup          0 2017-12-01 11:51 /user/haley
drwxr-xr-x   - hdfs   supergroup          0 2017-12-01 11:49 /user/hdfs
drwxrwxrwx   - mapred hadoop              0 2017-12-01 11:41 /user/history
drwxrwxr-t   - hive   hive                0 2017-12-01 11:42 /user/hive
drwxrwxr-x   - hue    hue                 0 2017-12-01 11:43 /user/hue
drwxrwxr-x   - oozie  oozie               0 2017-12-01 11:43 /user/oozie
drwxr-xr-x   - hdfs   supergroup          0 2017-12-01 11:51 /user/saturn
drwxr-x--x   - spark  spark               0 2017-12-01 11:42 /user/spark

```

The command and output from the CM API call ../api/v14/hosts

```sh

[root@ip-172-31-30-64 cloudera-scm-server]# curl -X GET -u admin:admin 'http://localhost:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "55ccb049-e022-4a1d-be75-13d82f7585ee",
    "ipAddress" : "172.31.19.21",
    "hostname" : "ip-172-31-19-21.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-30-64.ec2.internal:7180/cmf/hostRedirect/55ccb049-e022-4a1d-be75-13d82f7585ee",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  }, {
    "hostId" : "125bd4bb-fd45-4fa5-b01a-64d3d3bbc255",
    "ipAddress" : "172.31.24.75",
    "hostname" : "ip-172-31-24-75.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-30-64.ec2.internal:7180/cmf/hostRedirect/125bd4bb-fd45-4fa5-b01a-64d3d3bbc255",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  }, {
    "hostId" : "2657bef8-2611-44ef-b31a-0d8a02fb9613",
    "ipAddress" : "172.31.25.195",
    "hostname" : "ip-172-31-25-195.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-30-64.ec2.internal:7180/cmf/hostRedirect/2657bef8-2611-44ef-b31a-0d8a02fb9613",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  }, {
    "hostId" : "d405af32-b4be-4130-b6e8-6f7bb828bdf0",
    "ipAddress" : "172.31.26.68",
    "hostname" : "ip-172-31-26-68.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-30-64.ec2.internal:7180/cmf/hostRedirect/d405af32-b4be-4130-b6e8-6f7bb828bdf0",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  }, {
    "hostId" : "24ae926a-565a-4e8c-aefb-d733043b56b4",
    "ipAddress" : "172.31.30.64",
    "hostname" : "ip-172-31-30-64.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-30-64.ec2.internal:7180/cmf/hostRedirect/24ae926a-565a-4e8c-aefb-d733043b56b4",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33567498240
  } ]
}

```

The command and output from the CM API call ../api/v8/clusters/<githubName>/services

```sh

[root@ip-172-31-30-64 cloudera-scm-server]# curl -X GET -u admin:admin 'http://localhost:7180/api/v8/clusters/landyrt/services'
{
  "items" : [ {
    "name" : "hive",
    "type" : "HIVE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-30-64.ec2.internal:7180/cmf/serviceRedirect/hive",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HIVE_HIVEMETASTORES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HIVE_HIVESERVER2S_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hive"
  }, {
    "name" : "zookeeper",
    "type" : "ZOOKEEPER",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-30-64.ec2.internal:7180/cmf/serviceRedirect/zookeeper",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "ZOOKEEPER_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "ZOOKEEPER_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "ZooKeeper"
  }, {
    "name" : "hue",
    "type" : "HUE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-30-64.ec2.internal:7180/cmf/serviceRedirect/hue",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HUE_HUE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hue"
  }, {
    "name" : "oozie",
    "type" : "OOZIE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-30-64.ec2.internal:7180/cmf/serviceRedirect/oozie",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "OOZIE_OOZIE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Oozie"
  }, {
    "name" : "yarn",
    "type" : "YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-30-64.ec2.internal:7180/cmf/serviceRedirect/yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "YARN_JOBHISTORY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_NODE_MANAGERS_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_RESOURCEMANAGERS_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_USAGE_AGGREGATION_HEALTH",
      "summary" : "DISABLED"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "YARN (MR2 Included)"
  }, {
    "name" : "spark_on_yarn",
    "type" : "SPARK_ON_YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-30-64.ec2.internal:7180/cmf/serviceRedirect/spark_on_yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Spark"
  }, {
    "name" : "hdfs",
    "type" : "HDFS",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-30-64.ec2.internal:7180/cmf/serviceRedirect/hdfs",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HDFS_BLOCKS_WITH_CORRUPT_REPLICAS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_DATA_NODES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_FREE_SPACE_REMAINING",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_HA_NAMENODE_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_MISSING_BLOCKS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_UNDER_REPLICATED_BLOCKS",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "HDFS"
  } ]
}

```

Login to Hue and install the Hive sample data
Copy a HUE screen that shows the Hive tables to challenges/labs/3_hue_hive.png
Push this work to GitHub and label the Issue review
Assign the issue to the instructors

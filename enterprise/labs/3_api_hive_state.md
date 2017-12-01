Locate API version:

[root@ip-172-31-30-26 cloudera-scm-agent]# curl -X GET -u landyrt:cloudera 'http://localhost:7180/api/version'
v18

Hive status

```sh
root@ip-172-31-30-26 cloudera-scm-agent]#curl -u landyrt:cloudera 'http://localhost:7180/api/v18/clusters/Cluster%201/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-30-26.ec2.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-30-26.ec2.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
}
```

Hive stop

```sh
[root@ip-172-31-30-26 cloudera-scm-agent]# curl -X POST -u landyrt:cloudera 'http://localhost:7180/api/v18/clusters/Cluster%201/services/hive/commands/stop'
{
  "id" : 577,
  "name" : "Stop",
  "startTime" : "2017-11-30T19:57:35.503Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

Hive start

```sh
[root@ip-172-31-30-26 cloudera-scm-agent]# curl -X POST -u landyrt:cloudera 'http://aws_elephant:7180/api/v18/clusters/Cluster%201/services/hive/commands/start'
{
  "id" : 582,
  "name" : "Start",
  "startTime" : "2017-11-30T19:58:02.950Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}

```

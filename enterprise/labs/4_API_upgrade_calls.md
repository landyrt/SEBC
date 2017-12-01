Report the latest available version of the API

```sh
[root@ip-172-31-30-26 cloudera-scm-agent]# curl -X GET -u landyrt:cloudera 'http://localhost:7180/api/version'
v18
```


Report the CM version

```sh
[root@ip-172-31-30-26 cloudera-scm-agent]# curl -X GET -u landyrt:cloudera 'http://localhost:7180/api/v18/cm/version'
{
  "version" : "5.13.0",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20171002-1719",
  "gitHash" : "bd657e597e6743c458ee2c9aabe808b7c972981c",
  "snapshot" : false
}

```

List all CM users

```sh
[root@ip-172-31-30-26 cloudera-scm-agent]# curl -u landyrt:cloudera 'http://localhost:7180/api/v18/users'
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "landyrt",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}
```

Report the database server in use by CM

```sh
[root@ip-172-31-30-26 cloudera-scm-agent]# curl -u landyrt:cloudera 'http://localhost:7180/api/v18/cm/scmDbInfo'
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}

```



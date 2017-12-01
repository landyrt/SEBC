
curl -X GET -u landyrt:cloudera 'http://aws_elephant:7180/api/v18/cm/deployment' /api/v18/cm/deployment

```sh

{
  "timestamp" : "2017-12-01T01:24:25.220Z",
  "clusters" : [ {
    "name" : "cluster",
    "displayName" : "Cluster 1",
    "version" : "CDH5",
    "fullVersion" : "5.12.1",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-30-26.ec2.internal",
          "sensitive" : false
        }, {
          "name" : "hive_metastore_database_name",
          "value" : "hive",
          "sensitive" : false
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password",
          "sensitive" : true
        }, {
          "name" : "hive_proxy_user_groups_list",
          "value" : "hive,hue,sentry",
          "sensitive" : false
        }, {
          "name" : "hive_service_config_safety_valve",
          "value" : "<property><name>hive.server2.authentication</name><value>KERBEROS</value></property>\n<property>  <name>hive.server2.authentication.kerberos.principal</name> <value>hive/ip-172-31-29-75.ec2.internal@VINKOS.COM</value></property>\n<property> <name>hive.stats.ndv.error</name> <value>5.0</value></property>\n",
          "sensitive" : false
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn",
          "sensitive" : false
        }, {
          "name" : "sentry_service",
          "value" : "sentry",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-35812a9edba9b2239c57dce1004e1e38",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "ecb87495-0d9a-4f21-99ba-4f5ca1fd3fd2"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-5147e609303aee1163da6b5a982396a5",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-c0ade2d345bd6f8625aa06da59354a0e",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-HIVEMETASTORE-c0ade2d345bd6f8625aa06da59354a0e",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "c9b9uw7em23mi56kr5tcxaegs",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVEMETASTORE-BASE"
        }
      }, {
        "name" : "hive-HIVESERVER2-c0ade2d345bd6f8625aa06da59354a0e",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "12kvq9c9xny00yj1i84bn3ki2",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVESERVER2-BASE"
        }
      } ],
      "displayName" : "Hive",
      "roleConfigGroups" : [ {
        "name" : "hive-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-BASE",
        "displayName" : "Hive Metastore Server Default Group",
        "roleType" : "HIVEMETASTORE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ {
            "name" : "hive_enable_db_notification",
            "value" : "true",
            "sensitive" : false
          }, {
            "name" : "hive_metastore_java_heapsize",
            "value" : "5454692352",
            "sensitive" : false
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "545469235",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-BASE",
        "displayName" : "HiveServer2 Default Group",
        "roleType" : "HIVESERVER2",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ {
            "name" : "hiveserver2_enable_impersonation",
            "value" : "false",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "3013895782",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "507",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hive-WEBHCAT-BASE",
        "displayName" : "WebHCat Server Default Group",
        "roleType" : "WEBHCAT",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ ]
        }
      } ],
      "replicationSchedules" : [ ]
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "items" : [ {
          "name" : "enableSecurity",
          "value" : "true",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-35812a9edba9b2239c57dce1004e1e38",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "ecb87495-0d9a-4f21-99ba-4f5ca1fd3fd2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ddo77rykxqb9c6mz1qrvjikn7",
            "sensitive" : true
          }, {
            "name" : "serverId",
            "value" : "3",
            "sensitive" : false
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
        }
      }, {
        "name" : "zookeeper-SERVER-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ap1doc93d69k5e62kr4egwdyk",
            "sensitive" : true
          }, {
            "name" : "serverId",
            "value" : "2",
            "sensitive" : false
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
        }
      }, {
        "name" : "zookeeper-SERVER-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "eat5sle3xaggaj56onddt6opf",
            "sensitive" : true
          }, {
            "name" : "serverId",
            "value" : "1",
            "sensitive" : false
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
        }
      } ],
      "displayName" : "ZooKeeper",
      "roleConfigGroups" : [ {
        "name" : "zookeeper-SERVER-BASE",
        "displayName" : "Server Default Group",
        "roleType" : "SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "zookeeper"
        },
        "config" : {
          "items" : [ ]
        }
      } ]
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-30-26.ec2.internal",
          "sensitive" : false
        }, {
          "name" : "database_password",
          "value" : "hue_password",
          "sensitive" : true
        }, {
          "name" : "database_type",
          "value" : "mysql",
          "sensitive" : false
        }, {
          "name" : "hive_service",
          "value" : "hive",
          "sensitive" : false
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-7dfcef43b14e331d1982a8d7e1ad3082",
          "sensitive" : false
        }, {
          "name" : "oozie_service",
          "value" : "oozie",
          "sensitive" : false
        }, {
          "name" : "sentry_service",
          "value" : "sentry",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_LOAD_BALANCER-5147e609303aee1163da6b5a982396a5",
        "type" : "HUE_LOAD_BALANCER",
        "hostRef" : {
          "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2ha7n4hiioajlydgv31p6ssrm",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-HUE_LOAD_BALANCER-BASE"
        }
      }, {
        "name" : "hue-HUE_SERVER-5147e609303aee1163da6b5a982396a5",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "c12ae3af-94aa-458f-98d7-aab070060fa1",
            "sensitive" : true
          }, {
            "name" : "role_jceks_password",
            "value" : "8nfr8ju7q38irbd3qyvzfo06y",
            "sensitive" : true
          }, {
            "name" : "secret_key",
            "value" : "r4APzhTtI1FX4twrqfVK3d49FCSk70",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-HUE_SERVER-BASE"
        }
      }, {
        "name" : "hue-HUE_SERVER-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "9add06cb-6044-49c5-a207-4fd588706a7d",
            "sensitive" : true
          }, {
            "name" : "role_jceks_password",
            "value" : "dyvtz8tdz13v6fx7sigbmxe97",
            "sensitive" : true
          }, {
            "name" : "secret_key",
            "value" : "Q55FWmIzBuvtyrz9H52iBDlQ9Lj56l",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-HUE_SERVER-BASE"
        }
      }, {
        "name" : "hue-KT_RENEWER-5147e609303aee1163da6b5a982396a5",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1kqj1pn8470036cmeiwd5y5ve",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-KT_RENEWER-BASE"
        }
      }, {
        "name" : "hue-KT_RENEWER-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5nd1mrfkqug3m9f5j1dvizl1u",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-KT_RENEWER-BASE"
        }
      } ],
      "displayName" : "Hue",
      "roleConfigGroups" : [ {
        "name" : "hue-HUE_LOAD_BALANCER-BASE",
        "displayName" : "Load Balancer Default Group",
        "roleType" : "HUE_LOAD_BALANCER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hue-HUE_SERVER-BASE",
        "displayName" : "Hue Server Default Group",
        "roleType" : "HUE_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hue-KT_RENEWER-BASE",
        "displayName" : "Kerberos Ticket Renewer Default Group",
        "roleType" : "KT_RENEWER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      } ]
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive",
          "sensitive" : false
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9zd35avvbnoti9fpycuh8xer7",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "oozie-OOZIE_SERVER-BASE"
        }
      } ],
      "displayName" : "Oozie",
      "roleConfigGroups" : [ {
        "name" : "oozie-OOZIE_SERVER-BASE",
        "displayName" : "Oozie Server Default Group",
        "roleType" : "OOZIE_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "oozie"
        },
        "config" : {
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-30-26.ec2.internal",
            "sensitive" : false
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie_password",
            "sensitive" : true
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql",
            "sensitive" : false
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie",
            "sensitive" : false
          } ]
        }
      } ]
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs",
          "sensitive" : false
        }, {
          "name" : "rm_dirty",
          "value" : "false",
          "sensitive" : false
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "80",
          "sensitive" : false
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false",
          "sensitive" : false
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false",
          "sensitive" : false
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "7X2vBEYKesbiGptWYowvL5r3FCzvch",
          "sensitive" : true
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7co8w03bd994osssnjlb7tvts",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-JOBHISTORY-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-5147e609303aee1163da6b5a982396a5",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1i67i3z0avqwlr3aeusenzk8e",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b63dioao2y8wx0chfy8rtum55",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-3"
        }
      }, {
        "name" : "yarn-NODEMANAGER-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b21nr1uztd84qjr8f07nssgfr",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-2"
        }
      }, {
        "name" : "yarn-NODEMANAGER-c0ade2d345bd6f8625aa06da59354a0e",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "adfgmog2x61mjp3psnrxh7mnf",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-1"
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "53",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "9ln7pnrxs5ee6fpbfeuzsfcxr",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-RESOURCEMANAGER-BASE"
        }
      } ],
      "displayName" : "YARN (MR2 Included)",
      "roleConfigGroups" : [ {
        "name" : "yarn-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "16",
            "sensitive" : false
          }, {
            "name" : "mapred_submit_replication",
            "value" : "3",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "yarn-JOBHISTORY-BASE",
        "displayName" : "JobHistory Server Default Group",
        "roleType" : "JOBHISTORY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-1",
        "displayName" : "NodeManager Group 1",
        "roleType" : "NODEMANAGER",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1600",
            "sensitive" : false
          }, {
            "name" : "rm_io_weight",
            "value" : "800",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/data/disk0/yarn/nm,/data/disk1/yarn/nm",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/data/disk0/yarn/container-logs,/data/disk1/yarn/container-logs",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "6",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "6096",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-2",
        "displayName" : "NodeManager Group 2",
        "roleType" : "NODEMANAGER",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/data/disk0/yarn/nm,/data/disk1/yarn/nm",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/data/disk0/yarn/container-logs,/data/disk1/yarn/container-logs",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "7201",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-3",
        "displayName" : "NodeManager Group 3",
        "roleType" : "NODEMANAGER",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/data/disk0/yarn/nm,/data/disk1/yarn/nm",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/data/disk0/yarn/container-logs,/data/disk1/yarn/container-logs",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "15342",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-BASE",
        "displayName" : "NodeManager Default Group",
        "roleType" : "NODEMANAGER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/data/disk0/yarn/nm,/data/disk1/yarn/nm",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/data/disk0/yarn/container-logs,/data/disk1/yarn/container-logs",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "9352",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-BASE",
        "displayName" : "ResourceManager Default Group",
        "roleType" : "RESOURCEMANAGER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "15342",
            "sensitive" : false
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "6",
            "sensitive" : false
          } ]
        }
      } ]
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "items" : [ {
          "name" : "dfs_block_size",
          "value" : "268435456",
          "sensitive" : false
        }, {
          "name" : "dfs_encrypt_data_transfer_algorithm",
          "value" : "AES/CTR/NoPadding",
          "sensitive" : false
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "eccjgEvRHhhDrmPM0WhnvTXSYLDGdB",
          "sensitive" : true
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "TyQEF8IAJxCmY3wLeJM1jKZIPhOKRK",
          "sensitive" : true
        }, {
          "name" : "hadoop_security_authentication",
          "value" : "kerberos",
          "sensitive" : false
        }, {
          "name" : "hadoop_security_authorization",
          "value" : "true",
          "sensitive" : false
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "OnlHrLq8tpK6gNg0TKMs3Syz8SXFIM",
          "sensitive" : true
        }, {
          "name" : "rm_dirty",
          "value" : "false",
          "sensitive" : false
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "20",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-BALANCER-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-5147e609303aee1163da6b5a982396a5",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "418u0858gpfkfspeh9diba9gz",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8aukvyvwrn6z73ozdwkz28zeo",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3yopp7wda2j5piebmitnmudsu",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-c0ade2d345bd6f8625aa06da59354a0e",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d63pt7km10h2k9iqy80eglbv5",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-35812a9edba9b2239c57dce1004e1e38",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "ecb87495-0d9a-4f21-99ba-4f5ca1fd3fd2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "byaz20kl76uflygwawxrckna1",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-FAILOVERCONTROLLER-BASE"
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bj2dv8whey8oggs0a6ovrk4y5",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-FAILOVERCONTROLLER-BASE"
        }
      }, {
        "name" : "hdfs-HTTPFS-7dfcef43b14e331d1982a8d7e1ad3082",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1nzdcqg4zqflq716beatjsxml",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-HTTPFS-BASE"
        }
      }, {
        "name" : "hdfs-JOURNALNODE-35812a9edba9b2239c57dce1004e1e38",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "ecb87495-0d9a-4f21-99ba-4f5ca1fd3fd2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "el951k69iragal4zwq1bswa6e",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
        }
      }, {
        "name" : "hdfs-JOURNALNODE-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "76yn6xcr7fp90ki8wvauz3zra",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
        }
      }, {
        "name" : "hdfs-JOURNALNODE-c0ade2d345bd6f8625aa06da59354a0e",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4iks7gn6h8zo9oa5tociuu5ht",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
        }
      }, {
        "name" : "hdfs-NAMENODE-35812a9edba9b2239c57dce1004e1e38",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "ecb87495-0d9a-4f21-99ba-4f5ca1fd3fd2"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true",
            "sensitive" : false
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1",
            "sensitive" : false
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1",
            "sensitive" : false
          }, {
            "name" : "namenode_id",
            "value" : "61",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "awd2sefa0nxw3b0sbwvxah7ab",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-NAMENODE-BASE"
        }
      }, {
        "name" : "hdfs-NAMENODE-8c8b4bc041f656037b1dafb7e133bb06",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true",
            "sensitive" : false
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1",
            "sensitive" : false
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1",
            "sensitive" : false
          }, {
            "name" : "namenode_id",
            "value" : "55",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "dpck0uyc1e82ffllp71icrmjj",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-NAMENODE-BASE"
        }
      } ],
      "displayName" : "HDFS",
      "roleConfigGroups" : [ {
        "name" : "hdfs-BALANCER-BASE",
        "displayName" : "Balancer Default Group",
        "roleType" : "BALANCER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-BASE",
        "displayName" : "DataNode Default Group",
        "roleType" : "DATANODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824",
            "sensitive" : false
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/data/disk0/dfs/dn,/data/disk1/dfs/dn",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_data_dir_perm",
            "value" : "700",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "8441707724",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_http_port",
            "value" : "1006",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4296015872",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_port",
            "value" : "1004",
            "sensitive" : false
          }, {
            "name" : "rm_cpu_shares",
            "value" : "400",
            "sensitive" : false
          }, {
            "name" : "rm_io_weight",
            "value" : "200",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-BASE",
        "displayName" : "Failover Controller Default Group",
        "roleType" : "FAILOVERCONTROLLER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-BASE",
        "displayName" : "HttpFS Default Group",
        "roleType" : "HTTPFS",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-BASE",
        "displayName" : "JournalNode Default Group",
        "roleType" : "JOURNALNODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/data/jn",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-BASE",
        "displayName" : "NameNode Default Group",
        "roleType" : "NAMENODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/data/disk0/dfs/nn,/data/disk1/dfs/nn",
            "sensitive" : false
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-NFSGATEWAY-BASE",
        "displayName" : "NFS Gateway Default Group",
        "roleType" : "NFSGATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-SECONDARYNAMENODE-BASE",
        "displayName" : "SecondaryNameNode Default Group",
        "roleType" : "SECONDARYNAMENODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/data/disk0/dfs/snn",
            "sensitive" : false
          } ]
        }
      } ],
      "replicationSchedules" : [ ],
      "snapshotPolicies" : [ ]
    }, {
      "name" : "sentry",
      "type" : "SENTRY",
      "config" : {
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs",
          "sensitive" : false
        }, {
          "name" : "sentry_server_database_host",
          "value" : "ip-172-31-30-26.ec2.internal",
          "sensitive" : false
        }, {
          "name" : "sentry_server_database_password",
          "value" : "sentry_password",
          "sensitive" : true
        }, {
          "name" : "sentry_service_admin_group",
          "value" : "hive,impala,hue,solr,kafka,landyrt,dobeslao",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "sentry-GATEWAY-c0ade2d345bd6f8625aa06da59354a0e",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "sentry-GATEWAY-BASE"
        }
      }, {
        "name" : "sentry-SENTRY_SERVER-35812a9edba9b2239c57dce1004e1e38",
        "type" : "SENTRY_SERVER",
        "hostRef" : {
          "hostId" : "ecb87495-0d9a-4f21-99ba-4f5ca1fd3fd2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6y59tih1dzukviii9wvatet70",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "sentry-SENTRY_SERVER-BASE"
        }
      } ],
      "displayName" : "Sentry",
      "roleConfigGroups" : [ {
        "name" : "sentry-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "sentry"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-SENTRY_SERVER-BASE",
        "displayName" : "Sentry Server Default Group",
        "roleType" : "SENTRY_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "sentry"
        },
        "config" : {
          "items" : [ ]
        }
      } ]
    } ],
    "parcels" : [ {
      "product" : "CDH",
      "version" : "5.12.1-1.cdh5.12.1.p0.3",
      "stage" : "DISTRIBUTED",
      "clusterRef" : {
        "clusterName" : "cluster"
      }
    }, {
      "product" : "CDH",
      "version" : "5.12.1-1.cdh5.12.1.p0.3",
      "stage" : "ACTIVATED",
      "clusterRef" : {
        "clusterName" : "cluster"
      }
    } ],
    "uuid" : "d7863064-1516-4e1d-b995-134e1b321203"
  } ],
  "hosts" : [ {
    "hostId" : "ecb87495-0d9a-4f21-99ba-4f5ca1fd3fd2",
    "ipAddress" : "172.31.20.135",
    "hostname" : "ip-172-31-20-135.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "87f5672d-9923-4539-a5a2-26d2e9a8f0cd",
    "ipAddress" : "172.31.20.150",
    "hostname" : "ip-172-31-20-150.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6",
    "ipAddress" : "172.31.26.122",
    "hostname" : "ip-172-31-26-122.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "c5184015-98dd-48d6-a0ec-584eba53171d",
    "ipAddress" : "172.31.29.75",
    "hostname" : "ip-172-31-29-75.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "14387c9c-b5c7-4854-a634-6867fdd479cf",
    "ipAddress" : "172.31.30.26",
    "hostname" : "ip-172-31-30-26.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-5147e609303aee1163da6b5a982396a5",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "8beea127be927254b8e50805d8b170c55e6ec3bac2cc933c472614c93fe59ea1",
    "pwSalt" : -344310832648576696,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-7dfcef43b14e331d1982a8d7e1ad3082",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "79515f2c4a7a7fb629c12403db67aacf1326f5317857dcf50f8ee49216667f10",
    "pwSalt" : 2111005832172600606,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-5147e609303aee1163da6b5a982396a5",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "ed9dec09092a2b89331c8ea60c775b0eacb4bf84f5a8d6da4cf5ef71b43fdb03",
    "pwSalt" : 1862291387757504212,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-5147e609303aee1163da6b5a982396a5",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "0414fb3050e3e697d95931ed420d5dbcead69b03d759a674e6becd02f68d06b2",
    "pwSalt" : 2466773687176328337,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-5147e609303aee1163da6b5a982396a5",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "3354390dd63c564a2fdcc7cd82dfd80d7d6534d4fabd5a42176db3180a4a3ca2",
    "pwSalt" : -3576337246790522348,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-5147e609303aee1163da6b5a982396a5",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "f05fa9866869be3ad3590062f6eebe66a1b3898dc6feaa5a03d9067464486bfa",
    "pwSalt" : 7261445842376866732,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "154c75b86b1488ee6918c20a1e23c0e34d973dc4c77d46451efef274147ec5f6",
    "pwSalt" : -1603343470102836567,
    "pwLogin" : true
  }, {
    "name" : "dobeslao",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "76ea2deb6197023eefc97fc43728aa90b335d22812c1840dde312f599acb7674",
    "pwSalt" : -8191140385262008050,
    "pwLogin" : true
  }, {
    "name" : "landyrt",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "f42df10f5c6f8811c2f7838c247e25ba948ca1a268f587005debf4b3e229e226",
    "pwSalt" : -8584677058958715444,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "e05ff550d7e5232205e1321f31ce7ef39132fb3209962bf15d42c89a686dc877",
    "pwSalt" : 1724677452638589553,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.13.0",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20171002-1719",
    "gitHash" : "bd657e597e6743c458ee2c9aabe808b7c972981c",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-5147e609303aee1163da6b5a982396a5",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "4pyr4h3q3y926aamniryq4q6n",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-ALERTPUBLISHER-BASE"
      }
    }, {
      "name" : "mgmt-EVENTSERVER-5147e609303aee1163da6b5a982396a5",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "bz8lt0k9ibm19xmtbq8l0bezu",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-EVENTSERVER-BASE"
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-5147e609303aee1163da6b5a982396a5",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "f034kn2yhodkd8ugsqktq4fjh",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-HOSTMONITOR-BASE"
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-5147e609303aee1163da6b5a982396a5",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "67u9ik5z78br8hzqhqdjlxee5",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-REPORTSMANAGER-BASE"
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-5147e609303aee1163da6b5a982396a5",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "af17a197-450c-4871-93dc-2d3a93fa26e6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "dbr35vfvkdyvaj5bsl2zvoyt2",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-SERVICEMONITOR-BASE"
      }
    } ],
    "displayName" : "Landy Reyes",
    "roleConfigGroups" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-BASE",
      "displayName" : "Activity Monitor Default Group",
      "roleType" : "ACTIVITYMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-BASE",
      "displayName" : "Alert Publisher Default Group",
      "roleType" : "ALERTPUBLISHER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-BASE",
      "displayName" : "Event Server Default Group",
      "roleType" : "EVENTSERVER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-BASE",
      "displayName" : "Host Monitor Default Group",
      "roleType" : "HOSTMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-NAVIGATOR-BASE",
      "displayName" : "Navigator Audit Server Default Group",
      "roleType" : "NAVIGATOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-NAVIGATORMETASERVER-BASE",
      "displayName" : "Navigator Metadata Server Default Group",
      "roleType" : "NAVIGATORMETASERVER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-BASE",
      "displayName" : "Reports Manager Default Group",
      "roleType" : "REPORTSMANAGER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-30-26.ec2.internal",
          "sensitive" : false
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman",
          "sensitive" : false
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password",
          "sensitive" : true
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-BASE",
      "displayName" : "Service Monitor Default Group",
      "roleType" : "SERVICEMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-TELEMETRYPUBLISHER-BASE",
      "displayName" : "Telemetry Publisher Default Group",
      "roleType" : "TELEMETRYPUBLISHER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    } ]
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "AD_USE_SIMPLE_AUTH",
      "value" : "false",
      "sensitive" : false
    }, {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/23/2012 2:10",
      "sensitive" : false
    }, {
      "name" : "KDC_ADMIN_HOST",
      "value" : "ip-172-31-30-26.ec2.internal",
      "sensitive" : false
    }, {
      "name" : "KDC_ADMIN_PASSWORD",
      "value" : "BQIAAAA9AAEAClZJTktPUy5DT00ADGNsb3VkZXJhLXNjbQAAAAFaHvJ8AQAXABCIRvfq7o+xF60Gvdgwt1hsAAAAAQ==",
      "sensitive" : true
    }, {
      "name" : "KDC_ADMIN_USER",
      "value" : "cloudera-scm@VINKOS.COM",
      "sensitive" : false
    }, {
      "name" : "KDC_HOST",
      "value" : "ip-172-31-30-26.ec2.internal",
      "sensitive" : false
    }, {
      "name" : "KRB_MANAGE_KRB5_CONF",
      "value" : "true",
      "sensitive" : false
    }, {
      "name" : "MAX_RENEW_LIFE",
      "value" : "604800",
      "sensitive" : false
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD",
      "sensitive" : false
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "http://ip-172-31-30-26.ec2.internal/parcels/cdh5/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,http://ip-172-31-30-26.ec2.internal/parcels/spark2/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/",
      "sensitive" : false
    }, {
      "name" : "SECURITY_REALM",
      "value" : "VINKOS.COM",
      "sensitive" : false
    } ]
  },
  "allHostsConfig" : {
    "items" : [ {
      "name" : "rm_enabled",
      "value" : "true",
      "sensitive" : false
    } ]
  },
  "peers" : [ ],
  "hostTemplates" : {
    "items" : [ ]
  }
}

```

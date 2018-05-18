```
{
  "timestamp" : "2018-05-18T05:37:10.792Z",
  "clusters" : [ {
    "name" : "cluster",
    "displayName" : "moonyaero",
    "version" : "CDH5",
    "fullVersion" : "5.11.2",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-9dc69fca9bcfd5d9d72d0f07727b21c5",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "bd8b8758-2ac6-4e51-9ddb-3d34d5208c02"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dcq5mr21nhsw0pfxvyvwzz4k7",
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
        "name" : "zookeeper-SERVER-d6cb8f6137f6b3fe4c2ae790457fe56a",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "6024d8af-602a-40b9-a2b0-f67e8c9b571e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6no5e6joyk0fl4j5242z6a32d",
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
        "name" : "zookeeper-SERVER-e77e9cc362408b6d57aff4b2c97bc68d",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "a59c052e-c3f1-4d0c-a3bf-a175cec94d3c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "81vjsyvih6slsmxfulsqs597q",
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
          "items" : [ {
            "name" : "maxSessionTimeout",
            "value" : "60000",
            "sensitive" : false
          } ]
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
        "name" : "oozie-OOZIE_SERVER-d6cb8f6137f6b3fe4c2ae790457fe56a",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "6024d8af-602a-40b9-a2b0-f67e8c9b571e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d5tw0c96v8bnjrvtmwjcpq5do",
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
            "value" : "ip-172-31-27-72.ap-southeast-1.compute.internal",
            "sensitive" : false
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie",
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
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-27-72.ap-southeast-1.compute.internal",
          "sensitive" : false
        }, {
          "name" : "database_password",
          "value" : "huepassword",
          "sensitive" : true
        }, {
          "name" : "database_type",
          "value" : "mysql",
          "sensitive" : false
        }, {
          "name" : "hbase_service",
          "value" : "hbase",
          "sensitive" : false
        }, {
          "name" : "hive_service",
          "value" : "hive",
          "sensitive" : false
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-d6cb8f6137f6b3fe4c2ae790457fe56a",
          "sensitive" : false
        }, {
          "name" : "oozie_service",
          "value" : "oozie",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-d6cb8f6137f6b3fe4c2ae790457fe56a",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "6024d8af-602a-40b9-a2b0-f67e8c9b571e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "57bwf54a6hgrlprtnivkxxp0r",
            "sensitive" : true
          }, {
            "name" : "secret_key",
            "value" : "q50KzUscOZWC1LMWT1aWH5FIZcY0Sl",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-HUE_SERVER-BASE"
        }
      }, {
        "name" : "hue-HUE_SERVER-e77e9cc362408b6d57aff4b2c97bc68d",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "a59c052e-c3f1-4d0c-a3bf-a175cec94d3c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1n0g2l0xy1sc60gfz73usparm",
            "sensitive" : true
          }, {
            "name" : "secret_key",
            "value" : "FaNhGSZwwCsXSkhcRUalKRACi9b6Oa",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-HUE_SERVER-BASE"
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
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "2Vdpsm5vmeJEbXLdoMZSwqATE5frd2",
          "sensitive" : true
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "ypNSLnaAo8rvfG444ZxYyxNJSEvBPq",
          "sensitive" : true
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "ijvRgnoPbVNEbDza5B2X74tV48WBgy",
          "sensitive" : true
        }, {
          "name" : "rm_dirty",
          "value" : "true",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-d6cb8f6137f6b3fe4c2ae790457fe56a",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "6024d8af-602a-40b9-a2b0-f67e8c9b571e"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-BALANCER-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-1cb1e551c13afe4a2714556d81c405a8",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "bab5aea5-1c39-44a9-baaa-c5d99249b1a8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "wjgx04wvg3j3cl40websnh9s",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-2b4abac0b7b8abc226515972940b68f7",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "7d16db5b-cff7-4bb7-9ab0-4dbbd97097ca"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "rikl3b7q5mesayxuk8ukh9at",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-e77e9cc362408b6d57aff4b2c97bc68d",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "a59c052e-c3f1-4d0c-a3bf-a175cec94d3c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "aln4u66ny111loammfr8p01wt",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-1"
        }
      }, {
        "name" : "hdfs-NAMENODE-d6cb8f6137f6b3fe4c2ae790457fe56a",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "6024d8af-602a-40b9-a2b0-f67e8c9b571e"
        },
        "config" : {
          "items" : [ {
            "name" : "namenode_id",
            "value" : "49",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "47pcq4lgavytnxug727i4iopi",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-NAMENODE-BASE"
        }
      }, {
        "name" : "hdfs-SECONDARYNAMENODE-9dc69fca9bcfd5d9d72d0f07727b21c5",
        "type" : "SECONDARYNAMENODE",
        "hostRef" : {
          "hostId" : "bd8b8758-2ac6-4e51-9ddb-3d34d5208c02"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b0u4ispfaitmaweask20mov95",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-SECONDARYNAMENODE-BASE"
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
        "name" : "hdfs-DATANODE-1",
        "displayName" : "DataNode Group 1",
        "roleType" : "DATANODE",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "5367448780",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "2598371328",
            "sensitive" : false
          } ]
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
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "5367448780",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "3153068032",
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
          "items" : [ ]
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
            "value" : "/dfs/nn",
            "sensitive" : false
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022",
            "sensitive" : false
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "1179648000",
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
            "value" : "/dfs/snn",
            "sensitive" : false
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "1179648000",
            "sensitive" : false
          } ]
        }
      } ],
      "replicationSchedules" : [ ],
      "snapshotPolicies" : [ ]
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
          "value" : "true",
          "sensitive" : false
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "z4KGhSPZlWDD1N14wDuF5D1Pd5inBz",
          "sensitive" : true
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-9dc69fca9bcfd5d9d72d0f07727b21c5",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "bd8b8758-2ac6-4e51-9ddb-3d34d5208c02"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "av3ugvhuk5ff9c99ym5a0ux95",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-JOBHISTORY-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-1cb1e551c13afe4a2714556d81c405a8",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "bab5aea5-1c39-44a9-baaa-c5d99249b1a8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b2nuty1j86rz1486tu4cliifi",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-2b4abac0b7b8abc226515972940b68f7",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "7d16db5b-cff7-4bb7-9ab0-4dbbd97097ca"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4dayeb3939dbwczom4zr2txhk",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-e77e9cc362408b6d57aff4b2c97bc68d",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "a59c052e-c3f1-4d0c-a3bf-a175cec94d3c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2us2zvnh5ogl0qeo4e04cmk1v",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-1"
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-d6cb8f6137f6b3fe4c2ae790457fe56a",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "6024d8af-602a-40b9-a2b0-f67e8c9b571e"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "55",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "2vseunz2ln6eeo2nz41jw2sli",
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
            "value" : "6",
            "sensitive" : false
          }, {
            "name" : "mapred_submit_replication",
            "value" : "1",
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
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "4",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "2478",
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
            "value" : "/yarn/nm",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "4",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "3007",
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
            "value" : "3007",
            "sensitive" : false
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "4",
            "sensitive" : false
          } ]
        }
      } ]
    }, {
      "name" : "hbase",
      "type" : "HBASE",
      "config" : {
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs",
          "sensitive" : false
        }, {
          "name" : "rm_dirty",
          "value" : "true",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "hbase-MASTER-d6cb8f6137f6b3fe4c2ae790457fe56a",
        "type" : "MASTER",
        "hostRef" : {
          "hostId" : "6024d8af-602a-40b9-a2b0-f67e8c9b571e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8tsi4rksc9od16r8kmxvb6grj",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hbase-MASTER-BASE"
        }
      }, {
        "name" : "hbase-REGIONSERVER-1cb1e551c13afe4a2714556d81c405a8",
        "type" : "REGIONSERVER",
        "hostRef" : {
          "hostId" : "bab5aea5-1c39-44a9-baaa-c5d99249b1a8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dwnf15m50e1uds7z97qawohl9",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hbase-REGIONSERVER-BASE"
        }
      }, {
        "name" : "hbase-REGIONSERVER-2b4abac0b7b8abc226515972940b68f7",
        "type" : "REGIONSERVER",
        "hostRef" : {
          "hostId" : "7d16db5b-cff7-4bb7-9ab0-4dbbd97097ca"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6z4ubt1lkzvh3ci25xywtnt9h",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hbase-REGIONSERVER-BASE"
        }
      }, {
        "name" : "hbase-REGIONSERVER-e77e9cc362408b6d57aff4b2c97bc68d",
        "type" : "REGIONSERVER",
        "hostRef" : {
          "hostId" : "a59c052e-c3f1-4d0c-a3bf-a175cec94d3c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6uv12fxmfwdcpm9ceze01k3md",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hbase-REGIONSERVER-1"
        }
      } ],
      "displayName" : "HBase",
      "roleConfigGroups" : [ {
        "name" : "hbase-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hbase"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hbase-HBASERESTSERVER-BASE",
        "displayName" : "HBase REST Server Default Group",
        "roleType" : "HBASERESTSERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hbase"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hbase-HBASETHRIFTSERVER-BASE",
        "displayName" : "HBase Thrift Server Default Group",
        "roleType" : "HBASETHRIFTSERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hbase"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hbase-MASTER-BASE",
        "displayName" : "Master Default Group",
        "roleType" : "MASTER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hbase"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hbase-REGIONSERVER-1",
        "displayName" : "RegionServer Group 1",
        "roleType" : "REGIONSERVER",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hbase"
        },
        "config" : {
          "items" : [ {
            "name" : "hbase_regionserver_java_heapsize",
            "value" : "1998585856",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hbase-REGIONSERVER-BASE",
        "displayName" : "RegionServer Default Group",
        "roleType" : "REGIONSERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hbase"
        },
        "config" : {
          "items" : [ {
            "name" : "hbase_regionserver_java_heapsize",
            "value" : "2425356288",
            "sensitive" : false
          } ]
        }
      } ],
      "snapshotPolicies" : [ ]
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "items" : [ {
          "name" : "hbase_service",
          "value" : "hbase",
          "sensitive" : false
        }, {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-27-72.ap-southeast-1.compute.internal",
          "sensitive" : false
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password",
          "sensitive" : true
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
        "name" : "hive-GATEWAY-1cb1e551c13afe4a2714556d81c405a8",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "bab5aea5-1c39-44a9-baaa-c5d99249b1a8"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-2b4abac0b7b8abc226515972940b68f7",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "7d16db5b-cff7-4bb7-9ab0-4dbbd97097ca"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-9dc69fca9bcfd5d9d72d0f07727b21c5",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "bd8b8758-2ac6-4e51-9ddb-3d34d5208c02"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-d6cb8f6137f6b3fe4c2ae790457fe56a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "6024d8af-602a-40b9-a2b0-f67e8c9b571e"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-e77e9cc362408b6d57aff4b2c97bc68d",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "a59c052e-c3f1-4d0c-a3bf-a175cec94d3c"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-HIVEMETASTORE-d6cb8f6137f6b3fe4c2ae790457fe56a",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "6024d8af-602a-40b9-a2b0-f67e8c9b571e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b01zve6yk9di3nmpu5ci3453y",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVEMETASTORE-BASE"
        }
      }, {
        "name" : "hive-HIVESERVER2-d6cb8f6137f6b3fe4c2ae790457fe56a",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "6024d8af-602a-40b9-a2b0-f67e8c9b571e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "aouegptgtvispx8llyssxzqs9",
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
            "name" : "hive_metastore_java_heapsize",
            "value" : "1558183936",
            "sensitive" : false
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "155818393",
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
            "name" : "hiveserver2_java_heapsize",
            "value" : "1558183936",
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
            "value" : "2208615628",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "371",
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
    } ],
    "parcels" : [ {
      "product" : "CDH",
      "version" : "5.11.2-1.cdh5.11.2.p0.4",
      "stage" : "DISTRIBUTED",
      "clusterRef" : {
        "clusterName" : "cluster"
      }
    }, {
      "product" : "CDH",
      "version" : "5.11.2-1.cdh5.11.2.p0.4",
      "stage" : "ACTIVATED",
      "clusterRef" : {
        "clusterName" : "cluster"
      }
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "a59c052e-c3f1-4d0c-a3bf-a175cec94d3c",
    "ipAddress" : "172.31.25.84",
    "hostname" : "ip-172-31-25-84.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "6024d8af-602a-40b9-a2b0-f67e8c9b571e",
    "ipAddress" : "172.31.27.72",
    "hostname" : "ip-172-31-27-72.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "bab5aea5-1c39-44a9-baaa-c5d99249b1a8",
    "ipAddress" : "172.31.28.189",
    "hostname" : "ip-172-31-28-189.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "7d16db5b-cff7-4bb7-9ab0-4dbbd97097ca",
    "ipAddress" : "172.31.28.78",
    "hostname" : "ip-172-31-28-78.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "bd8b8758-2ac6-4e51-9ddb-3d34d5208c02",
    "ipAddress" : "172.31.29.43",
    "hostname" : "ip-172-31-29-43.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-9dc69fca9bcfd5d9d72d0f07727b21c5",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "7accea07708cc540434df5999468fd82d82d6efa84826c79e6173d9ba1f9d948",
    "pwSalt" : 9181069184187618965,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-9dc69fca9bcfd5d9d72d0f07727b21c5",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "27bc50155e06115158453eb67800e6c25564c7ea89fc59e45a6186e43fba0d7a",
    "pwSalt" : 1367351333932794514,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-9dc69fca9bcfd5d9d72d0f07727b21c5",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "0b1b6037bc45d37fb65c536b0d54cb5de02ab641013077347436c3d5694fb55b",
    "pwSalt" : -3141181362232403641,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-9dc69fca9bcfd5d9d72d0f07727b21c5",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "d03a8792717977979d1d5e692756010329f7b094cd0e5c99643d189c3dade123",
    "pwSalt" : -6132423777351285055,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "1b3fc31ebaa1904d047ae14f5c32f18fb8d6d132f7693941c4f53921c9ade60d",
    "pwSalt" : 4334178662735142940,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.11.2",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20170811-0014",
    "gitHash" : "3c3ea33a12076fb83a8f11c4452c52fac685d01b",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-9dc69fca9bcfd5d9d72d0f07727b21c5",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "bd8b8758-2ac6-4e51-9ddb-3d34d5208c02"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "8rx5zo5zdgr77yijt336mujy2",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-ALERTPUBLISHER-BASE"
      }
    }, {
      "name" : "mgmt-EVENTSERVER-9dc69fca9bcfd5d9d72d0f07727b21c5",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "bd8b8758-2ac6-4e51-9ddb-3d34d5208c02"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "a11vef4t65ew3mumuitmti3pc",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-EVENTSERVER-BASE"
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-9dc69fca9bcfd5d9d72d0f07727b21c5",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "bd8b8758-2ac6-4e51-9ddb-3d34d5208c02"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "9jx2kqed3y1gat5tispm6cya7",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-HOSTMONITOR-BASE"
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-9dc69fca9bcfd5d9d72d0f07727b21c5",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "bd8b8758-2ac6-4e51-9ddb-3d34d5208c02"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "ecqqiuhbmmgmcomjcyg18y2ef",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-REPORTSMANAGER-BASE"
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-9dc69fca9bcfd5d9d72d0f07727b21c5",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "bd8b8758-2ac6-4e51-9ddb-3d34d5208c02"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "d61wwnmjwixx8clsnxnaleh55",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-SERVICEMONITOR-BASE"
      }
    } ],
    "displayName" : "Cloudera Management Service",
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
          "value" : "1533018112",
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
          "value" : "ip-172-31-27-72.ap-southeast-1.compute.internal",
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
          "value" : "1533018112",
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
      "name" : "CLUSTER_STATS_START",
      "value" : "10/27/2012 6:10",
      "sensitive" : false
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD",
      "sensitive" : false
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "http://ip-172-31-29-43.ap-southeast-1.compute.internal/cloudera",
      "sensitive" : false
    } ]
  },
  "allHostsConfig" : {
    "items" : [ ]
  },
  "peers" : [ ],
  "hostTemplates" : {
    "items" : [ ]
  }
}
```
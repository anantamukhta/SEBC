{
  "timestamp" : "2018-05-18T05:29:24.295Z",
  "clusters" : [ {
    "name" : "cluster",
    "displayName" : "anantamukhta",
    "version" : "CDH5",
    "fullVersion" : "5.11.2",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-523618e8b6d554730a3ae372c6e47b2e",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "216cf7fa-a2ff-4f7c-8343-8e77f5b77551"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d1mxnjqdxandj381m9hj5lym",
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
        "name" : "oozie-OOZIE_SERVER-8d51115512473164d457b851a325e612",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "1e407ceb-ee54-4b8c-a73c-9d993c0e1255"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1in595kdv9qoamsnxgtgkemy8",
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
            "value" : "172.31.22.135",
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
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "800063488",
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
          "value" : "172.31.22.135",
          "sensitive" : false
        }, {
          "name" : "database_password",
          "value" : "hue",
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
          "value" : "hdfs-NAMENODE-523618e8b6d554730a3ae372c6e47b2e",
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
        "name" : "hue-HUE_SERVER-8d51115512473164d457b851a325e612",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "1e407ceb-ee54-4b8c-a73c-9d993c0e1255"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5osn09doh6gwshdkobz80oq9c",
            "sensitive" : true
          }, {
            "name" : "secret_key",
            "value" : "HuHnlIkVnenPDFZ2HlJod9I4ziVdPS",
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
          "value" : "grfavo8qQi4At9ZAZJA298CYTh7ZBF",
          "sensitive" : true
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "AOEZurYOAatcjK8NKWSaeWeNFrMcNJ",
          "sensitive" : true
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "7nCKihaJFRAbzwQN6kDPcPTHxORmzI",
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
        "name" : "hdfs-BALANCER-8d51115512473164d457b851a325e612",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "1e407ceb-ee54-4b8c-a73c-9d993c0e1255"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-BALANCER-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-1938cf11a930e62ab7ceaacb3023f1b0",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "07acdb97-4b12-4f29-9179-2fdfdc5da382"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5h4fb3kfj1go1iy4z6ylzxbsi",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-3e6f6e51f6a5fdaad665de28d5f64bb7",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "f106d9f4-8dd9-472b-b93a-b85f2c81fd2e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dh3vuoxq7yocjjg9upadpo18h",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-e25b85c5301a8633a6d2369886a56abd",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "50b580f2-fe2a-4d17-9798-9995863c58fe"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ermgulmow27hw960rd8jboapa",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-NAMENODE-523618e8b6d554730a3ae372c6e47b2e",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "216cf7fa-a2ff-4f7c-8343-8e77f5b77551"
        },
        "config" : {
          "items" : [ {
            "name" : "namenode_id",
            "value" : "43",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "c9cwtdfcaiwz27v69w75gpw4f",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-NAMENODE-BASE"
        }
      }, {
        "name" : "hdfs-SECONDARYNAMENODE-8d51115512473164d457b851a325e612",
        "type" : "SECONDARYNAMENODE",
        "hostRef" : {
          "hostId" : "1e407ceb-ee54-4b8c-a73c-9d993c0e1255"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "alqy61tss79ies8a10r9q7loc",
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
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "800063488",
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
            "value" : "3080716288",
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
            "value" : "800063488",
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
            "value" : "800063488",
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
          "value" : "NG5Fwkbbp0lcftnvG7ANfsnniWmhlQ",
          "sensitive" : true
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-523618e8b6d554730a3ae372c6e47b2e",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "216cf7fa-a2ff-4f7c-8343-8e77f5b77551"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7fzsi7oupyq4tiyiherlng3fb",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-JOBHISTORY-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-1938cf11a930e62ab7ceaacb3023f1b0",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "07acdb97-4b12-4f29-9179-2fdfdc5da382"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5m7k8w7lio9f6pkh8eb5z9j4r",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-3e6f6e51f6a5fdaad665de28d5f64bb7",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "f106d9f4-8dd9-472b-b93a-b85f2c81fd2e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ab0b9ed14odk9laz2l05791kt",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-e25b85c5301a8633a6d2369886a56abd",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "50b580f2-fe2a-4d17-9798-9995863c58fe"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1nt2xs79bs8boojxdufvgbfg4",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-523618e8b6d554730a3ae372c6e47b2e",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "216cf7fa-a2ff-4f7c-8343-8e77f5b77551"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "49",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "8mxrjf09eeccfxrl946ti2hrt",
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
            "value" : "2938",
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
            "value" : "2938",
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
        "name" : "hbase-MASTER-8d51115512473164d457b851a325e612",
        "type" : "MASTER",
        "hostRef" : {
          "hostId" : "1e407ceb-ee54-4b8c-a73c-9d993c0e1255"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "55syxw2wsdub95zt9guipkwcb",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hbase-MASTER-BASE"
        }
      }, {
        "name" : "hbase-REGIONSERVER-1938cf11a930e62ab7ceaacb3023f1b0",
        "type" : "REGIONSERVER",
        "hostRef" : {
          "hostId" : "07acdb97-4b12-4f29-9179-2fdfdc5da382"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "f1p5hm96laa2fxysvuoi0tf54",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hbase-REGIONSERVER-BASE"
        }
      }, {
        "name" : "hbase-REGIONSERVER-3e6f6e51f6a5fdaad665de28d5f64bb7",
        "type" : "REGIONSERVER",
        "hostRef" : {
          "hostId" : "f106d9f4-8dd9-472b-b93a-b85f2c81fd2e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "597uv32b3bd5i5zz08j91vhmq",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hbase-REGIONSERVER-BASE"
        }
      }, {
        "name" : "hbase-REGIONSERVER-e25b85c5301a8633a6d2369886a56abd",
        "type" : "REGIONSERVER",
        "hostRef" : {
          "hostId" : "50b580f2-fe2a-4d17-9798-9995863c58fe"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "clazljdipi67j6zsotyfu0klt",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hbase-REGIONSERVER-BASE"
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
          "items" : [ {
            "name" : "hbase_master_java_heapsize",
            "value" : "800063488",
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
            "value" : "2369781760",
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
          "value" : "172.31.22.135",
          "sensitive" : false
        }, {
          "name" : "hive_metastore_database_name",
          "value" : "hive",
          "sensitive" : false
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive",
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
        "name" : "hive-GATEWAY-1938cf11a930e62ab7ceaacb3023f1b0",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "07acdb97-4b12-4f29-9179-2fdfdc5da382"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-3e6f6e51f6a5fdaad665de28d5f64bb7",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "f106d9f4-8dd9-472b-b93a-b85f2c81fd2e"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-523618e8b6d554730a3ae372c6e47b2e",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "216cf7fa-a2ff-4f7c-8343-8e77f5b77551"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-8d51115512473164d457b851a325e612",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "1e407ceb-ee54-4b8c-a73c-9d993c0e1255"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-e25b85c5301a8633a6d2369886a56abd",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "50b580f2-fe2a-4d17-9798-9995863c58fe"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-HIVEMETASTORE-8d51115512473164d457b851a325e612",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "1e407ceb-ee54-4b8c-a73c-9d993c0e1255"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "atgyfr414ry5veqkwd3hxzxrf",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVEMETASTORE-BASE"
        }
      }, {
        "name" : "hive-HIVESERVER2-8d51115512473164d457b851a325e612",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "1e407ceb-ee54-4b8c-a73c-9d993c0e1255"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "23pkfqbwoxo8xjrm72772avel",
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
            "value" : "800063488",
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
            "value" : "800063488",
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
            "value" : "2618608844",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "440",
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
    "hostId" : "07acdb97-4b12-4f29-9179-2fdfdc5da382",
    "ipAddress" : "172.31.20.199",
    "hostname" : "ip-172-31-20-199.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "216cf7fa-a2ff-4f7c-8343-8e77f5b77551",
    "ipAddress" : "172.31.22.135",
    "hostname" : "ip-172-31-22-135.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "f106d9f4-8dd9-472b-b93a-b85f2c81fd2e",
    "ipAddress" : "172.31.24.79",
    "hostname" : "ip-172-31-24-79.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "50b580f2-fe2a-4d17-9798-9995863c58fe",
    "ipAddress" : "172.31.28.187",
    "hostname" : "ip-172-31-28-187.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "1e407ceb-ee54-4b8c-a73c-9d993c0e1255",
    "ipAddress" : "172.31.29.229",
    "hostname" : "ip-172-31-29-229.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-8d51115512473164d457b851a325e612",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "5cb3b422acfa7aa64aff37d068f572a1891597e50a0dbc483fb413f2f452eeb0",
    "pwSalt" : -2317303469192740399,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-8d51115512473164d457b851a325e612",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "974ea8a33a0b412d6d315871e889d148dc8f126fe67960c09c592161095f34fb",
    "pwSalt" : -5743678942047571627,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-8d51115512473164d457b851a325e612",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "16fc93b804e0f84ddd59de56cec944718fa02d763898fa547c8706593af6db3b",
    "pwSalt" : -4800600884929576862,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-8d51115512473164d457b851a325e612",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "89982684424b8622029bf957f71ad74ab1732dc73821543fb69bd8a4fad75690",
    "pwSalt" : 9072551211566703364,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "56149e3fc2480daa446308e5742a5afe45407fad1a8f06e2760e3dc9482a952d",
    "pwSalt" : -5147345358079579991,
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
      "name" : "mgmt-ALERTPUBLISHER-8d51115512473164d457b851a325e612",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "1e407ceb-ee54-4b8c-a73c-9d993c0e1255"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "d5sue2jmxb3imp3zwziydqj6m",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-ALERTPUBLISHER-BASE"
      }
    }, {
      "name" : "mgmt-EVENTSERVER-8d51115512473164d457b851a325e612",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "1e407ceb-ee54-4b8c-a73c-9d993c0e1255"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "cutz8d5jvd3rc09kqfi631vhh",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-EVENTSERVER-BASE"
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-8d51115512473164d457b851a325e612",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "1e407ceb-ee54-4b8c-a73c-9d993c0e1255"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "84io6pog8gxw1fj8m5dikbap0",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-HOSTMONITOR-BASE"
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-8d51115512473164d457b851a325e612",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "1e407ceb-ee54-4b8c-a73c-9d993c0e1255"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "6c1cv1j8r9hil61d7h8hiuszi",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-REPORTSMANAGER-BASE"
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-8d51115512473164d457b851a325e612",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "1e407ceb-ee54-4b8c-a73c-9d993c0e1255"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "1iaauhmj6i81zknbvi4g95z8v",
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
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "800063488",
          "sensitive" : false
        } ]
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
          "name" : "firehose_heapsize",
          "value" : "800063488",
          "sensitive" : false
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1040187392",
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
          "value" : "172.31.22.135",
          "sensitive" : false
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman",
          "sensitive" : false
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman",
          "sensitive" : true
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman",
          "sensitive" : false
        }, {
          "name" : "headlamp_heapsize",
          "value" : "800063488",
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
          "name" : "firehose_heapsize",
          "value" : "800063488",
          "sensitive" : false
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1040187392",
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
      "value" : "10/27/2012 10:00",
      "sensitive" : false
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD",
      "sensitive" : false
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "http://13.59.113.141/archive.cloudera.com/cdh5/parcels/5.11.2.4/",
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
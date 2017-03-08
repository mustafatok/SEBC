```json
{
  "timestamp" : "2017-03-08T10:15:09.406Z",
  "clusters" : [ {
    "name" : "mustafatok - SEBC Cluster",
    "version" : "CDH5",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "639631360"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-2b3366c1601e1a708c34eb8c789bb5f8",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-081bda7d9afb467ce"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7r6or7o33wem17hl1ry6aq2yk"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-7a76a2e661adbc46ea1063e4ab90d68d",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-06e752bc92fceb43a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "be5oxokcyjop4fskrl0hcplyq"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-b889abc59d503aafcd93e7738ba641be",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0f77aaf4f002910f9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5ili1c4hvfkdxnkmcnpf4ol1s"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_password",
            "value" : "cloudera"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "639631360"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-7a76a2e661adbc46ea1063e4ab90d68d",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-06e752bc92fceb43a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "calh843tinswftimwn0en2thd"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_password",
          "value" : "cloudera"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-2b3366c1601e1a708c34eb8c789bb5f8"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-7a76a2e661adbc46ea1063e4ab90d68d",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-06e752bc92fceb43a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dzs5kyws3ui6n48yslcgjbf2b"
          }, {
            "name" : "secret_key",
            "value" : "8FFL92Nr9mQFvwxO84eJ1bGp1tXrnF"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "639631360"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "3219965132"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "dfs_datanode_use_datanode_hostname",
            "value" : "true"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_client_use_datanode_hostname",
          "value" : "true"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "pTi4BWGBOAufteDxO0t4ZjXem6EM5J"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "dEQLMaJgcY0Uqzr14exdCKLRNdcY20"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "WllYpi9FLVifkC85BKXAXReU6Zky7a"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-7a76a2e661adbc46ea1063e4ab90d68d",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-06e752bc92fceb43a"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-2b3366c1601e1a708c34eb8c789bb5f8",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-081bda7d9afb467ce"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8cafebhcls9bb1emr8zbu3a6i"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-5e18d307ab3b6c4dee320c667ac8c92c",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0c545b899d71ec1d2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "89en1pa1rtv8196ao05gb21jy"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-b889abc59d503aafcd93e7738ba641be",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0f77aaf4f002910f9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6ih3gt5h3v38gzf6bswmpm3sk"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-c5d2ed92046a5f74dd0f1cad93567a6a",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0e42b56a6ebb510d1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "aofnabn1uq2bnqcixegqdoyzo"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-5e18d307ab3b6c4dee320c667ac8c92c",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0c545b899d71ec1d2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cyyvm3dpcly3ry3922iomj33t"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-7a76a2e661adbc46ea1063e4ab90d68d",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-06e752bc92fceb43a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "47nlhqxm6v6b83n40d9dnda9q"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-2b3366c1601e1a708c34eb8c789bb5f8",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "i-081bda7d9afb467ce"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "c3sw8eeulgd26b8v6t9uqmsvx"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-2b3366c1601e1a708c34eb8c789bb5f8",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-081bda7d9afb467ce"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2hdw47q822z0bkj9vglarjvkx"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-5e18d307ab3b6c4dee320c667ac8c92c",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0c545b899d71ec1d2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "11ohd6kpqqiw7nxids2uwgw33"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-7a76a2e661adbc46ea1063e4ab90d68d",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-06e752bc92fceb43a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1trl1dz6t2yr985hj00ubka2i"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-5e18d307ab3b6c4dee320c667ac8c92c",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0c545b899d71ec1d2"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "61"
          }, {
            "name" : "role_jceks_password",
            "value" : "11t5uyaf9nfaqdr0rdzvcnxhm"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-7a76a2e661adbc46ea1063e4ab90d68d",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-06e752bc92fceb43a"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "46"
          }, {
            "name" : "role_jceks_password",
            "value" : "5rbfx2qr5hcvtbqz2c4c5z66v"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "639631360"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "4939"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "639631360"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4939"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "PIpPrxUY4tqdEeS9LWOaWfQsMhBuB5"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-7a76a2e661adbc46ea1063e4ab90d68d",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-06e752bc92fceb43a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "df5zhebwr6z0h0zycb3d53143"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-2b3366c1601e1a708c34eb8c789bb5f8",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-081bda7d9afb467ce"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a59jsj56eh7pr0ckqrljvgu9a"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-5e18d307ab3b6c4dee320c667ac8c92c",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0c545b899d71ec1d2"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5t5xhraxlv7dw5w3v6992k58f"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-b889abc59d503aafcd93e7738ba641be",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0f77aaf4f002910f9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "26maflzhsnicj0kvyfcr7gnlb"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-c5d2ed92046a5f74dd0f1cad93567a6a",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0e42b56a6ebb510d1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1e2xmxnbop633hxfrtb1tj4a0"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-7a76a2e661adbc46ea1063e4ab90d68d",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-06e752bc92fceb43a"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "53"
          }, {
            "name" : "role_jceks_password",
            "value" : "3y8nft617mqmbuwk43s4xfang"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "639631360"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "639631360"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "2288831692"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "385"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_password",
          "value" : "cloudera"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-2b3366c1601e1a708c34eb8c789bb5f8",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-081bda7d9afb467ce"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-5e18d307ab3b6c4dee320c667ac8c92c",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0c545b899d71ec1d2"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-7a76a2e661adbc46ea1063e4ab90d68d",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-06e752bc92fceb43a"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-b889abc59d503aafcd93e7738ba641be",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0f77aaf4f002910f9"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-c5d2ed92046a5f74dd0f1cad93567a6a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0e42b56a6ebb510d1"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-7a76a2e661adbc46ea1063e4ab90d68d",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-06e752bc92fceb43a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bgtv1yngr40bknds6bny8ghnl"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-7a76a2e661adbc46ea1063e4ab90d68d",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-06e752bc92fceb43a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ef6c6mk70fgf1h9w0ccwz8829"
          } ]
        }
      } ],
      "displayName" : "Hive"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-0f77aaf4f002910f9",
    "ipAddress" : "172.31.17.199",
    "hostname" : "ip-172-31-17-199.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0c545b899d71ec1d2",
    "ipAddress" : "172.31.17.89",
    "hostname" : "ip-172-31-17-89.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-081bda7d9afb467ce",
    "ipAddress" : "172.31.20.157",
    "hostname" : "ip-172-31-20-157.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-06e752bc92fceb43a",
    "ipAddress" : "172.31.26.193",
    "hostname" : "ip-172-31-26-193.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0e42b56a6ebb510d1",
    "ipAddress" : "172.31.26.9",
    "hostname" : "ip-172-31-26-9.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-7a76a2e661adbc46ea1063e4ab90d68d",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "185fc1df895e386889b5f21ecc0a7aa6751ab4de5d3d0e8d69d9c30c7613e8b3",
    "pwSalt" : -7626524492543461029,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-7a76a2e661adbc46ea1063e4ab90d68d",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "34cce178752bfd876d35496ab830ebe4c58711ed835c430148f5ec9910d293b4",
    "pwSalt" : -3608313311658919145,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-7a76a2e661adbc46ea1063e4ab90d68d",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "be35fbe947c8368d7fa66fa5a96ce14ceb712dc33122969d3082ded11a20767c",
    "pwSalt" : -2950928666573214314,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-7a76a2e661adbc46ea1063e4ab90d68d",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "4359f30a80b6caf841d1af0d4c23b97e175faa8aea394cc09889d2e6af356668",
    "pwSalt" : 8670814294251872934,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "48889711d18ce6ef35aa335de59270f99735f72908adeb47da429bd8fd2e1ea7",
    "pwSalt" : -7690791303040235619,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "dc660fc5d2893deb4ed74e3ec3985530ebbc6453c18b447b4fd36e86d731e78d",
    "pwSalt" : 7821113272639458347,
    "pwLogin" : true
  }, {
    "name" : "mustafatok",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "ea62449f7e3fc848be994584171a7a7cde3261ba6911db94440aa80af7735325",
    "pwSalt" : -2177157882460293789,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20161019-1013",
    "gitHash" : "518f0d6d44abc87bc392646e4369a20c8192b7cf",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "639631360"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "639631360"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "831520768"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "cloudera"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "639631360"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "639631360"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "831520768"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-7a76a2e661adbc46ea1063e4ab90d68d",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-06e752bc92fceb43a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "6ilpm7yq5gqcb63r47ke5l0dz"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-7a76a2e661adbc46ea1063e4ab90d68d",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-06e752bc92fceb43a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "878zlm75mh65ksbcsc81t335p"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-7a76a2e661adbc46ea1063e4ab90d68d",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-06e752bc92fceb43a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "2lq6ft3gk94lwuumy1b76fxym"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-7a76a2e661adbc46ea1063e4ab90d68d",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-06e752bc92fceb43a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "bwurgmdb3enz4i6tapdp0686i"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-7a76a2e661adbc46ea1063e4ab90d68d",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-06e752bc92fceb43a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "2oss3wg5tnpliz2kcvrz8j8vu"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/27/2012 22:40"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/,http://ip-172-31-26-193.eu-central-1.compute.internal/accumulo-c5/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/"
    } ]
  }
}
```
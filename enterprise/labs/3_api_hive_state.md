```json
$ curl -X POST -u mustafatok:cloudera 'http://35.156.89.235:7180/api/v12/clusters/mustafatok%20-%20SEBC%20Cluster/services/hive/commands/stop'
{
  "id" : 1343,
  "name" : "Stop",
  "startTime" : "2017-03-08T10:25:24.604Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

```json
$ curl -u mustafatok:cloudera 'http://35.156.89.235:7180/api/v12/clusters/mustafatok%20-%20SEBC%20Cluster/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-26-193.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-26-193.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STOPPED",
  "healthSummary" : "DISABLED",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "DISABLED",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "DISABLED",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "STOPPED"
```

```json
$ curl X POST -u mustafatok:cloudera 'http://35.156.89.235:7180/api/v12/clusters/mustafatok%20-%20SEBC%20Cluster/services/hive/commands/start'
{
  "id" : 1347,
  "name" : "Start",
  "startTime" : "2017-03-08T10:26:27.609Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
```

```json
$ curl -u mustafatok:cloudera 'http://35.156.89.235:7180/api/v12/clusters/mustafatok%20-%20SEBC%20Cluster/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-26-193.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-26-193.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive/instances",
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
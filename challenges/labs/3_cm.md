## The command and output for hdfs dfs -ls /user

```
[ec2-user@ip-172-31-17-25 ~]$ hdfs dfs -ls /user
Found 8 items
drwxr-xr-x   - admin   admin               0 2017-03-10 04:20 /user/admin
drwxr-xr-x   - hdfs    supergroup          0 2017-03-10 04:20 /user/hdfs
drwxrwxrwx   - mapred  hadoop              0 2017-03-10 04:15 /user/history
drwxrwxr-t   - hive    hive                0 2017-03-10 04:16 /user/hive
drwxrwxr-x   - hue     hue                 0 2017-03-10 04:17 /user/hue
drwxr-xr-x   - neymar  neymar              0 2017-03-10 04:21 /user/neymar
drwxrwxr-x   - oozie   oozie               0 2017-03-10 04:17 /user/oozie
drwxr-xr-x   - ronaldo ronaldo             0 2017-03-10 04:21 /user/ronaldo
```

## The output from the CM API call ../api/v14/hosts

```json
[ec2-user@ip-172-31-17-25 ~]$ curl -u admin:admin http://ec2-35-156-174-131.eu-central-1.compute.amazonaws.com:7180/api/v14/hosts
{
  "items" : [ {
    "hostId" : "i-0061f2708ef2cd0e6",
    "ipAddress" : "172.31.17.25",
    "hostname" : "ip-172-31-17-25.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-29-137.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-0061f2708ef2cd0e6",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "i-0b8509397b0e03315",
    "ipAddress" : "172.31.19.108",
    "hostname" : "ip-172-31-19-108.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-29-137.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-0b8509397b0e03315",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "i-0387398764955ebf7",
    "ipAddress" : "172.31.22.5",
    "hostname" : "ip-172-31-22-5.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-29-137.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-0387398764955ebf7",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "i-06cbf97a504ba7fba",
    "ipAddress" : "172.31.23.114",
    "hostname" : "ip-172-31-23-114.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-29-137.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-06cbf97a504ba7fba",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "i-052e155db8a07f624",
    "ipAddress" : "172.31.29.137",
    "hostname" : "ip-172-31-29-137.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-29-137.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-052e155db8a07f624",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  } ]
}
```
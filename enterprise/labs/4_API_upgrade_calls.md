Report the latest available version of the API

```
$ curl -u mustafatok:cloudera 'http://35.156.89.235:7180/api/version'
v15
```

Report the CM version

```
$ curl -u mustafatok:cloudera 'http://35.156.89.235:7180/api/v15/cm/version'
{
  "version" : "5.10.0",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170120-1037",
  "gitHash" : "aa0b5cd5eceaefe2f971c13ab657020d96bb842a",
  "snapshot" : false
}
```

List all CM users

```
$ curl -u mustafatok:cloudera 'http://35.156.89.235:7180/api/v15/users'
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  }, {
    "name" : "mustafatok",
    "roles" : [ "ROLE_ADMIN" ]
  } ]
}
```

Report the database server in use by CM

```
$ curl -u mustafatok:cloudera 'http://35.156.89.235:7180/api/v15/cm/scmDbInfo'
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```
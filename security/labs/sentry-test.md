## Verify user privileges


```
[mustafatok@ip-172-31-26-193 ec2-user]$ klist
Ticket cache: FILE:/tmp/krb5cc_1001
Default principal: mustafatok/mustafatok@EU-CENTRAL-1.COMPUTE.INTERNAL

Valid starting       Expires              Service principal
09.03.2017 04:22:01  10.03.2017 04:22:01  krbtgt/EU-CENTRAL-1.COMPUTE.INTERNAL@EU-CENTRAL-1.COMPUTE.INTERNAL
	renew until 16.03.2017 05:22:01
```

```
[mustafatok@ip-172-31-26-193 ec2-user]$ beeline
Beeline version 1.1.0-cdh5.10.0 by Apache Hive
```

```
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-26-193.eu-central-1.compute.internal@EU-CENTRAL-1.COMPUTE.INTERNAL
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-26-193.eu-central-1.compute.internal@EU-CENTRAL-1.COMPUTE.INTERNAL
Connected to: Apache Hive (version 1.1.0-cdh5.10.0)
Driver: Hive JDBC (version 1.1.0-cdh5.10.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ
```

```
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20170309044242_8ac62375-5936-4030-be85-12105b2d083b): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170309044242_8ac62375-5936-4030-be85-12105b2d083b); Time taken: 0.695 seconds
INFO  : Executing command(queryId=hive_20170309044242_8ac62375-5936-4030-be85-12105b2d083b): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309044242_8ac62375-5936-4030-be85-12105b2d083b); Time taken: 0.266 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.316 seconds)

```

## Note:

```
Problem : All the tables were visible to the test user which is not supposed to happen in the first try.
Solution : Sentry was not enabled in Hive. I needed to enable it from Hive configuration.
```

## Create test roles

### George ( Sees all tables )
```
[mustafatok@ip-172-31-26-193 ec2-user]$ kinit george
Password for george@EU-CENTRAL-1.COMPUTE.INTERNAL: 
```

```
[mustafatok@ip-172-31-26-193 ec2-user]$ klist
Ticket cache: FILE:/tmp/krb5cc_1001
Default principal: george@EU-CENTRAL-1.COMPUTE.INTERNAL

Valid starting       Expires              Service principal
09.03.2017 05:05:10  10.03.2017 05:05:10  krbtgt/EU-CENTRAL-1.COMPUTE.INTERNAL@EU-CENTRAL-1.COMPUTE.INTERNAL
	renew until 16.03.2017 06:05:10
```

```
[mustafatok@ip-172-31-26-193 ec2-user]$ beeline
Beeline version 1.1.0-cdh5.10.0 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-26-193.eu-central-1.compute.internal@EU-CENTRAL-1.COMPUTE.INTERNAL
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-26-193.eu-central-1.compute.internal@EU-CENTRAL-1.COMPUTE.INTERNAL
Connected to: Apache Hive (version 1.1.0-cdh5.10.0)
Driver: Hive JDBC (version 1.1.0-cdh5.10.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20170309050505_7ad9cdf2-6024-4dc7-855d-a8479b17485e): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170309050505_7ad9cdf2-6024-4dc7-855d-a8479b17485e); Time taken: 0.066 seconds
INFO  : Executing command(queryId=hive_20170309050505_7ad9cdf2-6024-4dc7-855d-a8479b17485e): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309050505_7ad9cdf2-6024-4dc7-855d-a8479b17485e); Time taken: 0.144 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.31 seconds)

```

### George ( Sees only sample_07 )

```
[mustafatok@ip-172-31-26-193 ec2-user]$ kinit ferdinand
Password for ferdinand@EU-CENTRAL-1.COMPUTE.INTERNAL: 
```

```
[mustafatok@ip-172-31-26-193 ec2-user]$ klist
Ticket cache: FILE:/tmp/krb5cc_1001
Default principal: ferdinand@EU-CENTRAL-1.COMPUTE.INTERNAL

Valid starting       Expires              Service principal
09.03.2017 05:06:13  10.03.2017 05:06:13  krbtgt/EU-CENTRAL-1.COMPUTE.INTERNAL@EU-CENTRAL-1.COMPUTE.INTERNAL
	renew until 16.03.2017 06:06:13
```

```
[mustafatok@ip-172-31-26-193 ec2-user]$ beeline
Beeline version 1.1.0-cdh5.10.0 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-26-193.eu-central-1.compute.internal@EU-CENTRAL-1.COMPUTE.INTERNAL
scan complete in 1ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-26-193.eu-central-1.compute.internal@EU-CENTRAL-1.COMPUTE.INTERNAL
Connected to: Apache Hive (version 1.1.0-cdh5.10.0)
Driver: Hive JDBC (version 1.1.0-cdh5.10.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20170309050606_5ff0f766-f5f4-4000-bebc-55f05e239c51): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170309050606_5ff0f766-f5f4-4000-bebc-55f05e239c51); Time taken: 0.065 seconds
INFO  : Executing command(queryId=hive_20170309050606_5ff0f766-f5f4-4000-bebc-55f05e239c51): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170309050606_5ff0f766-f5f4-4000-bebc-55f05e239c51); Time taken: 0.124 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.288 seconds)

```
Adjustment:
```
Worker vcores	20
Worker spindles	12
Worker RAM	128
Workload factor	3
Worker nodes	10
```

Workload factor is used to determine the number of mappers and reducers in the system. The formula of "-D mapreduce.job.maps" and "mapreduce.job.reduces" is MIN(mapreduce.map.memory.mb, mapreduce.map.cpu.vcores, PRODUCT(Worker nodes,Workload factor)). That means if the workload factor is 1, only 1 mapper and 1 reducer are tried to be created for each worker. If it is set to 2 then 2 mappers and 2 reducers are created for each worker. So, the workload factor basically indicates the number of mappers and reducers per node.
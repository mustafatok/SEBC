```
#!/bin/sh
# Confirm the path values given below correspond to your installation

MR=/opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce
HADOOP=/opt/cloudera/parcels/CDH/bin

# Mark start of the loop
echo Testing loop started on `date`

# Mapper containers
for i in 2 8    
do
  # Reducer containers
  for j in 2 8 
  do                 
    # Container memory
    for k in 512 1024 
    do                         
       # Set mapper JVM heap 
       MAP_MB=`echo "($k*0.8)/1" | bc` 

       # Set reducer JVM heap 
       RED_MB=`echo "($k*0.8)/1" | bc` 

       echo "mappers=$i"
       echo "reducers=$j"
       echo "container mem=$k"
       echo "MAP_MB=$MAP_MB"
       echo "RED_MB=$RED_MB"

       echo "Running 'teragen'"
       time ${HADOOP}/hadoop jar ${MR}/hadoop-examples.jar teragen \
               -Dmapreduce.job.maps=$i \
               -Dmapreduce.map.memory.mb=$k \
               -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
               51200000 /user/mustafatok/results/tg-10GB-${i}-${j}-${k} 1>tera_${i}_${j}_${k}.out 2>tera_${i}_${j}_${k}.err                       

       echo "Running 'terasort'"
       time ${HADOOP}/hadoop jar $MR/hadoop-examples.jar terasort \
               -Dmapreduce.job.maps=$i \
               -Dmapreduce.job.reduces=$j \
               -Dmapreduce.map.memory.mb=$k \
               -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
               -Dmapreduce.reduce.memory.mb=$k \
               -Dmapreduce.reduce.java.opts.max.heap=$RED_MB \
               /user/mustafatok/results/tg-10GB-${i}-${j}-${k}  \
               /user/mustafatok/results/ts-10GB-${i}-${j}-${k} 1>>tera_${i}_${j}_${k}.out 2>>tera_${i}_${j}_${k}.err                         

       $HADOOP/hadoop fs -rm -r -skipTrash /user/mustafatok/results/tg-10GB-${i}-${j}-${k}                        
       $HADOOP/hadoop fs -rm -r -skipTrash /user/mustafatok/results/ts-10GB-${i}-${j}-${k}                 
    done
  done
done

echo Testing loop ended on `date`
```
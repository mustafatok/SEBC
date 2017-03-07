Result : 

```
[mustafatok@ip-172-31-26-193 ~]$ ./YARNtest.sh 
Testing loop started on Di 7. Mär 15:57:09 EST 2017


mappers=2
reducers=2
container mem=512
MAP_MB=409
RED_MB=409
Running 'teragen'

real	1m17.664s
user	0m6.038s
sys	0m0.275s
Running 'terasort'

real	1m58.894s
user	0m8.251s
sys	0m0.289s
Deleted /user/mustafatok/results/tg-10GB-2-2-512
Deleted /user/mustafatok/results/ts-10GB-2-2-512


mappers=2
reducers=2
container mem=1024
MAP_MB=819
RED_MB=819
Running 'teragen'

real	1m21.430s
user	0m6.261s
sys	0m0.251s
Running 'terasort'

real	1m56.197s
user	0m7.969s
sys	0m0.284s
Deleted /user/mustafatok/results/tg-10GB-2-2-1024
Deleted /user/mustafatok/results/ts-10GB-2-2-1024


mappers=2
reducers=8
container mem=512
MAP_MB=409
RED_MB=409
Running 'teragen'

real	1m14.214s
user	0m5.879s
sys	0m0.223s
Running 'terasort'

real	1m31.227s
user	0m7.917s
sys	0m0.286s
Deleted /user/mustafatok/results/tg-10GB-2-8-512
Deleted /user/mustafatok/results/ts-10GB-2-8-512


mappers=2
reducers=8
container mem=1024
MAP_MB=819
RED_MB=819
Running 'teragen'

real	1m25.029s
user	0m6.081s
sys	0m0.196s
Running 'terasort'

real	1m29.570s
user	0m8.374s
sys	0m0.276s
Deleted /user/mustafatok/results/tg-10GB-2-8-1024
Deleted /user/mustafatok/results/ts-10GB-2-8-1024


mappers=8
reducers=2
container mem=512
MAP_MB=409
RED_MB=409
Running 'teragen'

real	1m8.257s
user	0m6.049s
sys	0m0.245s
Running 'terasort'

real	1m45.826s
user	0m8.086s
sys	0m0.293s
Deleted /user/mustafatok/results/tg-10GB-8-2-512
Deleted /user/mustafatok/results/ts-10GB-8-2-512


mappers=8
reducers=2
container mem=1024
MAP_MB=819
RED_MB=819
Running 'teragen'

real	1m6.981s
user	0m5.682s
sys	0m0.253s
Running 'terasort'

real	1m52.233s
user	0m7.913s
sys	0m0.287s
Deleted /user/mustafatok/results/tg-10GB-8-2-1024
Deleted /user/mustafatok/results/ts-10GB-8-2-1024


mappers=8
reducers=8
container mem=512
MAP_MB=409
RED_MB=409
Running 'teragen'

real	1m8.577s
user	0m6.112s
sys	0m0.234s
Running 'terasort'

real	1m31.741s
user	0m7.891s
sys	0m0.258s
Deleted /user/mustafatok/results/tg-10GB-8-8-512
Deleted /user/mustafatok/results/ts-10GB-8-8-512


mappers=8
reducers=8
container mem=1024
MAP_MB=819
RED_MB=819
Running 'teragen'

real	1m2.445s
user	0m5.880s
sys	0m0.234s
Running 'terasort'


real	1m35.618s
user	0m7.496s
sys	0m0.309s
Deleted /user/mustafatok/results/tg-10GB-8-8-1024
Deleted /user/mustafatok/results/ts-10GB-8-8-1024
Testing loop ended on Di 7. Mär 16:21:16 EST 2017
```
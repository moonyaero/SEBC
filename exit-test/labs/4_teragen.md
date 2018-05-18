# teragen output
```
[root@ip-172-31-29-43 ~]# time sudo -u groot hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen \
>  -Ddfs.blocksize=67108864 \
>  -Dmapreduce.job.maps=40 \
>  -Dmapreduce.map.memory.mb=1024 \
>  -Dmapred.map.tasks=6 65536000 /user/groot/tgen
18/05/18 05:52:30 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-27-72.ap-southeast-1.compute.internal/172.31.27.72:8032
18/05/18 05:52:31 INFO terasort.TeraGen: Generating 65536000 using 40
18/05/18 05:52:31 INFO mapreduce.JobSubmitter: number of splits:40
18/05/18 05:52:31 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
18/05/18 05:52:31 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1526620731112_0003
18/05/18 05:52:31 INFO impl.YarnClientImpl: Submitted application application_1526620731112_0003
18/05/18 05:52:31 INFO mapreduce.Job: The url to track the job: http://ip-172-31-27-72.ap-southeast-1.compute.internal:8088/proxy/application_1526620731112_0003/
18/05/18 05:52:31 INFO mapreduce.Job: Running job: job_1526620731112_0003
18/05/18 05:52:37 INFO mapreduce.Job: Job job_1526620731112_0003 running in uber mode : false
18/05/18 05:52:37 INFO mapreduce.Job:  map 0% reduce 0%
18/05/18 05:52:45 INFO mapreduce.Job:  map 3% reduce 0%
18/05/18 05:52:46 INFO mapreduce.Job:  map 13% reduce 0%
18/05/18 05:52:52 INFO mapreduce.Job:  map 15% reduce 0%
18/05/18 05:52:54 INFO mapreduce.Job:  map 22% reduce 0%
18/05/18 05:52:55 INFO mapreduce.Job:  map 25% reduce 0%
18/05/18 05:53:01 INFO mapreduce.Job:  map 32% reduce 0%
18/05/18 05:53:02 INFO mapreduce.Job:  map 35% reduce 0%
18/05/18 05:53:05 INFO mapreduce.Job:  map 38% reduce 0%
18/05/18 05:53:07 INFO mapreduce.Job:  map 43% reduce 0%
18/05/18 05:53:08 INFO mapreduce.Job:  map 45% reduce 0%
18/05/18 05:53:16 INFO mapreduce.Job:  map 50% reduce 0%
18/05/18 05:53:17 INFO mapreduce.Job:  map 55% reduce 0%
18/05/18 05:53:18 INFO mapreduce.Job:  map 57% reduce 0%
18/05/18 05:53:27 INFO mapreduce.Job:  map 60% reduce 0%
18/05/18 05:53:28 INFO mapreduce.Job:  map 68% reduce 0%
18/05/18 05:53:36 INFO mapreduce.Job:  map 77% reduce 0%
18/05/18 05:53:42 INFO mapreduce.Job:  map 82% reduce 0%
18/05/18 05:53:49 INFO mapreduce.Job:  map 85% reduce 0%
18/05/18 05:53:52 INFO mapreduce.Job:  map 93% reduce 0%
18/05/18 05:53:58 INFO mapreduce.Job:  map 95% reduce 0%
18/05/18 05:54:04 INFO mapreduce.Job:  map 98% reduce 0%
18/05/18 05:54:05 INFO mapreduce.Job:  map 100% reduce 0%
18/05/18 05:54:05 INFO mapreduce.Job: Job job_1526620731112_0003 completed successfully
18/05/18 05:54:05 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=5120670
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=3426
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=160
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=80
        Job Counters
                Launched map tasks=40
                Other local map tasks=40
                Total time spent by all maps in occupied slots (ms)=353332
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=353332
                Total vcore-milliseconds taken by all map tasks=353332
                Total megabyte-milliseconds taken by all map tasks=361811968
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Input split bytes=3426
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=3736
                CPU time spent (ms)=177620
                Physical memory (bytes) snapshot=11157716992
                Virtual memory (bytes) snapshot=111356125184
                Total committed heap usage (bytes)=12182355968
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=140750829423462787
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=6553600000

real    1m37.046s
user    0m7.454s
sys     0m0.399s

```
# Output of hdfs dfs -ls /user/groot/tgen
```
[root@ip-172-31-29-43 ~]# sudo -u hdfs hdfs dfs -ls /user/groot/tgen
Found 41 items
-rw-r--r--   3 groot supergroup          0 2018-05-18 05:54 /user/groot/tgen/_SUCCESS
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:52 /user/groot/tgen/part-m-00000
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:52 /user/groot/tgen/part-m-00001
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:52 /user/groot/tgen/part-m-00002
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:52 /user/groot/tgen/part-m-00003
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:52 /user/groot/tgen/part-m-00004
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:52 /user/groot/tgen/part-m-00005
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:52 /user/groot/tgen/part-m-00006
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:52 /user/groot/tgen/part-m-00007
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:52 /user/groot/tgen/part-m-00008
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:52 /user/groot/tgen/part-m-00009
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:52 /user/groot/tgen/part-m-00010
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:52 /user/groot/tgen/part-m-00011
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00012
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00013
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00014
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00015
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00016
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00017
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00018
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00019
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00020
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00021
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00022
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00023
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00024
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00025
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00026
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00027
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00028
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00029
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00030
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00031
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00032
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00033
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00034
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00035
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00036
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:53 /user/groot/tgen/part-m-00037
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:54 /user/groot/tgen/part-m-00038
-rw-r--r--   3 groot supergroup  163840000 2018-05-18 05:54 /user/groot/tgen/part-m-00039

```
# Output of hadoop fsck -blocks /user/groot 

```
[root@ip-172-31-29-43 ~]# sudo -u hdfs hadoop fsck -blocks /user/groot
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-27-72.ap-southeast-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.29.43 for path /user/groot at Fri May 18 05:56:55 UTC 2018
.........................................Status: HEALTHY
 Total size:    6553600000 B
 Total dirs:    3
 Total files:   41
 Total symlinks:                0
 Total blocks (validated):      120 (avg. block size 54613333 B)
 Minimally replicated blocks:   120 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Fri May 18 05:56:55 UTC 2018 in 6 milliseconds


The filesystem under path '/user/groot' is HEALTHY

```

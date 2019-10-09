### zookeeper and kafka
ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services. All of these kinds of services are used in some form or another by distributed applications.


Create a dataproc with kafka
```
gcloud dataproc clusters create hw3  --metadata "run-on-master=true" --initialization-actions gs://bigdata-01/kafka/kafka.sh --bucket bigdata-01

gcloud dataproc clusters create hw3 \
    --num-masters 3 \
    --metadata "run-on-master=true" \
    --initialization-actions gs://bigdata-01/kafka/kafka.sh
```

--optional-components=ZOOKEEPER

--enable-component-gateway 

spark-submit --packages spark.jars.packages=org.apache.spark:spark-sql-kafka-0-10_2.11:2.2.0 streaming.py  -- 35.231.176.166:2181 test
````
gcloud dataproc jobs submit pyspark --cluster demo-cluster --properties spark.jars.packages=org.apache.spark:spark-sql-kafka-0-10_2.11:2.2.0 streaming.py  -- 35.231.176.166:2181 test
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic tes
````
Worked one:
````
gcloud dataproc jobs submit pyspark --cluster demo-cluster --jars gs://bigdata-01/spark-streaming-kafka-0-8-assembly_2.10-2.2.1.jar streaming.py  -- 35.231.176.166:2181 test
````

Kafka
````
kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
````

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2NDUwMjQxNjAsLTE0NjA3NDY4OTcsNT
Q1NTIzNDQ1LC0xMTU3MzEyOTEsMjAyMzM3NTg2MywxOTEzMjk1
MzgzLC0yMDk0NTczMjE0LDM5ODQyODM5NSwxMzM0MzU4NDI3LC
0xNjM1NzUzMTQ0XX0=
-->
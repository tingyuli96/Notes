### zookeeper and kafka
ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services. All of these kinds of services are used in some form or another by distributed applications.


Create a dataproc with kafka
```
gcloud dataproc clusters create hw3 --metadata "run-on-master=true" --initialization-actions gs://bigdata-01/kafka/kafka.sh --bucket bigdata-01

gcloud dataproc clusters create hw3 \
    --num-masters 3 \
    --metadata "run-on-master=true" \
    --initialization-actions gs://bigdata-01/kafka/kafka.sh
```
CPUS cuda wait 

--optional-components=ZOOKEEPER

--enable-component-gateway 

spark-submit --packages spark.jars.packages=org.apache.spark:spark-sql-kafka-0-10_2.11:2.2.0 streaming.py  -- 35.231.176.166:2181 test
````
gcloud dataproc jobs submit pyspark --cluster demo-cluster --properties spark.jars.packages=org.apache.spark:spark-sql-kafka-0-10_2.11:2.2.0 streaming.py  -- 35.231.176.166:2181 test
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic tes
````
Worked one:
````
gcloud dataproc jobs submit pyspark --cluster hw3 --jars gs://bigdata-01/spark-streaming-kafka-0-8-assembly_2.11-2.3.3.jar streaming.py  -- 35.237.39.36:9092 test
````
gcloud dataproc jobs submit pyspark --cluster hw3 --packages org.apache.spark:spark-streaming-kafka-0-8:2.3.3 streaming.py  -- 35.237.39.36:9092 test
Kafka

--jars gs://bigdata-01/spark-streaming-kafka-0-8-assembly_2.10-2.2.1.jar 
````
kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
````

[https://www.learningjournal.guru/courses/kafka/kafka-foundation-training/kafka-in-gcp/](https://www.learningjournal.guru/courses/kafka/kafka-foundation-training/kafka-in-gcp/)

spark-submit --jars ~/Downloads/spark-streaming-kafka-0-8-assembly_2.10-2.2.1.jar streaming.py  35.237.39.36:9092 test

[35.237.39.36](https://35.237.39.36/)

gcloud beta dataproc clusters create hw22 --optional-components=ANACONDA,JUPYTER --image-version=preview --enable-component-gateway --metadata PIP_PACKAGES=requests-oauthlib --initialization-actions gs://dataproc-initialization-actions/python/pip-install.sh --single-node



create a cluster 
can with or without kafka

deploy a kafka engine
publish topic on it


### Way2: using socket

with kafka

gcloud beta dataproc clusters create hw32 --optional-components=ANACONDA,JUPYTER --image-version=preview --enable-component-gateway --metadata 'PIP_PACKAGES=requests-oauthlib google-cloud-bigquery' --initialization-actions gs://dataproc-initialization-actions/python/pip-install.sh --single-node

gcloud beta dataproc clusters create hw31 --optional-components=ANACONDA,JUPYTER,ZOOKEEPER --image-version=preview --enable-component-gateway --metadata 'PIP_PACKAGES=google-cloud-bigquery' --initialization-actions gs://dataproc-initialization-actions/python/pip-install.sh --single-node --initialization-actions gs://bigdata-01/kafka/kafka.sh

pull from twitter api

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc4MzEzNTUzNSwtNzU3MTQ0OTAxLC0xMT
g3NTA4MDk0LC04NDQ5NjY5NDIsLTQxOTU5ODgxMywxNDQzMDA1
MTc1LC0xMzMxMzk3Njk2LC05NDcyMjAzNDksMTY2Njc5Njk2MS
wtODI3NzE1MzQ4LC0yMDEyNTEyMTE4LDIwMTQ3MjgzLC00NTUw
MTg3MTEsNDY3Mjk3NjY2LC03Nzg5NTQ3NjEsLTk0OTkwMTI2MC
wxMzYwODA3MzM1LC0xNDYwNzQ2ODk3LDU0NTUyMzQ0NSwtMTE1
NzMxMjkxXX0=
-->
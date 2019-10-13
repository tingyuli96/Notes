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
```
gcloud dataproc jobs submit pyspark --cluster hw3 --jars gs://bigdata-01/spark-streaming-kafka-0-8-assembly_2.11-2.3.3.jar streaming.py  -- 35.237.39.36:9092 test
```


### Way1: Kafka
with kafka
```
gcloud beta dataproc clusters create hw31 --optional-components=ANACONDA,JUPYTER,ZOOKEEPER --image-version=preview --enable-component-gateway --metadata 'PIP_PACKAGES=google-cloud-bigquery' --bucket bigdata-01 --initialization-actions gs://dataproc-initialization-actions/python/pip-install.sh --single-node --initialization-actions gs://bigdata-01/kafka/kafka.sh
```

### Way2: using socket
```
gcloud beta dataproc clusters create hw33 --optional-components=ANACONDA,JUPYTER --image-version=preview --enable-component-gateway --metadata 'PIP_PACKAGES=requests-oauthlib google-cloud-bigquery tweepy' --bucket bigdata-01 --initialization-actions gs://dataproc-initialization-actions/python/pip-install.sh --single-node
```
pull from twitter api ok

using tweepy
`pip install tweepy --user`
use user flag or there will be an error

if using anacoda,
then 
`conda install xxx `
`conda install -c conda-forge tweepy`

submit jobs
```
gcloud dataproc jobs submit pyspark --cluster hw33 
```




<!--stackedit_data:
eyJoaXN0b3J5IjpbNjQyNDk2NDcwLC0yOTkxMDA4NDcsMTUzMz
A2Nzg4MiwtODIxNzkzNzYyLDEyMjE0NDQzMjAsMTU3MjM0MzI2
LDExNjgzNjYxNjMsLTM2MzQ0NDU4OSwxMTA1ODg2NTU5LC03NT
cxNDQ5MDEsLTExODc1MDgwOTQsLTg0NDk2Njk0MiwtNDE5NTk4
ODEzLDE0NDMwMDUxNzUsLTEzMzEzOTc2OTYsLTk0NzIyMDM0OS
wxNjY2Nzk2OTYxLC04Mjc3MTUzNDgsLTIwMTI1MTIxMTgsMjAx
NDcyODNdfQ==
-->
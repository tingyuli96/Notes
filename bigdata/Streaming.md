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
gcloud beta dataproc clusters create hw33 --optional-components=ANACONDA,JUPYTER --image-version=preview --enable-component-gateway --metadata PIP_PACKAGES=requests_oauthlib google-cloud-bigquery tweepy --metadata gcs-connector-version=1.9.16 --metadata bigquery-connector-version=0.13.16 --bucket bigdata-01 --initialization-actions gs://dataproc-initialization-actions/python/pip-install.sh --initialization-actions gs://dataproc-initialization-actions/connectors/connectors.sh --single-node 
```
up can not install pip packages don't know why
```
gcloud beta dataproc clusters create hw32 --optional-components=ANACONDA,JUPYTER --image-version=preview --enable-component-gateway --metadata 'PIP_PACKAGES=requests_oauthlib==1.2.0' --metadata gcs-connector-version=1.9.16 --metadata bigquery-connector-version=0.13.16 --bucket bigdata-01 --initialization-actions gs://dataproc-initialization-actions/python/pip-install.sh --initialization-actions gs://dataproc-initialization-actions/connectors/connectors.sh --single-node 
```
```
gcloud beta dataproc clusters create hw32 --optional-components=ANACONDA,JUPYTER --image-version=preview --enable-component-gateway --metadata 'PIP_PACKAGES=requests_oauthlib==1.2.0' --bucket bigdata-01 --initialization-actions gs://dataproc-initialization-actions/python/pip-install.sh --initialization-actions gs://dataproc-initialization-actions/connectors/connectors.sh --single-node 
```
pull from twitter api ok

using tweepy
`pip install tweepy --user`
use user flag or there will be an error

if using anacoda,
then 
`conda install xxx `
`conda install -c conda-forge tweepy`

```
gcloud beta dataproc clusters create hw33 \
--optional-components=ANACONDA,JUPYTER \
--image-version=preview --enable-component-gateway \
--metadata 'PIP_PACKAGES=requests_oauthlib google-cloud-bigquery tweepy' \
--metadata gcs-connector-version=1.9.16 \
--metadata bigquery-connector-version=0.13.16 \
--bucket bigdata-01 \
--initialization-actions=gs://dataproc-initialization-actions/python/pip-install.sh,gs://dataproc-initialization-actions/connectors/connectors.sh \
--single-node 
```

submit jobs
```
gcloud dataproc jobs submit pyspark --cluster hw33 
```


Error:
1. checkpoint file does not exist
	
2. kill job in terminal
`gcloud dataproc jobs kill <JOBID>`



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1OTY0NzIzMTcsMTY5NjE3ODg1NiwzOT
Q2NDA5MzIsODU4MTE0MjE3LDE3Mzc4NTM2NDYsNzA2NTcwMjc5
LDEwNjc0ODU0NjIsLTgxMTMzOTk3Niw5MTI3NTc1NDksMTYyNj
YwMDMxNSw0MTQ0MjYxNjAsNzIyMTU1OTAyLDY0MjQ5NjQ3MCwt
Mjk5MTAwODQ3LDE1MzMwNjc4ODIsLTgyMTc5Mzc2MiwxMjIxND
Q0MzIwLDE1NzIzNDMyNiwxMTY4MzY2MTYzLC0zNjM0NDQ1ODld
fQ==
-->
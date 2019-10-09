### zookeeper and kafka
ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services. All of these kinds of services are used in some form or another by distributed applications.


Create a dataproc with kafka
```
gcloud beta dataproc clusters create hw3 --optional-components=ZOOKEEPER --metadata "run-on-master=true" --initialization-actions gs://bigdata-01/kafka/kafka.sh --bucket bigdata-01
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzk4NDI4Mzk1LDEzMzQzNTg0MjcsLTE2Mz
U3NTMxNDRdfQ==
-->
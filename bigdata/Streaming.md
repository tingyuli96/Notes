### zookeeper and kafka
ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services. All of these kinds of services are used in some form or another by distributed applications.


Create a dataproc with kafka
```
gcloud dataproc clusters create hw3  --enable-component-gateway --metadata "run-on-master=true" --initialization-actions gs://bigdata-01/kafka/kafka.sh --bucket bigdata-01
```
--optional-components=ZOOKEEPER
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTY3MjIzMTY3LDM5ODQyODM5NSwxMzM0Mz
U4NDI3LC0xNjM1NzUzMTQ0XX0=
-->
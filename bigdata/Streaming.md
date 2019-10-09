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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwOTQ1NzMyMTQsMzk4NDI4Mzk1LDEzMz
QzNTg0MjcsLTE2MzU3NTMxNDRdfQ==
-->
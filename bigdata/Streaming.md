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



````
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic tes
````

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTkxMzI5NTM4MywtMjA5NDU3MzIxNCwzOT
g0MjgzOTUsMTMzNDM1ODQyNywtMTYzNTc1MzE0NF19
-->
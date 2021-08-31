
# Docker multi-container environment with Hadoop, Spark and Hive
* Namenode: http://localhost:50070/
* Datanode: http://localhost:50075/
* Presto coordinator: http://localhost:8080/
* Spark master: http://localhost:8088/
* Spark worker: http://localhost:8081/
* Hive: http://<dockerhadoop_IP_address>:10000

## Quick Start

To deploy an the HDFS-Spark-Hive cluster, run:
```
  docker-compose up
```

## Quick Start HDFS


```
  docker exec -it namenode bash
```


## Quick Start Spark (PySpark)

Go to http://<dockerhadoop_IP_address>:8080 or http://localhost:8088/ on your Docker host (laptop) to see the status of the Spark master.

Go to the command line of the Spark master and start PySpark.
```
  docker exec -it spark-master bash

  /spark/bin/pyspark --master spark://spark-master:7077
```


## Quick Start Spark (Scala)

Go to http://<dockerhadoop_IP_address>:8088 or http://localhost:8088/ on your Docker host (laptop) to see the status of the Spark master.

Go to the command line of the Spark master and start spark-shell.
```
  docker exec -it spark-master bash
  
  spark/bin/spark-shell --master spark://spark-master:7077
```


## Quick Start Hive

```
  $ docker-compose exec hive-server bash
  # /opt/hive/bin/beeline -u jdbc:hive2://localhost:10000

```





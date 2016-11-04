---
layout: post
title: Kafka Papers Reading
category: 技术
tags:
keywords:
description:

---

#Introduce
* Publish-subscribe messaging system
	* Fast
	* Scalable
	* Durable
	* Distributed
* Home Page 
	* <http://kafka.apache.org>


#Architecture

* Too Simple <img src="/public/img/kafka-paper/architecture.png" width="50%" height="100%" align="right"/>
* Producer/Consumer
* Broker 


#Data Storage
* Too Naive <img src="/public/img/kafka-paper/datalogic.png" height="100%" width="50%" align="right" />
* Topic 
* Partition
* A Segment file
* Message id / offset
 



#Unconventional

* System Page Cache <img src="/public/img/kafka-paper/oldcopy.png" height="100%" width="50%" align="right"/>
* Sendfile API/ Zero Copy 
* Stateless broker
* Rewind
* Retention policy 




#Distributed
* Producer
* Consumer group

	```
	 a partition within a topic is the smallest unit of parallelism
	 require many more partitions in a topic than the consumers in each group
	 let consumers coordinate among themselves in a decentralized fashion
	```
	
* Zookeeper

	 ```
	 detecting the addition and the removal of brokers and consumers
	 triggering a rebalance process in each consumer when the above events happen
	 maintaining the consumption relationship and keeping track of the consumed offset of each partition
	 ```

#Replication

* Strongly consistent replicas
* Implementation
* Handling Failures

<img src="/public/img/kafka-paper/replicas.png" width="80%" align="center"/>

#Key Algorithm

<img src="/public/img/kafka-paper/rebalanceAlgo.png" align="center" width="70%" length="60%"/>


#Guarantees

* At-least-onece delivery
* Order guarantee
* CRCs


#Performance

* Producer sum:1000W size:200 byte/per batch:1 50
* Consumer batch:1000rows / 200 KB

<img src="/public/img/kafka-paper/producer.png" width="50%" heigth="100%"/><img src="/public/img/consumer.png" width="50%" heigth="100%"/>


#REFERENCES

* InfoQ <http://www.infoq.com/cn/articles/apache-kafka>
* LinkedIn <https://engineering.linkedin.com/kafka/intra-cluster-replication-apache-kafka>
* Papers <https://cwiki.apache.org/confluence/display/KAFKA/Kafka+papers+and+presentations>


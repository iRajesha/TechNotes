# My understanding of Apache Kafka

1.  Kafka is usually brought in when too many applications wants to interact with each other - A typical scenario in enterprise

2.  First topic to learn in Kafka is <strong> TOPICS</strong> themseleves
    - Imagine them as Tables in traditional DB
    - Each Topic can have multiple paritions 
    - Messages are stored in order and they are identified by offsets
3.  Kafka cluster is composed of multiple brokers. Each broker is a server

4. When you bring up the Kafka , Partitions of the topic will be distributed among the brokers

5.  Replication factor allows cluster to hold the multiple copies of the partition in case if one broker goes down for some reason , cluster will still perform

6.  At any given time , there will be one Leader i.e one broker serving a Partition - A leader for that partition , others are ISR - In syc replica

## Producers

1. Responsible for writing data to  partitions. We dont have to worry about identifiyin the brokers and clusters

2. You can set the acknowlegement level for producers 
- acks - 0 : No acknowledgement needed 
- 1- needed from leader 
-   2 - Needed confirmation from all the replications as well

3. If we provide a key for a message/data , data will always go to one partition

## Consumers
1.  Consumers groups are multiple consumer applications

2. Consumers can retrieve data from one or more partitions

3. Consumers offeset - Till where the data is read is stored in the Topic : `__consumer_offset`

## Zookeeper

1.  Zookeeper manages the brokers and help elect Leaders
2.  Sends notifications if any change in Kafka
3.  It operates on odd numbers 1,3,5


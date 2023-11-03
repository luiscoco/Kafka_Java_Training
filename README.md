# Kafka Java Training

## 1. What is Kafka?

Apache Kafka is basically an **Open-Source** messaging tool developed by **Linkedin** to provide **Low-Latency** and **High-Throughput** platform for the **real-time** data feed.

It is developed using **Scala** and **Java** programming Languages.

## 2. What is a Stream?

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/68fc64da-d5a0-47d2-8bfd-5b24df617255)

In general, a Stream can be defined as an unbounded and continuous flow of data packets in real-time. 

Data packets are generated in the form of key-value pairs and these are automatically transferred from the publisher, there is no need to place a request for the same.

## 3. What exactly is Kafka Stream?
 
![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/e0b1c4df-5dda-4197-be73-fe72f006bfa8)

Apache Kafka Stream can be defined as an open-source client library that is used for building applications and micro-services. 

Here, the input and the output data is stored in Kafka Clusters. 

It integrates the intelligibility of designing and deploying standard Scala and Java applications with the benefits of Kafka server-side cluster technology.

## 4. Apache Kafka Stream API Architecture

Apache KStreams internally use The producer and Consumer libraries. 

It is basically coupled with Kafka and the API allows you to leverage the abilities of Kafka by achieving Data Parallelism, Fault-tolerance, and many other powerful features.

The Different Components present in the KStream Architecture are as follows:

Input Stream

Output Stream

Instance

Consumer

Local State

Stream Topology

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/31a68d57-6a78-47db-95d0-f0c36cc5124b)

Input Stream and Output Streams are the Kafka Clusters that store the Input and Output data of the provided task.

Inside every instance, we have Consumer, Stream Topology and Local State

Stream Topology is actually the flow or DAG in which the given task is executed

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/2742922f-a000-489e-a3df-bcb55f198946)

Local State is the memory location that stores the intermediate results of the given operations like Map, FlatMap etc.

To increase data parallelism, we can directly increase the number of Instances. Moving ahead, we will understand the features of Kafka Streams.

## 5. Kafka Stream Features

Now, let us discuss the important features of Kafka streams that give it an edge over other similar technologies.

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/d0888fc7-ee80-42bd-8062-891700d50e50)

**Elastic**

Apache Kafka is an open-source project that was designed to be highly available and horizontally scalable. 

Hence, with the support of Kafka, Kafka streams API has achieved it’s highly elastic nature and can be easily expandable.

**Fault-tolerant**

The Data logs are initially partitioned and these partitions are shared among all the servers in the cluster that are handling the data and the respective requests. 

Thus Kafka achieves fault tolerance by duplicating each partition over a number of servers.

**Highly viable**

Since Kafka clusters are highly available, hence, they can be preferred any sort of use cases regardless of their size. 

They are capable of supporting small, medium and large scale use cases.

**Integrated Security**

Kafka has three major security components that offer the best in class security for the data in its clusters. They are mentioned below as follows:

Encryption of data using SSL/TLS

Authentication of SSL/SASL

Authorization of ACLs

Followed by Security, we have its support for top-end programming languages.

**Support for Java and Scala**

The best part about Kafka Streams API is that it gets integrated itself the most dominant programming languages like Java and Scala and makes designing and deploying Kafka Server-side applications with ease.

**Exactly-once processing semantics**

Usually, stream processing is a continuous execution of the unbounded series of data or events. But in the case of Kafka, it is not. 

Exactly-Once means that the user-defined statement or logic is executed only once and the updates to state, managed by SPE(Stream Processing Element) are committed only once in a durable back-end store

Unleash the power of distributed computing and scalable data processing with our Spark Certification.

## 6. Kafka Installation

If we are goint to download and run Kafka we can install latest Java version. 

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/67c0d54a-13c2-49bc-87d2-44b1c1e07993)

After installing Java JDK 21, we can run the following command to verify the installation.

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/b759eb36-9142-407e-bad3-09cea267d2b1)

But if we are going to run Kafka with the Confluence platform it is more advidable to install Java 11.

First, we are going to install Apache Kafka from the official site: https://kafka.apache.org/downloads

Press on the link file "kafka_2.13-3.6.0.tgz" to start the donwload.

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/462a0e3b-847e-42d1-8e21-483e1c9d7b10)

Then unzip the file in your local and move the folder to the C: hard disk.

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/0fba940f-9aa5-491d-8b06-b5e70a1e99e5)

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/f2e6a91e-ccd3-4b37-96c0-30fb99b4aa84)

## 7. We add the Kafka commands to the PATH variable

We copy the Kafka commands for windows path and we copy to the PATH environmental variable.

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/ee58aa02-cfd3-48ef-bc7d-b0bfd362d0f9)

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/bb0c97c5-3c7a-4f85-aa3d-0d27f0363dd7)

## 8. Running the zookeeper

Open a command prompt window and run the command 

```
C:\>zookeeper-server-start C:\kafka_2.13-3.6.0\config\zookeeper.properties
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/09da7e4c-e3c0-4272-a2e9-9de445944996)

## 9. Run kafka broker

Open a command prompt window and run the command 

```
C:\Users\LEnriquez>kafka-server-start C:\kafka_2.13-3.6.0\config\server.properties
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/005bde6b-51e1-4a7b-a2a0-8b99696087ee)

## 10. Run some kafka commands

This command is to list the topics in your local server

```
kafka-topics --list --bootstrap-server localhost:9092
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/46311b43-f99e-4c26-8c8e-2900806bf7ec)


For creating a new topic "first-topic" an specify the partitions

```
kafka-topics --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic first-topic
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/7d95731d-b391-47e6-bc5b-7e5298805941)

For describing an existing topic

```
kafka-topics --describe --bootstrap-server localhost:9092 --topic first-topic
```

```
kafka-console-consumer --bootstrap-server localhost:9092 --topic first-topic
```

```
kafka-console-producer --broker-list localhost:9092 --topic first-topic
```

```
kafka-topics --delete --bootstrap-server localhost:9092 --topic first-topic                           
```

**Note:**

For delete add the following in kafka server.properties

```
delete.topic.enable=true
```






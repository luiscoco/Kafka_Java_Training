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


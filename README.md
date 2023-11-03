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

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/b759eb36-9142-407e-bad3-09cea267d2b1)

But if we are going to run Kafka with the Confluence platform it is more advidable to install Java 11.



Yet, there are a few prerequisites for this. One needs to have Kafka and Zookeeper installed in the Local System.

The code is written is for wordcount which documented below as follows.


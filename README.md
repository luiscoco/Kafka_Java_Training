# Kafka Java Training

https://github.com/bharaththippireddy/kafkaforjavadevelopers

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/a08822b2-600f-454a-8334-0c129012bad2)

What is Kafka?: https://www.youtube.com/watch?v=aj9CDZm0Glc

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/3701e05b-3f98-4427-a812-fddb95e5ef4c)

## 0. Messaging system

In a point-to-point system, messages are persisted in a queue. 

One or more consumers can consume the messages in the queue, but a particular message can be consumed by a maximum of one consumer only.

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/fe405652-a82f-410e-829d-a7cc97fb4674)

## 1. What is Kafka?

What is Kafka and How does it work?: https://www.youtube.com/watch?v=LN_HcJVbySw

Apache Kafka Tutorial for Beginners: https://www.youtube.com/playlist?list=PLiMWaCMwGJXlL8-E-xu8RBwyC5YfS3V5e

Apache Kafka is basically an **Open-Source** messaging tool developed by **Linkedin** to provide **Low-Latency** and **High-Throughput** platform for the **real-time** data feed.

It is developed using **Scala** and **Java** programming Languages.

Apache Kafka is a distributed publish-subscribe messaging system and a robust queue that can handle a high volume of data and enables us to pass messages from one end-point to another.

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/25117890-7b86-43ec-814f-e09e7d28e92d)

### Topics

A stream of messages belonging to a category is called a topic. 

Data is stored in topics. Kafka topics are analogous to radio / TV channels. 

Multiple consumers can subscribe to same topic and consume the messages.

Topics are split into partitions. For each topic, Kafka keeps a minimum of one partition. 

Each such partition contains messages in an immutable ordered sequence.

### Partition offset

Each partitioned message has a unique sequence id called as offset. 

For each topic, the Kafka cluster maintains a partitioned log that looks like this:

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/a07ff6a2-e17a-4eb5-9721-08b8cfee6520)

Each partition is an ordered, immutable sequence of records that is continually appended to—a structured commit log. 

The records in the partitions are each assigned a sequential id number called the offset that uniquely identifies each record within the partition.

The Kafka cluster durably persists all published records—whether or not they have been consumed—using a configurable retention period. 

For example, if the retention policy is set to two days, then for the two days after a record is published, it is available for consumption, after which it will be discarded to free up space.

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/58de78c7-7c98-4707-ac34-d77439998905)

### Replicas of partition

Replicas are nothing but backups of a partition. 

Replicas are never read or write data. 

They are used to prevent data loss.

### Brokers

Brokers are simple system responsible for maintaining the published data. 

Each broker may have zero or more partitions per topic.

### Kafka Cluster

Kafka’s having more than one broker are called as Kafka cluster.

### Kafka Cluster Architecture

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/e51054b1-2c67-4978-aa64-c1bbb2b7b81b)

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/549aad47-8369-4aae-9d3a-fdc5a644a27a)

### Zookeeper

ZooKeeper is used for managing and coordinating Kafka broker. 

ZooKeeper service is mainly used to notify producer and consumer about the presence of any new broker in the Kafka system or failure of the broker in the Kafka system.

### Consumer Group

Consumers label themselves with a consumer group name, and each record published to a topic is delivered to one consumer instance within each subscribing consumer group.

### Kafka features

**High Throughput:** Provides support for hundreds of thousands of messages with modest hardware.

**Scalability:** Highly scalable distributed system with no downtime

**Data Loss:** Kafka ensures no data loss once configured properly

**Stream processing:** Kafka can be used along with real time streaming applications like Spark and Storm

**Durability:** Provides support to persisting messages on disk

**Replication:** Messages can be replicated across clusters, which supports multiple subscribers


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

Open a command prompt window and run the command **zookeeper-server-start**

```
zookeeper-server-start C:\kafka_2.13-3.6.0\config\zookeeper.properties
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/09da7e4c-e3c0-4272-a2e9-9de445944996)

## 9. Run kafka broker

Open a command prompt window and run the command **kafka-server-start**

```
kafka-server-start C:\kafka_2.13-3.6.0\config\server.properties
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/005bde6b-51e1-4a7b-a2a0-8b99696087ee)

## 10. Run some kafka commands

This command is to **list the topics** in your local server

```
kafka-topics --list --bootstrap-server localhost:9092
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/46311b43-f99e-4c26-8c8e-2900806bf7ec)


For **creating a new topic** "first-topic" an specify the partitions

```
kafka-topics --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic second-topic
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/78e7e5d1-a34a-4b4c-aafd-670ddcb4193e)

For **describing an existing topic**

```
kafka-topics --describe --bootstrap-server localhost:9092 --topic first-topic
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/7d95731d-b391-47e6-bc5b-7e5298805941)

We open a new prompt command window, for **creating a consumer**, we run the following command:

```
kafka-console-consumer --bootstrap-server localhost:9092 --topic second-topic
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/1608e09e-3f8a-47f6-a9e5-28f86b74eb53)

We open a new prompt command window, for **creating a new producer**, we run the following command:

```
kafka-console-producer --broker-list localhost:9092 --topic second-topic
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/b1d57937-d4be-4b8d-8afa-48284360b70f)

If we would like to **delete a topic** then run the command:

```
kafka-topics --delete --bootstrap-server localhost:9092 --topic second-topic                           
```

**NOTE:**

For delete add the following in kafka **server.properties**

```
delete.topic.enable=true
```

## 11. Kafka APIs

### Admin API

https://kafka.apache.org/documentation/#adminapi

### Producer API

https://kafka.apache.org/documentation/#producerapi

### Consumer API

https://kafka.apache.org/documentation/#consumerapi

### Streams API

https://kafka.apache.org/36/documentation/streams/

### Connect API

https://kafka.apache.org/documentation/#connectapi

## 12. Create a Kafka Producer Java application with VSCode

We create a new folder to place the Java application.

We right click inside the folder and we select the option **Open with VSCode**.

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/b6e778bf-c0cf-444c-b94c-42914f54180e)

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/eddfc3ef-f7ed-42b6-aa8f-5ff29088b145)

We press the keys **Ctl+Shift+P** to create a **new Java application in VSCode**

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/c5b3aed1-3a50-40c1-8cab-51f17e74fc6c)

We select the first option **No build tools**

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/dbd6f666-a160-412b-9bbc-902249801a13)

Now we select the folder where to place the new Java application

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/3d4d2d05-ddd3-4b93-8b8f-59e9d20f739f)

We set the new Java application name **OrderProducer**. The new Java application is created:

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/7da21ea6-78e6-4b76-b2bc-931ac144c13e)

We run this command to **compile the application** and generate the **App.class** file

```
C:\Kafka with Java\OrderProducer> javac src/App.java
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/c8525741-2316-4796-addc-7dca1d266c44)

For **running the application** we type the command:

```
C:\Kafka with Java\OrderProducer> java -cp src App  
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/d4a98fb5-6da1-4398-b945-44be81cd9cfa)

Now we enter the **Kafka Producer source code** in VSCode

```java
import org.apache.kafka.clients.producer.KafkaProducer;
import org.apache.kafka.clients.producer.Producer;
import org.apache.kafka.clients.producer.ProducerRecord;
import java.util.Properties;

public class KafkaProducerApp {
    public static void main(String[] args) {
        // Set up producer properties
        Properties properties = new Properties();
        properties.put("bootstrap.servers", "localhost:9092");
        properties.put("key.serializer", "org.apache.kafka.common.serialization.StringSerializer");
        properties.put("value.serializer", "org.apache.kafka.common.serialization.StringSerializer");

        // Create Kafka producer
        Producer<String, String> producer = new KafkaProducer<>(properties);

        // Produce a message
        String topic = "your-topic";
        String key = "key1";
        String value = "Hello, Kafka!";
        ProducerRecord<String, String> record = new ProducerRecord<>(topic, key, value);

        // Send the message
        producer.send(record);

        // Close the producer
        producer.close();
    }
}
```

Then we rename the application name to **KafkaProducerApp**

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/9d9b1986-e974-4752-a3c2-822597b69e37)

Now we create a new file called **log4j.properties** in the applicaton root and we input the following code:

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/3ad0f409-7cfd-40cf-9557-4e3ed6398cd2)

Then we **donwload Kafka JAR files** from Apache Kafka web page (https://kafka.apache.org/downloads), and we place the JAR files in the Kafka producer Java application **lib** folder

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/3c5dd16e-8d37-4f45-8d28-09a16cc0bf61)

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/d0f37880-3f67-4dd9-a2bc-01eef311bc08)

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/4d6e6392-6ec9-4c0b-afe5-e63f8582a769)

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/aa7729cc-90c5-4d03-b32b-57de9898b4d2)

To **compile the application** with this command:

```
C:\Kafka with Java\OrderProducer> javac -cp "lib/*;src" src/KafkaProducerApp.java
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/38718465-2739-4b29-aa67-bc8c1ab9616a)

Finally, we **run the application** with this command:

```
C:\Kafka with Java\OrderProducer> java -cp "lib/*;src;." KafkaProducerApp
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/86cffc0e-659b-4746-a563-698b0deabc7c)

## 13. Create a Kafka Consumer Java application with VSCode



## 14. How to run the Consumer and the Producer Java applications

### 14.1. First we have to run the **zookeeper-server-start** command

```
zookeeper-server-start C:\kafka_2.13-3.6.0\config\zookeeper.properties
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/adcdaea3-ba9a-4feb-87de-db5f65dc850c)

### 14.2. Open a command prompt window and run the command **kafka-server-start**

```
kafka-server-start C:\kafka_2.13-3.6.0\config\server.properties
```

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/64a7c126-3dbf-489a-876d-993a9986197b)

### 14.3. Then open with VSCode the **Kafka Consumer** application and run it

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/0c03893c-0fd5-465c-905a-6fb88752fae1)

### 14.4. Then open with VSCode the **Kafka Producer** application and run it

![image](https://github.com/luiscoco/Kafka_Java_Training/assets/32194879/40403620-3a24-498e-8f76-a33ea5737ca0)

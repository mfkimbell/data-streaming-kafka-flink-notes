# data-streaming-kafka-flink-notes

# Kafka
![image_589142173211625734253276](https://github.com/user-attachments/assets/b49b1c95-85a5-4add-a826-72379162a316)

* Kafka has clusters, which are a bunch of brokers. We have topics, which are data streams. Topics are partioned based on keys and split up among different brokers. There is fault tolerance. Consumers can consume a single stream at the same time, since "consuming" a stream doesn't necessarily mean removing any items. 

* Kafka is for accepting real-time data, and storing that data for a certain period time (sometimes indefinitely). 

* Kafka streams can send to other kafka streams. 

* kafka focuses on EVENTS rather than DATA. We used to focus on physical items and their state and store that in a database, it was a "request-response" model, where we would send https requests, and wait for responses before proceeding. Services were "monolithic" and tightly coupled. Kafka and event-driver architecture has a focus on asycrhonous communication. Things subscribe to topics and wait to do some computation, regardless of where it comes from.

* The reason kafka came about to handle and simplify large-scale data streams in modern distributed systems. Allows for high levels of publishing and consuming. 

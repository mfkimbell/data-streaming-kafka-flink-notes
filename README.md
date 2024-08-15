# data-streaming-kafka-flink-notes

# Apache Kafka
![image_589142173211625734253276](https://github.com/user-attachments/assets/b49b1c95-85a5-4add-a826-72379162a316)

* Kafka has clusters, which are a bunch of brokers. We have topics, which are data streams. Topics are partioned based on keys and split up among different brokers. There is fault tolerance. Consumers can consume a single stream at the same time, since "consuming" a stream doesn't necessarily mean removing any items. 

* Kafka is for accepting real-time data, and storing that data for a certain period time (sometimes indefinitely). 

* Kafka streams can send to other kafka streams. 

* kafka focuses on EVENTS rather than DATA. We used to focus on physical items and their state and store that in a database, it was a "request-response" model, where we would send https requests, and wait for responses before proceeding. Services were "monolithic" and tightly coupled. Kafka and event-driver architecture has a focus on asycrhonous communication. Things subscribe to topics and wait to do some computation, regardless of where it comes from.

* The reason kafka came about to handle and simplify large-scale data streams in modern distributed systems. Allows for high levels of publishing and consuming.

### Zookeeper
* Used for distributed coordination and configuration management.

# Apache Flink

* running flink applicaiton is called a "job"
* has a data streaming pipeline called a "job graph"
  
 <img width="442" alt="Screenshot 2024-08-14 at 8 19 44 PM" src="https://github.com/user-attachments/assets/93f82842-bb7d-4f24-abb3-880d663426d3">
 
* every processing step is executed by an "operator"
* data moves towards data sinks
  
<img width="682" alt="Screenshot 2024-08-14 at 8 20 59 PM" src="https://github.com/user-attachments/assets/cee329f6-a59a-4b42-ae26-1417cdd986bb">

* can have parallel independent operators
* "forwarding" an event stream is the simplest thing an operator can do

<img width="549" alt="Screenshot 2024-08-14 at 8 22 41 PM" src="https://github.com/user-attachments/assets/7986c8cc-cd06-4db4-b125-7ccd1372a64f">

* It can also "filter"/"repartition" data
  
<img width="1094" alt="Screenshot 2024-08-14 at 8 24 15 PM" src="https://github.com/user-attachments/assets/61822ba0-5d16-4402-983c-1e1d0394134e">

* You can then "merge"/"rebalance" data streams
  
<img width="1130" alt="Screenshot 2024-08-14 at 8 24 57 PM" src="https://github.com/user-attachments/assets/5fa29d02-3d56-4ea9-86ff-1e6cca65fa05">

# Differences between them
<img width="371" alt="Screenshot 2024-08-14 at 8 41 50 PM" src="https://github.com/user-attachments/assets/5ee3f34d-5aa4-4585-a7d6-96acd0fdd03f">
* Kafka generally provides the "stream data storage layer"
* Flink can handle batch processing and more compliated stream processing
* Flink has more of a focus on real time operations

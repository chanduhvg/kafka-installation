## Gopichand Bandarupalli

# Install Kafka
Go to Kafka Quickstart, download the current source tgz file to C:\.

Un-tar it (using Bash) and change into the directory.

The $ indicates a Bash prompt.

$ tar -xzf kafka_2.13-2.7.0.tgz

$ cd kafka_2.13-2.7.0

# Setting up the Kafka Environment
Run the following commands in order to start all services in the correct order:

Window 1 - Start the ZooKeeper service
```
$ bin/zookeeper-server-start.sh config/zookeeper.properties
```
Open another terminal session and run:

Window 2 - Start the Kafka service
```
$ bin/kafka-server-start.sh config/server.properties
```
Once all services have successfully launched, you will have a basic Kafka environment running and ready to use.

Window 3 - Create a topic to store your events
```
.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic gopi-messages
.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list
```
Window 4 - Run Kafka Producer (write some events)
```
.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic gopi-messages
```
Window 5 - Run Kafka Consumer (read the events)
```
.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic gopi-messages --from-beginning
```

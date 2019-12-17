# self-sufficient-kafka
https://hub.docker.com/repository/docker/pawzem1994/self-sufficient-kafka

# Version
Kafka 2.3.1 with scala 2.11.

# Basic Information
Basic Apache Kafka and zookeeper cluster integrated in one container.
Kafka is stored in folder `/opt/kafka/`. 

# Cluster coonfiguration
Kafka parametrized by provided server properties in `/opt/configs/server.properties`.

# Build from sources
`docker build -t pawzem1994/self-sufficient-kafka .`

# Run
`docker run -d --restart=unless-stopped -p 2181:2181 -p 9092:9092 --name kafka pawzem1994/self-sufficient-kafka`

# Topic craetion example
`docker exec kafka /opt/kafka/bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 2 --topic test`

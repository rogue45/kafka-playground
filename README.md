# kafka-playground
Kafka producer consumer testing

```
version: '3.8'

services:
  zookeeper:
    image: zookeeper:3.8.0
    container_name: zookeeper
    ports:
      - "2181:2181"
    environment:
      ZOOKEEPER_CLIENT_PORT: 2181
      ZOOKEEPER_TICK_TIME: 2000
      ZOO_MY_ID: 1
    restart: always
    network_mode: "host" 


  kafka:
    image: apache/kafka:3.8.0
    container_name: kafka
    ports:
      - "9092:9092"
    network_mode: "host"  

```
```
kafka cd into /opt/kafka/bin for access to bash scripts
./kafka-topics.sh --create --topic quickstart-events --bootstrap-server localhost:9092
./kafka-console-producer.sh --topic quickstart-events --bootstrap-server localhost:9092
./kafka-console-consumer.sh --topic quickstart-events --from-beginning --bootstrap-server localhost:9092
```

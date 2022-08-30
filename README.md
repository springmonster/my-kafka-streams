# Kafa Streams Demo

> [reference](https://github.com/Programming-with-Mati/kafka-streams-word-count)

## Start

1. start zookeeper, kafka

```shell
docker-compose up 
```

2. start application
3. connect kafka docker container in one terminal

```shell
kafka-console-consumer --topic word-count --bootstrap-server localhost:9092 \
 --from-beginning \
 --property print.key=true \
 --property key.separator=" : " \
 --key-deserializer "org.apache.kafka.common.serialization.StringDeserializer" \
 --value-deserializer "org.apache.kafka.common.serialization.LongDeserializer"
```

4. connect kafka docker container in another terminal

```shell
kafka-console-producer --topic sentences --bootstrap-server localhost:9092
```

5. input something after step 4
6. check step 3 terminal and java application console
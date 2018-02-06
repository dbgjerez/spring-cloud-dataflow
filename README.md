# spring-cloud-dataflow
Pipeline example with DataFlow

# Launch RabbitMQ
```bash
docker run -d -p 15672:15672 -p 5672:5672 --name rabbit rabbitmq:3-management
```

# Download and start Spring Cloud Data Flow
```bash
wget https://repo.spring.io/libs-snapshot/org/springframework/cloud/spring-cloud-dataflow-server-local/1.3.0.RELEASE/spring-cloud-dataflow-server-local-1.3.0.RELEASE.jar
```

To start Spring Cloud Data Flow with our RabbitMQ Docker we have to pass the connection data:
```bash
java -jar spring-cloud-dataflow-server-local-1.3.0.RELEASE.jar \
        --spring.rabbitmq.host=localhost \
        --spring.rabbitmq.port=5672 \
        --spring.rabbitmq.username=guest \
        --spring.rabbitmq.password=guest
```

# Download and start Spring Cloud Data Flow Shell
```bash
wget https://repo.spring.io/libs-snapshot/org/springframework/cloud/spring-cloud-dataflow-shell/1.3.0.RELEASE/spring-cloud-dataflow-shell-1.3.0.RELEASE.jar
```

```bash
java -jar spring-cloud-dataflow-shell-1.3.0.RELEASE.jar
```

# Import defaults RabbitMQ aplications
```bash
app import --uri http://bit.ly/Bacon-RELEASE-stream-applications-rabbit-maven
```

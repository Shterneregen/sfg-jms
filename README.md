# SFG JMS Examples

[Dockerfile for the ActiveMQ Artemis Project](https://github.com/vromero/activemq-artemis-docker)
```console
docker run -it --rm \
  -p 8161:8161 \
  -p 61616:61616 \
  vromero/activemq-artemis
``` 
Credentials: 
`artemis` / `simetraehcapa`

###### Notes:

##### How to use embedded artemis activemq server
* Add dependencies below
```
org.apache.activemq:artemis-server
org.apache.activemq:artemis-jms-server
```
* Paste it to the main method
```java
ActiveMQServer server = ActiveMQServers.newActiveMQServer(new ConfigurationImpl()
        .setPersistenceEnabled(false)
        .setJournalDirectory("target/data/journal")
        .setSecurityEnabled(false)
        .addAcceptorConfiguration("invm", "vm://0"));
server.start();
```

---
Original repo: 
[SFG JMS Examples](https://github.com/springframeworkguru/sfg-jms)
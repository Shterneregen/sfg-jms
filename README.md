# SFG JMS Examples

> The Java Message Service ([JMS](https://www.oracle.com/java/technologies/java-message-service.html)) API is a messaging standard that allows application components based on the Java Platform Enterprise Edition (Java EE) to create, send, receive, and read messages. It enables distributed communication that is loosely coupled, reliable, and asynchronous.

> Apache [ActiveMQ™](https://activemq.apache.org/index.html) is the most popular open source, multi-protocol, Java-based messaging server.

> ##### [ActiveMQ Artemis](https://activemq.apache.org/index.html)
> High-performance, non-blocking architecture for the next generation of event-driven messaging applications.
> * JMS 1.1 & 2.0 with full client implementation including JNDI
> * High availability using shared storage or network replication
> * Simple & powerful protocol agnostic addressing model
> * Flexible clustering for distributing load
> * Advanced journal implementations for low-latency persistence as well as JDBC
> * High feature parity with ActiveMQ 5 to ease migration

> Artemis will eventually become the successor to ActiveMQ 5.x as ActiveMQ 6.x.

---

[Dockerfile for the ActiveMQ Artemis Project](https://github.com/vromero/activemq-artemis-docker)
```console
docker run -it --rm -p 8161:8161 -p 61616:61616 vromero/activemq-artemis
```
Credentials: 
`artemis` / `simetraehcapa`

---

###### Notes:

`@JmsListener` - Annotation that marks a method to be the target of a JMS message listener on the specified `destination`

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
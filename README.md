# OpenLeap Admin UI
This monitoring application is based on [Spring Boot Admin Server](https://github.com/codecentric/spring-boot-admin) and can be used to 
visualize the state of a distributed microservice application and monitor and control single services.

It is part of the OpenLeap.io domain because it can also be used outside logistics projects and belongs to the technical infrastructure
components of a typical microservice application built with Spring Boot.

![overview][1]

The main purpose in production is to control the log level of single components and categories as well as controlling caches. Viewing the
logs is done with a centralized log monitoring system.

Additional configuration parameter has been added or preset to the configuration parameters of [Spring Boot Admin Server](https://github.com/codecentric/spring-boot-admin):

| Configuration parameter name | Default value | Description |
|------------------------------| ----- | ----- |
| `oleap.admin.start-page`     | `/wallboard` | The existing wallboard page shall be the start page after login. Possible values ``, `/application` |
| `oleap.eureka.url`            | `http://user:sa@localhost:8761` | URI to connect to the discovery server |
| `oleap.eureka.zone`           | `${oleap.eureka.url}/eureka/` | URI to get the zone settings from Eureka discovery server |
| `oleap.srv.hostname`          | `localhost` | Hostname that is used to register the Admin UI at the discovery server |
| `oleap.srv.protocol`          | `http` | Port that is used to register the Admin UI at the discovery server |
| `server.port`                | `${PORT:8155}` | Port where the Admin UI web server listening at |

Supported Spring profiles:

| Profile name | Description                                                                                                                 |
| ------------ |-----------------------------------------------------------------------------------------------------------------------------|
| `ELK` | All logs and traces are pushed to Logstash (via syslog) expected to listen on a server with hostname `elk` and port `5000`  | 

[1]: src/site/resources/overview.png

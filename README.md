# Chat Service

## About

## Core Technologies and Dependencies

### Dev
- Java 17
- MapStruct
- Lombok
- Docker
- Docker Compose

## Configuration properties

### **Types of configurations:**

#### **⚠️WARNING⚠️**

> All sensitive data (logins, passwords, certificates, tokens, keys, etc.),
> as well as data that can be changed without changing the service code
> (URL of external and internal services, connection pool size, etc.)
> **must** be set using `ENV` variables **without** default values.
>
> All significant settings and configuration should be described in configuration properties
> files **without hardcode in the code** of the service.

#### **General**
General configuration that does not depend on the environment
- [`src/main/resources/application.yml`](src/main/resources/application.yml)

#### **Local** (default)
Configuration for running Spring Boot service locally.
When the application starts, the `default` profile is automatically pulled up.
- [`src/main/resources/application-default.yml`](src/main/resources/application-default.yml).

#### **Build**
Configuration used to launch a service in any environment (staging, pre-production, production).
`ENV` variables **must** be used here.
- [`src/main/resources/application-build.yml`](src/main/resources/application-build.yml)

## [Docker Compose](https://docs.docker.com/compose/)

```bash
docker-compose -f chat-service-infrastructure/docker-compose.yml up
```

You can stop the containers using the following command:

```bash
docker-compose -f chat-service-infrastructure/docker-compose.yml down
```

You can stop the containers using the following command:

## Installation and Running

```bash
./gradlew clean build
```


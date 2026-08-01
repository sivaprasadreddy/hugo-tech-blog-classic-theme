---
title: "Getting Started with Spring Boot 3"
date: 2023-05-15
description: "Learn how to create a new Spring Boot 3 application and explore its new features and improvements."
categories: ["Spring"]
tags: ["Java", "Spring Boot"]
image: "https://images.unsplash.com/photo-1617042375876-a13e36732a04?auto=format&fit=crop&w=1200&q=80"
readTime: "8 min read"
---

Spring Boot 3.0 is a major release that brings a lot of new features and improvements. In this article, we'll explore how to get started with Spring Boot 3 and what's new in this version.

## Prerequisites

Before we begin, make sure you have the following installed:

- Java 17 or higher
- Maven 3.6+ or Gradle 7.5+
- Your favorite IDE (IntelliJ IDEA, Eclipse, VS Code)

## Key Features in Spring Boot 3

- Java 17 baseline
- Jakarta EE 9+ support
- Native compilation support with GraalVM
- Improved observability with Micrometer and OpenTelemetry

## Create the Application

Create a Spring Boot project with the `spring-boot-starter-web` dependency, then add a small REST controller. Spring Boot discovers the controller automatically when it is below the application class package.

```java
package com.sivalabs.demo;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class DemoApplication {

    public static void main(String[] args) {
        SpringApplication.run(DemoApplication.class, args);
    }
}
```

```java
package com.sivalabs.demo;

import java.util.Map;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
class GreetingController {

    @GetMapping("/api/greeting")
    Map<String, String> greeting() {
        return Map.of("message", "Hello from Spring Boot 3");
    }
}
```

Start the application with Maven:

```bash
./mvnw spring-boot:run
```

Then open `http://localhost:8080/api/greeting` to receive the JSON response.

## Configure the Application

Spring Boot configuration can live in `src/main/resources/application.yml`:

```yaml
spring:
  application:
    name: demo-service

server:
  port: 8080
```

## Conclusion

Spring Boot 3 brings significant improvements and modernization to the Spring ecosystem.

---
title: "The @SpringBootApplication annotation explained"
date: "2021-01-01"
categories: 
  - "spring-boot"
coverImage: "springbootapplication-scaled.jpg"
---

In this article, I will be explaining the @SpringBootApplication annotation.

## What is the @SpringBootApplication annotation

The @SpringBootApplication annotation is a convenience annotation that combines the **@EnableAutoConfiguration**, **@Configuration** and the **@ComponentScan** annotations in a Spring Boot application. These annotations do the following:

**@EnableAutoConfiguration** - This enables Spring Boot's [autoconfiguration mechanism](springboot-what-and-why.md#Autoconfiguration). Auto-configuration refers to creating beans automatically by scanning the classpath.

**@ComponentScan** - Typically, in a Spring application, annotations like @Component, @Configuration, @Service, @Repository are specified on classes to mark them as Spring beans. The @ComponentScan annotation basically tells Spring Boot to scan the current package and its sub-packages in order to identify annotated classes and configure them as Spring beans. Thus, it designates the current package as the root package for component scanning.

**@Configuration** - Designates the class as a configuration class for [Java configuration](https://learnjava.co.in/how-spring-works-under-the-hood/#Configuration_metadata). In addition to beans configured via component scanning, an application may desire to configure some additional beans via the @Bean annotation as demonstrated [here](https://learnjava.co.in/spring-java-configuration-example/). Thus, the return value of methods having the @Bean annotation in this class are registered as beans.

## How to use the @SpringBootApplication annotation

In order to run a Spring Boot application, it needs to have a class with the @SpringBootApplication annotation. The following code demonstrates this:

```java
package demo;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class Main {

    public static void main(String[] args) {
          SpringApplication.run(Main.class, args);
      }

}
```

- The **Main** class has the **@SpringBootApplication** annotation
- It simply invokes the **SpringApplication.run** method. This starts the Spring application as a standalone application, runs the embedded servers and loads the beans.
- Normally, such a main class is placed in a root package above other packages. This enables component scanning to scan all the sub-packages for beans.
- For a complete working example of a simple Spring Boot application you can refer to [this](how-to-create-a-hello-world-spring-boot-web-application-in-eclipse-using-maven.md) article.

## Conclusion

So, in this article, we learnt how the @SpringBootApplication annotation works and how to use it in a Spring Boot application.

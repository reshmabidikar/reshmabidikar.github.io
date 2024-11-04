---
title: "SpringBoot - What and Why"
date: "2019-04-12"
categories: 
  - "spring-boot"
---

Recently, everyone is talking about how [Spring Boot](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-5-with-spring-boot-2%2F) is much better compared to [Spring](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-spring-framework-masterclass%2F) and how it is modular and easy to set up. So in this blog post, I will explain a bit about what Spring Boot is and how it works

## What is Spring Boot?

As per the definition on the Spring.io site, "**Spring Boot makes it easy to create stand-alone, production-grade Spring based Applications that you can "just run**"

SpringBoot sits on top of Spring. It helps you to get started with a Spring application quickly without having to write a lot of boilerplate code. In addition, it provides embedded servers like Tomcat, Jetty etc. So even if you are creating a web application, you can just create a standalone application and deploy it in the embedded server.

So you don't need to waste any time writing boilerplate code, doing XML configuration, adding Jar files or bothering about deploying on a server. You can just focus on writing your code, Spring Boot will do the rest.

## Why Spring Boot

### Problems with Spring

If you have ever written a Spring application, you will know that it needs a lot of configuration. So suppose you are creating a web-based application via Spring that also accesses a database. You will need to use Spring MVC and Spring Data JPA. So in order to create such an application via Maven, you will typically need to do the following:

1. Create a Maven project and add all the dependencies for the necessary components like Spring MVC, Spring Data JPA, etc. within the pom file
2. Do configuration for MVC support like setting up ViewResolver, DispatcherServlet, component scan
3. Do configuration for database support like setting up DataSource, TransactionManager, EntityManager, etc
4. Add all the properties like Database URL, etc. within the properties file
5. Finally, write the code

So you can see that you need to do a lot of configuration in order to set up an application via Spring.

### How Spring Boot solves this issue

SpringBoot sits on top of Spring. You just need to tell SpringBoot the type of application you are developing. SpringBoot then adds the necessary jar files and does the application configuration assuming some defaults. These default values can easily be changed by the developer. For example, if you are developing a database application, you just need to specify this to SpringBoot in the configuration file. SpringBoot then downloads all the necessary jar files like the database drivers, etc and adds them to the classpath. It also configures some beans required for the application that you are developing assuming certain defaults

So in order to develop a SpringBoot application via Maven, you just need to do the following:

1. Add the starter packages for the type of application you are developing to the Maven pom file
2. Add all the properties like Database URL, etc within the properties file
3. Writer code

So compared with the Spring approach, this approach is much straightforward.

## SpringBoot components

SpringBoot consists of 3 main components:

### Starter Parent

This is a special starter that provides common configuration. In order to add this starter, you need to add the following dependency to your Maven pom file:

````
<parent> 
<groupId>org.springframework.boot</groupId> <artifactId>spring-boot-starter-parent</artifactId> 
<version>2.1.4.RELEASE</version> 
</parent>
````

### Starter packages

SpringBoot provides some starter packages that need to be added to your Maven file (Or Gradle if you are using Gradle for dependency management). These do the necessary configuration for you. Here is a list of some of the SpringBoot starter packages:

#### spring-boot-starter-web

This starter helps you get started with a web application. In order to add this starter, you need to add the following dependency to your Maven pom file:

````
<dependency> 
<groupId>org.springframework.boot</groupId> <artifactId>spring-boot-starter-web</artifactId> 
</dependency>
````

This tells SpringBoot that you are developing a web application, so it will add the necessary jar files. It will also include the embedded Tomcat server by default.

#### spring-boot-starter-data-jpa

This starter helps you get started with a database application using JPA. n order to add this starter, you need to add the following dependency to your Maven pom file:

````
<dependency> 
<groupId>org.springframework.boot</groupId> <artifactId>spring-boot-starter-data-jpa</artifactId> 
</dependency>
````

This tells SpringBoot that you are developing a database application, so it will add the necessary jar files.

#### spring-boot-starter-test

This starter tells SpringBoot that you need all the dependencies for testing. So when this starter is added, SpringBoot automatically adds Jar files related to JUnit, etc. In order to add this starter, you need to add the following dependency to your Maven pom file:

````
<dependency> 
<groupId>org.springframework.boot</groupId>
<artifactId>spring-boot-starter-test</artifactId> 
</dependency>
````

### Auto-configuration

Based on the dependencies in the classpath, SpringBoot tries to configure your application by providing suitable defaults. This is known as auto-configuration. So suppose you are building a web application and add the starter for it to the Maven pom file. SpringBoot automatically configures the DispatcherServlet, ViewResolver, etc. Or if you have added the spring-data-jpa-starter, SpringBoot will automatically configure the necessary beans like the TransactionManager, EntityManager, etc

## Embedded Servers

Normally, in order to deploy a web application, you need to have a web server like Tomcat or Jetty installed. So after writing the code for your application, you need to package it as a war file and deploy in on a server in order to test your code. SpringBoot simplifies this by making the server a part of your application. So the jar files for the server are included within your web application. This allows you to run your web application as a normal Java application. When you use the web starter, by default SpringBoot assumes that you are creating a web application and includes the tomcat server. However, you can easily change it to some other server like Jetty.

## SpringBoot example

In order to see how you create a simple Hello World SpringBoot application, you can refer to [this](https://learnjava.co.in/how-to-create-a-hello-world-spring-boot-web-application-in-eclipse-using-maven/) blog post.

## Conclusion

so, this blog posts explains what Spring Boot it and why you should use it in an application.

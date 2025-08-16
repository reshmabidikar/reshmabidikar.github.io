---
title: "Spring Modules Explained"
date: "2019-12-22"
categories: 
  - "spring"
tags: 
  - "spring"
  - "spring-modules"
---

The Spring framework is widely used for different types of applications right from web applications, to even standalone applications. Spring framework provides a wiring mechanism, so you do not have to configure your dependencies manually, Spring does this automatically for you. In this article, I will be giving an overview of the modules within the Spring framework. I will be explaining how many modules are there in the Spring framework and also be giving an overview of the modules.

## Introduction

The Spring Framework consists of several modules. Each module performs a different functionality. Depending on your requirements, you can add the dependencies for the necessary modules. Spring modules are grouped into different categories as explained below.

### Spring Core

This contains the **spring-core, spring-beans, spring-context, spring-context-support, and spring-expression modules**. These are the main modules that make up the Spring framework. Any Spring application needs to include these modules. These modules provide support for the IoC container and DI container. This helps to separate the configuration logic from your business logic.

### Spring Data access

This contains modules that help to access external data.

The **spring-jdbc** module helps to access databases via JDBC. It provides an abstraction over JDBC and helps to eliminate boilerplate code that one would need to write while using JDBC.

The **spring-orm** module helps you to integrate ORM frameworks like JPA or Hibernate with Spring. Using the spring-orm module with these frameworks helps to make use of Spring features like declarative transaction management.

The **spring-oxm** module provides support for object-XML mappings like JAXB

The **spring-tx** module helps in transaction management. You can use it to add transaction support to any POJO class.

### Spring web

This contains modules for creating web applications.

The **spring-web** module helps in creating basic web applications. You can use it to initialize the IoC container via servlets.

The **spring-webmvc** module has The Model-View-Controller(MVC) framework. So it helps to separate each layer of a web application. The spring-webmvc module can also be used to build REST applications

### Spring Test

This contains the **spring-test** module. You can use it for unit testing and integration testing. You can use it with testing frameworks like JUNIT or TestNG.

### Spring Messaging

This contains the spring-messaging module. This supports messaging-based applications.

### Spring AOP,Spring Aspects and Spring Instrumentation

The **spring-aop** module provides support for for aspect-oriented programming. The **spring-aspects** module can be used to integrate with AspectJ which is an Aspect-Oriented extension for Java. The **spring-instrumentation** module provides support to class instrumentation and classloader implementations and are used in Application servers

## Further Learning

- [Spring MasterClass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-spring-framework-masterclass%2F) 
- [Spring Tutorial For Beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-tutorial-for-beginners%2F) 
- [Step by Step Spring MVC Tutorial](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-mvc-tutorial-for-beginners-step-by-step%2F) 
- [Spring Framework in Easy Steps](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspringframeworkineasysteps%2F)

## Conclusion

So this article covers the categorization of the Spring modules and also gives an overview of the modules in each category.

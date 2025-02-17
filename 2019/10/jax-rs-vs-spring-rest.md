---
title: "JAX-RS vs Spring REST - Differences"
date: "2019-10-14"
categories: 
  - "rest"
  - "spring"
tags: 
  - "jax-rs"
  - "spring"
  - "springrest"
---

In this article, I will be covering the differences between JAX-RS/Jersey and Spring REST.

## What is REST?

[REST](https://learnjava.co.in/what-is-rest-api/) stands for Representational State Transfer. It is an architectural style that can be used for web services. A REST server exposes functionality as REST endpoints which are simply URLs. A REST client simply uses the services exposed by the REST server by accessing the corresponding URL.

## What is JAX-RS

JAX-RS stands for Java API for RESTful Web Services (JAX-RS). It is the standard Java API for developing RESTful web services. The latest version of JAX-RS is JAX-RS 2.0. It is part of Java EE 7, so it does not need to be included separately. It is just a specification, it does not provide an implementation. Jersey is the reference implementation of JAX-RS specification. There are other implementations of JAX-RS like RESTEasy, etc

## What is Spring REST

The Spring framework also provides REST support. The Spring MVC module can be used to develop a REST service. It defines several annotations that you can use to develop a REST application.

## What are the differences between JAX-RS and Spring REST

Although both JAX-RS and Spring REST can be used to create a RESTful service in Java, there are several differences between the two as follows:


|Jax-rs|Spring REST  |
|--|--|
| JAX-RS is the standard Java specification for RESTful web services | Spring REST is an alternate way of writing REST services in Java, it does not implement JAX-RS |
| JAX-RS is just a specification, you will need to include an implementation like Jersey in order to write REST services | Spring REST is the complete implementation for RESTful services by Spring. It can be used by itself. It does not implement JAX-RS |
|JAX-RS uses standard annotations that are part of Java EE  |Spring REST uses its own custom annotations for REST|



## Some important annotations in JAX-RS and Spring REST


| Jax-rs |Spring REST  |Use of Annotation |
|--|--|--|
| @Get |@RequestMapping, @GetMapping  | Used to specify that the method maps to an HTTP GET method|
| @Post |@RequestMapping, @PostMapping  |Used to specify that the method maps to an HTTP POST method |
| @Path | @RequestMapping | Used to specify The URI that the method or class maps to|
|@QueryParam  | @RequestParam | Used to specify a query parameter|
| @PathParam |@PathVariable  | Used to specify a path parameter|


## Further Learning

[Spring MasterClass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-spring-framework-masterclass%2F) [Spring Tutorial For Beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-tutorial-for-beginners%2F) [Step by Step Spring MVC Tutorial](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-mvc-tutorial-for-beginners-step-by-step%2F) [Spring Framework in Easy Steps](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspringframeworkineasysteps%2F) [Developing RESTful web services using JAX-RS and Jersey](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fdevelop-restful-java-web-services-using-jax-rs-and-jersey%2F)

## Conclusion

In this article, I provided a comparison between JAX-RS and Spring REST. I hope this article was useful in understanding the differences between Spring REST and JAX-RS.

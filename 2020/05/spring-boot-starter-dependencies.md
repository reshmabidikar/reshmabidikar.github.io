---
title: "Spring Boot Starter Dependencies Explained"
date: "2020-05-27"
categories: 
  - "spring-boot"
---

In this article, I will be covering what [Spring Boot](https://learnjava.co.in/springboot-what-and-why/) starter dependencies are and how they greatly simplify building a Spring application.

## Problems with dependencies

Suppose you are building a [Spring](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-spring-framework-masterclass%2F) application from scratch. Prior to [Spring Boot](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-boot-tutorial-for-beginners%2F), you had to manually add all the necessary dependencies to your project. So if you use Maven, you had to add all the dependencies to your pom file. For this, you would need to know the group id and artifact id of the dependency. You would also need to know if a particular version of a dependency is compatible with other versions, etc. This often leads to mis-matched dependencies which cause errors in the application.

## How Spring Boot dependencies address this issue

Spring Boot provides starter dependencies. A starter dependency is nothing but a special dependency that aggregates commonly used dependencies for a particular feature. For example, suppose you are building a Spring based web application. For this, you will need to add dependencies for **spring-core**, **spring-web**, **jackson**, etc. You will also need to get the right versions of all these dependencies. On the other hand, if you use Spring Boot, it provides a single dependency called **spring-boot-starter-web**. You just need to add this. This will automatically add all the dependencies that are required for a building a web application via Spring.

## Spring Boot starter dependencies

Some of the commonly known Spring Boot starters are as follows:

| Name |Description  |
|--|--|
|spring-boot-starter-web  | Used to build a spring based web application. Can also be used to build a REST application |
| spring-boot-starter-data-jpa | Used to add Spring Data JPA support |
| spring-boot-starter-test | Used to add testing support like JUnit Mockito, etc |
| spring-boot-starter-thymeleaf |Used to add Thymeleaf support  |

## Advantages of Spring Boot Starters dependencies

Some of the advantages of using starter dependencies are as follows:

- Starter dependencies speed up development
- They reduce the number of dependencies required for an application
- Developers do not need to know the names of the dependencies required for an application
- Developers do not need to know the exact version of the dependencies to use

## Conclusion

So in this article, we saw what Spring Boot starter dependencies are and how they make it very easy to build a Spring application.

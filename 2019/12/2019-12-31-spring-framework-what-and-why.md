---
title: "Spring framework - What and Why"
date: "2019-12-31"
categories: 
  - "spring"
tags: 
  - "how-spring-works"
  - "spring"
  - "spring-benefits"
---

The Spring framework is widely used for developing different types of applications. In this article, I will dive into the details of what is the spring framework and the advantages that it provides.

# Before Spring

A typical Java application consists of many objects. For example if you are building an application that interacts with the database, your application would have objects corresponding to the POJO class, DAO class, etc. The problem with Java was that there was no way to wire together these objects. So your main class or the starting point of the application would somehow need to create all the required objects and the other parts of the application would use these as required. Design patterns like Factory Pattern, Abstract Factory Pattern helped to ease this slightly, but still the responsibility of creating all the necessary objects still lay with the application code.

Java then introduced the EJB framework which eased this to some extent. The problem with EJB framework was that it was heavy and development using EJBs was not easy. Developers needed to create home and remote interfaces and write a lot of boilerplate code. Unit testing is also not easy with EJBs

\[table id=27 /\]

# What Spring is

The [Spring framework](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-tutorial-for-beginners%2F) was developed as a solution to these problems. At its very core, Spring provides a wiring mechanism. It consists of the Spring container which uses **Inversion of Control** mechanism. Inversion of Control simply means the container is responsible for creating objects and not the application program. One of the ways to achieve Inversion of Control is **Dependency Injection**. Spring uses Dependency Injection. In **Dependency Injection**, the objects are injected into other objects through **setter** methods or **constructors**. So basically, Spring takes care of creating and setting the necessary dependencies. So the application code only needs to take care of the business logic.

# How Spring is organised

The Spring framework consists of several modules, each module takes care of a different functionality. You can read more about Spring modules [here](https://learnjava.co.in/spring-modules-explained/).

# Benefits of Spring

Some of the benefits of the Spring framework are as follows:

- It is a lightweight framework. Since it consists of separate modules, you can only add the necessary modules.
- It is very easy to use and setup. You do not need to write any complex code like EJBs
- In addition to providing a basic wiring mechanism, spring provides separate modules that ease web development, database access, etc
- Spring also provides a separate transaction management modules that helps to manage transactions easily.

## Further Learning

[Spring MasterClass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-spring-framework-masterclass%2F) [Spring Tutorial For Beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-tutorial-for-beginners%2F) [Step by Step Spring MVC Tutorial](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-mvc-tutorial-for-beginners-step-by-step%2F) [Spring Framework in Easy Steps](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspringframeworkineasysteps%2F)

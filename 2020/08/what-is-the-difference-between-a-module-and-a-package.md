---
title: "What is the difference between a module and a package"
date: "2020-08-04"
categories: 
  - "java-9"
  - "java-interview-questions"
---

Java 9 has introduced the concept of modules in Java. You can take a look at [this](https://learnjava.co.in/java-9-modules-introduction/) article which explains more about modules.

Here, I will be explaining the difference between a module and a package in Java.

|Module|Package  |
|--|--|
| A package cannot be deployed by itself | A module can be deployed by itself |
|A package groups together related classes  | A module groups together related packages |
| Packages are present in Java right from the beginning | Modules were added by Java 9 |
|Packages were added to keep related classes together and to allow developers to have a class with the same name in a different packages  | Modules were added for security reasons and to reduce the size of the JDK |
|Classes defined within a package are accessible via reflection even if they are private  | Classes defined within a module are not accessible outside the module via reflection |
|Packages do not require a package descriptor  | Modules require a module descriptor which is a file called module-info.java |

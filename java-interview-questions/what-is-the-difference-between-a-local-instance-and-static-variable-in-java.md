---
title: "Difference between a local, instance and static variable in Java"
date: "2021-03-04"
categories: 
  - "core-java"
  - "java-interview-questions"
coverImage: "local-instance-static-scaled.jpg"
---

Java supports three types of variables, local, instance and static. This post explains the difference between a local, instance and static variable in Java

| Local Variable | Instance Variable | Static Variable |
| --- | --- | --- |
| Defined within a method or a code block | Defined outside a method at the class level | Defined outside a method at the class level |
| Is only accessible in the method/code block where it is declared | Is accessible throughout the class | Is accessible throughout the class |
| Remains in memory as long as the method executes | Remains in memory as long as the object is in memory | Remains in memory as long as program executes |
| Does not require any special keyword | Does not require any special keyword but any access specifier (private, protected or public) can be specified. Typically, private or protected is used | Requires the static keyword to be specified. In addition, any access specifier (private, protected or public) can be specified. Typically, public is used |
| Requires to be initialized before it is used | Is given default value based on its data type, so does not require to be initialized before it is used | Is given default value based on its data type, so does not require to be initialized before it is used. |

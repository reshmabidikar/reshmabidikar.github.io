---
title: "public static void main explained"
date: "2018-11-18"
categories: 
  - "core-java"
  - "java-interview-questions"
tags: 
  - "core-java"
  - "java-keywords"
  - "public"
  - "static"
  - "void"
---

I've seen a lot of questions posted which ask the meaning of public static void main in Java. In this blog post, I'm going to explain these keywords which are used with the main method.

The main method is the starting point in any standalone Java application. However, whenever you write a main method in Java, you need to precede it with the public static void keywords. So why are they required?

**Public** - Public is an access specifier. Refer [this](java-access-specifiers-explained.md) post to learn about the other access specifiers in Java. When the public access specifier is used for a member, it indicates that the member is accessible by code which is outside the class. So the main method needs to be public since it has to be accessible by the JVM when the program is run.

**Static** - The static keyword indicates that a member can be accessed without requiring an object of a class. Refer [this](static-keyword-explained.md) post for more information on the static keyword. So they keyword static allows the main() method to be invoked even before an object of the class is created.This is necessary since main( ) is called by the Java Virtual Machine before any objects are made.

**void** - The void keyword is used for methods that do not have a return value. The main method does not return anything and so the keyword void is specified.

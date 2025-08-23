---
title: "New Features in Java 11 Explained in Detail"
date: "2023-05-28"
categories: 
  - "core-java"
  - "java-11"
coverImage: "learnjava-git.jpg"
---

Java 11, is the latest long-term support (LTS) version of the Java programming language. It brings along several exciting features and improvements. In this blog post, we'll take high level look into the New Features in Java 11.

## Local Variable Syntax for Lambda Parameters

One of the most important features in Java 11 is the ability to use the `var` keyword for lambda parameters. This allows for more concise and readable code when working with lambda expressions.

Java 10 introduced the [Local Variable Type Inference feature](../java10/java-10-type-inference.md). However, the `var` keyword could not be used with lambda expressions. So, you would need to write a lambda expression as follows:

```java
(int a, int b) -> a + b
```

This code can be rewritten in Java 11 as follows:

```java
(var a, var b) -> a + b
```

## HTTP Client Improvements

Java 11 introduces a new and modern HTTP client API that supports HTTP/1.1, HTTP/2, and WebSocket. This new client offers a more flexible and efficient way to make HTTP requests and process responses. It's fully asynchronous and supports features like request/response streaming.

## Nest-Based Access Control

Java 11 introduces the concept of nest-based access control, which helps improve the encapsulation of classes within a package. It allows classes that are logically part of the same group to access each other's private members, enhancing security and reducing the need for reflection-based workarounds.

## Dynamic Class-File Constants

Java 11 introduces a new constant type called `CONSTANT_Dynamic`, which simplifies the creation of new constants at runtime. This is particularly useful for frameworks and libraries that generate classes dynamically.

## Improved Docker Support

Java 11 introduces enhancements to better support running Java applications in Docker containers. This includes a smaller base Docker image size thanks to the new `jlink` tool, which generates custom runtime images containing only the necessary modules.

## Epsilon Garbage Collector

Java 11 includes the Epsilon garbage collector, which is designed for performance testing and tuning purposes. It allows you to disable garbage collection altogether, which can be helpful for scenarios where memory management isn't a concern.

## Single-File Source Code Launch

With Java 11, you can now run a single Java source file directly using the `java` command. This feature makes it easier to quickly test small code snippets without the need to compile and manage separate class files.


## Conclusion

Java 11 brings a variety of features and improvements that make the language more modern, efficient, and developer-friendly. From the enhanced HTTP client to local variable syntax for lambda parameters, these features help developers write cleaner, more concise, and better-performing code. As a long-term support release, Java 11 provides a stable platform for building robust and scalable applications.

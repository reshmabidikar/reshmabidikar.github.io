---
title: "What is a marker interface is Java"
date: "2018-10-20"
categories: 
  - "core-java"
  - "java-interview-questions"
tags: 
  - "core-java"
  - "interfaces"
---

In this blog post, I will be explaining what is a marker interface in Java.

#### Marker Interface Definition

A marker interface is simply an interface that has no methods. Some examples of marker interfaces in Java are [Serialiazable](https://docs.oracle.com/javase/7/docs/api/java/io/Serializable.html) , [Cloneable](https://docs.oracle.com/javase/7/docs/api/java/lang/Cloneable.html) etc.

#### How Marker Interfaces work

So if there are no methods in a marker interfaces, how do they work? In other words, how does a class that implements a marker interface know what methods to provide?

The answer to this is that marker interface specify a design pattern used to provide run-time type information about the objects. The very fact that a class implements a marker interface indicates something to the JVM or compiler. So when the JVM sees an object of the marker Interface type, it will perform some special operation.

You can also define your own marker interfaces and write code that behaves in a special way if the marker interface is implemented. So for ex. objects that belong to a class that implements the marker interface can follow one path of execution in your code and objects that do not implement the marker interface can follow another path of execution.

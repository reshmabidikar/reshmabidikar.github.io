---
title: "System.out.println explained"
date: "2018-09-15"
categories: 
  - "core-java"
  - "java-interview-questions"
tags: 
  - "core-java"
---

In this blog post, I will be explaining the System.out.println statement which is the first statement you will come across when you start learning Java programming.

 

#### System

[System](https://docs.oracle.com/javase/9/docs/api/java/lang/System.html) is a final class in the java.lang package. It has several useful classes and methods. In addition to supporting standard input and output, it has methods to access external properties, method for initiating garbage collection, etc.  It supports input/output by providing static variables corresponding to the input/output streams.

 

#### Out

[Out](https://docs.oracle.com/javase/9/docs/api/java/lang/System.html#out) is a static variable in the System class. It is of the type [PrintStream](https://docs.oracle.com/javase/9/docs/api/java/io/PrintStream.html).  Since it is a static variable, it is instantiated at start up. It is mapped to the standard output which is the console. This stream is already open and ready to accept output data.

 

#### Println

[Println](https://docs.oracle.com/javase/9/docs/api/java/io/PrintStream.html#println) is a method within the [PrintStream](https://docs.oracle.com/javase/9/docs/api/java/io/PrintStream.html) class.  There are several overloaded versions of this method that accepts different types of data like String, integer, double, etc.  Each method prints the data passed to it and also adds new line.

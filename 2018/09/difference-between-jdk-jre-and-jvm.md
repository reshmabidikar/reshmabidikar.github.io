---
title: "Difference between JDK, JRE and JVM"
date: "2018-09-30"
categories: 
  - "core-java"
  - "java-interview-questions"
tags: 
  - "core-java"
  - "jdk"
  - "jre"
  - "jvm"
---

In this blog post, I am going to explain the JVM, JRE and JDK and how they differ from each other.

#### JVM

JVM stands for **Java Virtual Machine**. It provides the environment to execute the Java byte code.As you probably know, Java is platform independent i.e. the same Java class file can be run on any operating system. It is the JVM which makes Java platform independent. When you compile code written in other programming languages, it creates files that are operating system specific. When you compile Java code, it is compiled into platform independent bytecode which is present in the **.class** file created after compilation. The JVM understands and executes this bytecode. So the JVM it is on top of the operating system and runs the bytecode making Java platform independent.

#### JRE

JRE stands for **Java Runtime Environment**. JVM executes the bytecode from the .class file. However, in addition to the JVM, some additional libraries or jar files are required. So the JRE consists of these libraries and the JVM. The JRE supplies the libraries and the .class file to the JVM in order to execute the bytecode. JRE is used by anyone who wants to run Java code.

#### JDK

It stands for **Java Development Kit**.  The JRE provides the environment to only execute your Java code. However, if you want to write Java code, you need the JDK So when you write Java code, you will need tools to compile the Java program, you will need an archiver to generate the JAR file, etc. So JDK consists of all these tools required for Java development as well we the JRE. JDK is only used by Java developers.

---
title: "Why is Java Platform Independent"
date: "2019-04-15"
categories: 
  - "core-java"
  - "java-interview-questions"
tags: 
  - "classfile"
  - "jvm"
  - "platformindependent"
---

A very common interview question is to ask a candidate to explain how Java is platform independent. So let me explain this here.

Consider the following simple Java code:

````

public class HelloWorldDemo {

  public static void main(String[] args) {
  System.out.println("This is my first Java program!");
  }
}

````

So you can see that the code is in simple English text. After you write the code you need to compile it. Compilation is the process where the code is converted into a format that is understood by the underlying machine. The underlying machine does not understand the code that we write in English, so it must be converted to a format that it understands.

In languages like C or C++, the code is compiled into executable files (files with .exe extension) that are directly executed on the operating system. So if you have an exe file of a C program for Windows, the exe file will not run as it is on a Linux machine. This is because the exe file created is operating system specific.

On the other hand, When you compile Java code, it is compiled into platform-independent bytecode which is present in the **.class** file created after compilation. The byte code is not executable unlike the exe files that you obtain after compiling a C or C++ program. The bytecode needs to be interpreted. The bytecode is interpreted by the JVM. So the JVM sits on top of the operating system and Java programs run within the JVM and not directly in the operating system. Thus, you can run the same Java class file on different operating systems.

The magic is created by the JVM. So the JVM is operating system specific. So if you are operating on a Windows machine, you will use a different JVM, but if you are operating on a Linux machine, you will need to use a different JVM.

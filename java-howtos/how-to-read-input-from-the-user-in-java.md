---
title: "How to read input from the user in Java"
date: "2018-09-20"
categories: 
  - "java-io-en"
  - "java-io-examples"
tags: 
  - "core-java"
  - "java-io-en"
---

This blog post demonstrates how to read a user's input in Java. You can use the following code snippet:

```java

public class ReadInput { 
    public static void main(String args[]){ 
        Scanner scanner = new Scanner(System.in); 
        System.out.println("Enter your input:"); 
        int num = scanner.nextInt(); 
        System.out.println("The number entered is "+num); 
    } 
}
````

This code uses the [Scanner](https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html) class.This class has a method called `nextInt` which is used to read an integer input. In addition to this method, it has several other methods like `nextDouble`, `nextFloat` ,etc. which can be used to read other data types.  
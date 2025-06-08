---
title: "How to add two numbers in Java"
date: "2018-09-10"
categories: 
  - "java-examples"
tags: 
  - "core-java"
---

This blog posts shows how to add two numbers in Java:

```java

public class Demo {

    public static void main(String args[]){ 
        int a = 10; 
        int b = 20; 
        int result = add(a,b); 
        System.out.println("Result is "+result); 
    }

    private static int add(int a,int b){ 
        int result = a+b; 
        return result; 
    } 
}

```

Here, we are using the method add to add two numbers. It accepts 2 integer values, adds them and returns the result. You can change the data type/ return value to anything else like long,short, float, double, etc.

If you run the code, the following output will get printed to the console:

 

```
Result is 30
```

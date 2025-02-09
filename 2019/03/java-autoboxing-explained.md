---
title: "Java Autoboxing explained"
date: "2019-03-11"
categories: 
  - "core-java"
  - "java-interview-questions"
tags: 
  - "autoboxing"
---

In this blog post, I will be explaining Java's autoboxing feature in detail


#### What is Auto boxing?

Java provides class equivalents for all the primitive datatypes. So for example, there is an Integer class which corresponds to the int datatype, a Float class that corresponds to the float data type and so on. Not only that, Java can automatically convert between the class and the corresponding primitive type. So if there is an Integer type, Java can automatically convert it to int and if there is an int type, Java can automatically convert it to Integer. This is known as autoboxing.

Consider the following code snippet:

````

public static void main(String[] args) { 
  int i = 5; 
  Integer integer = i; 
  System.out.println("The value of integer is "+integer); 
}

````

Here, we have defined an **int** variable called **"i"** and assigned it the value 5. After that we have defined an **Integer** variable called **integer** and assigned it the value **"i"**. So note that this does not cause any compilation error. Java **automatically** converts the int value to the Integer type.

#### Why is autoboxing useful?

There are several scenarios where autoboxing is useful

**While using Collections**

The collections in the Java Collection API store a collection of objects. So the class equivalents of each primitive type can be used in order to store data of primitive types within a collection. Using autoboxing, we can then convert the primitive type to the corresponding object type.

**Keeping code clean**

Autoboxing keeps the code clean as there is no need to explicitly convert the primitive types to object types and vice versa.


#### Class equivalents for the primitive types

All the classes corresponding to the primitive data types are present in the java.lang package. The following table provides the names of each primitive type and its corresponding class equivalent:

| Primitive Type |Object Type|
|--|--|
| boolean|java.lang.Boolean|
| byte | java.lang.Byte |
|char  | java.lang.Character |
| double | java.lang.Double |
| float |java.lang.Float  |
| int |java.lang.Integer  |
| long |java.lang.Long  |

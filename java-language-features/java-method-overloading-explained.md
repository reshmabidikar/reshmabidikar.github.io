---
title: "Java Method Overloading Explained with Code Samples"
date: "2020-02-12"
categories: 
  - "java_language_features"
tags: 
  - "method-overloading"
---

Java method overloading allows defining two or more methods within the same class that share the same name. Method overloading makes the code clean and increases the readability of the code. [Method overloading](../java-interview-questions/object-oriented-principles-in-java.html) helps to achieve polymorphism which is one of the object-oriented principles. In this article, I will be covering method overloading in detail.

## Introduction

When methods are overloaded, their parameter declarations need to be different. The following code demonstrates this:

```java
public class AdditionService {

int add() { // no parameters

    return 3+5;

}

int add(int i) { //one integer parameter

    return i+i;

 }

int add(int i,int j) { //two integer parameters

 return i+j;

}

double add(double i,double j) { //two double parameters

    return i+j;

}

}
```

This class has 4 methods with the name **add**. All four add methods differ in the **parameters**, so there is no compilation error. So the add method is said to be “**overloaded**” four times.

The following code invokes these methods:

```java
public static void main(String[] args) {

AdditionService as = new AdditionService();

int sum1 = as.add();
System.out.println("Sum1 is "+sum1);

int sum2 = as.add(5);
System.out.println("Sum2 is "+sum2);

int sum3 = as.add(10,20);
System.out.println("Sum3 is "+sum3);

double sum4 = as.add(4.5, 6.7);
System.out.println("Sum4 is "+sum4);
 }
```


This code prints the following output:

```
Sum1 is 8

Sum2 is 10

Sum3 is 30

Sum4 is 11.2
```

## Overloading using Return Types

Overloaded methods must differ in the type and/or number of their parameters. So if the type/number of arguments is the same but return types are different, then the methods are not overloaded and the code will cause a compilation error. The following code demonstrates this:

```java
public class AdditionService {

//this code causes a compilation error

int add(int i,int j) {
    return i+j;
 }

 double add(int i,int j) {
    return i+j;
 }

}
```

Here, both the add methods accept two integer arguments. However, the first method returns an integer while the second methods returns a double value. This code causes a **compilation error** because there are two **add** methods accept 2 **integer**

## How method overloading works

When an overloaded method is invoked, Java uses the **type** and/**or number of arguments** to determine which version of the overloaded method to actually call. So Java simply executes the version of the method whose **parameters match** the **arguments** used in the call. While overloaded methods may have different **return** types, the return type alone is insufficient to distinguish two versions of a method. So if two methods have exactly the same number and type of parameters, but different return types, there will be a compilation error. **Method overloading** is one of the ways that Java supports the object-oriented principle of **polymorphism**.

## Conclusion

So in this article, we saw how method overloading works in Java.

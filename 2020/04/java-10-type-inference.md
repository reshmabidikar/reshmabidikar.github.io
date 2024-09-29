---
title: "Java 10 Type Inference explained with Code Samples"
date: "2020-04-07"
categories: 
  - "java-10"
---

A new feature added by [Java 10](https://learnjava.co.in/java-10/) is the **Local Variable Type Inference**. In this article, I will be covering this feature in detail.

## Introduction

Before Java 10, while declaring a variable, you explicitly had to specify its type, The following code demonstrates this:

```
int i = 10;
String s = "Hello";
```

So this code declares an **int** variable **i** and assigns it the value **10**. It also declares a **String** variable **s** and assigns it the value "**Hello**".

Java 10 introduces the **Local Variable Type Inference** feature. This means that Java can determine the **data type** of a variable based on the value assigned to the variable. So you do not need to explicitly specify the **data type**. Java 10 introduces a new type **var**. You need to specify '**var**' instead of the data type. The following code demonstrates this:

```
var i = 6;
var s = "Hello";

```

So this code declares the variables **i** and **s**. No data type is specified, the compiler infers the data type based on the value assigned to the variables.

You cannot use var for a variable without initializing it. So the following code will cause a compilation error:

```
var a;
```

Since **a** is not initialized, the compiler cannot determine its type. So the above code causes a compilation error.

## Valid Uses of Var

It is valid to use **var** only in specific scenarios. These are elaborated below.

### Local Variable

As seen above, you can use var for a local variable

### Loop control variable

You can use var as a loop control variable. The following code demonstrates this:

```
List<Integer> numbers = Arrays.asList(2,4,6,8,10);
for(var i = 0; i < numbers.size();i++) {
  System.out.println(numbers.get(i));
}
```

Here, the code uses **var** for the loop control variable **i** which iterates over the **numbers** list and prints each number.

### As a return value in a method

You can use **var** as the return value in a method. The following code demonstrates this:

```
public static int doSomething() {
  var i = 8;
  return i;
}
```

Here, the code uses **var** for the variable **i** which is returned by the method **doSomething**.

### To assign value returned by a method

You can use **var** to assign the value returned by a method. The following code demonstrates this:

```
var value = doSomething();
```

Here, the code uses **var** for the variable **value** which is assigned the value returned by the method **doSomething**.

## Invalid Uses of Var

There are some scenarios where it is invalid to use **var**. These are elaborated below.

### Instance variables

You cannot use **var** an an instance variable. So the following code is invalid:

```
public class Circle {
  
  private var radius; //will cause a compilation error

}
```

Here, the code uses **var** for the private instance field **radius** which is invalid.

### Method Parameters/Return Type

You cannot use **var** for method parameters or return type. So the following code snippets are invalid:

```
public static var doSomething()) {

}

public static void doSomethingElse(var a) {

}
```

So the method **doSomething** specifies a return type of **var** which is invalid. The method **doSomethingElse** specifies an argument a of type **var** which is also invalid.

### Array Initializer

You cannot use var while initializing an array. So the following code is invalid:

```
var myArray[] = {2,4,6,8,10};
```

Here, the code uses **var** with **myArray** and initializes it to some values which is invalid.

## Conclusion

So in this article, we saw how **Java 10 Local Variable Type Inference** works. We walked through the various scenarios where using var is valid and invalid.

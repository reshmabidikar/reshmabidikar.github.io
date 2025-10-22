---
title: "Java Varargs explained with code samples"
date: "2020-01-23"
categories: 
  - "java_language_features"
---

Java supports passing a variable number of arguments (varargs) to a method. In this article, I will be explaining this feature.

## What is varargs

JDK 5 added the varargs feature, which allow creating a method that accepts a variable number of arguments. Prior to the varargs support, if you wanted to create a method with variable arguments, you either had to overload the method or use a Collection or array as a parameter.

## Varargs Syntax

A variable number of arguments is specified using an argument name and three dots. The following code demonstrates this:

```java
void method myMethod(String ...str){
//method body
}
```

This specifies a String argument str which is a vararg. So you can invoke this method as follows:

```java
myMethod("a");  //with 1 parameter

myMethod("a","b"); //with 2 parameters

myMethod("a", "b", "c"); //with 3 parameters
```

## Code Sample

The following code demonstrates a code sample that uses varargs:

```java
public class VarargDemo {

  public static int calculate(int... num) {
    int sum = 0;
    for (int i : num) {
      sum += i;
    }
    return sum;
  }

  public static void main(String[] args) {
    System.out.println("With one argument:" + calculate(5));
    System.out.println("With two arguments:" + calculate(3, 7));
    System.out.println("With three arguments:" + calculate(2, 4, 8));

  }

}
```

This code has a method _calculate_ that accepts a parameter _num_ which is a vararg. It simple returns the num of the values specified in the vararg. It uses a for-each loop to iterate through the vararg. The main method then invokes this method with one, two and three arguments. So this code prints the following output:

```
With one argument:5
With two arguments:10
With three arguments:14
```

## Varargs Rules

There are some rules that need to be followed while creating a vararg argument. These are as follows:

- The vararg must be the last argument in the method declaration. So if a method accepts multiple arguments, the vararg must be the last argument
- A method cannot have more than one vararg

## Conclusion

So in this article, we saw what Java varargs are, how varargs work and how they help in creating methods that accept a variable number of arguments in Java.

---
title: "Java 8 forEach loop explained with code samples"
date: "2019-04-08"
categories: 
  - "java-8-features"
  - "java-interview-questions"
tags: 
  - "core-java"
  - "java-collections-framework-en"
  - "java8"
---

[Java 8](https://reshmabidikar.github.io/blog.html#java-8-new-features) introduced a lot of new features like functional interfaces, lambda expressions, etc. These provide a totally new way of programming for developers. One such feature is the forEach support added to the Collection interfaces. In this blog post, I will be covering this feature in detail.

#### What is forEach

Java 8 added a new method called `forEach` to all the Collection interfaces via the [Iterable](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html) interface. You can use this method to iterate through a Collection internally without the need for an explicit for loop.

#### Before Java 8

Prior to Java 8, if we wanted to iterate through a Collection like a [List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html), we had to write code similar to the following:

````java

public class ForEachDemo { 
  public static void main(String args[]) { 
    List <Integer> list = Arrays.asList(5,3,11,15,9); 
    for(int num:list) { 
      System.out.println("Number is "+num); 
    }
  } 
}
````

So you need to write a for loop to iterate through the elements in the List. In the body of the for loop, you can write the code that you want to be executed on each element in the list.

#### Java 8 Way

Starting with Java 8, you can iterate through a Collection using the forEach method. So you can write code similar to the following:

````java

public class ForEachDemo { 
  public static void main(String args[]) { 
    List<Integer> list = Arrays.asList(5,3,11,15,9); 
    list.forEach(num -> System.out.println("Number is "+num));
  } 
}
````

So here, we are invoking the [forEach](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html#forEach-java.util.function.Consumer-) method on the List interface. We are passing a [lambda expression](java-8-lambda-expressions-explained.md) to the [forEach](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html#forEach-java.util.function.Consumer-) method that prints the current element. So, you can see that there is no explicit for loop used here.

#### How forEach works

Java 8 has added a new method called [forEach](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html#forEach-java.util.function.Consumer-) on the [Iterable](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html) Interface. The [Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html) interface extends this interface and so this method is automatically available in all the Collection interfaces like [Set](https://docs.oracle.com/javase/8/docs/api/java/util/Set.html) and [List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)

The [forEach](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html#forEach-java.util.function.Consumer-) method accepts a single argument which is a [Consumer](https://docs.oracle.com/javase/8/docs/api/java/util/function/Consumer.html) instance. [Consumer](../java8-examples/java-8-consumer-interface-example.md) is a functional interface. Refer to [this](java-8-functional-interface.md) blog post to understand more about functional interfaces. [Consumer](../java8-examples/java-8-consumer-interface-example.md) has a single method called `accept` which accepts input of any data type.

The [forEach](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html#forEach-java.util.function.Consumer-) method is given a default implementation within the [Iterable](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html) interface. Refer to [this](java-8-default-method-in-interface-explained.md) blog post to understand default interface methods introduced by Java 8. This is just to avoid making changes to the code for all the [Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html) classes to provide an implementation for this method. If the default implementation was not provided, Java would have to provide an implementation for the [forEach](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html#forEach-java.util.function.Consumer-) method in each of the [Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html) classes like [ArrayList](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html), [HashSet](https://docs.oracle.com/javase/8/docs/api/java/util/HashSet.html). etc.

The default implementation of the [forEach](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html#forEach-java.util.function.Consumer-) method iterates through all the elements of the [Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html) on which it is invoked and invokes the accept method with the specified lambda expression. Here we are using a lambda expression that simply prints the input number. So the [forEach](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html#forEach-java.util.function.Consumer-) method invokes the accept method with this expression and prints each number in the input list.

Just like List, you can use the forEach method to iterate over a Map or Set as well.

#### Why forEach is better

Compared to the traditional approach, the Java 8 approach is much better. The traditional approach is verbose and requires explicit code to be written. In contrast, the Java 8 code is concise and easy to read.

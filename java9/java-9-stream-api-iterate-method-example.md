---
title: "Java 9 Stream API iterate method example"
date: "2019-11-18"
categories: 
  - "java-9"
tags: 
  - "java9"
  - "java9stream"
  - "java9streamiterate"
---

Another improvement made by Java 9 is adding a new Stream.iterate method. This is a new feature in Java 9 Stream API.

## Java 8 Stream.iterate

Prior to Java 9, The Stream Interface already had an iterate method. The Stream.iterate is a static method on the Stream interface. You can use it to create a new Stream. It accepts the following parameters:

- Initial Value
- UnaryOperator instance which is used to find subsequent values.

It returns a Stream instance.

The following code demonstrates this method:

```
Stream<Integer> numberStream = Stream.iterate(2, num -> num+2).limit(10);
numberStream.forEach(System.out::println);
```

This code uses an initial value of 2. Also, the UnaryOperator is implemented via a lambda expression that simply increments the previous value by 2.

Note that the Stream.iterate method returns an infinite Stream. So the code uses the limit method to terminate the Stream. So this code prints the following output:

```
2
4
6
8
10
12
14
16
18
20
```

## Java 9 Stream.iterate

Java 9 has added an overloaded version of the Stream.iterate method. In addition to the initial value and UnaryOperator, this method also accepts a Predicate instance. This Predicate instance determines when the Stream must terminate.

The following code demonstrates this:

```
Stream<Integer> numberStream2 = Stream.iterate(2,num -> num <= 20, num -> num+2);
    numberStream2.forEach(System.out::println);
```

This code accepts an initial value of 2 and a UnaryOperator operator instance that increments the value by 2. In addition, this code also accepts a Predicate instance. The Predicate is implemented by a lambda expression that checks if the num <= 20. So this code prints the same output as before.

## Conclusion

So in this article, we have seen another Java 9 Stream API enhancement which is the Stream.iterate method. I hope you find this article and other articles in this [series](https://learnjava.co.in/java-9-posts/) useful to understand Java 9 new features.

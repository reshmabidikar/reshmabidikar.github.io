---
title: "Java 9 Stream dropWhile method with examples"
date: "2019-09-28"
categories: 
  - "java-9"
tags: 
  - "java9dropwhile"
---

Java 8 introduced the Stream API which allows processing and applying some operations to the elements in a Collection. Java 9 has made some improvements to the Stream API. One such improvement is the dropWhile method. In this article, I will be covering the Java 9 Stream dropWhile method in detail. I will also be writing some Java 9 dropWhile examples.

The dropWhile method is the exact opposite of the takeWhile method that I had covered earlier [here](java-9-stream-takewhile-with-examples.md). It behaves differently on ordered and unordered Streams as explained subsequently.

## dropWhile on Ordered Stream

As per the API documentation, when the dropWhile is applied on an ordered Stream, it returns, a stream consisting of the remaining elements after dropping the longest prefix of elements that match the given predicate. So basically, the dropWhile method applies the Predicate on each element in the input Stream and drops it if the condition is true. It continues this until the condition becomes false.

The following code demonstrates this:

```java
Stream<Integer> inputList = Stream.of(5, 8, 12, 16,51);
inputList.dropWhile(num -> num < 10).forEach(num -> System.out.print(num+" "));
```

In this case, we have an input Stream of ordered Integers. The dropWhile is used to drop the longest subset of numbers that are less than 10. So when you execute this code, it will print the following output:

```
12 16 51
```

## dropWhile on Unordered Stream

As per the API documentation, when the dropWhile is applied on an unordered Stream, it can drop any subset of matching elements, but the behavior is non-deterministic and so it may return a different result each time. So basically, what this means is that the dropWhile method may or may not drop a subset of elements that match the specified Predicate. The following code demonstrates this:

```java
Stream<Integer> unorderedList = Stream.of(31,5,7,18, 12, 6,2,1, 16,51);
unorderedList.dropWhile(num -> num < 10).forEach(num -> System.out.print(num+" "));
```
In this case, the input Stream is not ordered. So when you execute this code, it will print a different result each time.

## When all elements in the Stream match the Predicate

Irrespective of whether a Stream is ordered or unordered, the dropWhile method drops the entire input stream when all the elements in the Stream match the Predicate. The following code demonstrates this:

```java
Stream<Integer> allMatch = Stream.of(1,6,3);
allMatch.dropWhile(num -> num < 10).forEach(num -> System.out.print(num+" "));
```

In this case, all the elements in the input Stream match the condition, that is all the elements are less than 10. So when you execute this code, it will print not print anything

## When none of the elements in the Stream match the Predicate

Irrespective of whether a Stream is ordered or unordered, the dropWhile method returns retains the entire input Stream when none of the elements in the Stream match the Predicate. The following code demonstrates this:

```java
Stream<Integer> noneMatch = Stream.of(11,18,14,26);
noneMatch.dropWhile(num -> num < 10).forEach(num -> System.out.print(num+" "));
```

In this case, none of the elements in the input Stream match the condition, that is all the there is no element that is less than 10. So when you execute this code, it will print the following:

```
11 18 14 26
```

## Conclusion

So, in this article we learned about the Java 9 Stream `dropWhile` method.

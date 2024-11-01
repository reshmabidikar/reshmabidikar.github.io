---
title: "Java 9 Stream takeWhile with examples"
date: "2019-08-19"
categories: 
  - "java-9"
tags: 
  - "java9"
  - "java9sreamapiimprovements"
  - "java9takewhile"
---

[Java 8](https://learnjava.co.in/java-8/) introduced the Stream API which allows processing and applying some operations to the elements in a Collection. [Java 9](https://learnjava.co.in/java-9-posts/) has made some improvements to the [Stream API](https://learnjava.co.in/java-8-stream-api/). One such improvement is the takeWhile method. In this article, I will be covering the Java 9 Stream takeWhile method in detail. I will also be writing some Java 9 takeWhile examples.

The takeWhile method operates on a Stream. It accepts a Predicate instance and applies the Predicate to all the elements in the input stream and produces an output stream. It behaves differently depending on whether the input Stream is ordered or unordered.

## takeWhile on Ordered Stream

As per the API documentation, when the takeWhile is applied on an ordered Stream, it returns, a stream consisting of the longest prefix of elements taken from this stream that match the given predicate if the stream is ordered. So basically, the takeWhile method applies the Predicate on each element in the input Stream until the condition in the Predicate becomes false. So basically, the first element in the output stream will be the first element in the input stream (if it matches the Predicate) and the last element in the output stream is the last element in the input stream that matches the Predicate.

The following code demonstrates this:

```
Stream<Integer> inputList = Stream.of(5, 8, 12, 19,41);
inputList.takeWhile(num -> num < 10).forEach(num -> System.out.println(num));
```

In this case, we have an input Stream of ordered Integers. The code uses takeWhile to obtain a subset of elements that are less than 10. So when you execute this code, it will print the following output:

```
5 8
```

## takeWhile on Unordered Stream

As per the API documentation, when the takeWhile is applied on an unordered Stream, it can return any subset of matching elements, but the behavior is non-deterministic and so it may return a different result each time. So basically, what this means is that the takeWhile method may or may not return a subset of elements that match the specified Predicate. It may also return an empty subset. The following code demonstrates this:

```
Stream<Integer> inputList = Stream.of(5, 8, 12,4, 7,4,1,16);
inputList.takeWhile(num -> num < 10).forEach(num -> System.out.println(num));
```

In this case, the input Stream is not ordered. So when you execute this code, it will print a different result each time.

## When all elements in the Stream match the Predicate

Irrespective of whether a Stream is ordered or unordered, the takeWhile method returns the entire input stream when all the elements in the Stream match the Predicate. The following code demonstrates this:

```
Stream<Integer> orderedInput = Stream.of(5, 8, 9,16);
orderedInput.takeWhile(num -> num < 20).forEach(num -> System.out.print(num+" "));

```

In this case, all the elements in the input Stream match the condition, that is all the elements are less than 20. So when you execute this code, it will print the following output:

```
5 8 9 16
```

## When none of the elements in the Stream match the Predicate

Irrespective of whether a Stream is ordered or unordered, the takeWhile method returns an empty set when none of the elements in the Stream match the Predicate. The following code demonstrates this:

```
Stream<Integer> unorderedInput = Stream.of(5, 8, 12,4,6, 7,3,1,16);
unorderedInput.takeWhile(num -> num < 2).forEach(num -> System.out.println(num));
```

In this case, none of the elements in the input Stream match the condition, that is all the there is no element that is less than 2. So when you execute this code, it will not print anything to the console.

## Conclusion

So in this article, we learned about Java 9 Stream takeWhile method and saw how to use it with code samples.

---
title: "Parallel Streams in Java with code samples"
date: "2021-04-15"
categories: 
  - "java8"
coverImage: "java_parallel_streams-scaled.jpg"
---

In my [earlier](java-8-stream-api.md) article, I had covered the Stream API in depth. In this article, we will be taking a look at parallel streams. Simply speaking, a parallel stream is a stream that operates on its elements in parallel.

## How to obtain a parallel stream

Just like the `stream` method, all the Collection interfaces have a `parallelStream` method. This returns a parallel stream on the underlying Collection.

Consider the following code:

```java
List<String> food = Arrays.asList("Pizza","Sandwich","Burger","Rice");
Stream<String> foodStr = food.parallelStream();
```

This code first creates a String List `food` with some values. It then invokes the `parallelStream` method on food. This returns a String Stream which is a parallel stream.

In addition, the Stream interface also has a method `parallel`. If the stream on which this method is invoked is a sequential stream, it returns a parallel stream corresponding to it. If the stream on which it is invoked in a parallel stream, it returns the stream itself.

Consider the following code:

```java
Stream<String> foodStream = Stream.of("Pizza","Sandwich","Burger","Rice");
Stream<String> parallelFoodStream = foodStream.parallel();

```

This code first creates a String Stream `foodStream` using the `Stream.of` method. This creates a sequential stream. It then invokes the parallel method on `foodStream`. This returns a parallel stream corresponding to `foodStream`.

## How parallel streams work

A parallel stream operates on the elements of the underlying stream in parallel and then combines the results at the end. This gives parallel streams a performance advantage over sequential stream. However, a word of caution. When parallel streams are used, the order of execution is not guaranteed. Hence, you should use them only for operations where the order of execution does not matter.

Consider the following code:

```java
List<Integer> marks = Arrays.asList(81,76,69,92,84,75,88,96,54,91);
List<Integer> marks2 = marks.parallelStream().filter(m -> m > 80).collect(Collectors.toList());
System.out.println(marks2);
```

This code first creates an Integer List `marks` using some values. It then obtains a parallel stream on `marks` and invokes the [filter](stream-api-filter-example.md) method on the stream. The `parallelStream` method creates multiple smaller streams. The `filter` operation is performed on each stream by a separate thread. Finally, the result of performing the filter operation are combined before performing the `collect` operation.

This code produces the following output:

```
[81, 92, 84, 88, 96, 91]
```

## Difference between a sequential and parallel stream

Now that we are familiar with parallel streams, let me list down the difference between a sequential and a parallel stream.

1. Sequential streams use a single thread to process all the elements in the stream. Parallel streams on the other hand split the stream into smaller streams and use separate threads to process each stream.
2. In order to obtain a sequential stream on a collection, you need to use the stream method. In order to obtain a parallel stream on a collection, you need to invoke the parallelStream method.
3. Parallel streams are more efficient than sequential streams on multi-core processors.

## Conclusion

So, in this article, we understood what parallel streams are, how one can obtain a parallel stream and the differences between a sequential and a parallel stream.

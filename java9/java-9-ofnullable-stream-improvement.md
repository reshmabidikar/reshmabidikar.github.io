---
title: "Java 9 Stream.ofNullable explained with code samples"
date: "2019-12-18"
categories: 
  - "java-9"
tags: 
  - "java-9"
  - "java-9-stream-improvements"
---

One of the improvements made by Java 9 to the Stream API is the Stream.ofNullable method. In this article, we will be taking a closer look at this method.

## Introduction

Java 9 has added the Stream.ofNullable method to the Stream interface. This helps in avoiding a NullPointerException.

### Prior to Java 9

Prior to Java 9, you could use the Stream.of method to create a Stream with values. However, a Stream could not be created from a null value and if done, it would result in a NullPointerException.

The following code demonstrates this:

```java
Stream<Integer> stream = Stream.of(10);
System.out.println("Stream size:"+stream.count());
```

So this creates a Stream with a single element. Now suppose you specify a null value in the Stream.of method as follows:

```java
Stream<Integer> stream = Stream.of(null);
System.out.println("Stream size:"+stream.count());
```

The above code will result in a NullPointerException.

Using Java 9

Java 9 Stream.ofNullable helps to avoid a NullPointerException. It basically creates a Stream with the specified value and is the value is null, it creates an empty Stream. The following code demonstrates this:

```java
Stream<Integer> stream = Stream.ofNullable(null);
System.out.println("Stream size:"+stream.count());
```

So now the code no longer throws a NullPointerException, it prints the following output to the console:

Stream size:0

## Conclusion

So this article demonstrates the Java 9 Stream.ofNullable method and how you can use it to create a Stream from a null value.

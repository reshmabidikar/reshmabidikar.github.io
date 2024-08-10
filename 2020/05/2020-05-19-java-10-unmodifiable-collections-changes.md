---
title: "Java 10 Unmodifiable Collections Changes"
date: "2020-05-19"
categories: 
  - "java-10"
---

One of the new features added by Java 10 is some new methods for creating unmodifiable collections. In this article, I will be covering the Java 10 Unmodifiable Collections.

# What is an Unmodifiable Collection?

As the name implies, an unmodifiable Collection is a Collection that cannot be modified. So if you create an unmodifiable collection and then try to add or remove a value from it, Java throws an Exception

# What is the use of an Unmodifiable Collection

Sometimes, you may need to create a read only copy of a Collection. Unmodifiable collections are useful in such scenarios.

# How to create an Unmodifiable Collection using Java 10

Java 10 has added a `copyOf`method to all the Collection interfaces. You can use this to create an unmodifiable Collection. The following code demonstrates this:

```
List<Integer> numberList = Arrays.asList(2,4,6,8,10);
numberList.add(12); // Line 1 - no exception
    
List<Integer> unmodifiableList = List.copyOf(numberList);
unmodifiableList.add(14); //Line 2 - throws exception
```

This code creates an Integer List. Line 1 adds a value to the List. This does not cause any exception. Then, the code uses the `List.copyOf`method. This creates an unmodifiable List. Line 2 then tries to add a value to this List. However, this code throws an UnsupportedOperationException.

 

# Difference between copyOf and Collections.unmodifiableList

Prior to Java 10, you could create unmodifiable Collections via the [Collections](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html) class.  The `Collections`class has several utility methods that return an unmodifiable Collection. For example, the `Collections.unmodifiableList`returns an unmodifiable List.  So you may wonder why Java 10 has added the `copyOf`method and what is the difference between `copyOf`and `Collections.unmodifiableList`

The `Collections.unmodifiableList`method returns an unmodifiable view of the source List. So if the source List is modified, these changes are reflected in the unmodifiable List. The `copyOf`methods on the other hand, return a read-only copy of the source Collection. So even if the source Collection is modified, the unmodifiable Collection does not change.

# toUnmodifiable method

Java 10 has also added a `toUnmodifiable`method on the Collectors class. This helps to create an unmodifiable Collection from a Stream. The following code demonstrates this:

```
Stream<String> myStream = Stream.of("red","blue","green");
  List<String> colours = myStream.collect(Collectors.toUnmodifiableList());
```

This code creates a Stream of Strings. It then uses the `Stream.collect`method to convert the Stream to a List. It specifies the `Collectors.unmodifiableList()`which returns a `Collector`that creates an unmodifiable List.

 

# Conclusion

So in this article, we saw the Java 10 `copyOf`method that helps to create unmodifiable Collection. We also understood the difference between `Collections.unmodifiableList`method and the `copyOf`method. Finally, we took a look at the `Collectors.toUnmodifiable`method also added by Java 10.

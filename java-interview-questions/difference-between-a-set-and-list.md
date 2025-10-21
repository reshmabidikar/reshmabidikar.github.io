---
title: "What is the difference between a Set and List?"
date: "2018-08-31"
categories: 
  - "collections-framework"
  - "java-interview-questions"
tags: 
  - "arraylist"
  - "core-java"
  - "java-collections-framework-en"
  - "set"
---

A very common question asked in Java interviews is to explain the difference between a **Set** and a **List**. So,in this post I'm going to explain this in detail.

### What is common between Set and List?

Before I start with the differences, let me explain what is common between the two. Both [Set](https://docs.oracle.com/javase/8/docs/api/java/util/Set.html) and [List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html) are sub interfaces of the [Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html) interface in the [java.util](https://docs.oracle.com/javase/8/docs/api/java/util/package-summary.html) package. Both store a group of elements, however they differ slightly in the way they store data.

### So what are the differences?

#### Duplicates

A List allows duplicate elements i.e. the same element can be present more than once. A Set on the other hand does not allow duplicates. So if the same element is added again, it will overwrite the previous value of the element.

#### Ordering of Elements

Also, a List is ordered i.e. elements in a list are stored in the order in which they are inserted & this order is maintained.The List interface has a method called add. It adds object sequentially to the list, so the first object added will be at the first position, the second object at the second position and so on. So the order in which the elements are inserted into the list is maintained and it remains fixed.A Set on the other hand is unordered so the order in which the elements are inserted into the Set will not be maintained. So the element that is added first to the Set may not be present in the Set in the first position unlike a List.

#### Positional Access

Since the order of elements in a list is fixed, it allows positional access. This means that you can access an element in a list by its position in the list. The List interface has a method called [get](https://docs.oracle.com/javase/8/docs/api/java/util/List.html#get-int-) to support positional access. This method accepts an integer value which is the position of the element. So this method returns the element at the specified position.Since a Set is not ordered, it does not allow positional access i.e. you cannot access an element in the Set by its position. So unlike the List interface, the Set interface does not define a get method.

### Implementations

[ArrayList](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html) is the most popular implementation of the List interface. It has many other implementations like [LinkedList](https://docs.oracle.com/javase/8/docs/api/java/util/LinkedList.html), [Vector](https://docs.oracle.com/javase/8/docs/api/java/util/Vector.html), etc.

[Hashset](https://docs.oracle.com/javase/8/docs/api/java/util/HashSet.html) is the most popular implementation of the Set interface. It has many other implementations like [TreeSet](https://docs.oracle.com/javase/8/docs/api/java/util/TreeSet.html), [LinkedHashSet](https://docs.oracle.com/javase/8/docs/api/java/util/LinkedHashSet.html), etc.

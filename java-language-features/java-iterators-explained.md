---
title: "What are Iterators in Java?"
date: "2018-11-29"
categories: 
  - "collections-framework"
  - "java-interview-questions"
  - "java_language_features"
tags: 
  - "core-java"
  - "iterator"
  - "java-collections-framework-en"
---

Java provides an interface called [Iterator](https://docs.oracle.com/javase/8/docs/api/java/util/Iterator.html) that is used to iterate over or loop through the elements in a collection. You can use an iterator on any [Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html) interfaces or any of its sub interfaces like [List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html) or [Set](https://docs.oracle.com/javase/8/docs/api/java/util/Set.html).

Consider the following code snippet:

````java
public static void main(String[] args) { 
    List<Integer> list = new ArrayList<Integer>(); 
    for(int i = 0; i < 10; i ++) { 
        list.add(i+2); 
    } 
    Iterator<Integer> itr = list.iterator(); 
    while (itr.hasNext()){ 
        int i = itr.next(); 
        System.out.println("i="+i); 
    } 
} 
````

This code demonstrates how you can use iterator to iterate over a List. Here, we are iterating over a list of integers. But you can use it to iterate over any data type. The iterator method on the list interface returns an iterator instance. In the iterator variable declaration, we need to specify the data type that the iterator will iterate over. In this case, we are specifying Integer. Once we obtain an iterator, we can use it in a while loop. The iterator has a method called [hasNext](https://docs.oracle.com/javase/8/docs/api/java/util/Iterator.html#hasNext--), this returns true if there are elements left to be iterated. So if there are any elements left, then the while loop is entered. The [next](https://docs.oracle.com/javase/8/docs/api/java/util/Iterator.html#next--) method returns the next element in the list. The while loop is repeated till all the elements in the list are exhausted.

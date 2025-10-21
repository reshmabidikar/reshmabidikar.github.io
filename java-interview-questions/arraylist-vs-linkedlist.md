---
title: "ArrayList Vs LinkedList"
date: "2019-02-04"
categories: 
  - "collections-framework"
  - "java-interview-questions"
tags: 
  - "collections"
  - "java-collections-framework-en"
---

In this blog post, I will be comparing the [ArrayList](https://docs.oracle.com/javase/7/docs/api/java/util/ArrayList.html) and [LinkedList](https://docs.oracle.com/javase/7/docs/api/java/util/LinkedList.html) classes. I will be explaining how they are similar, how they are different and when you should use which.

#### Similarities:

1. Both are Collections and implement the [List](https://docs.oracle.com/javase/7/docs/api/java/util/List.html) interface
2. Both are used to store a dynamic number of elements (Primitive or Object type)

#### Differences

1. ArrayList uses an array data structure internally to store the data. A LinkedList on the other hand, uses a doubly linked list internally as the data structure to store data.
2. When you need to insert or delete data from the bottom of the List, an ArrayList is faster. If you need to insert or delete an element from the middle of the list, a LinkedList is faster. An ArrayList uses an array to store the data internally. So when you insert or delete an element from the bottom of the list, this does not affect the array. However, if you insert or delete an element from the middle of the list, this affects the internal array. So it needs to be resized and elements need to be moved up or down in order to accommodate the newly inserted or deleted element.
3. Position based access is faster in an ArrayList than a LinkedList. Since ArrayList uses an array internally, it is easier to find an element at a particular position, you just need to specify the position and retrieve the element at the location. However, in the case of a LinkedList, the entire list has to be traversed in order to retrieve an element at a particular position.
4. A LinkedList has more memory overhead. An ArrayList only holds the elements in the internal array, whereas the LinkedList needs to store the address of the next and previous elements in the internal linked list.

#### When should you use which?

In generally programming, you will see an ArrayList used more frequently than a LinkedList. Position based access is faster in an ArrayList , whereas insertions and deletions to the middle of the list are faster in a LinkedList. So if your code merely accesses elements in a list, without modifying the list much, than you should use an ArrayList. However, if your code needs to frequently add or remove elements in the middle of the list, then a LinkedList should be used.

---
title: "How to convert a List to a Set"
date: "2018-10-10"
categories: 
  - "collections-framework"
  - "java-collection-examples"
---

In this blog post ,I will be showing you how you can convert a List to a Set. Consider the following code snippet:

```java

public class ListToSetDemo {

public static void main(String[] args) { 
    
    List<Integer> list = Arrays.asList(5,3,11,15,9);

    //Method 1 
    Set<Integer> set = new HashSet<Integer>(list); 
    System.out.println("Set is "+set);

    //method 2 
    Set<Integer> set2 = new HashSet<Integer>(); 
    set2.addAll(list); 
    System.out.println("Set is "+set2);
    } 
}
```

This code demonstrates two ways to convert a List to a Set.

**Method 1**

Here, we are creating a new [HashSet](https://docs.oracle.com/javase/8/docs/api/java/util/HashSet.html). We are invoking the [constructor](https://docs.oracle.com/javase/8/docs/api/java/util/HashSet.html#HashSet-java.util.Collection-) that accepts a Collection object. Here, we are passing in the input list to this constructor.

**Method 2**

Here again, we are creating a new [HashSet](https://docs.oracle.com/javase/8/docs/api/java/util/HashSet.html). However, we are using the default constructor. We are then invoking the [addAll](https://docs.oracle.com/javase/8/docs/api/java/util/Set.html#addAll-java.util.Collection-) method and passing in the input list.

When you run this code, it will print the following output:

```
Set is [3, 5, 9, 11, 15]
Set is [3, 5, 9, 11, 15]
```

Note that the order of the elements in the Set is not the same as in the input List.

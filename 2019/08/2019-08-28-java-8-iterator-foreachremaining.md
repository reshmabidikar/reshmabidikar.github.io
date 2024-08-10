---
title: "Java 8 Iterator forEachRemaining method with code samples"
date: "2019-08-28"
categories: 
  - "java-8-features"
  - "java8"
tags: 
  - "java-8"
  - "java8collectionimprovements"
  - "java8foreachremaining"
---

[Java 8](https://learnjava.co.in/java-8/) has added a method called forEachRemaning to the Iterator interface. This helps in using an Iterator to internally iterate over a Collection, without an explicit loop. In this article, I will be covering this method with a code sample.

\[table id=24 /\]

## Pre Java 8 code

Before Java 8, you had to write code similar to the following in order to use an Iterator:

```
public class ForEachRemainingDemo {

  public static void main(String[] args) {
    List<Integer> input = Arrays.asList(5, 3, 11, 15, 9, 2, 5, 11);
    Iterator<Integer> itr = input.iterator();
    while(itr.hasNext())
      System.out.println(itr.next());

  }

}
```

So in this code, you need to use a while loop in order to use the iterator to iterate through the input list.

## Using Java 8 forEachRemaining

Java 8 added the forEachRemanining method to the Iterator interface. So using this method, the above code can be re-written as follows:

```
public class ForEachRemainingDemo {

  public static void main(String[] args) {
    List<Integer> input = Arrays.asList(5, 3, 11, 15, 9, 2, 5, 11);
    Iterator<Integer> itr = input.iterator();
    itr.forEachRemaining(num -> System.out.println(num));
  }

}
```

 

## forEachRemaining Explained

So basically, when you use the forEachRemaining method, you no longer require a while loop in order to iterate through the input list via an Iterator. The forEachRemaining method accepts as a parameter a Consumer instance. The above code implements this via a lambda expression, that simply prints the number. The forEachRemaining method does not provide any other benefit other than eliminating the need to write a while loop.

## Conclusion

The forEachRemaining is a new method in the Iterator interface and helps to iterate through a Collection without an explicit loop when an Iterator is used.

---
title: "Java 8 Collection removeIf method with code samples"
date: "2019-08-31"
categories: 
  - "java-8-features"
tags: 
  - "java8"
  - "java8collectionimpreovements"
  - "java8collectionremoveif"
coverImage: "collection-removeIf-scaled.jpg"
---

Java 8 has added a new method called removeIf to the Collection interface. You can use this to remove an element from a Collection in Java. In this article, I will be explaining how this method works.

## What does RemoveIf do?

This method removes an element from the Collection that matches a particular condition. It returns a boolean value which indicates whether some values were removed or not. The condition to be checked is specified via a [Predicate](https://reshmabidikar.github.io/2018/10/java-8-predicate-example.html) instance. Predicate is an in-built [functional interface](https://reshmabidikar.github.io/2019/03/java-8-functional-interface.html) that accepts an argument of any data type and returns a boolean. You can implement it via a [lambda expression](https://reshmabidikar.github.io/2019/05/java-8-lambda-expressions-explained.html).

## RemoveIf Integer Code Sample

The following code demonstrates this method on an Integer List:

```java
public class RemoveIfDemo {

  public static void main(String[] args) {
    List<Integer> input = new ArrayList<Integer>();
    input.add(5);
    input.add(12);
    input.add(17);
    input.add(18);
    input.add(25);
    
    boolean anyElementRemoved = input.removeIf(num -> (num%2==0));
    if(anyElementRemoved){
      System.out.println("Elements were removed");
      input.forEach(num -> System.out.println(num));
    }
    else
      System.out.println("Elements were not removed");

  }

}
```

This code creates an Integer List **input** with some values. It then invokes the **removeIf** method on **input** with a lambda expression that checks if a number is even. So the code applies this lambda expression to each element in the list and the removes the even numbers. So when you execute this code, it prints the following output to the console:

```
Elements were removed
5
17
25
```

## RemoveIf String Code Sample

The following code demonstrates this method on a String List:

```java
public class RemoveIfStringDemo {

  public static void main(String[] args) {
    List<String> input = new ArrayList<String>();
    input.add("March");
    input.add("January");
    input.add("September");
    input.add("December");
    
    boolean elementsRemoved = input.removeIf(str -> str.endsWith("day"));
    if(elementsRemoved){
      System.out.println("Elements were removed");
      input.forEach(str -> System.out.println(str));
    }
    else
      System.out.println("Elements were not removed");
  }

}
```

This code creates a String list input with some String values. It then invokes the **removeIf** method on **input** with a lambda expression that checks if a String ends with **"day"**. Since there are no strings in the input list that match this condition, no values are removed from input and the removeIf method returns a false. So when you execute this code, it prints the following output:

```
Elements were not removed
```

## Conclusion

So in this article, you saw how to use the Java 8 Collection.removeIf method to remove an object from an ArrayList. We saw code samples that remove a value from an Integer List and from a String List.

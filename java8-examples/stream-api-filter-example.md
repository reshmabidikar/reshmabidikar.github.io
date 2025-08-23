---
title: "Stream API Filter examples with code samples"
date: "2019-06-19"
categories: 
  - "java-8-examples"
tags: 
  - "java-8"
  - "stream-api"
---

In this blog post, I will be demonstrating the [filter](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html#filter-java.util.function.Predicate-) method provided by Java 8 Stream API.In order to understand the Stream API in detail, refer to[this](../java8-features/java-8-stream-api.md)blog post.

## Introduction

The [filter](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html#filter-java.util.function.Predicate-) method in the Stream API can be applied on an existing Stream. It creates a new Stream with all the elements that match the condition specified in the [filter](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html#filter-java.util.function.Predicate-) method. It accepts a [Predicate](https://reshmabidikar.github.io/2018/10/java-8-predicate-example.html) instance which is an in-built functional interface. 

## Code Sample with Integer

```java
public class FilterStreamDemo {

  public static void main(String[] args) {
    List<Integer> input = Arrays.asList(5, 3, 11, 15, 9, 2, 5, 11);
    Stream<Integer> stream = input.stream().filter(num -> num >= 9);
    stream.forEach(num -> System.out.println(num));

  }

}
```

This code uses the [filter](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html#filter-java.util.function.Predicate-) method to obtain all the elements that are **greater than 9**. It first obtains a stream instance on the input **ArrayList** using the [stream()](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#stream--) method. Then the code invokes the [filter](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html#filter-java.util.function.Predicate-) method on the stream instance. Here, the [Predicate](https://reshmabidikar.github.io/2018/10/java-8-predicate-example.html) is implemented via a **lambda** expression. So the code passes each element in the input list to the [Predicate](https://reshmabidikar.github.io/2018/10/java-8-predicate-example.html), checks if the number is greater than 9 and if so adds it to the new Stream.

When you execute this code, it will print the following output:

```
11
15
9
11
```

## Code Sample with String

The following code demonstrates the **filter** method with a **String** **ArrayList** as input:

```java
public class FilterStringDemo {
  public static void main(String[] args) {
    List<String> strList = Arrays.asList("Apple","Orange","Mango","Banana");
    Stream<String> filteredStream = strList.stream().filter( str -> str.startsWith("M"));
    filteredStream.forEach(str -> System.out.println(str));

  }
}
```

Here, the **filter** method is used to find the list of **fruits** in the input list that starts with an “**M**“. So when you execute this code, it prints the following output:

```
Mango
```

# Code Sample with any Class

You can also use the **filter** method on your own **custom classes**. For example. consider the following **Animal** class:

```java
public class Animal {
  
  private String name;
  
  private String type;
  public Animal(String name, String type) {
    super();
    this.name = name;
    this.type = type;
  }
        //getters and setters
}
```

This code defines a class **Animal** with two fields, “**name**” and “**type**“. The name signifies the name of the **Animal** and type signifies whether the **Animal** is a **herbivore** or **carnivore**. Now consider the following code that creates a **List** of **Animals** and uses the **filter** method:

```java
public class FilterAnimalDemo {

  public static void main(String[] args) {
    List<Animal> animals = new ArrayList<Animal>(); 
    animals.add(new Animal("cow","herbivore"));
    animals.add(new Animal("lion","carnivore"));
    animals.add(new Animal("tiger","carnivore"));
    animals.add(new Animal("giraffe","herbivore"));
    animals.add(new Animal("zebra","herbivore"));
    
    Stream<Animal> herbivores = animals.stream().filter(animal -> animal.getType().equals("herbivore"));
    herbivores.forEach(animal -> System.out.println(animal.getName()));

  }


}
```

This code uses the **filter** method to find all the animals that are **Herbivores**. So when you execute this code, it will print the following output:

```
cow
giraffe
zebra
```

You can get the source code for this example along with the code for other Java 8 examples at the Github repository [here](https://github.com/reshmabidikar/Java8Demo).

---
title: "Stream API anyMatch explained with code samples"
date: "2019-05-21"
categories: 
  - "java-8-examples"
tags: 
  - "java8"
  - "stream-api"
---

In this blog post, I will be demonstrating the anyMatch method provided by Java 8 Stream API.

In order to understand the Stream API in detail, refer to [this](../java8-features/java-8-stream-api.md) blog post.

## Code Sample with Integer

You can use the [anyMatch](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html#anyMatch-java.util.function.Predicate-) method to determine if any element in a Collection matches a particular condition.

Consider the following code snippet:

```java
public class AnyMatchDemo {
  public static void main(String[] args) {
    List<Integer> input = Arrays.asList(5, 3, 11, 15, 9, 2, 5, 11);
    boolean found = input.stream().anyMatch(num -> num > 9);
    System.out.println("number > 9 "+found);
  }
}
```

This code checks if there is any number in the input collection that is **greater than 9**. First, the code obtains a [Stream](../java8-features/java-8-stream-api.md) on the input ArrayList using the [stream()](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#stream--) method. Then the code invokes the [anyMatch](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html#anyMatch-java.util.function.Predicate-) method on the stream instance. This method accepts a [Predicate](java-8-predicate-example.md) instance. It has a method called [test](https://docs.oracle.com/javase/8/docs/api/java/util/function/Predicate.html#test-T-). This method accepts an argument of any data type and returns a boolean. The above code implements the [Predicate](java-8-predicate-example.md) via a lambda expression. So the code passes each element in the input list to the [Predicate](java-8-predicate-example.md), checks if the number is greater than 9 and if so returns a boolean value accordingly.

So when you execute this code, it will print the following output:

```
number > 9 true
```

## Code Sample with String

The following code demonstrates the **anyMatch** method with a **String** **ArrayList** as input:

```java
public static void main(String[] args) {
  List<String> strList = Arrays.asList("Apple","Orange","Mango","Banana");
  boolean anyMatch = strList.stream().anyMatch( str -> str.startsWith("S"));
  System.out.println("Fruit starting with S present: "+anyMatch);

}
```

Here, the **anyMatch** method is used to determine if there is any **fruit** in the input list that starts with an "**S**". So when you execute this code, it prints the following output:

```
Fruit starting with S present: false
```

## Code Sample with Class

The following code demonstrates the **anyMatch** method with an **ArrayList** of a custom type called **Animal**.

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

This code defines a class **Animal** with two fields, "**name**" and "**type**". The name signifies the name of the **Animal** and type signifies whether the **Animal** is a **herbivore** or **carnivore**. Now consider the following code that creates a **List** of **Animals** and uses the **anyMatch** method:

```java
public static void main(String[] args) {
    List<Animal> animals = new ArrayList<Animal>(); 
    animals.add(new Animal("cow","herbivore"));
    animals.add(new Animal("lion","carnivore"));
    animals.add(new Animal("tiger","carnivore"));
    animals.add(new Animal("giraffe","herbivore"));
    animals.add(new Animal("zebra","herbivore"));
    
    boolean herbivorePresent = animals.stream().anyMatch(animal -> animal.getType().equals("herbivore"));
    System.out.println("Herbivore present="+herbivorePresent);

  }
```

This code uses the **anyMatch** method to determine if there is any **Animal** in the **List** that is a **Herbivore**. So when you execute this code, it will print the following output:

```
Herbivore present=true
```

You can get the source code for this example along with the code for other Java 8 examples at the GitHub repository [here](https://github.com/reshmabidikar/Java8Demo).

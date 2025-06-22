---
title: "Stream API AllMatch in Java 8 with examples"
date: "2019-08-02"
categories: 
  - "java-8-examples"
tags: 
  - "java8"
  - "java8streamallmatch"
  - "java8streamapi"
---

In this blog post, I will be demonstrating the allMatch method provided by Java 8 Stream API.

In order to understand the Stream API in detail, refer to [this](https://reshmabidikar.github.io/2019/05/java-8-stream-api.html) blog post.

## Code Sample with Integer

You can use the [allMatch](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html#anyMatch-java.util.function.Predicate-) method to determine if all the elements in a Collection matches a particular condition.

Consider the following code snippet:

```java
public class AllMatchIntegerDemo {

  public static void main(String[] args) {
    List<Integer> input = Arrays.asList(5, 3, 11, 15, 9, 2, 5, 11);
    boolean found = input.stream().allMatch(num -> num % 2 == 0);
    System.out.println("All even numbers: "+found);

  }

}
```

This code checks if all the numbers in the input stream are even. First, the code obtains a [Stream](https://docs.oracle.com/javase/8/docs/api/?java/util/stream/Stream.html) on the input ArrayList using the [stream()](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#stream--) method. Then the code invokes the [allMatch](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html#allMatch-java.util.function.Predicate-)method on the stream instance. This method accepts a [Predicate](https://reshmabidikar.github.io/2018/10/java-8-predicate-example.html) instance.[Predicate](https://reshmabidikar.github.io/2018/10/java-8-predicate-example.html) is an in-built functional interface. It has a method called [test](https://docs.oracle.com/javase/8/docs/api/java/util/function/Predicate.html#test-T-). This method accepts an argument of any data type and returns a boolean. The above code implements the [Predicate](https://reshmabidikar.github.io/2018/10/java-8-predicate-example.html) via a lambda expression. So the code passes each element in the input list to the [Predicate](https://reshmabidikar.github.io/2018/10/java-8-predicate-example.html), checks if the number is even and if so returns a boolean value accordingly.

So when you execute this code, it will print the following output:

```
All even numbers: false
```

## Code Sample with String

The following code demonstrates the **allMatch** method with a **String** **ArrayList** as input:

```java
public class AllMatchStringDemo {

  public static void main(String[] args) {
    List<String> strList = Arrays.asList("Monday","Sunday","Wednesday");
    boolean allMatch = strList.stream().allMatch( str -> str.endsWith("day"));
    System.out.println("All days of the week: "+allMatch);

  }
}
```

Here, the **allMatch** method is used to determine if all the Strings in the input list are days of the week and end with "day“. So when you execute this code, it prints the following output:

```
All days of the week: true
```

## Code Sample with Class

The following code demonstrates the **allMatch** method with an **ArrayList** of a custom type called **Person**.

```java
public class Person {
  
  private String name;
  private int age;
  
  public Person(String name, int age) {
    super();
    this.name = name;
    this.age = age;
  }
}
```

This code defines a class **Person** with two fields, “**name**” and “**age**“. Now consider the following code that creates a **List** of **Person objects** and uses the **allMatch** method:

```java
public class AllMatchClassDemo {

  public static void main(String[] args) {
    List<Person> personList = new ArrayList<Person>(); 
    personList.add(new Person("Tom",25));
    personList.add(new Person("Jane",31));
    personList.add(new Person("Ram",15));
  
    
    boolean adultPresent = personList.stream().allMatch(person -> person.getAge() > 18);
    System.out.println("All adults present="+adultPresent);

  }

}
```

This code uses the **allMatch** method to determine if all the **Person objects** in the **List** are adults, that is they have age > 18. So when you execute this code, it will print the following output:

```
All adults present=false
```

You can get the source code for this example along with the code for other Java 8 examples at the Github repository [here](https://github.com/reshmabidikar/Java8Demo).

---
title: "Java 8 Stream API map method with examples"
date: "2019-07-14"
categories: 
  - "java-8-examples"
tags: 
  - "java-8-map-operation"
  - "java8"
  - "stream-api"
---

In this blog post, I will be demonstrating the Java 8 Stream API map method. In order to understand the Stream API in detail, refer to [this](../java8-features/java-8-stream-api.md) blog post.

## Introduction

The **map** method in the Stream API can be applied on an existing Stream. It applies some logic to each element in the input stream and produces an output stream. For example, if there is an integer stream, you can you the map operation to multiply each element by 5. Or if you have a Stream of String values, you can use the map operation to convert each element in the Stream to uppercase.

The map operation accepts a `Function` instance which is an in-built functional interface. Refer [this](java-8-function-interface-example.md) blog post for a detailed Function example.

## Code Sample with Integer

Consider the following code sample:

```java
public class MapIntegerDemo {

  public static void main(String[] args) {
    List<Integer> input = Arrays.asList(5, 3, 11, 15, 9, 2, 5, 11);
    System.out.println("Input list:");
    input.forEach(num -> System.out.println(num));
    System.out.println("Squared list:");
    input.stream().map(num -> num*num).forEach(num -> System.out.println(num));
    
  }
}
```

This code operates on an **Integer** stream. It uses the **map** operation to create a new stream that has the squares of all the elements in the input stream. So when you execute this code, it will print the following output:

```
Input list:
5
3
11
15
9
2
5
11
Squared list:
25
9
121
225
81
4
25
121
```

## Code Sample that converts String to a custom class

The map operation can be used to convert an object of one type to an object of a different type. Consider the following code:

```java
public class Vehicle {
  
  private String type;
  
  private String make;
  
  private String model;
  
  public Vehicle(String type){
    this.type = type;
  }

//getters and setters

}
```

Here, the **Vehicle** class has fields corresponding to type, make and model. It also has a constructor that accepts the type as a String.

Now consider the following code:

```java
public class MapVehicleDemo {

  public static void main(String[] args) {
    List<String> vehicleTypes = Arrays.asList("Car","Aeroplane","Bicycle");
    
    List<Vehicle> vehicles = vehicleTypes.stream().map(str->new Vehicle(str)).collect(Collectors.toList());
    vehicles.forEach(vehicle -> System.out.println("Vehicle is of type:"+vehicle.getType()));

  }

}
```

Here, we have a **String** List **vehicleTypes** that stores different types of Vehicles. A Stream instance is obtained on the **vehicleTypes** and the map operation is invoked. The **map** operation uses the **Vehicle** constructor to create a **Vehicle** object for each **Vehicle** type. The collect method then converts the Stream to a List. So when you execute this code, it will print the following output:

```
Vehicle is of type:Car
Vehicle is of type:Aeroplane
Vehicle is of type:Bicycle


```

I hope this post on the Java 8 Stream API Map example was useful to to to understand the map operation. You can get the source code for this example along with the code for other Java 8 examples at the GitHub repository [here](https://github.com/reshmabidikar/Java8Demo).

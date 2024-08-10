---
title: "Java 8 Map compute methods with code samples"
date: "2019-10-04"
categories: 
  - "java-8-features"
tags: 
  - "java-8-collection-improvements"
  - "java8"
  - "java8mapcompute"
---

In this article, I will be covering the [Java 8](https://learnjava.co.in/java-8/) Map compute methods.Java 8 has introduced the **Map.compute, Map.computeIfPresent example, and Map.computeIfAbsent** methods.

\[table id=24 /\]

## compute

The `compute`method computes a new value for a particular key and updates the **Map** with the new value. Even if the specified key is not present in the map, it computes the value for the key and adds the key-value mapping to the **Map**.

The following code demonstrates this:

```
Map <Integer,String> students = new HashMap<Integer,String>();
students.put(100, "Swati Shashtri");
students.put(101, "Gina George");
students.put(102, "Puja Khanna");
    
students.compute(100, (key,value) -> value+",Pune");
System.out.println(students.get(100));
students.compute(101, (key,value) -> value+",Bangalore");
System.out.println(students.get(101));
```

 

Here, there is a **Map** that has a student id as the key and student name as the value. There are 3 entries in the Map. The `compute`method appends a city to the name of the student. So for the student with id **100**, it appends the city as "**Pune**" and for the student with id **101**, it appends the value "**Bangalore**".

So when you execute this code, it will print the following output:

```
Swati Shashtri,Pune
Gina George,Bangalore
```

## computeIfPresent

The `computeIfPresent`method is similar to the `compute`method, but it computes a value for the specified key only if the key is present in the map. `Compute`on the other hand computes a value for the specified key even if it is not present in the map and adds it to the map. The following code demonstrates this:

```
Map <Integer,String> students = new HashMap<Integer,String>();
students.put(100, "Swati Shashtri");
students.put(101, "Gina George");
students.put(102, "Puja Khanna");
    
students.compute(103, (key,value) -> value+",Pune");
System.out.println(students.get(103));
students.computeIfPresent(104, (key,value) -> value+",Bangalore");
System.out.println(students.get(104));
```

 

The above code first invokes compute with the key "**103**".  Since there is no key-value mapping corresponding to "**103**", `compute`computes the value as per the lambda expression and adds it to the map. Next, the code invokes`computeIfPresent`for key "**104**". This key is also not present in the **Map**. Unlike `compute`, the `computeIfPresent`

only computes and adds to the **map** if the key is present. Since this key is not present in the map, the `computeIfPresent`does not do anything. So when you execute this code, it will print the following:

```
null,Pune
null
```

## computeIfAbsent

The `computeIfAbsent`method computes a value for a key if it is not present in the map. The following code demonstrates this:

```
Map<String, Integer> fruitsLengthMap = new HashMap<String, Integer>();
fruitsLengthMap.put("apple", 5);
fruitsLengthMap.put("strawberry", 10);

String banana = "banana";

fruitsLengthMap.computeIfAbsent(banana, key -> key.length());
System.out.println(fruitsLengthMap.get(banana));
```

 

**fruitsLengthMap** is a **Map** that stores the name of a fruit as a key and its **String** length as the value. The `computeIfAbsent`method adds the value “**banana**” with its **length**. This method accepts as a parameter a key value and a `Function`interface. This is an in-built functional interface. Here, it is implemented by a lambda expression that simply returns the length of the key. This is then added as the value corresponding to the key. So when this code is executed, it will print the following output:

```
6
```

## Further Learning

- [Java Functional Programming with Lambdas and Streams](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Ffunctional-programming-with-java%2F)
- [Java 8 lambdas and Streams](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava8_lambdasandstreams%2F)

## Conclusion

In this article, we took a look at a **Map.compute** example. We also covered what is **Map.computeIfAbsent** and what is **Map.computeIfPresent**.

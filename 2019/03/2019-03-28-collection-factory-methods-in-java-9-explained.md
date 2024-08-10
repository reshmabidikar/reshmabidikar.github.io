---
title: "Collection Factory Methods in Java 9 with Code Samples"
date: "2019-03-28"
categories: 
  - "java-9"
  - "java-interview-questions"
---

One of the new features of **Java 9** is the **Java 9 Collection factory methods**. These allow you to directly create a Collection object with a list of values. In this blog post, I will be explaining this feature in detail.

## Before Java 9

Suppose you want to create a **List** of **String** values. Prior to Java 9, you had to write code like the following:

```
List<String> inputList = new ArrayList<String>(); 
inputList.add("One"); 
inputList.add("Five"); 
inputList.add("Ten"); 
inputList.add("Twenty");
```

 

The above code snippet involves invoking the [List.add](https://docs.oracle.com/javase/8/docs/api/java/util/List.html#add-E-) method **several times** and does not look very clean. **Java 9** introduced a new method that allows directly adding a list of elements into a Collection without having to invoke the [add](https://docs.oracle.com/javase/8/docs/api/java/util/List.html#add-E-) method several times.

## Java 9 way

**Java 9** introduced a factory method called [of](https://docs.oracle.com/javase/9/docs/api/java/util/List.html#of-E...-) on the **Collection interfaces**. This method is present on all the Collection interfaces i.e. **List, Set and Map**. It returns a Collection containing an arbitrary number of elements. So this can be used to create the collection with a list of elements.

For example, suppose you want to create a List of String values. You can write code similar to the following:

```
List<String> inputList = List.of("One","Five","Ten","Twenty");
```

 

This code is **much cleaner** than repeatedly adding the elements in the **List** via the [add](https://docs.oracle.com/javase/8/docs/api/java/util/List.html#add-E-) method. You can create the **List** in a single line of code.

There are several overloaded versions of the [of](https://docs.oracle.com/javase/9/docs/api/java/util/List.html#of-E...-) method. For example the [List.of()](https://docs.oracle.com/javase/9/docs/api/java/util/List.html#of--) method can be used to create an empty list. The [List.of(E e)](https://docs.oracle.com/javase/9/docs/api/java/util/List.html#of-E-) can be used to create a List with a single element. You can refer to the [API documentation](https://docs.oracle.com/javase/9/docs/api/java/util/List.html) for the complete list of methods.

Note only [List](https://docs.oracle.com/javase/9/docs/api/java/util/List.html), the of method is present on the [Set](https://docs.oracle.com/javase/9/docs/api/java/util/Set.html) and [Map](https://docs.oracle.com/javase/9/docs/api/java/util/Map.html) interfaces as well. So you can create a **Set or Map** of elements using the **of** method.

Consider the following code snippet:

```
Set<String> inputSet = Set.of("One","Five","Ten","Twenty");
```

So this returns a Set with the specified values.

So also the following code snippet create a Map:

```
Map<String, String> map = Map.of("1","One", "5", "Five","10","Ten","20","Twenty");
```

## of method vs Arrays.asList

Java also provides the [Arrays.asList](https://docs.oracle.com/javase/7/docs/api/java/util/Arrays.html#asList\(T...\)) method which can be used to **create a List** in a single line of code. So consider the following code snippet:

```
List<String> inputList = Arrays.asList("One","Five","Ten","Twenty");
```

So this code is quite similar to the one written using the **of** method. Also, The [Arrays.asList](https://docs.oracle.com/javase/7/docs/api/java/util/Arrays.html#asList\(T...\)) has been around since Java 5. So why was the need for the of method in **Java 9**?

There are a couple of differences between the **Arrays.asList** and the **of** method.

##### You can use the Of method to generate a Set or Map too

As demonstrated above, you can use the [Arrays.asList](https://docs.oracle.com/javase/7/docs/api/java/util/Arrays.html#asList\(T...\)) method only if you want to generate a **List**. The **of** method on the other hand is present on the **Set and Map** interfaces as well. So in addition to **List**, you can use it to create a **Set or Map too.**

### The of method does not affect the input array

Consider the following code snippet:

```
String array[] = {"One","Five","Ten","Twenty"}; 
List<String> inputList = Arrays.asList(array); 
array[2] = "Eight"; 
System.out.println("InputList is "+inputList);
```

So here we are setting the element at **position 2** in the array to a new value. This also modifies the **List**. So this code will print the following output:

```
InputList is [One, Five, Eight, Twenty]
```

However, this is not true about the [of](https://docs.oracle.com/javase/9/docs/api/java/util/List.html#of-E...-) method. So consider the following code snippet:

```
String array[] = {"One","Five","Ten","Twenty"}; 
List<String> inputList = List.of(array); 
array[2] = "Eight"; 
System.out.println("InputList is "+inputList);
```

So this will print the following output:

```
InputList is [One, Five, Ten, Twenty]
```

So this means that the List is not affected when the array is changed.

### List.of method does not allow null elements

Consider the following code snippet:

```
List<String> inputList = Arrays.asList("One","Five",null,"Twenty"); 
System.out.println("InputList is "+inputList);
```

So here, a null value is specified in the Array.asList method. When you run this code, it prints the following output:

```
InputList is [One, Five, null, Twenty]
```

The [List.of](https://docs.oracle.com/javase/9/docs/api/java/util/List.html#of-E...-) method, on the other hand, does not permit **null** values. So consider the following code snippet:

```
List<String> inputList = List.of("One","Five",null,"Twenty"); 
System.out.println("InputList is "+inputList);
```

When you run this code, a NullPointerException occurs as follows:

```
Exception in thread "main" java.lang.NullPointerException
at java.base/java.util.Objects.requireNonNull(Unknown Source)
at java.base/java.util.ImmutableCollections$ListN.<init>(Unknown Source)
at java.base/java.util.List.of(Unknown Source)
at leanjava.java9.CollectionsFactoryMethodsDemo.main(CollectionsFactoryMethodsDemo.java:11)
```

## Conclusion

So, in this article, we learned about Java 9 Collection Factory Methods. We understood how to use them and how they work.

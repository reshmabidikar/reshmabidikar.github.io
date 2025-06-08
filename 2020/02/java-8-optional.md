---
title: "Java 8 Optional Explained with code samples"
date: "2020-02-21"
categories: 
  - "java-8-features"
tags: 
  - "java8"
  - "java8optional"
---

[Java 8](https://reshmabidikar.github.io/blog.html#java-8-new-features) has introduced a bunch of new features. The Optional feature introduced by Java 8 helps in avoiding unexpected exceptions. In this article, I will be covering this feature in detail.

## Optional Introduction

An optional can be used to represent a value that can either be present or absent. Many times methods return a null value. If the code that invokes the method expects a non-null value, this can result in a **NullPointerException**. To avoid this, you need to add explicit null checks in your code. This can make the code difficult to read.

Consider the following code:

```
Person person = new Person();
if(person != null){ // Null Check
  String name = person.getName();
}


```

The above code needs to have an explicit null check for Person object. Only if the person object is not null, the code invokes the getName method.

Java 8 Optionals help to avoid explicit null checks like this. So you can re-write the above code using an Optional as follows:

```
Optional<Person> person = Optional.of(new Person()); 
person.ifPresent(person -> System.out.println(person.getName()));
```

So Optionals help in avoiding boilerplate code associated with null checks and make the code readable.

## Creating Optional

There are three static methods on the Optional class which can be used to create an Optional. These are as explained below.

### Optional.empty

The **Optional.empty** can be used to create an empty Optional, that is an Optional without a value. The following code demonstrates this:

```
Optional<String> opStr = Optional.empty();
```

So this code creates an empty String Optional.

### Optional.of

You can use the **Optional.of** method to create an Optional with a non-null value. The following code demonstrates this:

```
Optional<Integer> opNum = Optional.of(10);
```

So this code creates an Optional of type Integer with the value 10.

### Optional.ofNullable

You can use the Optional.ofNullable method to create an Optional that can hold both a null as well as a non-null value.

Consider the following code snippet:

```
Optional<Integer> opNum = Optional.ofNullable(10);
```

So this code creates an Optional of type **Integer** with the value **10**.

However, when you invoke the **ofNullable** method with a null, it returns as empty Optional. The following code demonstrates this:

```
Optional<Integer> opNum = Optional.ofNullable(null);
```

This code creates an empty optional.

## Methods in Optional

There are several methods in the Optional class that can be used to perform useful operations related to Optionals. Some of the methods in the Optional class are covered here.

### Optional.isPresent

The Optional.isPresent method determines if a value is present within an Optional. It returns a **boolean** value.

Consider the following code snippet:

```
Optional<Integer> opNum = Optional.ofNullable(10);
System.out.println("Value is present:"+opNum.isPresent());
```

Since the Optional **opNum** has the value **10**, this code will print **true**.

### Optional.ifPresent

The **Optional.ifPresent** method performs an action on the value in the Optional if present. If there is no value in the Optional it does not do anything. It accepts as parameter a **Consumer** instance which specifies the action to be performed on the Optional. The following code demonstrates this:

```
Optional<Integer> opNum= Optional.ofNullable(10);
opStr.ifPresent(num-> System.out.println(num+5));
```

Here, an Optional String **opNum** is created with the value **10**. A lambda expression is specified in the **ifPresent** method that simply adds 5 to the number and prints it.

If an empty Optional is used with the **ifPresent** method it does nothing as demonstrated below:

```
Optional<String> opStr = Optional.ofNullable(null);
opStr.ifPresent(str-> System.out.println(str));
```

Since **opStr** is an empty optional, this code does not do anything.

### Optional.get

The **Optional.get** method returns the value in the Optional. If there is no value within the Optional, it throws a **NoSuchElementException** exception.

Consider the following code snippet:

```
Optional<Integer> opNum = Optional.of(10);
int value = opNum.get();
System.out.println(value);
```

This code uses the **get** method to retrieve the value in the Optional **opNum**, which will return **10**.

If the **get** method is used with an empty Optional it throws an Exception. The following code demonstrates this:

```
Optional<Integer> opNum = Optional.ofNullable(null);
Integer num = opNum.get();
System.out.println(num);
```

This code prints the following output:

```
Exception in thread "main" java.util.NoSuchElementException: No value present
```

## Conclusion

So this article demonstrates the Java 8 optional feature. It covers how to create an Optional and some of the important methods in the Optional class.

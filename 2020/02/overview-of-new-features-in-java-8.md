---
title: "New Java 8 Features Overview with explanations"
date: "2020-02-25"
categories: 
  - "java8"
---

Though I've covered many Java 8 new features, I've never really given an overview of all the new features as a whole. So I will be covering that in this article.

## Functional Interfaces

**Functional interfaces** are simply interfaces with just one abstract method. Java 8 has introduced the `@FunctionalInterface`

annotation that designates an interface as a functional interface. Functional Interfaces and Lambda expressions go hand in hand. Java 8 has also added some built-in functional interfaces like Predicate, Consumer, Supplier, etc. You can read more about Functional interfaces [here](https://reshmabidikar.github.io/2019/03/java-8-functional-interface.html).

## Lambda expressions

The most talked-about feature in Java 8 is **lambda expressions**. Java is an object-oriented language, however, object-oriented code sometimes tends to be lengthy and verbose. Java 8's lambda expressions enable programmers to overcome this issue by writing code as **functions**. This gets rid of a lot of boilerplate code and helps to keep things clean. Lambda expressions make use of functional interfaces. So a lambda expression can be used to **implement the abstract method** in a functional interface. You can read more about lambda expressions [here](https://reshmabidikar.github.io/2019/05/java-8-lambda-expressions-explained.html).

## Stream API

The **Stream API** is useful in performing **bulk operations on collections**. For example, suppose you have a List of integers and you want to create a new List that has all the values incremented by 1. Before Java 8, you would need to write several lines of code for this, with the Stream API, you can achieve this using a single line of code. Stream operations also make use of lambda expressions. You can read more about the Stream API [here](https://reshmabidikar.github.io/2019/05/java-8-stream-api.html).

## Static and Default interface methods

Prior to Java 8, interfaces could only have public and abstract methods. Starting with Java 8, they can also have **static and default methods**. Static and default methods are methods with a **method body**. Default methods help to keep code **backwards compatible** when new methods are added to an interface. Static methods allow having **utility code** within interfaces. You can read more about the Static methods [here](https://reshmabidikar.github.io/2019/03/java-8-static-interface-methods.html) and Default methods [here](https://reshmabidikar.github.io/2019/03/java-8-default-method-in-interface-explained.html).

## DateTime API

Java 8 intro the **Datetime API** for date handling. Prior to Java 8, the Date and Calendar classes were available for date handling. However, these were not very user-friendly and powerful. So date and time manipulation were cumbersome using these classes. The DateTime API provides many methods that make date handling very easy. There are 3 main classes within the DateTime API, the **LocalDate**, **LocalTime** and **LocalDateTime** classes. You can read more about the LocalDate class [here](https://reshmabidikar.github.io/2019/06/java-8-localdate-class-explained.html) and LocalDateTime class [here](https://reshmabidikar.github.io/2020/01/java-8-localdatetime-class.html).

## Method references

Java 8 introduced a new operator called the **method reference operator**. It is represented by the**:: symbol**. Method references can be used to **refer to an existing method**. This gives you the ability to reuse existing code. They are a step forward from lambda expressions and help to make code even more concise. You can read more about method references [here](https://reshmabidikar.github.io/2019/05/java-8-method-reference-operator-explained.html).

## Optional

Java 8 has added a feature called **Optional**. Optional is simply a container that can hold a value. Many times methods return a null value. If the code that invokes the method expects a non-null value, this can result in a **NullPointerException**. To avoid this, you need to add explicit null checks in your code. Optionals help in **avoiding this boilerplate code** and help in writing clean code. You can read more about Java 8 optionals [here](https://reshmabidikar.github.io/2020/02/java-8-optional.html).

## Conclusion

So, in this article, we learned about the new Java 8 features like functional interfaces, lambda expressions, method references, Stream API and so forth.

---
title: "Java 8 DoubleToIntFunction Example"
date: "2020-05-15"
categories: 
  - "java-8-examples"
---

In this blog post, I will be explaining how the Java 8 functional interface [DoubleToIntFunction](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToIntFunction.html) works. To know more about functional interfaces, you can refer [this](https://reshmabidikar.github.io/2019/03/java-8-functional-interface.html) blog post.

# What is DoubleToIntFunction

The [DoubleToIntFunction](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToIntFunction.html) interface is a specialization of the [Function](https://reshmabidikar.github.io/2019/04/java-8-function-interface-example.html) interface. While the [Function](https://reshmabidikar.github.io/2019/04/java-8-function-interface-example.html) interface accepts any data type, the [DoubleToIntFunction](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToIntFunction.html) interface accepts as parameter a double value and returns a result of type int. To see an example of the [Function](https://reshmabidikar.github.io/2019/04/java-8-function-interface-example.html) interface, refer to [this](https://reshmabidikar.github.io/2019/04/java-8-function-interface-example.html) blog post.

The [DoubleToIntFunction](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToIntFunction.html) interface provides a method called `applyAsInt`. It accepts a single parameter of double data type. It returns a result of int data type. So it basically applies the logic in the `applyAsInt` method to the input parameter and returns the result.

# DoubleToIntFunction Interface Example Code

The following code snippet demonstrates the DoubleToIntFunction interface:

```java
DoubleToIntFunction integerRetriever = input -> Double.valueOf(input).intValue();
Double input = 5.6;
System.out.println("Integer Value "+integerRetriever.applyAsInt(input) );
```

Here, we have written a [DoubleToIntFunction](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToIntFunction.html) implementation that returns the Integer part of the input number. The [DoubleToIntFunction.applyAsInt](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToIntFunction.html#applyAsInt-double-) method is implemented using a lambda expression. So when you execute this code, it will print the following output:

```
Integer Value 5
```

# Conclusion

The `DoubleToIntFunction` is a specialization of the Function interface. It accepts as parameter a Double input and returns an Integer output.

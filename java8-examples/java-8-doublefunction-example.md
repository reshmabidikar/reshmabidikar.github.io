---
title: "Java 8 DoubleFunction Example"
date: "2019-09-08"
categories: 
  - "java-8-examples"
---

In this blog post, I will be explaining how the Java 8 functional interface [DoubleFunction](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleFunction.html) works. To know more about functional interfaces, you can refer [this](../java8-features/java-8-functional-interface.md) blog post.

The [DoubleFunction](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleFunction.html) interface provides a method called [apply](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleFunction.html#apply-double-). It accepts a single parameter of double data type. It returns a result of any data type. So it basically applies the logic in the apply method to the input parameter and returns the result. The [DoubleFunction](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleFunction.html) interface is a specialization of the [Function](java-8-function-interface-example.md) interface. While the [Function](java-8-function-interface-example.md) interface accepts any data type, the [DoubleFunction](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleFunction.html) interface accepts a long value. To see an example of the [Function](java-8-function-interface-example.md) interface, refer to [this](java-8-function-interface-example.mdl) blog post.

#### DoubleFunction Interface that returns an Integer

Consider the following code snippet:

```java
DoubleFunction<Integer> integerRetriever = input -> new Double(input).intValue();
Double input = 4.8;
System.out.println("Integer Value "+integerRetriever.apply(input) );
```

Here, we have written a [DoubleFunction](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleFunction.html) implementation that returns an Integer. So it accepts a Double input and returns the Integer part of the input number. The [DoubleFunction.apply](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleFunction.html#apply-double-) method is implemented using a lambda expression. So when you execute this code, it will print the following output:

```
Integer Value 4
```

You can get the source code for this example along with the code for other Java 8 examples at the GitHub repository [here](https://github.com/reshmabidikar/Java8Demo).

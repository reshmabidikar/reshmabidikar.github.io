---
title: "Java 8 DoubleToLongFunction Example"
date: "2020-06-12"
categories: 
  - "java-8-examples"
---

In this blog post, I will be explaining how the Java 8 functional interface [DoubleToLongFunction](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToLongFunction.html) works. To know more about functional interfaces, you can refer [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

\[table id=24 /\]

# What is DoubleToLongFunction

The [DoubleToLongFunction](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToLongFunction.html) interface is a specialization of the [Function](https://learnjava.co.in/java-8-function-interface-example/) interface. While the [Function](https://learnjava.co.in/java-8-function-interface-example/) interface accepts any data type, the [DoubleToLongFunction](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToLongFunction.html) interface accepts as parameter a double value and returns a result of type long. To see an example of the [Function](https://learnjava.co.in/java-8-function-interface-example/) interface, refer to [this](https://learnjava.co.in/java-8-function-interface-example/) blog post.

 

The [DoubleToLongFunction](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToLongFunction.html) interface provides a method called [applyAsLong](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToLongFunction.html#applyAsLong-double-). It accepts a single parameter of double data type. It returns a result of long data type. So it basically applies the logic in the [applyAsLong](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToLongFunction.html#applyAsLong-double-) method to the input parameter and returns the result.

# DoubleToLongFunction Example Code

The following code snippet demonstrates the [DoubleToLongFunction](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToLongFunction.html) interface:

```
DoubleToLongFunction longRetriever = input -> Double.valueOf(input).longValue();
Double input = 5.6;
System.out.println("Long Value "+longRetriever.applyAsLong(input) );
```

Here, we have written a [DoubleToLongFunction](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToLongFunction.html) implementation that returns the Integer part of the input number as a long. The [DoubleToLongFunction](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToLongFunction.html)[.applyAsLong](https://docs.oracle.com/javase/9/docs/api/java/util/function/DoubleToLongFunction.html#applyAsLong-double-) method is implemented using a lambda expression. So when you execute this code, it will print the following output:

```
Long Value 5


```

# Conclusion

The DoubleToLongFunction is a specialization of the Function interface. It accepts as parameter a Double input and returns a Long output.

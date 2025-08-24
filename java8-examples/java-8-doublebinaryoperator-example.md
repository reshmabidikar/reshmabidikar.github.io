---
title: "Java 8 DoubleBinaryOperator example"
date: "2020-04-24"
categories: 
  - "java-8-examples"
---

In this blog post, I will be explaining how the Java 8 [DoubleBinaryOperator](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleBinaryOperator.html) functional interface works. To know more about functional interfaces, you can refer [this](../java8-features/java-8-functional-interface.md) blog post.

# What is DoubleBinaryOperator

The [DoubleBinaryOperator](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleBinaryOperator.html) is a specialization of the [BinaryOperator](java-8-binaryoperator-example.md) interface. To see an example of the [BinaryOperator](java-8-binaryoperator-example.md) interface, refer to [this](java-8-binaryoperator-example.md) blog post.

While the [BinaryOperator](java-8-binaryoperator-example.md) interface accepts any data type, the [DoubleBinaryOperator](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleBinaryOperator.html) interface accepts arguments of double data type.

The [DoubleBinaryOperator](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleBinaryOperator.html) interface provides a method [applyAsDouble](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleBinaryOperator.html#applyAsDouble-double-double-). It accepts two arguments of double data type. It returns a result double data type. So it basically applies the logic in the applyAsDouble method to the input parameters and returns a double result.

# Code sample for DoubleBinaryOperator

Consider the following code snippet:

```java
DoubleBinaryOperator multiplier = (a, b) -> a * b;
double input1 = 6;
double input2 = 5;
System.out.println("Result of multiplying " + input1 + " and " + input2 + " is " + multiplier.applyAsDouble(input1, input2));
```

Here, we have written a [DoubleBinaryOperator](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleBinaryOperator.html) implementation that accepts two Double inputs, multiplies them and returns the result. The [DoubleBinaryOperator,applyAsDouble](https://docs.oracle.com/javase/8/docs/api/java/util/function/DoubleBinaryOperator.html#applyAsDouble-double-double-) method is implemented using a lambda expression. So when you execute this code, it will print the following output:

```
Result of multiplying 6.0 and 5.0 is 30.0
```
# Conclusion

So in this article, we saw how the Java 8 DoubleBinaryOperator functional interface works. We used a lambda expression to implement it.

You can get the source code for this example along with the code for other Java 8 examples at the GitHub repository [here](https://github.com/reshmabidikar/Java8Demo).

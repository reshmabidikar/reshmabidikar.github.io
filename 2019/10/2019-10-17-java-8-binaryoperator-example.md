---
title: "Java 8 BinaryOperator Example"
date: "2019-10-17"
categories: 
  - "java-8-examples"
tags: 
  - "java-8"
  - "java-8-binaryoperator"
  - "java-8-functional-interfaces"
---

In this blog post, I will be explaining how the Java 8 BinaryOperator functional interface works. To know more about functional interfaces, you can refer to [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

\[table id=24 /\]

# What is BinaryOperator

The [BinaryOperator](https://docs.oracle.com/javase/8/docs/api/java/util/function/BinaryOperator.html) is a specialization of the [BiFunction](https://learnjava.co.in/java-8-bifunction-example/) interface that accepts 2 arguments. However, unlike the [BiFunction](https://learnjava.co.in/java-8-bifunction-example/) it accepts 2 arguments of the same data type and returns a result of the same data type. The [BinaryOperator](https://docs.oracle.com/javase/8/docs/api/java/util/function/BinaryOperator.html) internally uses the [BiFunction.apply](https://docs.oracle.com/javase/8/docs/api/java/util/function/BiFunction.html#apply-T-U-) method.

#### BinaryOperator Interface Example with Integer data type

Consider the following code snippet:

```
BinaryOperator<Integer> additionCalculator = (a, b) -> a +b;
int input1 = 6;
int input2 = 5;
System.out.println("Result of adding " + input1 + " and " + input2 + " is " + additionCalculator.apply(input1, input2));
```

 

Here, we have written a [BinaryOperator](https://docs.oracle.com/javase/8/docs/api/java/util/function/BinaryOperator.html) implementation that operates on Integer data type. It accepts two integer values, adds them and returns the result. [The BiFunction.apply](https://docs.oracle.com/javase/8/docs/api/java/util/function/BiFunction.html#apply-T-U-) method is implemented using a lambda expression.  So when you execute this code, it will print the following output:

```
Result of adding 6 and 5 is 11
```

#### BinaryOperator Interface Example with String data type

Consider the following code snippet:

 

```
BinaryOperator<String> strOperator = (str1,str2) -> str1.concat(" ").concat(str2);
String str1 = "Hello";
String str2 = "World";
System.out.println("Concatenated String:" + strOperator.apply(str1, str2));
```

 

This code demonstrates a BinaryOperator instance that operates on String values. It accepts 2 String values, concatenates them and returns the result. So when you execute this code, it prints the following output:

```
Concatenated String:Hello World
```

You can get the source code for this example along with other code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

# Conclusion

So in this article, we explored the Java 8 BinaryOperator interface.  We also saw a BinaryOperator example with Integer data type and String data type.

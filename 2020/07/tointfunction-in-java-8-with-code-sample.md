---
title: "ToIntFunction in Java 8 With Code Sample"
date: "2020-07-09"
categories: 
  - "java-8-examples"
  - "java8"
---

Functional interfaces and lambda expressions are one of the major features in Java 8. Java provides a lot of in-built functional interfaces in the java.util.function package. One of these is the **ToIntFunction.** In this blog post, I will be explaining how thisfunctional interface works. To know more about functional interfaces, you can refer to [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

## What is ToIntFunction

**ToIntFunction** is an in-built functional interface in the **java.util.Function** package. It accepts an argument of any data type but returns a result of type **int**.

It is a primitive specialization of the [Function](https://learnjava.co.in/java-8-function-interface-example/) interface that always returns a result of **int** type. So **IntFunction<T>** is similar to [**Function<T,Integer>**](https://learnjava.co.in/java-8-function-interface-example/)

It has an **applyAsInt**method. It then applies the logic in this method on the argument passed in to produce the **int** result.

## ToIntFunction Sample Code

The following code snippet demonstrates this interface:

```
ToIntFunction<String> strLengthProducer = str -> str.length();

int len = strLengthProducer.applyAsInt("Hello!");

System.out.println("Length:"+len);
```

Here, `strLengthProducer` accepts a String input. The code uses a lambda expression that simply returns the length of the input String.

This code prints the following output:

```
Length:6
```

Note that you need to use a lambda expression that returns an int value while implementing this interface. Otherwise, the code will cause a compilation error.

## Difference between IntFunction and ToIntFunction

There is another functional interface [IntFunction](https://learnjava.co.in/intfunction-in-java-8-with-code-sample/) in the **java.util.Function** package. This interface accepts an **int** argument and returns a result of any data type. **ToIntFunction** on the other hand, accepts an argument of any data type and returns an **int** result. So the difference between them is that [IntFunction](https://learnjava.co.in/intfunction-in-java-8-with-code-sample/) accepts an argument of **int** data type while **ToIntFunction** produces an **int** result.

## Conclusion

So in this article, we took a look at the **ToIntFunction** interface. This interface is a specialization of the [Function](https://learnjava.co.in/java-8-function-interface-example/) interface. It accepts an argument of any data type and returns a result of **int** data type.

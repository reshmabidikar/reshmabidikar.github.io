---
title: "IntBinaryOperator"
date: "2021-04-01"
categories: 
  - "java-8-examples"
coverImage: "IntBinaryOperator-1-scaled.jpg"
---

In this blog post, I will be explaining how the Java 8 functional interface **IntBinaryOperator** works. To know more about functional interfaces, you can refer to [this](https://reshmabidikar.github.io/2019/03/java-8-functional-interface.html) blog post.

## What is IntBinaryOperator

**IntBinaryOperator** is an in-built functional interface in the **java.util.Function** package. It accepts two **int** arguments, operates on it and produces a result of type **int**. It is a specialization of the [BinaryOperator](https://reshmabidikar.github.io/2019/03/java-8-functional-interface.html) interface. It has a **applyAsInt** method. It applies the logic in this method on the **int** arguments passed in and produces an **int** result.

## IntBinaryOperator Code Sample

The following code demonstrates this interface:

```java
IntBinaryOperator intBinaryOp = (num1,num2) -> num1+num2;
int input1=14,input2=12;
int result = intBinaryOp.applyAsInt(input1, input2);
System.out.println("result:"+result);
```

- Line 1 declares a **IntBinaryOperator** instance **intBinaryOp** and implements it via a lambda expression that adds the input arguments and returns the result.
- Line 3 invokes the **applyAsInt** method on some input values.

This code prints the following output:

```
result:26
```

## Why IntBinaryOperator

The **IntBinaryOperator** interface is a non-generic primitive specialization of the [BinaryOperator](https://reshmabidikar.github.io/2019/10/java-8-binaryoperator-example.html) interface. The other functional interfaces like [Supplier](https://learnjava.co.in/java-8-supplier-interface-example/), [Predicate](https://reshmabidikar.github.io/2018/10/java-8-predicate-example.html),[Consumer](https://reshmabidikar.github.io/2019/04/java-8-consumer-interface-example.md) also have primitive specializations like [IntSupplier](https://reshmabidikar.github.io/2018/12/java-8-intsupplier-interface-example.html), [LongPredicate](https://reshmabidikar.github.io/2018/12/java-8-longpredicate-interface-example.html), [IntConsumer](https://reshmabidikar.github.io/2019/07/java-8-intconsumer-interface.html), etc. The primitive specializations help to improve performance when the input parameters are of primitive types. For example, in the above example, we can also use a [BinaryOperator](https://reshmabidikar.github.io/2019/10/java-8-binaryoperator-example.html) interface as follows:

```
BinaryOperator<Integer> binaryOp = (num1,num2) -> num1+num2;
int input1=14,input2=12;
int result = binaryOp.apply(input1, input2);
System.out.println("result:"+result);
```

- Line 1 declares a [BinaryOperator](https://reshmabidikar.github.io/2019/10/java-8-binaryoperator-example.html) instance **binaryOp** and implements it via the same lambda expression as used above.
- Line 3 then invokes the **apply** method on the values **14, 12**. Since the input value is a primitive type, Java uses **autoboxing** to convert the primitive **int** type to the wrapper type that is **Integer** before applying the lambda expression. This reduces the performance slightly. However, in the case of **IntBinaryOperator**, no such conversion is required since the **applyAsInt** method accept arguments of type **int** already. Thus the primitive specialization offers a slight performance advantage as it does away with the need of autoboxing.

## Conclusion

So in this article, we took a look at the **IntBinaryOperator** interface. This interface is a specialization of the [BinaryOperator](https://reshmabidikar.github.io/2019/10/java-8-binaryoperator-example.html) interface that accepts **int** parameters and returns an **int** result.

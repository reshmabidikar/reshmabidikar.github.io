---
title: "DoubleUnaryOperator in Java 8 With Code Sample"
date: "2021-02-18"
categories: 
  - "java-8-examples"
  - "java8"
coverImage: "doubleunaryoperator-scaled.jpg"
---

In this blog post, I will be explaining how the Java 8 functional interface **DoubleUnaryOperator** works. To know more about functional interfaces, you can refer to [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

\[table id=24 /\]

## What is DoubleUnaryOperator

**DoubleUnaryOperator** is an in-built functional interface in the **java.util.Function** package. It accepts an argument of **double** data type, operates on it and produces a result of type **double**. It is a specialization of the [UnaryOperator](https://learnjava.co.in/java-8-unaryoperator-example/) interface. It has an [applyAsDouble](https://docs.oracle.com/en/java/javase/15/docs/api/java.base/java/util/function/DoubleUnaryOperator.html#applyAsDouble\(double\)) method. It applies the logic in this method on the **double** argument passed in and produces a **double** result.

## DoubleUnaryOperator Code Sample

The following code demonstrates this interface:

```
DoubleUnaryOperator doubleUnaryOp = num -> Math.sqrt(num);
double input = 9;
double result = doubleUnaryOp.applyAsDouble(input);
System.out.println("result:"+result);
```

- Line 1 declares a **DoubleUnaryOperator** instance **doubleUnaryOp** and implements it via a lambda expression that returns the square root of the input number
- Line 3 invokes the **applyAsDouble** method on an input value.

This code prints the following output:

```
result:3.0
```

## Why DoubleUnaryOperator

The **DoubleUnaryOperator** interface is a non-generic primitive specialization of the [UnaryOperator](https://learnjava.co.in/java-8-unaryoperator-example/) interface. The other functional interfaces like [Supplier](https://learnjava.co.in/java-8-supplier-interface-example/), [Predicate](https://learnjava.co.in/java-8-predicate-example/),[Consumer](https://learnjava.co.in/java-8-consumer-interface-example/) also have primitive specializations like [IntSupplier](https://learnjava.co.in/java-8-intsupplier-interface-example/), [LongPredicate](https://learnjava.co.in/java-8-long-predicate-interface-example/), [IntConsumer](https://learnjava.co.in/java-8-intconsumer-interface/), etc. The primitive specializations help to improve performance when the input parameters are of primitive types. For example, in the above example, we can also use a [UnaryOperator](https://learnjava.co.in/java-8-unaryoperator-example/) interface as follows:

```
UnaryOperator<Double> unaryOp = num -> Math.sqrt(num);
double input = 9;
double result = unaryOp.applyAsDouble(input);
System.out.println("result:"+result);
```

- Line 1 declares a [UnaryOperator](https://learnjava.co.in/java-8-unaryoperator-example/) instance **unaryOp** and implements it via the same lambda expression as used above.
- Line 3 then invokes the [applyAsDouble](https://learnjava.co.in/java-8-unaryoperator-example/) method on the value **9**. Since the input value is a primitive type, Java uses **autoboxing** to convert the primitive **double** type to the wrapper type that is **Double** before applying the lambda expression. This reduces the performance slightly. However, in the case of **DoubleUnaryOperator**, no such conversion is required since the **applyAsDouble** method accepts an argument of type **double** already. Thus the primitive specialization offers a slight performance advantage as it does away with the need of autoboxing.

## Conclusion

So in this article, we took a look at the **DoubleUnaryOperator** interface. This interface is a specialization of the [UnaryOperator](https://learnjava.co.in/java-8-unaryoperator-example/) interface that accepts a **double** parameter and returns a **double** result.

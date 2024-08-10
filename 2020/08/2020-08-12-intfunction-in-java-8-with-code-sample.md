---
title: "IntFunction in Java 8 With Code Sample"
date: "2020-08-12"
categories: 
  - "java-8-examples"
  - "java8"
---

In this blog post, I will be explaining how the Java 8 functional interface **IntFunction** works. To know more about functional interfaces, you can refer to [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

\[table id=24 /\]

## What is IntFunction

**IntFunction** is an in-built functional interface in the java.util.Function package. It accepts an argument of **int** data type, operates on it and produces a result of any data type. It is a specialization of the [Function](https://learnjava.co.in/java-8-function-interface-example/) interface. It has an [apply](https://docs.oracle.com/javase/9/docs/api/java/util/function/IntFunction.html#apply-int-) method. It applies the logic in this method on the **int** argument passed in and produces a result of the specified data type.

## IntFunction Code Sample

The following code demonstrates this interface:

```
IntFunction<Double> doubleRetriever = input -> Double.valueOf(input);
System.out.println("Double value " + doubleRetriever.apply(5));
```

This code implements this interface via a lambda expression that returns a result of **Double** type. It simply returns a Double value corresponding to the **int** input passed in.

This code prints the following output:

```
Double value 5.0
```

## Why IntFunction

**IntFunction** is a primitive specialization of the [Function](https://learnjava.co.in/java-8-function-interface-example/) interface. The other functional interfaces like [Supplier](https://learnjava.co.in/java-8-supplier-interface-example/), [Predicate](https://learnjava.co.in/java-8-predicate-example/),[Consumer](https://learnjava.co.in/java-8-consumer-interface-example/) also have primitive specializations like [IntSupplier](https://learnjava.co.in/java-8-intsupplier-interface-example/), [LongPredicate](https://learnjava.co.in/java-8-long-predicate-interface-example/), [IntConsumer](https://learnjava.co.in/java-8-intconsumer-interface/), etc. The primitive specializations help to improve performance when the input parameters are of primitive types. For example, in the above example, we can also use a [Function](https://learnjava.co.in/java-8-function-interface-example/) interface as follows:

```
Function<Integer,Double> doubleRetriever2 = input -> Double.valueOf(input);
System.out.println("Double value " + doubleRetriever2.apply(5));
```

This code uses a [Function](https://learnjava.co.in/java-8-function-interface-example/) interface. It then invokes the [apply](https://learnjava.co.in/java-8-function-interface-example/) method on the value **5**. Since the input value is a primitive type, Java uses **autoboxing** to convert the primitive int type to an **Integer** before applying the lambda expression. This reduces the performance slightly. However, in the case of **IntFunction**, no such conversion is required since the I**ntFunction.apply** method accepts an argument of type **int** already. Thus the primitive specialization offers a slight performance advantage as it does away with the need of autoboxing.

## Conclusion

So in this article, we took a look at the **IntFunction** interface. This interface is a specialization of the [Function](https://learnjava.co.in/java-8-function-interface-example/) interface that accepts an **int** parameter and returns a result on any data type.

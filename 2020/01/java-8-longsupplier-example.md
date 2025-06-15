---
title: "Java 8 LongSupplier explained with code samples"
date: "2020-01-07"
categories: 
  - "java-8-examples"
tags: 
  - "java8"
  - "java8functionalinterfaces"
  - "java8longsupplier"
---

In this blog post, I will be explaining how the Java 8 functional interface [LongSupplier](https://docs.oracle.com/javase/8/docs/api/java/util/function/LongSupplier.html) works. To know more about functional interfaces, you can refer [this](https://reshmabidikar.github.io/2019/03/java-8-functional-interface.html) blog post.

The [LongSupplier](https://docs.oracle.com/javase/8/docs/api/java/util/function/LongSupplier.html) interface provides a method called [getAsLong](https://docs.oracle.com/javase/8/docs/api/java/util/function/LongSupplier.html#getAsLong--). This method does not accept any arguments. It returns a Long data type. The [LongSupplier](https://docs.oracle.com/javase/8/docs/api/java/util/function/LongSupplier.html) interface is a specialization of the `Supplier` interface that returns a Long. To see an example of the Supplier interface, refer to [this](https://reshmabidikar.github.io/2018/08/java-8-supplier-interface-example.html) blog post.

## LongSupplier example

Consider the following code snippet:

```java
LongSupplier getRandom = () ->  new Random().nextLong();
System.out.println("Random number 1 = "+getRandom.getAsLong());
System.out.println("Random number 2 = "+getRandom.getAsLong());
```
Here, we have implemented the LongSupplier.getAsLong method using a lambda expression. This getAsLong method simple returns a random integer less than 100. So when this code is executed, it will print output similar to the following:

```
Random number 1 = -1689842518791524672
Random number 2 = 8225865813273814162
```

You can get the source code for this example along with other code for other Java 8 examples at the Github repository [here](https://github.com/reshmabidikar/Java8Demo).

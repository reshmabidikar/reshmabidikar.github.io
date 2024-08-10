---
title: "Java 8 BooleanSupplier Example"
date: "2018-11-11"
categories: 
  - "java-8-examples"
tags: 
  - "functional-interface"
  - "interfaces"
  - "java8"
---

In this blog post, I will be explaining how the Java 8 functional interface BooleanSupplier works. To know more about functional interfaces, you can refer [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

\[table id=24 /\]

The  BooleanSupplier interface provides a method called getAsBoolean. This method does not accept any arguments. It returns a boolean value. The BooleanSupplier interface is a specialization of the Supplier interface that returns a boolean. To see an example of the [Supplier](https://docs.oracle.com/javase/8/docs/api/java/util/function/Supplier.html) interface, refer to [this](https://learnjava.co.in/java-8-supplier-interface-example/) blog post.

#### BooleanSupplier example

Consider the following code snippet:

\[java\]

public class BooleanSupplierExample {

public static void main(String\[\] args) { BooleanSupplier booleanSupplier = () -> true; System.out.println("Boolean flag = "+booleanSupplier.getAsBoolean()); } }

\[/java\]

Here, we have implemented the getAsBoolean method using a lambda expression. This simply returns the value true. So when this code is executed, it will print the following output:

```
Boolean flag = true
```

You can get the source code for this example along with other code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

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

In this blog post, I will be explaining how the Java 8 functional interface BooleanSupplier works. To know more about functional interfaces, you can refer [this](https://reshmabidikar.github.io/2019/03/java-8-functional-interface.html) blog post.

The BooleanSupplier interface provides a method called `getAsBoolean`. This method does not accept any arguments. It returns a boolean value. The BooleanSupplier interface is a specialization of the `Supplier` interface that returns a boolean. To see an example of the [Supplier](https://docs.oracle.com/javase/8/docs/api/java/util/function/Supplier.html)interface, refer to [this](https://reshmabidikar.github.io/2018/08/java-8-supplier-interface-example.html) blog post.

#### BooleanSupplier example

Consider the following code snippet:

````java
public class BooleanSupplierExample {

    public static void main(String[] args) { 
        BooleanSupplier booleanSupplier = () -> true; 
        System.out.println("Boolean flag = "+booleanSupplier.getAsBoolean()); 
    } 
}
````

Here, we have implemented the `getAsBoolean` method using a lambda expression. This simply returns the value true. So when this code is executed, it will print the following output:

```
Boolean flag = true
```

You can get the source code for this example along with other code for other Java 8 examples at the GitHub repository[here](https://github.com/reshmabidikar/Java8Demo).

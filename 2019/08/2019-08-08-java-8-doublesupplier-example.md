---
title: "Java 8 DoubleSupplier Example"
date: "2019-08-08"
categories: 
  - "java-8-examples"
  - "java8"
tags: 
  - "java8"
  - "java8doublesupplier"
  - "java8functionalinterfaces"
---

In this blog post, I will be explaining how the DoubleSupplier Java 8 functional interface works. To know more about functional interfaces, you can refer [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

\[table id=24 /\]

The  DoubleSupplier interface provides a method called getAsDouble This method does not accept any arguments. It returns a Double data type. The DoubleSupplier interface is a specialization of the Supplier interface that returns a double value. To see an example of the Supplier interface, refer to [this](https://learnjava.co.in/java-8-supplier-interface-example/) blog post.

#### DoubleSupplier example

Consider the following code snippet:

```
public class DoubleSupplierDemo {

  public static void main(String[] args) {
    DoubleSupplier getRandom = () ->  new Random().nextDouble();
    System.out.println("Random number 1 = "+getRandom.getAsDouble());
    System.out.println("Random number 2 = "+getRandom.getAsDouble());

  }

}
```

 

Here, we have implemented the DoubleSupplier.getAsDouble method using a lambda expression.  This getAsDouble method simple returns a random double. So when you execute this code, it will print some random double numbers similar to the following:

```
Random number 1 = 0.06545562920379944
Random number 2 = 0.4493283376525269
```

You can get the source code for this example along with other code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

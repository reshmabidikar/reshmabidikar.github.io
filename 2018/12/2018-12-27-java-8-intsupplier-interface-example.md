---
title: "Java 8 IntSupplier Interface Example"
date: "2018-12-27"
categories: 
  - "java-8-examples"
---

In this blog post, I will be explaining how the Java 8 functional interface IntSupplier works. To know more about functional interfaces, you can refer [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

\[table id=24 /\]

The  IntSupplier interface provides a method called getAsInt This method does not accept any arguments. It returns an Int data type. The IntSupplier interface is a specialization of the Supplier interface that returns an int. To see an example of the Supplier interface, refer to [this](https://learnjava.co.in/java-8-supplier-interface-example/) blog post.

#### IntSupplier example

Consider the following code snippet:

\[java\]</pre> public class IntSupplierDemo {30

public static void main(String\[\] args) { IntSupplier getRandom = () -> new Random().nextInt(100); System.out.println("Random number 1 = "+getRandom.getAsInt()); System.out.println("Random number 2 = "+getRandom.getAsInt()); }

} <pre> \[/java\]

Here, we have implemented the IntSupplier.getAsInt method using a lambda expression.  This getAsInt method simple returns a random integer less than 100. So when this code is executed, it will print the following output:

```
Random number 1 = 98 
Random number 2 = 89
```

You can get the source code for this example along with other code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

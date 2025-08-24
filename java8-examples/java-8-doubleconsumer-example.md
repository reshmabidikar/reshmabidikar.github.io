---
title: "Java 8 DoubleConsumer example"
date: "2019-06-26"
categories: 
  - "java-8-examples"
tags: 
  - "functional-interface"
  - "interfaces"
  - "java8"
---

In this blog post, I will be explaining how the Java 8 functional interface DoubleConsumer works. To know more about functional interfaces, you can refer [this](../java8-features/java-8-functional-interface.md) blog post.

The `DoubleConsumer` interface provides a method called `accept`. It accepts a single parameter of double data type. It does not return anything, it returns a void. So it operates via side effects i.e. it modifies the parameter passed in. The `DoubleConsumer` interface is a specialization of the [Consumer](java-8-consumer-interface-example.md) interface. While the [Consumer](java-8-consumer-interface-example.md)  interface accepts any data type, the DoubleConsumer interface accepts a Double value. 

#### DoubleConsumer Example

Consider the following code snippet:

```java
public class DoubleConsumerDemo {

  public static void main(String args[]) {
    DoubleConsumer squareGenerator = (num) -> System.out.println(num*num);
    double input = 5.0;
    squareGenerator.accept(input);
  }

}

```

Here, the `DoubleConsumer.accept` method accepts a double value. It squares it (i.e. multiplies it by itself) and prints the result. So when the above code is executed, it will print the following output:

```
25.0
```

You can get the source code for this example along with other code for other Java 8 examples at the GitHub repository [here](https://github.com/reshmabidikar/Java8Demo).

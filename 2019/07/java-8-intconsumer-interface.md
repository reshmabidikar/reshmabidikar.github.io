---
title: "Java 8 IntConsumer Interface"
date: "2019-07-02"
categories: 
  - "java-8-examples"
tags: 
  - "functional-interface"
  - "interfaces"
  - "java8"
---

In this blog post, I will be explaining how the Java 8 functional interface IntConsumer works. To know more about functional interfaces, you can refer [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

The IntConsumer interface provides a method called accept. It accepts a single parameter of int data type. It does not return anything, it returns a void. So it operates via side effects i.e. it modifies the parameter passed in. The IntConsumer interface is a specialization of the Consumer interface. While the Consumer interface accepts any data type, the IntConsumer interface accepts an Integer value. To see an example of the Consumer interface, refer to [this](https://learnjava.co.in/java-8-consumer-interface-example/) blog post.

#### IntConsumer Example

Consider the following code snippet:

```
public class IntConsumerDemo {

  public static void main(String args[]) {
    IntConsumer incrementby5 = (num) -> System.out.println("Input:"+num+", Incremented Value:"+(num+5));
    incrementby5.accept(12);
    incrementby5.accept(23);
  }

}

```

Here, the [IntConsumer.accept](https://docs.oracle.com/javase/8/docs/api/java/util/function/IntConsumer.html#accept-int-) method accepts an integer value. It increments the input by 5 and prints the result. So when the above code is executed, it will print the following output:

```
Input:12, Incremented Value:17
Input:23, Incremented Value:28
```

You can get the source code for this example along with other code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

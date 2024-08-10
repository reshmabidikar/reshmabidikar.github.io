---
title: "Java 8 LongConsumer example"
date: "2019-07-18"
categories: 
  - "java-8-examples"
tags: 
  - "functional-interface"
  - "interfaces"
  - "java8"
---

In this blog post, I will be explaining how the Java 8 functional interface [LongConsumer](https://docs.oracle.com/javase/8/docs/api/java/util/function/LongConsumer.html) works. To know more about functional interfaces, you can refer [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

\[table id=24 /\]

The [LongConsumer](https://docs.oracle.com/javase/8/docs/api/java/util/function/LongConsumer.html) interface provides a method called [accept](https://docs.oracle.com/javase/8/docs/api/java/util/function/LongConsumer.html#accept-long-). It accepts a single parameter of long data type. It does not return anything, it returns a void. So it operates via side effects i.e. it modifies the parameter passed in.The [LongConsumer](https://docs.oracle.com/javase/8/docs/api/java/util/function/LongConsumer.html) interface is a specialization of the [Consumer](https://docs.oracle.com/javase/8/docs/api/java/util/function/Consumer.html) interface. While the [Consumer](https://docs.oracle.com/javase/8/docs/api/java/util/function/Consumer.html) interface accepts any data type, the [LongConsumer](https://docs.oracle.com/javase/8/docs/api/java/util/function/LongConsumer.html) interface accepts a long value. To see an example of the [Consumer](https://docs.oracle.com/javase/8/docs/api/java/util/function/Consumer.html) interface, refer to [this](https://learnjava.co.in/java-8-consumer-interface-example/) blog post.

#### LongConsumer Example

Consider the following code snippet:

```
public class LongConsumerDemo {

  public static void main(String args[]) {
    LongConsumer decrementBy5 = (num) -> System.out.println("Input:"+num+", Incremented Value:"+(num-5));
    decrementBy5.accept(12);
    decrementBy5.accept(23);
  }

}

```

 

Here, the [LongConsumer.accept](https://docs.oracle.com/javase/8/docs/api/java/util/function/LongConsumer.html#accept-long-) method accepts a long value. It decrements the value by 5 and prints the result.  So when the above code is executed, it will print the following output:

```
Input:12, Incremented Value:7
Input:23, Incremented Value:18
```

You can get the source code for this example along with other code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

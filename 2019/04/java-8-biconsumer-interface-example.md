---
title: "Java 8 BiConsumer Interface Example"
date: "2019-04-20"
categories: 
  - "java-8-examples"
---

In this blog post, I will be explaining how the Java 8 functional interface BiConsumer works. To know more about functional interfaces, you can refer [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

The BiConsumer interface provides a method called accept. It accepts 2 parameters of any data type. It does not return anything, it returns a void. So it operates via side effects i.e. it modifies the parameters passed in. The BiConsumer interface is a specialization of the Consumer interface. To see an example of the Consumer interface, refer to [this](https://learnjava.co.in/java-8-consumer-interface-example/) blog post.

#### BiConsumer example with Two Integer parameter

Consider the following code snippet:

````
public class BiConsumerDemo {

  public static void main(String args[]){ 
    BiConsumer<Integer,Integer> displaySum = (input1,input2) -> System.out.println("Sum of inputs is "+(input1+input2)); 
    displaySum.accept(4,8); 
  }
} 
````

Here, we have implemented the BiConsumer.accept method using a lambda expression. This accept method accepts 2 Integer arguments. It adds them iand prints the result to the console. So when this code is executed, it will print the following output:

```
Sum of inputs is 12
```

#### Consumer example with Integer and String as parameter

Consider the following code snippet:

````

public class BiConsumerDemo {

  public static void main(String args[]){ 
    BiConsumer<String,Integer> printConcatenatedValue = (input1,input2) -> System.out.println("Result of concatenating the inputs is "+(input1+input2)); printConcatenatedValue.accept("Hello World",5); 
  }
}
````

Again, we have implemented the BiConsumer.accept method using a lambda expression. This accept method accepts an Integer and a String value. It concatenates both the inputs using the + operator and prints the results. So when you execute this code, it will print the following output:

```
Result of concatenating the inputs is Hello World5
```

You can get the source code for this example along with the code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

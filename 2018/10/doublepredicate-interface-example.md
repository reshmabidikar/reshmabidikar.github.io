---
title: "DoublePredicate Interface in Java 8 with code examples"
date: "2018-10-12"
categories: 
  - "java-8-examples"
---

In this blog post, I will be explaining how the Java 8 functional interface DoublePredicate works. To know more about functional interfaces, you can refer [this](https://reshmabidikar.github.io/2019/03/java-8-functional-interface.html) blog post.

The `DoublePredicate` interface provides a method called `test`. This method accepts a parameter of Double data type and returns a boolean. The `DoublePredicate` interface is a specialization of the `Predicate` interface. While the `Predicate` interface accepts any data type, the `DoublePredicate` interface accepts a Double value. To see an example of the `Predicate` interface, refer to [this](https://reshmabidikar.github.io/2018/10/java-8-predicate-example.html) blog post.

#### DoublePredicate Example

Consider the following code snippet:

```java
public class DoublePredicateDemo {

public static void main(String args[]) { 
    DoublePredicate greaterThan1 = (input) -> input > 1; 
    System.out.println("0.75 is greater than 1 = "+greaterThan1.test(0.75)); 
    System.out.println("1.12 is greater than 1 = "+greaterThan1.test(1.25)); 
}

}

```

Here, the `DoublePredicate.Test` method checks if the input number is greater than 1. So when the above code is executed, it will print the following output:

```
0.75 is greater than 0 = false 
1.12 is greater than 0 = true
```

You can get the source code for this example along with other code for other Java 8 examples at the Github repository [here](https://github.com/reshmabidikar/Java8Demo).

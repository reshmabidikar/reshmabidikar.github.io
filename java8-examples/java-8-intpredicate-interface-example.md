---
title: "IntPredicate Interface in Java 8 with examples"
date: "2018-11-27"
categories: 
  - "java-8-examples"
---

In this blog post, I will be explaining how the Java 8 functional interface `IntPredicate` works. To know more about functional interfaces, you can refer [this](../java8-features/java-8-functional-interface.md) blog post.

The `IntPredicate` interface provides a method called `test`. This method accepts a parameter of Integer data type and returns a boolean. The `IntPredicate` interface is a specialization of the [Predicate](java-8-predicate-example.md) interface. While the [Predicate](java-8-predicate-example.md) interface accepts any data type, the `IntPredicate` interface accepts an Integer value. 

#### IntPredicate Example

Consider the following code snippet:

````java
public class IntPredicateDemo { 
    public static void main(String args[]) { 
        IntPredicate greaterThan10 = (input) -> input > 10; 
        System.out.println("4 is greater than 10 = "+greaterThan10.test(4)); 
        System.out.println("15 is greater than 10 = "+greaterThan10.test(15)); 
     } 
  }
````

Here, the `IntPredicate.test` method checks if the input number is greater than 10. So when the above code is executed, it will print the following output:

```
4 is greater than 10 = false 
15 is greater than 10 = true
```

You can get the source code for this example along with other code for other Java 8 examples at the Github repository[here](https://github.com/reshmabidikar/Java8Demo).

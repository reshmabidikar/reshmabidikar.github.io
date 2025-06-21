---
title: "LongPredicate Interface in Java 8 with code samples"
date: "2018-12-06"
categories: 
  - "java-8-examples"
---

In this blog post, I will be explaining how the Java 8 functional interface LongPredicate works. To know more about functional interfaces, you can refer [this](https://reshmabidikar.github.io/2019/03/java-8-functional-interface.html) blog post.

The LongPredicate interface provides a method called test. This method accepts a parameter of Long data type and returns a boolean. The LongPredicate interface is a specialization of the Predicate interface. While the [Predicate](https://docs.oracle.com/javase/8/docs/api/java/util/function/Predicate.html) interface accepts any data type, the LongPredicate interface accepts an Long value. To see an example of the Predicate interface, refer to[this](https://learnjava.co.in/java-8-predicate-example/)blog post.

#### LongPredicate Example

Consider the following code snippet:

````java
public class LongPredicateDemo {

    public static void main(String[] args) { 
        LongPredicate greaterThan10 = (input) -> input > 10; 
        System.out.println("4 is greater than 10 = "+greaterThan10.test(new Long(4)))System.out.println("15 is greater than 10 = "+greaterThan10.test(new Long(15))); 
     }
}
````

Here, the `LongPredicate.test` method checks if the input number (of type Long) is greater than 10. So when the above code is executed, it will print the following output:

```
4 is greater than 10 = false 
15 is greater than 10 = true
```

You can get the source code for this example along with other code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

---
title: "Predicate interface in Java 8 with examples"
date: "2018-10-02"
categories: 
  - "java-8-examples"
tags: 
  - "functional-interface"
  - "java8"
  - "predicate"
---

In this blog post, I will be explaining how the Java 8 functional interface Predicate works. To know more about functional interfaces, you can refer [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

\[table id=24 /\]

The Predicate interface provides a method called test. This method accepts a parameter of any data type and returns a boolean.

#### Predicate method with Integer argument

Consider the following code snippet:

\[java\] public class PredicateDemo {

public static void main(String\[\] args) { Predicate<Integer> greaterThan8 = (input) -> input > 8; System.out.println("4 is greater than 8 = "+greaterThan8.test(4)); System.out.println("12 is greater than 8 = "+greaterThan8.test(12)); }

}

\[/java\]

Here, the Predicate.test method checks if the input number is greater than 8. So when the above code is executed, it will print the following output:

```
4 is greater than 8 = false
12 is greater than 8 = true
```

#### Predicate method with String argument

Consider the following code snippet:

\[java\]

import java.util.function.Predicate;

public class PredicateDemo {

public static void main(String\[\] args) { Predicate<String> startsWithHello = (str) -> str.startsWith("Hello"); System.out.println("Hello World starts with Hello = "+startsWithHello.test("Hello World")); System.out.println("Test String starts with Hello = "+startsWithHello.test("Test String"));

}

}

\[/java\]

Here, the Predicate.test method checks if the input String starts with the String "Hello". So when the above code is executed, it will print the following output:

```
Hello World starts with Hello = true 
Test String starts with Hello = false
```

You can get the source code for this example along with the code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

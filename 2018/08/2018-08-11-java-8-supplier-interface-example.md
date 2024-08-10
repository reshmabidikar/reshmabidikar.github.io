---
title: "Java 8 Supplier Interface example"
date: "2018-08-11"
categories: 
  - "java-8-examples"
tags: 
  - "functional-interface"
  - "interfaces"
  - "java8"
  - "supplier"
---

In this blog post, I will be explaining how the Java 8 functional interface Supplier works. To know more about functional interfaces, you can refer [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

The Supplier interface provides a method called get.  This method does not accept any arguments. It can return any data type.

#### Supplier example with Integer return type.

Consider the following code snippet:

```java

public static void main(String\[\] args) {

Supplier<Integer> getRandom = () -> new Random().nextInt(100); System.out.println("Random number 1 = "+getRandom.get()); System.out.println("Random number 2 = "+getRandom.get());

}

```

Here, we have implemented the Supplier.get method using a lambda expression.  This get method simple returns a random integer less than 100. So when this code is executed, it will print the following output:

```
Random number 1 = 98
Random number 2 = 89
```

#### Supplier example with Date as return type

Consider the following code snippet:

````java

public class SupplierDemo {

public static void main(String\[\] args) {

Supplier<Date> dateGenerator = () -> new Date(); System.out.println("Date is "+dateGenerator.get());

}

````

Again, we have implemented the Supplier.get method using a lambda expression.  This get method simple returns a date object. So when this code is executed, it will print the following output:

```
Date is Sun Nov 11 13:27:43 IST 2018
```

You can get the source code for this example along with the code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

---
title: "Java 8 Consumer Interface example"
date: "2019-03-25"
categories: 
  - "java-8-examples"
tags: 
  - "functional-interface"
  - "interfaces"
  - "java8"
---

In this blog post, I will be explaining how the Java 8 functional interface Consumer works. To know more about functional interfaces, you can refer [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

The Consumer interface provides a method called accept. It accepts a single parameter of any data type. It does not return anything, it returns a void. So it operates via side effects i.e. it modifies the parameter passed in.

#### Consumer example with Integer parameter

Consider the following code snippet:

````
public class ConsumerDemo {

public static void main(String args[]){ 
Consumer<Integer> squareGenerator = (input) -> System.out.println("Square of "+input +" is "+(input\*input)); 
squareGenerator.accept(6); 
}

} }

````

Here, we have implemented the Consumer.accept method using a lambda expression. This accept method accepts an Integer argument. It squares it and prints the result to the console. So when this code is executed, it will print the following output:

```
Square of 6 is 36
```

#### Consumer example with String as parameter

Consider the following code snippet:

````

public class ConsumerDemo { 
public static void main(String args[]){ 
Consumer<String> subStringGenerator = (str) -> System.out.println(str.substring(0, 5));
String input = "Hello World"; subStringGenerator.accept(input); 
} 
}

````

Again, we have implemented the Consumer.accept method using a lambda expression.  This accept method accepts a String value. It prints its sub string consisting of the first 5 characters in the String. So when you execute this code, it will print the following output:

```
Hello
```

You can get the source code for this example along with the code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

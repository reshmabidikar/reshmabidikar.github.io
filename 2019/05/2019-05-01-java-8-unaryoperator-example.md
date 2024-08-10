---
title: "Java 8 UnaryOperator Example"
date: "2019-05-01"
categories: 
  - "java-8-examples"
tags: 
  - "functional-interface"
  - "interfaces"
  - "java8"
---

In this blog post, I will be explaining how the Java 8 functional interface UnaryOperator works. To know more about functional interfaces, you can refer [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

\[table id=24 /\]

The UnaryOperator interface extends the [Function](https://learnjava.co.in/java-8-function-interface-example/) interface. It inherits the [apply](https://docs.oracle.com/javase/8/docs/api/java/util/function/Function.html#apply-T-) method in the [Function](https://learnjava.co.in/java-8-function-interface-example/) interface. The lambda expression passed to the UnaryOperator is used to provide an implementation for the apply method in the [Function](https://learnjava.co.in/java-8-function-interface-example/) interface.

 

#### UnaryOperator example with Integer data type.

Consider the following code snippet:

\[java\] public class UnaryOperatorDemo {

public static void main(String\[\] args) {

UnaryOperator<Integer> increaseBy5 = num -> num+5; System.out.println("Output with input 7 is "+increaseBy5.apply(7)); }

}

\[/java\]

Here, we have implemented the [UnaryOperator.apply](https://docs.oracle.com/javase/8/docs/api/java/util/function/Function.html#apply-T-) method using a lambda expression.  This method simply increases the value of the input number by 5 and returns it. So when you execute this code, it will print the following output:

```
Output with input 7 is 12
```

#### UnaryOperator example with Integer array as data type

Consider the following code snippet:

\[java\] public class UnaryOperatorDemo {

public static void main(String\[\] args) { List<Integer> list = Arrays.asList(5, 3, 11, 15, 9, 2, 5, 11);

UnaryOperator<List<Integer>> increaseBy5 = input -> { List<Integer> output = new ArrayList<Integer>(); input.forEach(num -> output.add(num+5)); return output; }; List<Integer> output = increaseBy5.apply(list); output.forEach(num -> System.out.println(num));

}

}

\[/java\]

Again, the UnaryOperator accepts an Integer List.  It increments each element in the list by 5 and returns another list with these values. Within the lambda expression, it uses the forEach method to iterate on the input list, obtain each element, increment it by 5 and add it to the output list. So when you execute this code, it will print the following output:

```
10
8
16
20
14
7
10
16


```

 

 

You can get the source code for this example along with other code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

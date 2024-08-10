---
title: "Lambda expressions in Java 8 explained with code samples"
date: "2019-05-15"
categories: 
  - "java-8-features"
  - "java-interview-questions"
---

You Java 8 introduced a new feature called lambda expressions. In this blog post, I will be explaining lambda expressions in detail.

\[table id=24 /\]

## What are lambda expressions

Lambda expressions are used to define anonymous functions, that is a function without a name.  Lambda expressions and functional interfaces together help in writing clean code. A functional interface is nothing but an interface with a single method. In order to understand more about functional interfaces, you can refer to [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post. Lambda expressions can be used to implement functional interfaces.

## Lambda expression syntax

The general syntax of a lambda expression is as follows:

(parameters) -> {method body}

### Parameters

Parameters specify the parameters to be passed to the lambda expression. You can pass one or more parameters. You need to enclose the parameters in parentheses. If there is only one parameter, you can skip the parentheses. Also, parameters are optional. If the lambda expression does not accept any parameters, you need to specify empty parantheses.

 

### Lambda Operator

\-> specifies the lambda operator.

### Lambda expression body

You need to follow the lambda operator with the body of the lambda expression. You can include any code in the body of the lambda expression. Also, you need to include Curly brackets around the body only if the body consists of more than one statement.

## Lambda expression example

Lambda expressions are used to implement functional interfaces. Consider the following code snippet:

\[java\]

@FunctionalInterface public interface DemoInterface {

public void aMethod();

}

\[/java\]

You can implement his interface using a Lambda expression as follows:

\[java\]

public class DemoClass {

public static void main(String args\[\]){

DemoInterface demoInterface = () -> System.out.println("Demo Interface"); demoInterface.aMethod();

}

}

\[/java\]

Here, we are assigning the lambda expression () -> System.out.println("Demo Interface"); to an instance of the DemoInterface. The lambda expression provides the implementation for the method aMethod in the interface. So when the code invokes this method, the code within the lambda expression is executed.  In this case, it simply has a Sysout statement. So when you execute this code, it will print the following output:

```
Demo Interface
```

## Advantages of lambda expressions

### Keeping Code concise

Lambda expressions help to keep the code concise. Prior to Java 8, we would need to write code similar to the following in order to implement a functional interface:

\[java\]

public class DemoClass implements DemoInterface{

public static void main(String args\[\]){

DemoInterface demoInterface = new DemoClass(); demoInterface.aMethod();

}

public void aMethod(){ System.out.println("Demo Interface"); }

}

\[/java\]

So basically, we need to create a class that implements the interface, provide an implementation for the method in the interface and invoke this method. When you compare this code to the code written earlier using lambda expressions it is much cleaner. You just need to write one line of code

### Passing around code as arguments

Lamda expressions are anonymous functions. They allow you to pass code as method arguments. So consider the following code snippet:

\[java\]

public interface Shape {

public void draw();

}

public class ShapeDemo {

public static void main(String\[\] args) { drawShape(() -> System.out.println("Drawing Rectangle")); drawShape(() -> System.out.println("Drawing Circle")); drawShape(() -> System.out.println("Drawing Triangle"));

}

public static void drawShape(Shape shape){ shape.draw(); }

}

\[/java\]

This code defines a functional interface Shape with a method draw. The ShapeDemo class has a method drawShape that accepts a Shape object. It invokes the draw method. Instead of passing a Shape implementation for each Shape (i.e. Rectangle, Circle and Triangle), the main method passes a lambda expression corresponding to the implementation for each Shape.

When you execute this code, it will print the following output:

```
Drawing Rectangle
Drawing Circle
Drawing Triangle
```

---
title: "Java 8  Functional Interface explained with code samples"
date: "2019-03-18"
categories: 
  - "java-8-features"
  - "java-interview-questions"
tags: 
  - "functional-interface"
  - "interfaces"
  - "java8"
---

Java 8 introduced the concept of functional interfaces. In this blog post, I will be explaining what a Java 8 functional interface is.

#### What is a functional interface?

A functional interface is nothing but an interface that has only one abstract method. It can have more than one static and default methods, but it should have only one abstract method in order to qualify as a functional interface. Consider the following code snippet:

````java
package learnjava.java8;

@FunctionalInterface 
public interface MyFunctionalInterface {

    public void method1();

    public default void defaultMethod(){ 
        System.out.println("Default method"); 
    }

    public default void staticMethod(){ 
        System.out.println("Static method"); 
    }
}
````

Here, we have defined an interface called **MyFunctionalInterface**. This has only one abstract method called **method1** and so this is a functional interface. It also has a **default** and a **static** method. Note that we have specified the [@FunctionalInterface](https://docs.oracle.com/javase/8/docs/api/java/lang/FunctionalInterface.html) annotation. This annotation specifies that this is a functional interface. So if we try to add **another abstract method** to this interface, it will **cause a compilation error**. So consider the following code snippet:

````java
@FunctionalInterface 
public interface MyFunctionalInterface {

  public void method1();

  public void method2();

}
````

The above code snippet causes a compilation error since there are 2 abstract methods in the interface.

Note that the [@FunctionalInterface](https://docs.oracle.com/javase/8/docs/api/java/lang/FunctionalInterface.html) annotation is **optional**. So if we remove this annotation, the compilation error goes away but the interface will no longer be a functional interface. We can still have a functional interface without the [@FunctionalInterface](https://docs.oracle.com/javase/8/docs/api/java/lang/FunctionalInterface.html) annotation. Any interface that has a single abstract method qualifies to be a functional interface irrespective of whether it has the[@FunctionalInterface](https://docs.oracle.com/javase/8/docs/api/java/lang/FunctionalInterface.html) annotation or not.

#### Why are functional interfaces useful?

Functional interfaces are used to create **anonymous functions** using **lambda expressions**. Java 8 introduced lambda expressions as a powerful way to create anonymous functions. So if you have a functional interface, you can use a lambda expression to provide an implementation for the interface without having to write the boiler-plate code.

Suppose, you need to write a class that implements the **MyFunctionalInterface** declared above. Prior to Java8, you would need to write code similar to the following:

````java
public class MyClass implements MyFunctionalInterface {

    @Override public void method1() { 
        System.out.println("Method1");
    }

    public static void main(String args[]){ 
        MyClass obj = new MyClass(); 
        obj.method1(); 
    }
}
````

When you run this code, it will print the following output:

```
method1
```

However, in Java 8, you can re-write the code above as follows:

````java
public class MyClass {

    public static void main(String args[]){ 
        MyFunctionalInterface myInterface = () -> { 
                System.out.println("method1");
            }
        myInterface.method1(); 
  } 
}
````

So now, **we don't need the class to implement the interface** and provide a method body. Compared to the traditional code this code is compact and eliminates the need to create a class that implements the interface. When this code is executed, it will also print the same output as before:

```
method1
```

#### Existing Functional Interfaces in Java

Java already has some functional interfaces.[java.lang.Runnable](https://docs.oracle.com/javase/8/docs/api/java/lang/Runnable.html),[java.util.Comparator](https://docs.oracle.com/javase/8/docs/api/java/util/Comparator.html) are all examples of functional interfaces. These interfaces were present before Java 8. However, after Java 8 they were made functional interfaces with the [@FunctionalInterface](https://docs.oracle.com/javase/8/docs/api/java/lang/FunctionalInterface.html) annotation. The advantage of making these functional interfaces is that you do not need to create a new class just to implement them, yo can provide implementations for the abstract method within these interfaces via lambda expressions.

#### java.util.Function

Java 8 introduced a new package called [java.util.Function](https://docs.oracle.com/javase/8/docs/api/java/util/function/package-summary.html). It has a number of useful functional interfaces. For example, it provides the [Predicate](https://reshmabidikar.github.io/2018/10/java-8-predicate-example.html) interface. It has a single method called `test`. This accepts an argument of any type and returns a boolean result. 

Consider the following sample code:

````java
import java.util.function.Predicate;

public class PredicateDemo {

    public static void main(String[] args) { 
        Predicate<Integer> greaterThan8 = (input) -> input > 8; 
        System.out.println("4 is greater than 8 = "+greaterThan8.test(4)); 
        System.out.println("12 is greater than 8 = "+greaterThan8.test(12)); 
    }
}
````

So here, the `Predicate.test` method checks if the input integer is **greater than 8**. So when you run the code above, it will print the following output:

````
4 is greater than 8 = false 
12 is greater than 8 = true
````

Just like [Predicate](https://reshmabidikar.github.io/2018/10/java-8-predicate-example.html), there are a number of useful interfaces in the [java.util.Function](https://reshmabidikar.github.io/2019/04/java-8-functional-interface-example.html). It is not possible to explain all these interfaces here but you can take a look at the [API documentation.](https://docs.oracle.com/javase/8/docs/api/java/util/function/package-summary.html)

#### Conclusion

So, this article explains what a Java 8 functional interface is. It also explains how you can implement a functional interface via a [lambda expression](https://reshmabidikar.github.io/2019/05/java-8-lambda-expressions-explained.html). Finally, it covers some on the in-built functional interfaces.

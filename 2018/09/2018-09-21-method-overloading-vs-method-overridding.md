---
title: "Method Overloading Vs Method overridding"
date: "2018-09-21"
categories: 
  - "core-java"
  - "java-interview-questions"
tags: 
  - "core-java"
  - "method-overloading"
  - "method-overridding"
  - "oops-concepts-en"
  - "polymorphism-en"
---

 

In this blog post, I will be explaining the difference between method overloading and method overidding.

#### What is method overloading?

In Java it is possible to define two or more methods within the same class that share the same name, as long as their parameter declarations are different. When this is the case, the methods are said to be overloaded, and the process is referred to as method overloading. The following code demonstrates this:

\[java\]

public class AddDemo {

public int add(int a,int b){ return a+b; }

public double add(double a,double b){ return a+b; }

}

\[/java\]

So here this class has two methods with the name "**add**". The first version accepts two integer values and returns an int, whereas the second version accepts two double values and returns a double. So both these methods have the same name i.e. **add**, but accept different types of parameters. Overloaded methods must differ in the type and/or number of their parameters. While overloaded methods may have different return types, the return type alone is insufficient to distinguish two versions of a method. When an overloaded method is invoked, Java uses the type and/or number of arguments as its guide to determine which version of the overloaded method to actually call. In other words, Java looks for a match between the arguments used to call the method and the method’s parameters. The compiler determines the version of the overloaded method to invoke based on the number and type of arguments, so method overloading is an example of compile time polymorphism.

#### What is method overridding?

In a class hierarchy, when a method in a subclass has the same name and type signature as a method in its superclass, then the method in the subclass is said to override the method in the superclass. Consider the following code:

\[java\]

public class Base {

public void print(){ System.out.println("Base"); } }

public class Sub extends Base{

public void print(){ System.out.println("Sub"); }

public static void main(String args\[\]){ Base b = new Sub(); b.print(); } }

\[/java\]

 

Here, both the **Base** class as well as the **Sub** class have a method called **print**. Here, the sub-class method **print**  **overrides** the base class method **print**.  In the **main** method, we are defining a **Base** class variable "**b**" and assigning it a **Sub** class object. This code prints the following output on execution:

```
Sub
```

Although we are creating a **Base** class variable **b**, the object assigned to this variable determines which method to invoke. Since a **Sub** class object is assigned to the variable **b**, the method in the sub-class is invoked. So it is the object type and not reference type that determines the method to invoke.  Thus, method overridding is known as runtime polymorphism since the version of an overridden method that will be invoked is determined at runtime.

 

So to summarize, both method overloading and method overridding are ways in which Java achieves polymorphism. However, the version of an overloaded method that will be invoked is determined at compile time based on the number and type of arguments. So method overloading is an example of compile time polymorphism. The version of an overridden method that will be invoked is determined at runtime based on the object used.  So method overridding is an example of runtime polymorphism.

The following table lists the differences between method overloading and method overridding in detail:

\[table id=5 /\]

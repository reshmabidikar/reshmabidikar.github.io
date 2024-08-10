---
title: "Java 8 Default Interface methods explained"
date: "2019-03-08"
categories: 
  - "java-8-features"
  - "java-interview-questions"
tags: 
  - "abstract-classes"
  - "default-interface-methods"
  - "interfaces"
  - "java8"
---

One of the new features provided by **Java 8** is the support for default methods in interfaces. In this blog post, I will be explaining Java 8 default interface methods in detail. I will be covering what default methods are, how they work and why they were added.

\[table id=24 /\]

#### What are default interface methods?

Default methods are methods in an interface that have method bodies, They are specified with the  keyword "**default**".

#### How do default interface methods work?

Prior to Java 8, interfaces could not have method bodies.  So consider the following code snippet:

\[java\]

public interface MyInterface { public void methodA();

public void methodB(){ System.out.println("In methodB"); } }

\[/java\]

 

This code causes a compilation error. This is because **methodB** has a method body.  However, if you are using Java 8, you can change the code as follows:

\[java\]

public interface MyInterface { public void methodA();

default public void methodB(){ System.out.println("In methodB"); } }

\[/java\]

So now, the default keyword is added for methodB. So in Java 8, you can have methods with method bodies within an interface as long with the **default** keyword. Any class that implements this interface need not provide a method body for the **methodB**.  So consider the following code:

\[java\]

public class MyClass implements MyInterface {

@Override public void methodA() { System.out.println("In methodA");

}

public static void main(String args\[\]){ MyClass obj = new MyClass(); obj.methodA(); obj.methodB(); }

}

\[/java\]

 

Here, we have a class called **MyClass** that implements the **MyInterface**.  So you can see that **MyClass** does not provide any implementation for **methodB**. That is because it has a default implementation within the interface itself.  So when you run this code, it will print the following output:

```
In methodA
In methodB
```

You can also provide an implementation for a default method in the class that implements the interface.  So you can provide an implementation for **methodB** in **MyClass** as follows:

\[java\]

public void methodB(){ System.out.println("In MyClass.methodB"); }

\[/java\]

If you run the code now, it will print the following output:

```
In methodA
In MyClass.methodB
```

So when you provide an implementation for a default method in a class, Java ignores the method implementation in the interface and uses the method implementation from the class.

 

#### What was the need for default methods?

Allowing methods with method bodies in interfaces is a paradigm shift for those who used interfaces prior to Java 8. The main reason behind using an interface is to define a behavior but leave it to the classes that implement the interface to specify how to implement that behavior. However, allowing method bodies within an interface defeats this purpose. Why then did Java 8 include this feature?

##### To keep code backward compatible and prevent it from breaking when you add new methods to an interface

Consider the scenario where you have an interface with some methods. Suppose there are several classes that implement this interface. If you add a new method to the interface, there will be compilation errors in all the classes that implement the interface. However, if the new method in the interface has a default implementation, then all the existing classes that implement the interface will work without any changes.

 

##### To add forEach support in Collections without code changes to Collection classes

Java 8 has added the forEach method to all the Collections via the [Iterable](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html) interface. So there is a new method called [forEach](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html#forEach-java.util.function.Consumer-) added to the [Iterable](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html) interface. All the Collection classes implement the [Iterable](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html) interface. The [forEach](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html#forEach-java.util.function.Consumer-) method is given a default implementation within the Iterable interface. So the Collection classes work as they are without any code changes. If default interfaces methods were not supported, then all the Collection classes would need to be modified to add code for the forEach method.

 

#### Java 8 Abstract classes VS interfaces

The default method support in Java 8 has reduced the distinction between abstract classes and interfaces.  This is because like abstract classes, interfaces can also have method implementations in Java 8. However, there are still some differences between the two.

The main difference is that an abstract class is a class and it can have a state through instance fields. Interfaces on the other hand cannot have state and are used to specify a behavior. This does not change with the introduction of default interface methods. Default methods simple provide the feature of being able to add additional functionality to the interfaces without affecting existing classes that implement the interface.

Another difference is that an abstract class can have a constructor, an interface cannot have a constructor.

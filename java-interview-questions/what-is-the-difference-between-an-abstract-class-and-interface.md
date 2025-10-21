---
title: "Difference between an abstract class and interface in Java"
date: "2018-09-10"
categories: 
  - "core-java"
  - "java-interview-questions"
tags: 
  - "abstract-class"
  - "core-java"
  - "interfaces"
---

Another commonly asked interview question is to explain the difference between an abstract class and an interface. So in this blog post, I will give you a detailed explanation.

#### What is an Abstract Class?

An abstract class is a class that has one or more abstract method. An abstract method is a method that has the "abstract" keyword specified in the method definition. It does not have any method body, it is up to the subclass of the abstract class to provide an implementation for the abstract method.

#### So why is an abstract class useful?

Sometimes, you will want to create a super class that defines a method that all its sub classes must implement, but it leaves the exact implementation to the sub class. For ex. suppose you have a class called Shape, you can define an abstract method called draw. You can then have subclasses for various shapes like Rectangle, Triangle, etc which provide implementations for the draw method. So while the "draw" method makes no sense for the Shape class, it makes sense for the Rectangle and Triangle classes and so it makes sense to have the code for the draw me

#### What is an Interface?

An interface is a java construct that specifies methods without any method bodies. The code for the methods within the interface must be provided by the classes that implement the interface.

#### Why is an interface useful?

Using an interface, you can specify what a class must do, but not how it does it. So you can use it to specify a behavior that classes must implement.

#### So what are the similarities between abstract class and interface?

- Both abstract classes and interfaces are used to specify a behavior
- Both cannot be instantiated

#### How are they different?

|Abstract Class|Interface  |
|--|--|
| An abstract class can have non-abstract methods i.e. methods with method bodies |All methods within the interface are abstract so it cannot have methods with method bodies.  |
| Only one class can extend an abstract class | An interface can be implemented by several classes |
|An abstract class can have protected and public abstract methods  | An interface can have only have public abstract methods |
| Can have instance variables |Cannot have instance variables, all variables are implicitly static and final since an interface cannot be instanitated  |
|Can have a constructor  | Cannot have constructors |

#### When to use which?

An abstract class should be used when you want methods in the base class to have some basic default behavior but want to leave it to the subclasses to override these methods. An interface should be used when you want to define a behavior that other classes (probably external) must implement.

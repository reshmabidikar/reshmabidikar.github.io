---
title: "What is the final keyword in Java?"
date: "2018-09-05"
categories: 
  - "java-interview-questions"
  - "java_language_features"
tags: 
  - "core-java"
  - "final"
  - "java-keywords"
---

A very common interview question is to ask about the final keyword and what it means when it is used with different constructs like field, method, etc. So in this blog post I'm going to explain the final keyword in detail.

#### Final Variable

A variable can have the **final** keyword specified.**Final** keyword for a variable means that you cannot modify the contents of the variable after you declare it. So you cannot assign a value to a final variable, doing so will result in a compilation error. So you must initialize a **final** variable when you declare it.A final variable is generally used to define a constant in Java. It is a common coding convention to choose all uppercase identifiers for **final** variables.

#### Final Method

A method can have the **final** keyword specified. **Final** keyword for a method means that you cannot override the method. So if a sub-class tries to override a final method, there will be a compilation error. Although you cannot override a final method, a subclass still inherits it. So you can use an object of the sub-class to invoke a final method in the base class.

#### Final class

A class can also have the **final** keyword. **Final** keyword for a class means that you cannot extend the class. So if you try to create a sub-class of a **final** class, this will cause a compilation error.

#### Final parameters

Parameters passed to a method can have the **final** keyword specified. You cannot change a **final** parameter inside a method. So if you try to assign a value to a final parameter in a method,it will cause a compilation error.

#### Final Interface

An interface cannot have the **final** keyword. The basic purpose of an interface is to define methods which classes can implement. And the basic purpose of the **final** keyword is to prevent inheritance. So if **final** keyword is allowed for an interface it would make no sense because **final** would prevent the interface from being implemented.

---
title: "What Are Java constructors?"
date: "2018-12-11"
categories: 
  - "java-interview-questions"
  - "java_language_features"
tags: 
  - "constructors"
  - "core-java"
---

A _constructor_ is a special method that is invoked as soon as an object is created using the _new_ operator. In this blog post, I will explaining constructors. Constructors are most commonly used to execute some code that needs to be run **as soon as an object** of a class is created like setting initial values to the instance variables. Consider the following code snippet:

\[java\]

public class Person {

private String firstName; private String lastName;

public void setPersonDetails(String firstName,String lastName){ this.firstName=firstName; this.lastName=lastName; } }

\[/java\]

Here, there is a _Person_ class. There is a method called _setPersonDetails_. This method sets values to the _firstName_ and _lastName_ fields. However we need to invoke this method, each time we create a _Person_ object. If we forget to invoke this method, the _firstName_ and _lastName_ fields will not be set . So we need some way for the person details to be automatically set when a _Person_ object is created. Fortunately, Java supports this **automatic initialization via constructors**. So lets add a constructor to the _Person_ class:

\[java\]

public Person(String firstName,String lastName){ this.firstName=firstName; this.lastName=lastName; }

\[/java\]

As you can see, a constructor is very similar to an ordinary method. What sets them apart is that they do not have a **return type**, not even **void** unlike other methods defined in a class. Also, the **name** of the constructor is **exactly the same** as the name of the class. This constructor is automatically invoked as soon as the new keyword is encountered and the code in the body of the constructor is executed. So as soon as a _Person_ object is created using the new operator this constructor is invoked and it sets the values for the _firstName_ and _lastName_ fields

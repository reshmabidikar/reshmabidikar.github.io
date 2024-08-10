---
title: "Static keyword explained"
date: "2018-09-12"
categories: 
  - "java-interview-questions"
  - "java_language_features"
tags: 
  - "core-java"
  - "java-keywords"
  - "static"
---

In this blog post, I will be explaining Java's static keyword.

#### What is the static keyword?

There will be times when you will want to define a class member i.e. either method or field independent of any object of that class. To create such a member, we need to precede its declaration with the  **static** keyword**.** When a member is declared static, it can be accessed before any objects of its class are created, and without reference to any object, i.e. it can be accessed directly with the class name. You can declare both methods and variables to be static.

 

#### What is a Static Variable?

A variable preceded with the static keyword is a static variable.  It can be accessed irrespective of any member directly using the class name. Variables declared as **static** are essentially, global variables. When objects of a class are created, no copy of a **static** variable is made. Instead, all objects of the class share the same **static** variable.

 

**Static method**

A method preceded with the static keyword is a static method.  A static method can be invoked directly with the classname, it does not need an object of the class. Static methods have the following restrictions:

- Can only call other **static** methods
- Must only access **static** data.
- Cannot refer to **this** or **super** in any way.

#### Static block

In addition to static variables and methods, there can also be a static block.  It has the following syntax:

\[java\]

static {

}

\[/java\]

 

So it is just a block of code that has the static keyword. A static block is executed first when the class is loaded in memory, even before the main method and even before an object of the class is created. It is generally used to initialize static variables.

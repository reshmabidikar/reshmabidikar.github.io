---
title: "Java This Keyword Explained"
date: "2018-10-07"
categories: 
  - "java-interview-questions"
  - "java_language_features"
tags: 
  - "core-java"
  - "java-keywords"
---

In this blog post, I will be explaining the 'this' keyword.Sometimes a method will need to refer to the object that invoked it. To allow this, Java defines the **this** keyword. **this** can be used inside any method to refer to the _current_ object i.e. the object on which the method was invoked.

Consider the following code snippet:

```java

private int radius;

public Circle(int radius)

{

this.radius = radius;

}

````

Since both the passed in variables and the instance fields have the same names, **this** is used to distinguish. So **this.radius** refers to the current object’s copy of the radius instance field & **radius** refers to the value passed in.

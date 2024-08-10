---
title: "Java Access specifiers explained"
date: "2018-09-04"
categories: 
  - "java-interview-questions"
  - "java_language_features"
tags: 
  - "core-java"
  - "java-access-specifiers"
---

Java provides a mechanism to precisely control access to the various members of a class via access specifiers. In this blog post, I will be explaining Java's access specifiers i.e. private, protected, public and default.

#### Private

When a member of a class is specified as **private** then that member can only be accessed only by other members of its class. However, it will not accessible outside of the class via the dot operator. All private fields need to have getter and setter methods to retrieve and set their values. Otherwise, they will not be accessible outside of the class..

#### Public

When a member of a class is modified by the **public** specifier, then that member can be accessed by any other code. It is not generally recommend to have this access specifiers for fields of a class. All fields of a class should have private access specifiers and public getter and setter methods to access them.

#### Default access Specifier

The **default** access specifier comes into play when no other access specifier is used. The default access means that the field is accessible within the class and outside of the class in all classes within the same package, However, the field is not accessible to classes which are in different packages.

 

#### Protected

The **protected** access specifier applies only when inheritance is involved. So when the protected access specifier is used for a field, the field becomes accessible in the sub classes of the class in which the field is defined. In addition,  the field is also accessible to other classes within the same package.

 

#### Summary

The following table summarizes the access specifiers:

\[table id=2 /\]

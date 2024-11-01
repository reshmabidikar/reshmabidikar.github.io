---
title: "Java Super Keyword explained"
date: "2019-07-10"
categories: 
  - "java_language_features"
tags: 
  - "super"
---

## What is the Super Keyword?

Super keyword is used to access members of the superclass from the subclass. It can be used to access both instance fields and methods.

## Code Sample

Consider the following code:

```
public class Base {
  
  int a;
  int b;
  
  public void baseMethod() {
    System.out.println("In base class method”);
  }

}

public class Sub extends Base {
  
  int c;
  
  public void subMethod() {
    super.a=4;
    super.b=9;
    super.baseMethod();
    System.out.println("In sub class method");
  }
  
}

```

- There are 2 classes, **Base** and **Sub**
- **Sub** is a sub-class of **Base**; it has a method called **subMethod**
- The **base** fields **a,b** are accessed via the **super** keyword in **subMethod**
- The base method **baseMethod** is also accessed via the **super** keyword

When this code is executed, it will print the following output:

```
In base class method
In sub class method
```

## Points to Remember

- The **super** keyword is a bit redundant for instance fields and methods since as long as the instance fields and method of the superclass and not private, they can be accessed directly in the sub-class.
- The **super** keyword is useful for accessing class members only when the base class has a member with the same name.
- A subclass constructor can invoke a superclass constructor using the super keyword.

---
title: "Java Final Keyword Explained with Code Samples"
date: "2019-09-12"
categories: 
  - "java_language_features"
---

In this article, I will be covering Java's final keyword. I will be demonstrating the final keyword in Java with an example.

## Introduction

You can use the final keyword with a method or instance field. When you use it with a method, it prevents the method from being overridden. When you use it with a field, it prevents the field from being modified.

## Final Method

```java
public class Base {

    public final void show() {
        System.out.println("In show”);
   }
}

public class Sub extends Base {

// This method causes a compilation error

    public void show() {

    }

}

}
```

- Class **Base** has a method **show** which is marked as **final**
- **Sub** is a sub-class, it overrides **show**
- There is a compilation error in **Sub** as the final method cannot be overridden


## Final Field

Declaring a variable as final prevents its contents from being modified. This means that you must initialize a final variable when it is declared.

The following code demonstrates a final field:

```java
public void aMethod() {

final int d = 10;

d = 3; // compilation error

}
```

- The method **aMethod** has a field called **d** which is marked as **final**
- The method tries to set **d** to **3**
- There is a compilation error since the **final** variable cannot be modified

## Conclusion

So, in this article, we saw why final keyword is used in Java.

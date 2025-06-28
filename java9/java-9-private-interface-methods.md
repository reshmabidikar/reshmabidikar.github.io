---
title: "Java 9 Private Interface Methods with code sample"
date: "2019-05-31"
categories: 
  - "java-9"
tags: 
  - "java-9"
---

In this blog post, I will be explaining Java 9 private interface methods. This is another of Java 9's new features.

## Introduction

Java 8 introduced default and static methods in interfaces. Default methods are nothing but methods with some method bodies. Such methods have the keyword "**Default**" specified. Private interface methods allow code reuse in default methods. So if there is some common code across two or more default methods, this code can be placed in a private method

## Code Sample

```java
public interface MyInterface {
  
  default void method1() {
    commonCode();
    System.out.println("Code for method1");
  }
  
  
  default void method2() {
    commonCode();
    System.out.println("Code for method2");	
  }
  
  private void commonCode() {
    System.out.println("Common code");
  }

}
```

In the above example, the interface `MyInterface`has 2 default methods, `method1`and `method2`.In addition, there is a method `commonCode`which is a private method. This is invoked from both `method1`and `method2`. So any code that is common can be placed here.

## Conclusion

So, in this article, we learned about private interface methods introduced by Java 9.

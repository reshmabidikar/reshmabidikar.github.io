---
title: "Singleton class Explained"
date: "2018-09-25"
categories: 
  - "core-java"
  - "java-interview-questions"
tags: 
  - "core-java"
  - "singleton-class"
---

Singleton is a design pattern. A singleton class is a class for which only one object can be created. You can create a singleton class by using a private constructor. The following code snippet demonstrates this:

```java

private static Singleton singletonInstance;

private Singleton(){

}

public static Singleton getInstance() { 
    if (singletonInstance == null){         singletonInstance = new Singleton(); } 
    return singletonInstance; 
}
````

Here, we have a private constructor and a public getInstance method. The getInstance checks if an instance already exists. If an instance does not exist, it creates one using the private constructor. If an instance exists, it just returns it. So this method ensures that there is only one instance of the Singleton class. Any external class that needs an instance of the Singleton class, should invoke the getInstance method.

---
title: "Java 8 Static Interface methods with code samples"
date: "2019-03-15"
categories: 
  - "java-8-features"
  - "java-interview-questions"
tags: 
  - "interfaces"
  - "java8"
  - "static"
---

Just like [default methods](java-8-default-method-in-interface-explained.md), Java 8 also supports **static** methods in interfaces. In this blog post, I will be explaining Java 8 static interface methods in detail. I will be covering what static methods are, how they work and why they were added.

#### What are static interface methods?

Static interface methods are methods with the **static** keyword are with a method body.

#### How do static interface methods work?

Consider the following code snippet:

````java
public interface MyInterface {

  static public void staticMethod() { 
    System.out.println("In staticMethod of interface"); 
  } 
} 
````

So in the code above, `staticMethod` is a static interface method. So we have defined a method with a method body within the interface. It has the static keyword specified. Prior to Java 8, the above code would have caused an error due to two reasons:

1. There is a method with a method body within the interface
2. There is a static method with in the interface

#### How are they similar to default methods?

Just like default methods, static interface methods have a method body. Also, just like in the case of default methods, the classes that implement the interface do not need to provide an implementation for the static methods.

#### How are they different from default interface methods?

##### Static interface methods have the static keyword

As seen earlier, instead of the default keyword, they have the static keyword.

##### Static interface methods cannot be overridden.

Another difference is that unlike default methods, static methods cannot be overridden.So consider the following code:

````java

public interface MyInterface {

    default public void defaultMethod(){ 
        System.out.println("In defaultMethod of interface"); 
    }

    static public void staticMethod() { 
        System.out.println("In staticMethod of interface"); 
    } 
} 
  
public class MyClass implements MyInterface { 
  
    @Override 
    public void defaultMethod() { 
        System.out.println("In defaultMethod of class"); 
    } 
    
    @Override 
    static public void staticMethod() { 
        System.out.println("In staticMethod of class"); 
    } 
}
````

The above code causes a compilation error. This is because of the @Overrides annotation on the staticMethod which is a static method in the MyInterface. If this annotation is removed, the compilation error goes away.

##### They cannot be invoked using the class or object.

Consider the following code snippet:

````java
public interface MyInterface {

    default public void defaultMethod() { 
        System.out.println("In defaultMethod of interface"); 
    }

    static public void staticMethod() { 
        System.out.println("In staticMethod of interface"); 
    } 
}

public class MyClass implements MyInterface {

    public static void main(String args[]){ 
        MyClass obj = new MyClass(); 
        obj.defaultMethod(); 
        obj.staticMethod(); //this line causes a compilation error 
    }
}
````

The above code causes a compilation error. This is because of the staticMethod being invoked using the MyClass reference object i.e. obj.The static interface method can only be invoked using the MyInterface reference as follows:

````java
MyInterface.staticMethod();
````

#### How are static interface methods useful?

Static interface methods are part of the interface's API and not the classes that implement the interface. They allow you to group together utility methods within an interface. So you do not need to create a utility class with utility methods. So static interface methods keeps your design clean. You do not need to create an object of a class to just invoke some utility methods.


#### Conclusion

So, in this article, we learnt about Java 8 static interface methods. We learnt how thy can be used and what benefits they provide.

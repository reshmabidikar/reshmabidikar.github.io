---
title: "Java Interfaces explained"
date: "2018-12-17"
categories: 
  - "java_language_features"
tags: 
  - "core-java"
  - "interfaces"
---

In this blog post, I will be explaining what Java interfaces are and how they can be used.

#### What is an interface?

An interface is a java construct that is used to specify a behavior that classes must implement. It does this by specifying methods without any method bodies. The code for the methods within the interface must be provided by the classes that implement the interface. So using an **interface**, you can specify what a class must do, but not how it does it.

For example, consider the following code snippet:

````java
public interface Animal {

    public void speak();
}
````

This interface keyword specifies that this is an interface. Instead of the class keyword, the interface keyword is used, otherwise its body is very similar to a class. There is a speak method within this interface. There is no code in the speak method. Methods specified in an interface have no method bodies. Code is not allowed in a method in an interface since the basic concept of an interface is to use it to specify what should be done but leave a class to decide how to do it. So in this case, this Animal interface specifies that it has a speak method, but it does not specify how the animal should speak. . We can write other classes like Dog, Cat, etc which implement this interface and provide code in the speak method.

#### How does a class implement an interface?

Consider the following code snippet:

````java
public class Dog implements Animal {

    public void speak(){
        System.out.println("Woof Woof!");
    }
}
````

Here, the class declaration is followed by this implements keyword and the interface name. This specifies that the Dog class implements the Animal interface.

Once an interface is defined, any number of classes can implement the **interface**. So I can create another class called Cat and provide its own speak implementation. So the advantage of specifying the speak method in the interface is that it provides a contract, any class that implement the Animal interface, must provide implementation for the speak method. Also, each class is free to provide its own implementation of the speak method, this makes sense since each shape Animal will have a different way speaking. Also, one class can implement any number of interfaces as long as it provides implementations for all the methods in all the interfaces.

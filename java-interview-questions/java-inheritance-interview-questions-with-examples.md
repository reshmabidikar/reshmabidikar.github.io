---
title: "Java Inheritance Interview Questions With Examples"
date: "2021-04-08"
categories: 
  - "java-interview-questions"
coverImage: "java_inheritance_interview_questions-scaled.jpg"
---

In this article, I will be listing some Java inheritance interview questions

## What are the benefits of inheritance in Java?

Answer:

Inheritance has the following benefits:

1. It permits code reuse. So, if there is some common code that can be used across a set of subclasses it can be specified in the base class and reused by all the subclasses.
2. It facilitates polymorphism via method overriding. Method overriding allows a subclass to specify a method with the same type signature as a method in the superclass. To know more about method overriding refer to [this](method-overloading-vs-method-overridding.md) blog post.
3. It makes the code extendable. So, if there is already some code, developers can use the code by creating a subclass and they need not write it again

## What are the different types of inheritance?

Answer:

Java supports the following types of inheritance:

1. Single Inheritance - In this case, a class has only one subclass
2. Multi-level Inheritance - In this case, a subclass in turn has a subclass
3. Hierarchical Inheritance - In this case, a base class has multiple subclasses

## Explain the extends keyword

Answer:

You can use the **extends** keyword to create a subclass. It needs to be specified after the subclass name, along with the base class name.

Consider the following code:

```java
class Shape {

}
```

This code specifies a `Shape` class.

And consider the following code:

```java
class Square extends Shape {

}
```

This code specifies a `Square` class. The **extends** keyword is specified after the class name, followed by `Shape`. So, this indicates that `Square` is a subclass of `Shape`

## How can inheritance be used to achieve polymorphism?

Answer:

Inheritance helps to achieve runtime polymorphism. Java allows assigning a subclass object to a variable of the superclass type. When an overridden subclass method is invoked using such a reference variable, the code in the subclass gets executed. Thus, by assigning different subclass objects to a superclass variable, we can execute different code via the same method call.

Consider the following code:

```java
public class Animal {
  
  void speak() {
    System.out.println("animal speaking");
  }
}
```

This code specifies an `Animal` class. It has a `speak` method.

And consider the following `Animal` subclasses:

```java
public class Cat extends Animal {

  void speak() {
    System.out.println("meow");
  }
}

public class Dog extends Animal{

  void speak() {
    System.out.println("woof woof");
  }
}
```

This code specifies a `Cat` class and a `Dog` class. Both are subclasses of `Animal` and override the `speak` method.

Now consider the following code:

```java
public class AnimalDemo {

  public static void main(String[] args) {
    Animal animal = new Cat();
    animal.speak();
    
    animal = new Dog();
    animal.speak();

  }

}
```

This code specifies an `AnimalDem`o class. The `main` method first defines a variable `animal` of type `Animal` but assigns it a new `Cat` object. It then invokes the `speak` method on `animal`. Since `animal` is assigned a `Cat` object, this results in the `Cat` class method being invoked. It then assigns a new `Dog` object to the `animal` variable and again invokes the `speak` method on `animal`. Since `animal` is assigned a `Dog` object, this results in the `Dog` class method being invoked. So, the same method call (`animal.speak`) results in different methods getting executed. Thus, this helps to achieve polymorphism. Since the call to the overridden method is resolved at runtime, this is known as runtime polymorphism.

This code produces the following output:

```
meow
woof woof
```

## What is the use of the super keyword?

Answer:

You can use the **super** keyword as follows:

1. To access a superclass field/method from a subclass method. In this case, you need to follow the super keyword by the dot operator and the superclass member name
2. To invoke a superclass constructor. In this case, the super keyword needs to followed by the superclass constructor parameters in parentheses and resembles a method call.

To know more about the super keyword, you can read [this](https://learnjava.co.in/java-super-keyword-explained/) article.


## Conclusion

So, in this article, we took a look at some Java Inheritance Interview Questions.
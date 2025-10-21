---
title: "Constructors in Inheritance - Different scenarios explained"
date: "2020-05-01"
categories: 
  - "java_language_features"
---

In this article, I will be covering how constructors work in inheritance.

## How Constructor invocation works in Inheritance

Constructor invocation works slightly differently when inheritance is involved. When an object of the **sub-class** is created, it **implicitly** invokes the c**onstructor in the base class**. Once the code in the base class constructor is completed, control returns to the sub class constructor and the code is the sub-class constructor is executed.

There are different scenarios in which the invocation differs slightly. Let's explore these scenarios

## Scenario 1 - Base class has a constructor

When the base-class has a constructor, creating an object of the sub-class results in automatic invocation of the base class constructor.Consider the following code snippet:

```java
public class Animal {

public Animal() {
    System.out.println("In Animal constructor");
}
}

public class Cat extends Animal{

public Cat() {
    System.out.println("In Cat constructor");
}
}
```

Here, The `Animal`class has a constructor. `Cat` is a sub-class of `Animal` and has its own constructor.

Now consider the following code:

```java
Cat cat = new Cat();
```

This code creates a new `Cat` object. In such a scenario, Java first invokes the `Animal`constructor after which it invokes the `Cat` constructor. So this code prints the following output:

```
In Animal constructor
In Cat constructor
```

## Scenario 2 - Base class does not have a constructor

If there is no constructor in the base class, Java provides a default no arguments constructor in the base class and inserts a call to this constructor from the sub-class constructor. So consider the following code snippet:

```java
public class Animal{
}

public class Cat extends Animal {

Cat() {
    System.out.println("In cat constructor");
}

}
```

Here, The `Animal` class does not have a constructor. `Cat` is a sub-class of `Animal` and has its own constructor.

Now consider the following code:

```java
Cat cat = new Cat();
```

This code creates a new `Cat` object. Since there is no constructor in the `Animal` class, Java creates a default constructor in the `Animal` class and inserts a call to it. So this code prints the following output:

```
In cat constructor
```

## Scenario 3 - Constructor with arguments in the sub-class

When there is a constructor with arguments in the base-class, Java is not able to add a default constructor in the base-class. So a compilation error occurs. Consider the following code:

```java
public class Animal {

String name;

public Animal(String name) {
this.name = name;
}

}

public class Cat extends Animal{



Cat() { //this causes a compilation error

}

}
```

Here, the `Animal` class has a constructor that accepts an argument. The `Cat` class has a no arguments constructor. However, a compilation error occurs in the `Cat` class. This is because there is no default no-arguments constructor in the `Animal` class. Also, Java is unable to insert a default constructor since there is a constructor with arguments in the base class. You can fix this by explicitly adding a no arguments constructor in the `Animal` class or by invoking the `Animal` constructor from the `Cat` constructor explicitly

## Conclusion

So in this article, we saw how constructors are used in inheritance in Java. We understood the various scenarios for Java constructor inheritance. In summary, when you create an object of a subclass, Java implicitly invokes the base class constructor. If there is no constructor in the base class, Java supplies a default no arguments constructor in the base class and inserts a call to this constructor.

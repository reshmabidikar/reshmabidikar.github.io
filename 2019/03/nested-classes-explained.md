---
title: "Nested Classes explained"
date: "2019-03-05"
categories: 
  - "java_language_features"
tags: 
  - "core-java"
  - "inner-class"
  - "nested-class"
---

Quite often, we come across the term "Nested Class" in Java. It is a very common interview topic as well. So in this

blog post, I will be explaining what a nested class is in Java.

#### What is a Nested Class?

As the word suggests, a nested Java class is a class which lies within another Java class. Consider the following code snippet:

````
class OuterClass {

    class NestedClass{

    }
}
````

The class **NestedClass** is like any other member of the **OuterClass**. It has access to other members that is methods and variables of the **OuterClass** even if a member is a private member. On compiling this code snippet, the compiler creates two class files. One will be the **OuterClass.class** and the other will be the **OuterClass$NestedClass.class**. If you have more than one nested class, the compiler creates a separate class file for each one. However, each of them will be prefixed with the name of the enclosing class and the $ sign.

#### Why do we need nested classes?

The following are some reasons where you will need Nested classes:

1. Logical grouping of classes - If a class is useful to only one class, then it is logical to embed it in that class and keep the two together.
2. More readable and maintainable code - Nesting small classes within top level classes places the code closer to where it is used.
3. Increased Encapsulation - Wrapping together data & code that operates on the data together as a single unit is referred to as encapsulation. So by including a class within another class, we are wrapping together the code that operates on the data into a single unit.

#### Static Nested Classes

A nested class can be a **static or non-static** class. As you probably know, a static variable is the same for all objects of a class. Static nested classes also belong to the class and not to any one instance of the class. They belong to the class that encloses them and not its objects.

````

public class OuterClass {

    private int outerField; 
    private static int staticOuterField;

    static class StaticNestedClass {

    private int nestedField;

    public void nestedMethod() { 
        // System.out.println("Value of outerField is "+outerField); //causes compilation error 
        System.out.println("Value of staticOuterField "+staticOuterField); 
        System.out.println("Value of nestedField is "+nestedField); }

    } 
    public static void main(String[] args) { 
        OuterClass.StaticNestedClass object = new OuterClass.StaticNestedClass();object.nestedMethod();
    }
}
````

Here, we have declared an outer class called **OuterClass** and a static nested class called **StaticNestedClass**. The **OuterClass** has two fields, **outerField** which is an instance field and**staticOuterField** which is a static field. The **NestedClass** has a field called**nestedField** and a method called **nestedMethod**. The**nestedMethod** has Sysout statements which print the values of all 3 fields. Since the **NestedClass** is static, it cannot access the non static field in the **OuterClass**. so there is a compilation error at the line where the non static field is accessed by the **NestedClass**.

A static nested class cannot access the enclosing class members directly. It first needs to create an instance of the outer class and then use that instance to access the outer class members. In the main method, an object of the **NestedClass** is created using the following syntax:

````
OuterClass.StaticNestedClass object = new OuterClass.StaticNestedClass();
````

#### Inner Classes

Non-static nested classes are called **Inner classes**. Consider the following code snippet:

````
public class OuterClass {

    private int outerField; 
    private static int staticOuterField;

    class InnerClass {

    private int innerField; 
    // private static nestedField;//causes compilation error;

    public void innerMethod() { 
        System.out.println("Value of outerField is "+outerField); 
        System.out.println("Value of staticOuterField "+staticOuterField); 
        System.out.println("Value of innerField is "+innerField); }
    }

    public static void main(String[] args) { 
        OuterClass outerObject = new OuterClass(); 
        OuterClass.InnerClass innerObject = outerObject.new InnerClass(); 
        innerObject.innerMethod();
    }
} 
````

In the code snippet above, the class **InnerClass** is an inner class. As opposed to static nested classes, an inner class belongs to instances of the enclosing class. As with instance methods and variables, an inner class has direct access to an objects methods and fields. Also, because an inner class is associated with an instance, it cannot define any static members itself.   Objects that are instances of an inner class exist within an instance of the outer class. To instantiate an inner class, you must first instantiate the outer class.  So in the main method, we have written the following code:

````
OuterClass outerObject = new OuterClass(); 
OuterClass.InnerClass innerObject = outerObject.new InnerClass();
````

#### Types of Inner Classes

There are two types of inner classes, Local and anonymous classes.

##### Local Classes

Local classes are declared within a block of code and are visible only within that block. So if you have an inner class within a method it is known as a local class. Typically, a local class is defined within a method but it can also be defined within a static block or even the constructor of a class.

Consider the following code snippet:

````
public class OuterClass {

    public void OuterMethod() {
        class LocalClass {
        }
    }
}
````

Some important points to note about local classes:

- Since local classes are inner classes, they can access all the members of the containing class. In addition, they can also access any local variables or method parameters that are in the scope of the local method definition and declared as final.
- A local class is visible only within the block that defines it, it can never be used outside the block
- Local classes cannot be declared public,protected,private or static. These modifiers are for members of classes, they are not allowed with local variable declarations or local class declarations.

##### Anonymous classes

An anonymous class is a local class without a name. So you can declare a local class within the body of a method without naming it.Anonymous inner class always extend a class or implement an interface. Consider the following code snippet:

````
public abstract class Animal {

    abstract void speak();
}

public class AnimalDemo {

    public static void main(String[] args) { 
    Animal dog = new Animal() { 
        void speak() { 
            System.out.println("woof woof"); 
        } 
    }; 
    dog.speak(); 
 }

}

````

So here we have an abstract class called Animal. It has an abstract method called speak. We have another class called AnimalDemo. In the main method we are creating a new Animal object called Dog and providing the implementation for the speak method there itself. So, instead of creating a separate class called Dog that extends the Animal class, we are creating an Anonymous inner class for Dog. Similarly, Anonymous inner classes can be created by implementing an interface too.

---
title: "Java  8 Method Reference operator explained"
date: "2019-05-27"
categories: 
  - "java-8-features"
  - "java-interview-questions"
---

Java 8 introduced an operator represented by a double colon(::), known as the "Method Reference" operator.   In this blog post, I will be explaining this operator. A basic understanding of [lambda expessions](https://learnjava.co.in/java-8-lambda-expressions-explained/) is required in order to understand method references.

\[table id=24 /\]

# What is the Method Reference operator?

The method reference operator can be used to refer to a method. Normally, you can implement a functional interface using a lambda expression. Sometimes, your code may already have a method that has the same functionality that you want your lambda expression to implement. So instead of re-writing the code using a lambda expression, you can implement the lambda expression via the existing method.

# Code Sample

Consider the following code:

```
@FunctionalInterface
public interface Shape {
  public void draw();
}

```

This is a functional interface called Shape. It has a single method called "draw()".

Now consider the following code for a class **ShapeDrawingDemo**

```
public class ShapeDrawingDemo {


  public static void main(String[] args) {
    Shape rectangle = () -> System.out.println("Drawing Rectangle");
    rectangle.draw();
  }

}

```

ShapeDrawingDemo has the main method. It creates a `Shape`called `rectangle`and implements it via a lambda expression that simply executes a Sysout statement.

Now suppose your code already has a method as follows:

```
public class ShapeDrawingDemo {
  
  public static void drawingRectangle(){
    System.out.println("Drawing Rectangle");
  }
  

  public static void main(String[] args) {
    Shape rectangle = () -> System.out.println("Drawing Rectangle");
    rectangle.draw();
  }
}
```

So the ShapeDrawingDemo class already has a method called `drawingRectangle` that does the same thing as the lambda expression i.e. it prints a Sysout statement. So the main method can be re-written using a method reference as follows:

```
public static void main(String[] args) {
  Shape rectangle = ShapeDrawingDemo::drawingRectangle;
  rectangle.draw();
}
```

Here, instead of using a lambda expression to implement the Shape interface, the code uses a method reference. So the code implements the method draw in the functional interface Shape via the drawingRectangle method in ShapeDrawingDemo class.

# Types of Method References

## Static method Reference

Static method Reference occurs when the code references a static method in a class via the :: operator. In the code sample above, the `drawingTriangle`is a static method and so it is an example of a static method reference.

**Syntax**

`classname::staticmethodname;`

## Instance Method Reference

Instance method reference occurs when the code references an instance method of a class is referenced via the :: operator.

**Syntax**

`objectname::instancemethodname;`

Consider the following code:

```
public class ShapeDrawingDemo {
  
  public void drawingTriangle(){
    System.out.println("Drawing Triangle");
  }
  

  public static void main(String[] args) {
    Shape rectangle = () -> System.out.println("Drawing Rectangle");
    rectangle.draw();
    ShapeDrawingDemo sd = new ShapeDrawingDemo();
    Shape triangle = sd::drawingTriangle;
    triangle.draw();

  }

}
```

Here, the `drawingTriangle`method is no longer static. The main method creates an object of the ShapeDrawingDemo class sd. This is used in the method reference.

## Reference to an instance method of an arbitrary object

This occurs when the code references an instance method of a class but not on any specific object via the :: operator.

**Syntax**

`classname::instancemethodname;`

Consider the following code snippet:

```
public class MethodRefDemo {

  public static void main(String[] args) {
    List<String> strList = Arrays.asList("Apple","Orange","Mango","Banana");
  strList.forEach(String::toUpperCase);
  }

}
```

The main method has a forEach method. The code invokes the `toUpperCase`method on each String object in the list. The code does not invoke the `toUpperCase`method on a specific `String`object and so it specifies the `String`class in the method reference.

## Constructor Reference

Constructor reference occurs when the code references a constructor of a class via the :: operator.

**Syntax**

`classname::new;`

Consider the following code:

```
public class Person {
  
  private String name;
  private int age;
  
  public Person(String name, int age) {
    super();
    this.name = name;
    this.age = age;
  }
        //getter and setter methods

}
```

This is a Person class with 2 fields, name and age.

Now consider the following PersonSupplier interface:

```
@FunctionalInterface
public interface PersonSupplier {
  public Person createPerson(String name,int age);
}
```

This is a functional interface. It has a method createPerson, that accepts values for name and age and returns a Person object.

Using a lambda expression, you can implement the PersonSupplier interface as follows:

```
PersonSupplier personSupplier = (name,age) -> new Person(name,age);
```

You can re-write the above code using a constructor reference as follows:

```
public class ConstructorRefDemo {
  
    public static void main(String[] args) {
    PersonSupplier personSupplier = Person::new;
    Person person = personSupplier.createPerson("abc", 25);
    
  }

}
```

Instead of using a lambda expression, the code uses a constructor reference.

You can get the source code for this example along with other code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

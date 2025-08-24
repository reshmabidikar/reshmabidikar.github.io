---
title: "Java 8 BiFunction Example"
date: "2019-06-09"
categories: 
  - "java-8-examples"
tags: 
  - "functional-interface"
  - "interfaces"
  - "java8"
---

In this blog post, I will be explaining how the Java 8 functional interface BiFunction works. To know more about functional interfaces, you can refer [this](../java8-features/java-8-functional-interface.md) blog post.

The [BiFunction](https://docs.oracle.com/javase/8/docs/api/java/util/function/BiFunction.html) is a specialization of the [Function](java-8-function-interface-example.md) interface that accepts 2 arguments. Just like [Function](java-8-function-interface-example.md) it provides a method called apply. This method accepts 2 arguments of any data type and returns a result. So it basically applies the logic in the apply method to the input parameters and returns the result.

#### BiFunction Interface Example with two integer inputs and Integer output

Consider the following code snippet:

```java
private static void example1() { 
    BiFunction<Integer,Integer,Integer> multiplier = (a,b) -> {return a\*b;}; 
    int input1 = 6; 
    int input2 = 8; 
    System.out.println("Result of multiplying "+input1+" and "+input2 +" is "+multiplier.apply(input1,input2) ); 
 }
```

Here, we have written a BiFunction implementation that accepts 2 integer values, multiplies them and returns the result. The BiFunction.apply method is implemented using a lambda expression. This expression accepts two integer values, multiplies them and returns the result. So when you execute this code, it will print the following output:

```
Result of multiplying 6 and 8 is 48
```

#### BiFunction Interface Example with String and Character input and String array as the output

Consider the following code snippet:

````java

private static void example2() { 
    String input = "hello,world"; 
    BiFunction<String,Character,String[]> stringSplitter = (inputStr,inputChar) -> {String[] list = inputStr.split(inputChar.toString()); 
    return list;
}; 
    String[] result = stringSplitter.apply(input, new Character(',')); 
    for(String str:result) { 
        System.out.println("String is "+str); 
    } 
}

````

This code splits a String into a String array based on the character specified. It returns the String array. So when this code is executed, it will print the following output:

```
String is hello
String is world
```

#### BiFunction Interface Example with a String and Integer as input and Object as output

Consider the following code snippet:

````java

public class Person {

private String name; private int age;

    public Person(String name, int age) { 
        super(); 
        this.name = name; 
        this.age = age; 
    }

// Getter setter methods

}

private static void example3(){ 
    
    String input = "hello,world";
    BiFunction<String,Integer,Person> personCreator = (name,age) -> {return new Person(name,age);}; 
    Person person = personCreator.apply("Mickey Mouse",35); 
    System.out.println("Person object created with name as "+person.getName()); 
}
````

This `BiFunction` implementation accepts a String and Integer as input, creates a Person object with those values and returns that Person object. So when you execute this code, it will print the following output:

```
Person object created with name as Mickey Mouse
```

You can get the source code for this example along with other code for other Java 8 examples at the GitHub repository [here](https://github.com/reshmabidikar/Java8Demo).

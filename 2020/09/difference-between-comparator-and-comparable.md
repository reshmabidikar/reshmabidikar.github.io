---
title: "Difference between Comparator and Comparable"
date: "2020-09-23"
categories: 
  - "core-java"
  - "java-interview-questions"
  - "java_language_features"
  - "java-collection-examples"
---

Java has two interfaces that you can use for sorting custom objects. These are the Comparator and Comparable interface. In this article, I will be explaining the differences between the two.

## Basic difference between Comparator and Comparable

The main difference between the Comparator and Comparable interface is that you can use Comparator  to compare two independent objects. The Comparable on the other hand is used to compare the current object with another object.

Consider the following **Person** class:

```
public class Person {
  
  private String name;
  private int age;
  
  public Person(String name, int age) {
    super();
    this.name = name;
    this.age = age;
  }
}
```

Suppose you want to sort **Person** objects on the basis of the age fields. Let us understand how you can achieve this using both Comparator and Comparable.

### Sorting Using Comparator

In order to sort using Comparator, you will first need to create a class that implements the Comparator interface.  The following code demonstrates this:

```
public class PersonComparator implements Comparator<Person> {

  @Override
  public int compare(Person person1, Person person2) {
    return person1.getAge() - person2.getAge();
  }

}
```

So **PersonComparator** simply implements the Comparator interface and overrides the **compare** method. You can now use this to sort Person objects as follows:

```
Person person1 = new Person("Mickey",56);
Person person2 = new Person("Donald",45);
    
Comparator<Person> personComparator = new PersonComparator();
    
int compare = personComparator.compare(person1, person2);
```

This code creates two **Person** objects. It then uses the **PersonComparator** to compare these Person objects.

### Sorting Using Comparable

In order to sort using Comparable, you need to make the Person class implement the Comparable interface. The following code demonstrates this:

```
public class Person implements Comparable<Person>{
  
  private String name;
  private int age;

        //constructor, getters and setters

  @Override
  public int compareTo(Person p) {
    return this.age - p.age;
  }



}
```

 

So Person class implements the Comparable interface and overrides the **compareTo** method. You can use it to sort Person objects as follows:

```
Person person1 = new Person("Mickey",56);
Person person2 = new Person("Donald",45);
    
int compare = person1.compareTo(person2);
```

This code creates two **Person** objects. It then invokes the **compareTo** method on **person1**

## Other Differences Between Comparator and Comparable

In addition to the main difference demonstrated above, there are several differences between Comparator and Comparable. These are as follows:

- Starting with Java 8, Comparator has been designated as a functional interface, so you can use a [lambda expression](http://localhost/learnjava/java-8-lambda-expressions-explained/) to implement it. On the other hand, Comparable is not a functional interface.
- Starting with Java 8, a lot of [static](http://localhost/learnjava/java-8-static-interface-methods/) and [default](http://localhost/learnjava/java-8-default-method-in-interface-explained/) methods have been added to the Comparator interface that support various functionalities. Comparable on the other hand, does not have any static/default methods
- Comparator uses the **compare** method for performing the comparison, Comparable on the other hand uses the **compareTo** method
- Comparator is part of the **java.util** package, Comparable is part of the **java.lang** package
- While using Comparable, you need to modify the class that needs sorting. On the other hand, you can use Comparable to sort any class without having the sorting logic within the class. So, Comparable is useful when the class that needs sorting is aware of the sorting logic.

## Conclusion

In this article, we took a look at the Comparable and Comparator interfaces. We saw how both work and what are the main differences between the two.

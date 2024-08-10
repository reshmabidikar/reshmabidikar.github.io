---
title: "How to sort a List on objects in Java using a Compator"
date: "2019-04-04"
categories: 
  - "collections-framework"
  - "java-interview-questions"
tags: 
  - "comparator"
  - "java-collections-framework-en"
  - "sortinglist"
---

In this blog post, I will be explaining how you can sort a List of objects in Java using the [Comparator](https://docs.oracle.com/javase/8/docs/api/java/util/Comparator.html) interface.

#### Input List

Suppose, there is a Person class as follows:

\[java\]

public class Person {

private String firstName; private String lastName; private int age;

public Person(String firstName,String lastName,int age){ this.firstName=firstName; this.lastName=lastName; this.age=age;

//getter and setter methods public String toString(){ return firstName+" "+lastName+":"+age; } }

}

\[/java\]

And you have a list of Person objects as follows:

\[java\] Person person1 = new Person("Mickey", "Mouse",34); Person person2 = new Person("Donald", "Duck",45); Person person3 = new Person("Peppa", "Pig",12); List<Person> people = new ArrayList<Person>(); people.add(person1); people.add(person2); people.add(person3); \[/java\]

#### Using Comparator to sort in increasing order of age

And suppose you want to sort them in the increasing order of age. You can use a Comparator as follows:

\[java\]

Collections.sort(people, new Comparator<Person>() { public int compare(Person person1,Person person2){ return person1.getAge() - person2.getAge();

} });

\[/java\]

Here a [Comparator](https://docs.oracle.com/javase/8/docs/api/java/util/Comparator.html) is used. The [Comparator](https://docs.oracle.com/javase/8/docs/api/java/util/Comparator.html) interface has a [compare](https://docs.oracle.com/javase/8/docs/api/java/util/Comparator.html#compare-T-T-) method. This method returns a positive integer if the first argument is greater than the second, it returns 0 if both the arguments are the same and it returns a negative integer if the first argument is smaller than the second.

Here, we are simply subtracting the ages i.e. the age of the second person object from the age of the first person object. So if the age of the first person object is greater than that of the second person object, it will return a positive integer.

This comparator is then passed to the Collections.sort method. So the Collections.sort will use this Comparator implementation for sorting the Person objects in the input list.

Here is the complete code:

\[java\]

public class SortObjectsDemo {

public static void main(String\[\] args) { Person person1 = new Person("Mickey", "Mouse",34); Person person2 = new Person("Donald", "Duck",45); Person person3 = new Person("Peppa", "Pig",12);

List<Person> people = new ArrayLis<Person>(); people.add(person1); people.add(person2); people.add(person3);

System.out.println("Before sorting"); System.out.println(people); Collections.sort(people,new Comparator<Person>() { public int compare(Person person1,Person person2){ return person1.getAge() - person2.getAge();

} }); System.out.println("After sorting"); System.out.println(people); }

}

\[/java\]

When you run this code, it prints the following output:

```
Before sorting
[Mickey Mouse:34, Donald Duck:45, Peppa Pig:12]
After sorting
[Peppa Pig:12, Mickey Mouse:34, Donald Duck:45]


```

#### Sorting in decreasing order of age

If you want to sort in the decreasing order of age, you can change the Comparator as follows:

\[java\]

Collections.sort(people, new Comparator<Person>() { public int compare(Person person1,Person person2){ return person2.getAge() - person1.getAge();

} });

\[/java\]

This will produce the following output:

```
Before sorting
[Mickey Mouse:34, Donald Duck:45, Peppa Pig:12]
After sorting
[Donald Duck:45, Mickey Mouse:34, Peppa Pig:12]
```

#### Sorting based on first name

Also, if you want to sort based on the first name, you can change the comparator as follows:

\[java\]

Before sorting \[Mickey Mouse:34, Donald Duck:45, Peppa Pig:12\] After sorting \[Donald Duck:45, Mickey Mouse:34, Peppa Pig:12\]

\[/java\]

This code prints the following output:

```
Before sorting
[Mickey Mouse:34, Donald Duck:45, Peppa Pig:12]
After sorting
[Donald Duck:45, Mickey Mouse:34, Peppa Pig:12]
```

#### Implementing Comparator using a lambda expression

You can also implement a Comparator using a Java 8 lambda expression. So you can write the following code:

\[java\]

Collections.sort(people,(p1,p2) ->{return p1.getFirstName().compareTo(p2.getFirstName()); });

\[/java\]

So this code produces the same output as before:

```
Before sorting
[Mickey Mouse:34, Donald Duck:45, Peppa Pig:12]
After sorting
[Donald Duck:45, Mickey Mouse:34, Peppa Pig:12]
```

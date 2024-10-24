---
title: "Java 8 Stream API Distinct method with code samples"
date: "2019-12-14"
categories: 
  - "java-8-examples"
  - "java8"
---

In this article, I will be demonstrating the distinct method provided by Java 8 Stream API.

In order to understand the Stream API in detail, refer to [this](https://learnjava.co.in/java-8-streams/) blog post.

## Introduction

The Stream interface has a method called distinct. You can use this method to eliminate duplicates from a Stream. So you can use this to eliminate duplicates from a Collection.

## Using Stream.distinct with Integers

The following code sample demonstrates using the Stream.distinct with an Integer List:

```
List<Integer> input = Arrays.asList(3,12,11,45,12,5,3,9,20,11,3);
System.out.print("Input:");
input.forEach(num -> System.out.print(num+" "));
System.out.println();
System.out.print("Output:");
List<Integer> distinctInput = input.stream().distinct().collect(Collectors.toList());
distinctInput.forEach(num -> System.out.print(num+" "));

```

So first, the code invokes the stream method on the input List. Then, the code invokes the distinct method to obtain unique elements in the Stream. Finally, the code invokes the collect method to convert the Stream back to a List. So this code prints the following output:

```
Input:3 12 11 45 12 5 3 9 20 11 3 
Output:3 12 11 45 5 9 20
```

## Using Stream.distinct with Objects

In addition to primitive types, you can also use the Stream.distinct method with object types. Suppose you have a Person class as follows:

```
public class Person {
  
  private String name;
  private int age;
  
  public Person(String name, int age) {
    super();
    this.name = name;
    this.age = age;
  }
// getters and setters
  
  /* (non-Javadoc)
   * @see java.lang.Object#toString()
   */
  public String toString(){
    return name;
  }
}
```
The following code demonstrates adding some Person objects to a list and then eliminating duplicates from the List:

```
		List<Person> personList = new ArrayList<Person>();
		Person jane = new Person("Jane",32);
		personList.add(jane);
		Person bill = new Person("Bill",28);
		personList.add(bill);
		Person joe = new Person("Joe",36);
		personList.add(joe);
		personList.add(jane);
		System.out.print("Input:");
		personList.forEach(person -> System.out.print(person+" "));
		List<Person> output = personList.stream().distinct().collect(Collectors.toList());
		System.out.println();
		System.out.print("Output:");
		output.forEach(person -> System.out.print(person+" "));
```

So here, the code creates 3 person objects. The code adds the person object "jane" twice to the input List. The code then invokes the Stream.distinct method to eliminate duplicates and finally converts the Stream to a List. So this code prints the following output:

```
Input:Jane Bill Joe Jane 
Output:Jane Bill Joe


```

## Further Learning

- [Java Functional Programming with Lambdas and Streams](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Ffunctional-programming-with-java%2F)
- [Java 8 lambdas and Streams](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava8_lambdasandstreams%2F)

## Conclusion

So in this article, we saw how to use the Java 8 Stream API distinct method. We saw how to use the Stream distinct method with objects as well as primitive types.

---
title: "Java 8 Stream API explained with code samples"
date: "2019-05-03"
categories: 
  - "java-8-features"
  - "java-interview-questions"
tags: 
  - "java-8"
  - "java-8-streams"
---

Java 8 introduced the Stream API. The Stream API along with lambda expressions can be used to perform bulk operations on the elements in a Collection. Not only that, you can pipeline the Stream operations to perform a number of sequential operations.

## How do Streams work?

A new method called stream has been added to all the Collection interfaces, this returns a[java.util.Stream](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html) interface. There are various methods on this stream interface that perform the corresponding operation on the Stream instance.

Suppose you have an integer array. Suppose you want to find all the elements that are greater than the value 9. Before Streams and Java 8, you would need to write code like the following:

````

public class FilterStreamDemo {

    public static void main(String[] args) { 
        List<Integer> input = Arrays.asList(5, 3, 11, 15, 9, 2, 5, 11);

        List<Integer> output = new ArrayList<Integer>(); 
        for(int num:input) { 
            if(num >= 9) {
                output.add(num);
            } 
        } 
    }
} 
````

So this code iterates through the input list. It checks if each number is greater than 9 and if so adds it to the output list.

Using Streams, we can re-write the above code as follows:

````

public class FilterStreamDemo {

    public static void main(String[] args) { 
        List<Integer> input = Arrays.asList(5, 3, 11, 15, 9, 2, 5, 11); 
        Stream<Integer> stream = input.stream().filter(num -> num >= 9); 
    }
}
````

The code first invokes the `input.stream` method which returns a `Stream` instance. There is a [filter](https://reshmabidikar.github.io/2019/06/stream-api-filter-example.html) method present on the [Stream](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html) interface. This accepts a [Predicate](https://reshmabidikar.github.io/2018/10/java-8-predicate-example.html) instance. Here, we are passing a lambda expression for the [Predicate](https://reshmabidikar.github.io/2018/10/java-8-predicate-example.html). So the lambda expression matches any element which is greater than 9. Thus, the [filter](https://reshmabidikar.github.io/2019/06/stream-api-filter-example.html) method runs this Predidate on every element in the input Stream and creates a new Stream with the output. So the result is a Stream that only has elements greater than 9. Compared to the earlier code, this code is much cleaner and easy to read.

## Iterating Through a Stream

Just like Java 8 provides the forEach method for iterating through a Collection, it also provides this method on the Stream interface. So using this forEach, you can iterate through a Stream. Consider the following code snippet:

````
public class FilterStreamDemo {

    public static void main(String[] args) { 
        List<Integer> input = Arrays.asList(5, 3, 11, 15, 9, 2, 5, 11); 
        Stream<Integer> stream = input.stream().filter(num -> num >= 9); 
        stream.forEach(num -> System.out.println(num));
    }
} 
````

Here, the `Stream.filter` is used to filter the Stream and create a new Stream with numbers greater than 9. Then the code invokes the forEach method on the Stream. Just like the forEach method on the Collection interfaces, this forEach method accepts a Consumer object. Here, the code is passing a lambda expression for the Consumer instance. This lambda expression simply prints the corresponding element.

So when you execute this code, it will print the following output:

````
11 15 9 11
````

## Chaining Operations

The real power of Streams is that it allows you to chain a number of operations. For example, consider the following code:

````
public class StreamChainingOperationsDemo {

    public static void main(String[] args) { 
        List<Integer> input = Arrays.asList(5, 3, 11, 15, 9, 2, 5, 11); 
        long count = input.stream().filter(num -> num >= 9).distinct().count(); 
        System.out.println("count ="+count);
    }
} 
````

Here, the code first invokes the filter method. This is followed by the distinct method which returns a Stream with unique elements. So basically, the distinct method eliminates duplicates in the input Stream. Finally, the code invokes the count method. This returns the number of elements in the input Stream. So when you execute this code, it will print the following output:

````
count =3
````

## Converting Stream to a Collection

You can convert the results of chaining several Streams back to a Collection. There is a method called collect on the Stream interface for this. So consider the following code snippet:

````
public class CollectStreamDemo {

    public static void main(String[] args) { 
        List<Integer> list = Arrays.asList(5, 3, 11, 15, 9, 2, 5, 11); 
        List<Integer> distinctList = list.stream().distinct().collect(Collectors.toList()); distinctList.forEach(num -> System.out.println(num)); 
        }
} 
````

Here, the code invokes the distinct method to obtain the unique elements in the input. Then the code invokes the collect method.This accepts a Collector instance. There is a Collectors class. It has a method called toList which returns a Collector that converts the Stream to a List. So when you execute this code, it prints the following output:

````
5 3 11 15 9 2
````

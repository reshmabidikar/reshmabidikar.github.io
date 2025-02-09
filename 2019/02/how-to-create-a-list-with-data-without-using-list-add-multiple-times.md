---
title: "How to create a list with data without using list.add multiple times"
date: "2019-02-12"
categories: 
  - "collections-framework"
  - "java-collection-examples"
---

In this blog post, I will be explaining how you can easily create a List of elements with some data. Consider the following code snippet:

````
public static void main(String[] args) { 
    List<Integer> input = new ArrayList<Integer>(); 
    input.add(3); 
    input.add(9); 
    input.add(5); 
    input.add(15); 
    input.add(11);

}
````

The code above creates a new [ArrayList](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html) called input. It invokes the add method multiple times in order to add data to this list. This code does not look very clean. The above code can be re-written as follows:

````
List<Integer> input = Arrays.asList(3,9,5,15,11);
````

Here, the [Arrays.asList](https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html#asList-T...-) method is invoked. The [Arrays](https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html) class has methods for manipulating arrays. It also has the [asList](https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html#asList-T...-) method. This returns a List which is backed by the specified array.So in this case, the [Arrays.asList](https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html#asList-T...-) returns an [ArrayList](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html) that has the elements specified.

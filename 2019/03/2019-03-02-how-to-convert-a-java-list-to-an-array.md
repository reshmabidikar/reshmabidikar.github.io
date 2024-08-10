---
title: "How to convert a Java list to an array"
date: "2019-03-02"
categories: 
  - "collections-framework"
  - "java-collection-examples"
tags: 
  - "java-arrays"
  - "java-collections-framework-en"
---

In this blog post, I will be explaining how you can convert a Java list to an array. To see how to convert an Array to a List, click [here](https://learnjava.co.in/how-to-convert-an-array-to-a-list/).

 

There are a couple of ways to do this. Consider the following code snippet:

\[java\]

public class ListToArrayDemo {

public static void main(String\[\] args) { //Method 1 List<Integer> list = Arrays.asList(5,3,11,15,9); Object\[\] objects = list.toArray();

//Method 2 Integer\[\] integers = new Integer\[list.size()\]; integers = list.toArray(integers);

//Method 3 Integer\[\] integers2 = new Integer\[list.size()\]; for(int i = 0; i < list.size();i++){ integers2\[0\] = list.get(0); }

} }

\[/java\]

This code shows 3 ways to convert a List having integers to an array. Though I've used an Integer List here, you can use a List that stores any type of data.

**Method 1** 

The [toArray](https://docs.oracle.com/javase/8/docs/api/java/util/List.html#toArray--) method available on the list interface is used in this approach. This method returns an Object array. The downside to this approach is that the resultant array is an Object array. So you loose the type of data present in the original list.

**Method 2**

Here, the [toArray](https://docs.oracle.com/javase/8/docs/api/java/util/List.html#toArray-T:A-) method available on the list interface which accepts an input array is used. So we are first creating an integer array and passing this to the toArray method. The advantage of this approach is that the resultant array is also of the same type as the data in the input List.

 

**Method 3**

Here, we are manually iterating through the input List and adding each element to the array. So we are using a for loop. This retrieves each element in the list and adds it to an array.

 

**Which approach to use?**

I would recommend using method 2. This directly gives an array of the desired type and does not require any manual code.

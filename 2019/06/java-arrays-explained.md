---
title: "Java Arrays explained with code samples"
date: "2019-06-05"
categories: 
  - "java_language_features"
tags: 
  - "arrays"
---

## Introduction

An array is essentially a list of values referred to by a common name. Java arrays can be one-dimensional or multi-dimensional.

## Declaring and Initializing an Array

Consider the following code snippet:

```
int myArray[];

myArray = new int[10];
```

Here, **int** refers to the type of data that will be stored in the array and **myArray** is the name given to the array. In the second line myArray is allocated memory. The new keyword is used.**\[10\]** \- indicates the size of the array. So this statement creates a new array with space for 10 integer values.

The declaration and memory allocation can also be combined into a single statement as follows:

```
int myArray[] = new int[10];
```
## Accessing the elements of an array

Each **value** within the array is called an **element** in the array. You can access any element in an array by specifying its **position** within **square brackets**. The array index begins at 0, so the 1st element is at position 0, the 2nd at position 1 and so on.

Consider the following code snippet:

```
myArray[2] = 8;

System.out.println("Element at myArray[2]="+myArray[2]);
```

The element at index 2 i.e. the 3rd element in the array is assigned the value 8. So when you execute this code, it will print the following output:

```
Element at myArray[2]=8
```

## Initializing an Array at the time of declaration

Arrays can also be initialized when they are declared as follows:

```
int myArray[] = {2,4,6,8,10};
System.out.println("Element at myArray[3]="+myArray[3]);
```

Here, a list of **comma-separated** **values** surrounded by curly braces is used. Size is not specified in the square brackets explicitly; it is the same as the number of elements in the curly brackets.

When you execute this code, it will print the following output:

```
Element at myArray[3]=8
```

## Obtaining the Length of an Array

There is a **length** method provided on the array object. This can be used to determine the size of the array.

```
int myArray[] = {2,4,6,8,10};
System.out.println("Size of the array is "+myArray.length);
```

So when this code is executed, it will print the following output:

```
Size of the array is 5
```

## Conclusion

So, in this article, we understood what Java arrays are and how they can be used.

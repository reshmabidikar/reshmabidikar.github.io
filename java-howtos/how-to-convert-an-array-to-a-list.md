---
title: "How to convert an Array to a List"
date: "2018-08-17"
categories: 
  - "collections-framework"
  - "java-collection-examples"
tags: 
  - "core-java"
  - "java-arraylist"
  - "java-collections-framework-en"
  - "java-loops-en"
---

If you have a non primitive array type, you can use the following code to convert it to a list:

````java

public class ArrayToListConverter { public static void main(String args[]) {
    Integer[] intArr = {2, 4, 6, 8, 10};
    List<Integer> intList = new ArrayList<Integer>();

    //Method 1 - Using for loop 
    for (int i : intArr) {
        intList.add(i);
    }

    //Method 2 - Via Arrays.asList 
    intList = Arrays.asList(intArr);

}

}

````

**Method 1**

Here, we are manually iterating through the elements in the list and adding them to an int array.

**Method 2**

Here, we are using the Arrays.asList method. This returns a list corresponding to the array passed in. Note that this method wont work if the array is of primitive type like this:

````java

int[] intArr = {2,4,6,8,10};

````

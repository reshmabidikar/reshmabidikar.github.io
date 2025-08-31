---
title: "How to find the largest number in an array"
date: "2018-08-20"
categories: 
  - "java-examples"
tags: 
  - "core-java"
  - "java-arrays"
  - "java-if-else-en"
  - "java-loops-en"
---

The following code demonstrates how to find the largest number in an array:

````java

package demo;

public class LargestNumberDemo {

public static void main(String[] args) { 
    Integer[] intArr = {45,21,88,210,550,1,34}; 
    int max = 0; 
    for(int num:intArr) { 
        if(num > max) max = num; 
    } 
    System.out.println("Biggest number is "+max);
    }
}
````

So the for loop iterates through the array. Initially, the variable max is set to 0. Each number is compared with 'max' and if it is greater than max, then it is assigned to 'max'. This process is repeated till all the elements in the array are exhausted.

This will print the following output:

```
Biggest number is 550
```

You can use this code to find the largest number from any Collection type like Set or List.

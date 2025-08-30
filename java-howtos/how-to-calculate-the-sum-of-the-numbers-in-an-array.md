---
title: "How to calculate the sum of the numbers in an array"
date: "2019-02-11"
categories: 
  - "java-examples"
tags: 
  - "java-loops-en"
---

In this blog post, I will be explaining how you can calculate the sum of numbers in an array. Consider the following code snippet:

````java
package demo;

public class SumDemo {

    public static void main(String[] args) { 
        int numbers[] = {5,4,7,9,12};
        int sum = 0; 
        for(int number:numbers) { 
            sum += number; 
        } 
        System.out.println("sum="+sum);
    }
}
````

A variable called sum is used to store the sum of numbers. It is initialized to 0. There is a for loop used. This iterates through the input list. It adds each number in the list to the sum variable.

This code will print the following output:

```
sum=37
```

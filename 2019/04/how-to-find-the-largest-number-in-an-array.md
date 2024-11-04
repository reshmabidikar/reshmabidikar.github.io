---
title: "How to find the largest number in an array"
date: "2019-04-17"
categories: 
  - "java-examples"
tags: 
  - "javaarray"
  - "largestelementinarray"
---

In this blog post, I will be demonstrating how you can find the largest number in an array or list. Consider the following code snippet:

````
package demo;

public class FindLargestNumberDemo {

    public static void main(String[] args) {
        int[] myArray = {2, 4, 6, 8, 10, 45, 9, 18, 90, 12};

        int largest = 0;
        for (int num : myArray) {
            if (num < largest) {
                largest = num;
            }
            System.out.println("Largest number is " + largest);

        }
    }
}

````



Here, we are declaring an array with a list of values. We are then iterating through the elements in the array. We are also declaring a variable called largest and setting its value to 0. Each element in the array is compared to the variable largest. If is is greater than largest, the variable largest is assigned the current element. This is continued for all the elements in the input array. So when this code is executed, it will print the following output:

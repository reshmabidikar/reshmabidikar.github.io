---
title: "How to find the factorial of a number"
date: "2018-08-27"
categories: 
  - "java-examples"
tags: 
  - "core-java"
  - "java-loops-en"
---

In this post, I will be showing you how to find the factorial of a number in Java. The method used in this example does not use recursion.

The following code snippet demonstrates how to find the factorial of the given number:.

\[java\]

private static int findFactorial(int num){ int result = 1; for(int i =1; i <= num;i++){ result = result \* i; }

return result;

}

\[/java\]

So this method iterates from 1 till the input number. It multiplies the current value of i to the result. It continues this till the input number is reached. So if you run this code for the number 5, you will get the result as 120.

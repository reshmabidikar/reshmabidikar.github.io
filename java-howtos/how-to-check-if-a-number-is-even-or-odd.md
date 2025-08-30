---
title: "How to check if a number is even or odd"
date: "2019-03-20"
categories: 
  - "java-examples"
tags: 
  - "odd-even"
---

This blog post demonstrates how you can check if a number is even or odd via Java.

Consider the following code snippet:

````java

public class EvenOddDemo {

public static void main(String[] args) { 
Scanner scanner = new Scanner(System.in); 
System.out.println("Enter your input:"); 
int num = scanner.nextInt();

if(num % 2 == 0) {
  System.out.println("The input number "+num+" is even");
} else { 
  System.out.println("The input number "+num+" is odd");
} 

scanner.close();

}

}

````

This code first reads an input number using the [Scanner](https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html) class. It then uses the % operator. The % operator returns the remainder of division. So the code checks if the remainder obtained after dividing by 2 is 0. If so, the number is odd, otherwise the number is even.

So if you run the code with input as 4, the following output is printed:

```
Enter your input:
4
The input number 4 is even
```

If you run the code with input as 7, the following output is printed:

```
Enter your input:
7
The input number 7 is odd
```

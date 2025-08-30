---
title: "How to check if a number is a prime number"
date: "2019-01-03"
categories: 
  - "java-examples"
tags: 
  - "core-java"
  - "java-loops-en"
  - "prime-numbers"
---

In this blog post, I will be demonstrating how you can check if a number is a prime number. Consider the following code snippet:

````java
public static void main(String[] args) { 
    Scanner scanner= new Scanner(System.in); 
    System.out.println("Input the number to be checked:");

    int num=scanner.nextInt();
    boolean isPrime = true;

    if (num == 0 || num == 1) { 
        isPrime = false; 
    } else {
        for (int i = 2; i &lt;= num / 2; i++) { 
            if (num % i == 0) { 
                isPrime = false; break; 
            } 
        } 
    }

    if(isPrime) 
        System.out.println("The number "+num+" is prime!"); 
    else 
        System.out.println("The number "+num+" is not prime!");
}

````

The code first accepts a number from the user. It then checks if the number is 0 or 1, both of which are not prime numbers. It then iterates from 2 till the number/2. It checks if the remainder obtained after dividing the input number with the current index of the for loop is 0. If so, the number is not prime and so it exits the for loop.

So if you run the code for the value 13, the following output will be printed:

```
Input the number to be checked:
13
The number 13 is prime!
```

Similarly, if you run the code for the value 9, the following output will be printed:

```
Input the number to be checked:
9
The number 9 is not prime!
```

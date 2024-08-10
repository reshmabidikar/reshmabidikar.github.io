---
title: "Java If else"
date: "2019-05-09"
categories: 
  - "java_language_features"
tags: 
  - "java-if-else-en"
---

In this blog post, I will be explaining how the if else statement works in Java.

# What is if-else

The if-else statement is used to check for a condition. If the condition specified after the "if" keyword is true, the code following the if keyword is executed. If the code following the if keyword is false, the code following the else keyword is executed.

# **Syntax**

\[java\]

if(condition){

//some code here

}

else{ // this part is optional

//some code here

}

\[/java\]

# Code Sample 1

Consider the following code snippet:

\[java\]

int a = 20;

int b = 15;

if(a > b)

{

System.out.println("a is greater than b");

}

else {

System.out.println("a is less than b");

}

\[/java\]

- Variables called **a** and **b** are declared and initialized to 20 and 15 respectively
- The **if** keyword is followed by a condition i.e. **a > b**
- Since **a > b** is true, the code within the **if** block is executed
- If **a > b** was false, the code within the **else** block would have been executed

 

When this above code is executed, it will print the following output:

```
a is greater than b
```

 

If you change the value of b to 25, the code within the else block will be executed. So the following will be printed to the console:

```
a is less than b
```

# Code Sample 2

The **else** statement is optional. If you skip it and if the condition within the if statement is false, then the line following the if block is executed.

 

So consider the following code snippet:

\[java\]

int a = 10;

int b = 25;

if(a > b){

System.out.println("a is greater than b");

}

System.out.println("Outside if");

\[/java\]

So when this code is executed, it will print the following output:

```
Outside if
```

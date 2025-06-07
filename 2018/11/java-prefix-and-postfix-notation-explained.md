---
title: "Java prefix and postfix notation explained"
date: "2018-11-14"
categories: 
  - "java-interview-questions"
  - "java_language_features"
tags: 
  - "core-java"
  - "operators"
---

You might have used the increment and decrement operators in Java. You can use these in prefix and postfix form. In this blog post I will be explaining the difference between the two. When you use the increment or decrement operator before the operand it is said to be in prefix form. In such cases the increment or decrement operation is performed first before evaluating the expression.

````
int i = 5; 
int j = ++i;

System.out.println("j="+j); 
System.out.println("i="+i);
````

This code prints the following output:

```
j=6
i=6
```

So here value of j is 6 because the increment operation is performed first.

However when the increment or decrement operator is used after the operand it is said to be in postfix form. In such cases the increment or decrement operation is performed after evaluating the expression.

````
int i = 5; 
int j = i++;

System.out.println("j="+j); 
System.out.println("i="+i);
````

This code prints the following output:

```
j=5
i=6
```

So here value of j is 5. This is because the increment operation is performed after the assignment .

Note that in both cases the increment or decrement operation is performed on the operand . The difference lies in when the operation is performed

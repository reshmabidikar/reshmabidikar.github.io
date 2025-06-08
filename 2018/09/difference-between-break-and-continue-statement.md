---
title: "Difference between Break and Continue statement"
date: "2018-09-24"
categories: 
  - "core-java"
  - "java-interview-questions"
tags: 
  - "break-statement"
  - "continue-statement"
  - "core-java"
  - "java-jump-statements"
---

Both the break and continue statements are used to change the fliw of executionin Java loops. However they differ in the way they work.

#### What is a break statement?

A break statement is used to terminate a loop. So the moment a break statement is encountered, control is transferred outside the loop even if condition part of the loop is true.

Consider the following code snippet:

```java
for(int i = 0; i < 50;i++) { 
    if(i == 10) 
        break; 
    System.out.println("i="+i); 
} 
System.out.println("Outside loop");
```

This will print the following output:

```
i=0
i=1
i=2
i=3
i=4
i=5
i=6
i=7
i=8
i=9
Outside loop
```

So the loop executes till i reaches 10. Once the value of i is 10, the loop is exited.

In addition a break statement is also used in a switch block to skip further case statements the moment a match is encountered.

#### What is a continue statement?

Continue statement is used when you want to stop processing the remaining code in the body of a loop for a particular iteration but continue the loop for the next iteration.

Consider the following code snippet:

```java

for(int i = 0; i < 10;i++){ if(i % 2 == 0) continue; System.out.println("i="+i);

} System.out.println("Outside loop");

```

This code snippet prints only the odd numbers from 1 to 10. So it will print the following output:

```
i=1
i=3
i=5
i=7
i=9
Outside loop
```

So if the number is even (determined by the if check for i % 2 == 0), the continue statement is executed which skips Sysout statement and continues at the top of the loop.

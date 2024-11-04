---
title: "JShell in Java 9"
date: "2019-04-22"
categories: 
  - "core-java"
  - "java-9"
tags: 
  - "java9"
  - "jshell"
  - "repl"
---

One of the new features added by Java 9 is the JShell. In this blog post, I will be explaining how JShell works.

# What is JShell ?

JShell provides REPL capabilities to Java. REPL stands for Read Evaluate Print Loop. Many languages like Python also provide REPL capabilities.

REPL allows you to write Java code and test it without the need to compile it.

# How to launch JShell

Step 1 - Make sure you have JDK 9 installed

Step 2 -Open a Command prompt and navigate to the JDK\\bin folder

[![](images/Jshell1-300x78.png)](images/Jshell1.png)

Step 3 - Type JShell

[![](images/jshell2-300x101.png)](images/jshell2.png)

# How to Use JShell

Type the code that you want to test. I have typed 4+5. Press Enter

[![](images/jshell3-300x124.png)](images/jshell3.png)

Step 5 - View the results

![](images/Jshell4-300x154.png)

Example 2 - Using a Sysout statement

[![](images/jshell5-300x196.png)](images/jshell5.png)

Example 3 - Assigning a value to a variable and using it

[![](images/jshell6-300x182.png)](images/jshell6.png)

# How to exit JShell

Type /exit

[![](images/jshell7-300x217.png)](images/jshell7.png)

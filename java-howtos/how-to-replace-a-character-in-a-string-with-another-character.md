---
title: "How to replace a character in a String with another character"
date: "2018-08-18"
categories: 
  - "java-string-examples"
  - "strings"
tags: 
  - "core-java"
  - "java-string-handling"
---

There is a replace method provided by the String class that can be used to replace a character in a String with another character. The following code snippet demonstrates this:

````java

package demo;

public class StringDemo {

public static void main(String[] args) { 
    String str = "Hello World"; 
    String modifiedStr = str.replace('o', 'i'); 
    System.out.println("Modified String is "+modifiedStr);
  } 
}

````

So the above code will replace all occurrences of the letter 'o' in the String "Hello World" an 'i' and will print the following:

```
Helli World
```

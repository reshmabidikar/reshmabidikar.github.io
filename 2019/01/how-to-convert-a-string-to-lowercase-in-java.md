---
title: "How to convert a String to lowercase in Java"
date: "2019-01-06"
categories: 
  - "java-string-examples"
  - "strings"
tags: 
  - "core-java"
  - "java-string-handling"
---

In this blog post, I will be explaining how you can convert a String to lowercase in Java. Consider the following code snippet:

````
package learnjava.strings;

public class StringLowerCaseDemo {

public static void main(String[] args) { 
    String str = "Hello World"; 
    str = str.toLowerCase(); 
    System.out.println(str);
}

} 
````

There is a [String.toLowerCase](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#toLowerCase--) method. This converts the String object on which it is invoked to lowercase and returns the converted String. So when you run the above code, you will get the following output:

```
hello world
```

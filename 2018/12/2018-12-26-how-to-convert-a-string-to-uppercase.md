---
title: "How to convert a String to uppercase"
date: "2018-12-26"
categories: 
  - "java-string-examples"
  - "strings"
tags: 
  - "core-java"
  - "java-string-handling"
---

In this blog post, I will be explaining how you can convert a String to uppercase. Consider the following code snippet:

 

\[java\]

package learnjava.strings;

public class StringUpperCaseDemo {

public static void main(String\[\] args) { String str = "Hello World"; str = str.toUpperCase(); System.out.println(str);

}

}

\[/java\]

 

There is a [String.toUpperCase](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#toUpperCase--) method. This converts the String object on which it is invoked to uppercase and returns the converted String. So when you run the above code, you will get the following output:

```
HELLO WORLD
```

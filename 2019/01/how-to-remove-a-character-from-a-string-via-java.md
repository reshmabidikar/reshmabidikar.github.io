---
title: "How to remove a character from a String via Java"
date: "2019-01-02"
categories: 
  - "java-string-examples"
  - "strings"
tags: 
  - "core-java"
  - "java-string-handling"
---

In this blog post, I will be explaining how you can remove a character from a String via Java. Consider the following code snippet:

````
package learnjava.strings;

public class RemoveCharacterDemo {

public static void main(String[] args) { 
    String str = "Hello World"; 
    String modifiedStr = str.replace("l", ""); System.out.println(modifiedStr);
    }
}
````

There is a method [String.replace](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#replace-char-char-). This replaces the specified character with another character. Here, we are replacing the character 'l' with an empty character. So effectively, it is like removing the character "l". When you run this code, you will get the following output:

```
Heo Word
```

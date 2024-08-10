---
title: "How to find the number of words in a Sentence"
date: "2018-08-23"
categories: 
  - "java-string-examples"
  - "strings"
tags: 
  - "core-java"
  - "java-string-handling"
---

In order to find the number of words in a sentence, you can use the String.split method. The following code demonstrates this:

 

\[java\]

package demo;

public class StringDemo {

public static void main(String\[\] args) { String str = "My first Java program"; String\[\] words = str.split(" "); System.out.println("There are "+words.length+" words");

} }

\[/java\]

So the split method splits the given String on the basis of the space character. It returns a String array with all the words in the input String. You can use any other character to split the String as well.

When you run this code, it will print the following on the console:

```
There are 4 words
```

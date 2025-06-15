---
title: "How to check if a String has only alphabets"
date: "2018-08-19"
categories: 
  - "java-string-examples"
  - "strings"
tags: 
  - "core-java"
  - "java-regular-expressions-en"
  - "java-string-handling"
---

You can use Java regular expressions to check if a String has only alphabets as follows:

\[java\]

package demo;

public class StringDemo {

public static void main(String\[\] args) { String str = "HelloWorld"; String regex = "^\[a-zA-Z\]+$"; boolean matches = str.matches(regex); System.out.println(matches);

} }

\[/java\]

 

The above code will print true when you run it. If you change the String str to have any other characters like numbers or special characters, it will print false.

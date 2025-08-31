---
title: "How to reverse a String in Java"
date: "2018-08-24"
categories: 
  - "java-string-examples"
  - "strings"
tags: 
  - "core-java"
  - "java-string-handling"
---

In this post, I will demonstrate how to reverse a String in Java. You can do this in the most obvious way i.e. iterating through the String in the reverse order and creating a new String. The following code snippet demonstrates this:

````java

private static String reverse(String str) {     
    String reversedString = ""; 
    for(int i = str.length()-1;i &gt;=0 ; i--){ 
        reversedString = reversedString + str.charAt(i); 
    } 
    return reversedString; 
}

````

A better way is to use Java's [StringBuilder](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html) class that has an in-built [reverse](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html#reverse--) method. The following code snippet demonstrates this:

````java

StringBuilder strBuilder = new StringBuilder(str); 
String reversedString = strBuilder.reverse().toString();

````

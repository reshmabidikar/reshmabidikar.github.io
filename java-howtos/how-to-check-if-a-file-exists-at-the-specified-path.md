---
title: "How to check if a file exists at the specified path"
date: "2019-01-09"
categories: 
  - "java-io-en"
  - "java-io-examples"
tags: 
  - "core-java"
  - "java-io-en"
---

In this blog post, I will be explaining how you can check if a file exists at a specified path. Consider the following code snippet:

````java
public class FileExists {

public static void main(String args[]){ 
    String fileName = "C:/Test.txt"; 
    File file = new File(fileName); 
    if(file.exists()){ 
        System.out.println("File is present"); 
    } else 
        System.out.println("File is missing"); 
    } 
}
````

Here the [File.exists](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#exists--) method is used. This returns a true if a file with the specified name exists at the path specified, otherwise it returns a false.

If you run this code, you will get the following output (Assuming there is a file on C drive called test.txt):

```
File is present
```

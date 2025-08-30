---
title: "How to create a new file using Java"
date: "2019-01-11"
categories: 
  - "java-io-en"
  - "java-io-examples"
tags: 
  - "core-java"
  - "java-io-en"
---

In this blog post, I will be demonstrating how you can create a new empty file via Java. Consider the following code snippet:

````java
package learnjava.io;

import java.io.File; import java.io.IOException;

public class CreateFileDemo {

public static void main(String[] args) { 
    String fileName = "C:/Test2.txt"; 
    File file = new File(fileName); 
    try { 
        if (file.createNewFile()) 
            System.out.println("File created successfully"); 
        else 
            System.out.println("There was an error in creating the file"); 
    } catch (IOException e) { 
        System.out.println("There was an exception in creating the file:"+e.getMessage()); 
    }
}
}
````

There is a method called [File.createNewFile](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#createNewFile--). This creates a new file corresponding to the path in the File object. It returns a boolean value if the file is created successfully. If there is already a file at the path with the same name or if there is any other issue in creating the file, then this method returns a false. Note that the [File.createNewFile](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#createNewFile--) can throw an IOException, so this needs to be handled by the code.

When you execute the above code snippet, the following is printed to the console (Assuming there is no file at C:/Test2.txt):

```
File created successfully
```

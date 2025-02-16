---
title: "How to make a file read-only in Java"
date: "2019-01-12"
categories: 
  - "java-io-en"
  - "java-io-examples"
tags: 
  - "core-java"
  - "java-io-en"
---

In this blog post, I will be explaining how you can make a file read-only in Java. Consider the following code snippet:

````

package learnjava.io;

import java.io.File;

public class ReadOnlyDemo {

    public static void main(String[] args) { 
        String fileName = "F:/Test1.txt"; 
            File file = new File(fileName); 
            if(file.setReadOnly()) { 
                System.out.println("File is now readonly"); 
            } else 
                System.out.println("Failed to make the file readonly");

    }
}
````

There is a method called [File.setReadOnly](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#setReadOnly--). This makes a file as read only. It returns true if the file is made readonly successfully. If the file does not exist at that path, or if any other issue occurs, it returns false. So if you run the above code snippet, the file "F:/Test1.txt" will be made as readonly. If you try to edit and save it, you will see the following error:

[![](images/file-readonly-300x156.png)](images/file-readonly.png)

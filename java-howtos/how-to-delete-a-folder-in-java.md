---
title: "How to delete a folder in Java"
date: "2019-01-09"
categories: 
  - "java-io-en"
  - "java-io-examples"
tags: 
  - "core-java"
  - "java-io-en"
---

In this blog post, I will be demonstrating how you can delete a folder in Java. Consider the following code snippet:

````java

package learnjava.io;

import java.io.File;

public class DeleteDirectory { 
    public static void main(String[] args) { 
        String fileName = "F:/TestFolder"; 
        File file = new File(fileName); 
        if (file.exists()) { 
            if (file.isDirectory()) { 
                File[] files = file.listFiles(); 
                if (files.length == 0) { 
                    System.out.println("Folder is empty so deleting it"); 
                if (file.delete()) { 
                    System.out.println("Deleted file successfully"); 
                } else 
                System.out.println("Error in deleting file"); 
            } else { 
                System.out.println("There are " + files.length + " files in the folder, so folder cannot be deleted"); 
            } 
        } else { 
            System.out.println("F:/Test.txt is not a folder"); 
        } 
    } else 
        System.out.println("Folder F:/TestFolder1 is missing, so could not be deleted")
        } 
} 
````

There is a [file.delete](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#delete--) method that can be used to delete a folder. However, if the folder has some files, the delete method fails. So first you need to check if there are files in the folder. You can do this by using the [file.isDirectory](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#isDirectory--) method which returns a true if the path given to it is a directory and the [file.list](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#list--) method which returns an array of the files in the directory. So assuming the TestFolder is empty, when you run the code, it will print the following output:

```
Folder is empty so deleting it
Deleted file successfully
```

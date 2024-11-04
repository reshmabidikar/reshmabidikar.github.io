---
title: "How to obtain a list of files in a folder"
date: "2019-04-02"
categories: 
  - "java-io-en"
  - "java-io-examples"
tags: 
  - "core-java"
  - "java-io-en"
---

In this blog post, I will be explaining how you can obtain a list of files in a folder. Consider the following code snippet:

````

package learnjava.io;

import java.io.File;

public class FilesInFolderDemo {

    public static void main(String[] args) {
        String folderName = "F:/TestFolder";
        File file = new File(folderName);
        if (file.exists() && file.isDirectory()) { // check if file exists & is a folder 
            File[] files = file.listFiles(); //get list of files 
            if (files.length > 0) {
                System.out.println("There are " + files.length + " files in the folder");
                for (int i = 0; i < files.length; i++) {
                    System.out.println("File name is " + files[i]);
                }
            } else { //empty folder! 
                System.out.println("Folder is empty !");
            }
        } else {
            System.out.println("Folder " + folderName + " is missing or is not a folder");
        }
    }
} 
````

There is a method called [File.list](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#list--) on the file interface. If the File object corresponding to the specified path is a directory, then this method will return a list of file names. So the code above will print the following output (assuming there are 2 files test.txt and test2.txt in the TestFolder):


```
There are 2 files in the folder
File name is F:\TestFolder\test.txt
File name is F:\TestFolder\test2.txt
```

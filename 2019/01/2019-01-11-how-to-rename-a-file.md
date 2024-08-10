---
title: "How to rename a file"
date: "2019-01-11"
categories: 
  - "java-io-en"
  - "java-io-examples"
tags: 
  - "core-java"
  - "java-io-en"
---

In this blog post ,I will be showing you how you can rename a file. Consider the following code snippet:

\[java\]

package learnjava.io;

import java.io.File;

public class RenameFileDemo { public static void main(String args\[\]){ String fileName = "C:/Test.txt"; String newFileName = "C:/test2.txt"; File file = new File(fileName); if(file.exists()){ File newFile = new File(newFileName); boolean renamed = file.renameTo(newFile); if(renamed) System.out.println("File renamed successfully"); else System.out.println("There was an error in renaming the file"); } else System.out.println("File is missing"); } }

\[/java\]

If you run this code, it will produce the following output:

```
File renamed successfully
```

 

There is a method called [File.renameTo](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#renameTo-java.io.File-) which can be used to rename a file. It accepts as argument a file object. The file object should be constructed with the new name to be given to the file. Note that the full path needs to be specified.

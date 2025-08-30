---
title: "How to create a Directory in Java"
date: "2019-01-12"
categories: 
  - "java-io-en"
  - "java-io-examples"
tags: 
  - "core-java"
  - "java-io-en"
---

In this blog post, I will be covering how you can create a directory in Java. Consider the following code snippet:

````java
package learnjava.io;

import java.io.File;

public class CreateDirectory {

    public static void main(String[] args) { 
        String fileName = "C:/Parent/Demo"; 
        File file = new File(fileName); 
        boolean created = file.mkdirs(); 
        if(created) 
            System.out.println("Directory created successfully"); 
        else 
            System.out.println("Failed to created directories");
    }
}
````

There is a [File.mkdirs](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#mkdirs--) method. This creates the directory corresponding to the File object including any non-existent parent directories. It returns a true if the directory was created successfully, otherwise it returns a false. In this case, it will print the following output (Assuming there is no error in creating the directory):

```
Directory created successfully
```

There is also a [File.mkdir](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#mkdir--) method. This creates a directory corresponding to the path specified, but does not create parent directories. So if the parent directory is missing, this method will return a false value.

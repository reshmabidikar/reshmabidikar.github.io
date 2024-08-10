---
title: "How to find the total space in a drive in Java"
date: "2019-01-13"
categories: 
  - "java-io-en"
  - "java-io-examples"
tags: 
  - "core-java"
  - "java-io-en"
---

In this blog post, I will be explaining how you can find the total space available in a drive via Java. Consider the following code snippet:

 

\[java\]

package learnjava.io;

import java.io.File;

public class FindTotalSpaceDemo {

public static void main(String\[\] args) { String fileName = "C:/"; File file = new File(fileName); long totalSpace = file.getTotalSpace();

System.out.println("totalSpace = "+totalSpace/1000000000+ " GB");

}

}

\[/java\]

 

There is a method called [File.getTotalspace](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#getTotalSpace--). This returns the number of bytes available on the partition that is encapsulated by the file object.

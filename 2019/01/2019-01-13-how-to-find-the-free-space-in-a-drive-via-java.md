---
title: "How to find the free space in a drive via Java"
date: "2019-01-13"
categories: 
  - "java-io-en"
  - "java-io-examples"
tags: 
  - "core-java"
  - "java-io-en"
---

In this blog post, I will be explaining how you can find the free space in a drive via Java. Consider the following code:

\[java\]

package learnjava.io;

import java.io.File;

public class FindFreeSpaceDemo { public static void main(String\[\] args) { String fileName = "C:/"; File file = new File(fileName); long freeSpace = file.getFreeSpace(); System.out.println("freeSpace = "+freeSpace/1000000000+ " GB");

} }

\[/java\]

 

There is a method [File.getFreeSpace](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#getFreeSpace--). This returns the number of bytes available on the drive that is encapsulated by the current File object. According to the API documentation, the number of bytes is a hint and not a guarantee. There is another method called [File.getUsuableSpace](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#getUsableSpace--).  This returns the number of bytes available to the virtual machine. This method checks for write permissions and other operating system restrictions and will therefore usually provide a more accurate estimate of how much new data can actually be written than the [File.getFreeSpace](https://docs.oracle.com/javase/8/docs/api/java/io/File.html#getFreeSpace--) method.

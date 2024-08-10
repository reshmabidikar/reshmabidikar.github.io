---
title: "How to Delete a file"
date: "2019-01-09"
categories: 
  - "java-io-en"
  - "java-io-examples"
tags: 
  - "core-java"
  - "java-io-en"
---

In this blog post, I will be demonstrating how you can delete a file in Java. Consider the following code snippet:

\[java\]

package learnjava.io;

import java.io.File;

public class DeleteFile {

public static void main(String\[\] args) { String fileName = "D:/Test.txt"; File file = new File(fileName); if (file.exists()) { if (file.delete()) { System.out.println("Deleted file successfully"); } else System.out.println("Error in deleting file"); } else System.out.println("File is missing, so could not be deleted"); }

}

\[/java\]

 

There is a File.delete method available to delete a file. It returns true, if the delete was successful, otherwise returns a false. So if you run the above code snippet, the following output will be printed (Assuming there is a file called test.txt on D Drive):

 

```
Deleted file successfully
```

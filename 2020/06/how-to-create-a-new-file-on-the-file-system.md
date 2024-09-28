---
title: "How to create a new File on the file system"
date: "2020-06-05"
categories: 
  - "others"
---

In this article, I will be demonstrating how you can create a new file on the file system.

# Using File.createNewFile

The File class has a method `createNewFile`. You can use this to create a new file on the fie system. The following code demonstrates this:

```
private static void createNewFile(String filePath) {
    File file = new File(filepath);
    try {
      file.createNewFile();
    } catch (IOException e) {
      // TODO Auto-generated catch block
      e.printStackTrace();
    }
  }
```

This code creates a file at the specified filePath. The file path should include the file location as well as file name. The `createNewFile` method returns a boolean value which indicates whether file creation was successful or not.

# Using FileWriter.write

The `java.io.FileWriter` has a write method that you can use to write to a file. If the underlying file does not exist, this method automatically creates the file. So you can use this approach when you want to create a file and write some data to it. The following code demonstrates this:

```
private static void createNewFileUsingFileWriter(String filePath) {
     FileWriter fileWriter;
    try {
      fileWriter = new FileWriter(filePath);
       fileWriter.write("Hello World");
       fileWriter.close();
    } catch (IOException e) {
      // TODO Auto-generated catch block
      e.printStackTrace();
    }
    
    
  }
```

The code first creates a `FileWriter` object corresponding to `filePath`. It then uses the `fileWriter.write` method to write the String "**Hello World**" at this path. So this will create the file as well as write the String value to this file.

# Using FileOutputStream.write

Just like `java.io.FileWriter`, there is a `java.io.FileOutputStream` class that you can use to write to a file. So, it has a `write` method as well. However, the `FileOutputStream` can only write bytes. So you can use this approach when you want to create a file and write some data to it. The following code demonstrates this:

```
private static void createNewFileUsingFileOutputStream(String filePath) {
     FileOutputStream fos;
    try {
      fos = new FileOutputStream(filePath);
      fos.write(new String("Hello World").getBytes());
      fos.close();
    } catch (IOException e) {
      // TODO Auto-generated catch block
      e.printStackTrace();
    }
    
    
  }
```

Just like the `FileWriter` code, this code creates a `FileOutputStream` corresponding to `filePath`. It then uses the `write` method to write to this file.

# Conclusion

So in this article we saw the different ways in which you can create a file on the file system in Java. We saw how the `file.createNewFile`

, `FileWriter` and `FileOutputStream` can be used to create a File

---
title: "Java Try With Explained with Code Samples"
date: "2019-12-24"
categories: 
  - "java_language_features"
tags: 
  - "java-try-with"
---

The Java try with statement allows you to declare some resources with the try statement. Java automatically closes these resources once the try statement ends. This makes the code clean. Java introduced the try-with statement as part of Java 7.

## Without Try/With

Consider the following code that does not use try-with:

```
public static void saveFile(String fileName, String content) {
   try {
     BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(fileName));
     bufferedWriter.write(content);
     bufferedWriter.close();
   } catch (IOException e) {
     e.printStackTrace();
   }
 }
```

This code uses BufferedWriter to write to a file. Once the code finishes writing the content to the file, it closes the BufferedWriter.

## Using try/With

You can re-write the above code using a try-with statement as follows:

```
public static void saveFile2(String fileName, String content) {
   try (BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(fileName))){
     bufferedWriter.write(content);
   } catch (IOException e) {
     e.printStackTrace();
   }
 }
```

The try statement includes the resources that need to be closed automatically. In this case, it is the BufferedWriter.So there is no need to explicitly close the BufferedWriter once the File writing is done.

## Using Multiple Resources with try-with

You can also specify more than one resource with the try/with statement. Java closes each of the specified resources. The following code demonstrates this:

 

```
public static void readAndWriteToFile(String inputFile, String outputFile) {
   try (BufferedReader bufferedReader = new BufferedReader(new FileReader(inputFile));BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(outputFile))){
   	 String line = bufferedReader.readLine();
      while (line != null) {
     	 bufferedWriter.write(line);
        line = bufferedReader.readLine();
      }
   } catch (IOException e) {
     e.printStackTrace();
   }
 }

```

This code reads the content of a file and writes it to another file. It uses a BufferedReader to read the input file and a BufferedWriter to write to the output file. Both the BufferedReader and BufferedWriter are specified with the try statement. They are separated with a semi-colon as required by the try-with statement. The code does not need to close the BufferedReader and BufferedWriter explicitly.

## Conclusion

So this article explains what is the try with resources in Java. It allows you to specify the resources that need to be automatically closed after the try statement.

---
title: "How to read a file in Java"
date: "2018-08-17"
categories: 
  - "java-io-en"
  - "java-io-examples"
tags: 
  - "core-java"
  - "java-io-en"
  - "java-loops-en"
---

In Java, you can use the BufferedReader class as follows in order to read a file:

 

\[java\]

package demo;

import java.io.BufferedReader; import java.io.File; import java.io.FileNotFoundException; import java.io.FileReader; import java.io.IOException;

public class MyTextFileReader {

public static void main(String args\[\]){ try { BufferedReader br = new BufferedReader(new FileReader(new File("F:/test.txt"))); String line = null; while ((line = br.readLine()) != null) { System.out.println(line); } } catch ( IOException e) { // TODO Auto-generated catch block e.printStackTrace(); } }

}

\[/java\]

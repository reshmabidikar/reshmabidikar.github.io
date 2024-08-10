---
title: "Java loops Examples"
date: "2018-10-23"
categories: 
  - "java_language_features"
  - "java-examples"
tags: 
  - "core-java"
  - "java-loops-en"
---

In this blog post, I am going to demonstrate all of Java's loops. I am going to write loops that prints the sum of numbers in a List.

#### For Loop

\[java\]

private static int sumFor(List<Integer> numbers){ int sum = 0; for(int i=0; i < numbers.size();i++){ sum += numbers.get(i); } return sum; }

\[/java\]

 

#### For Each Loop

\[java\]

private static int sumForEach(List<Integer> numbers){ int sum = 0; for(int num:numbers){ sum += num; } return sum; }

\[/java\]

#### While Loop

\[java\]

private static int sumWhile(List<Integer> numbers){ int sum = 0; int i = 0; while (i < numbers.size()){ sum += numbers.get(i); i++; } return sum; }

\[/java\]

#### Do While Loop

\[java\]

private static int sumDoWhile(List<Integer> numbers){ int sum = 0; int i = 0; do{ sum += numbers.get(i); i++; }while (i < numbers.size()); return sum; }

\[/java\]

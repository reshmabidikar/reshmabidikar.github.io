---
title: "How to print the current date and time"
date: "2018-10-25"
categories: 
  - "java-date-handling"
tags: 
  - "java-dates"
---

In this blog post, I will be demonstrating how you can print the current date and time.

 

Consider the following code snippet:

\[java\]

import java.util.Calendar;

public class PrintCurrentDateTimeDemo {

public static void main(String\[\] args) { Date date = new Date(); System.out.println("Current date and time is "+date);

}

}

\[/java\]

 

Here, we are using a [java.util.Date instance](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html).   This represents a particular instance in time. When we create a new Date object with the default constructor, it creates a Date object with the current date and time. The Sysout statement then prints the Date and time in this date object.

So this code prints the following output:

```
Current date and time is Mon Feb 25 09:31:36 IST 2019
```

---
title: "How to convert a String to a Date"
date: "2018-11-08"
categories: 
  - "java-date-handling"
  - "java-string-examples"
  - "strings"
tags: 
  - "java-date-handling"
  - "java-string-handling"
---

In this blog post, I will be demonstrating how you can convert a String to a Date object. Consider the following code snippet:

\[java\]

public class StringToDate {

public static void main(String\[\] args) { System.out.println("Enter a date:"); Scanner scanner = new Scanner(System.in); String dateStr = scanner.nextLine(); System.out.println("Input date is "+dateStr); SimpleDateFormat simpleDateFormat = new SimpleDateFormat("dd-MM-yyyy"); try { Date date = simpleDateFormat.parse(dateStr); System.out.println("Date in date format is "+date); } catch (ParseException e) { // TODO Auto-generated catch block e.printStackTrace(); } scanner.close();

}

}

\[/java\]

The input Date in String format is read using the [Scanner](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html) class. The code uses the [SimpleDateFormat](https://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html) class. This is a class that provides date formatting functions. In the constructor, you need to specify the format in which the input date is specified as a String. So in this case, I have specified "**dd-MM-yyyy**" which means the date will be in this format. Then, the [parse](https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html#parse\(java.lang.String\)) method is invoked. This method is defined in the [DateFormat](https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html) class which is a super-class of [SimpleDateFormat](https://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html) . This returns a Date object corresponding to the input String.

 

So if you run this code with the input as "**08-09-2018**", it will print the following output:

```
Enter a date:
08-09-2018
Input date is 08-09-2018
Date in date format is Sat Sep 08 00:00:00 IST 2018



```

Note that the input date should match the format that is specified in the [SimpleDateFormat](https://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html) constructor. Suppose we specify as input like this "**08-Sep-18**", and if you run the code now, it will print the following:

```
Enter a date:
08-Sep-18
Input date is 08-Sep-18
java.text.ParseException: Unparseable date: "08-Sep-18"
at java.text.DateFormat.parse(Unknown Source)
at learnjava.dates.StringToDate.main(StringToDate.java:17)
```

 

The API documentation for [SimpleDateFormat](https://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html)  specifies the pattern Strings that you need to use for various date formats.

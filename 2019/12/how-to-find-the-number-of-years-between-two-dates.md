---
title: "How to find the number of years between two Dates"
date: "2019-12-06"
categories: 
  - "java-8-examples"
  - "java-date-handling"
  - "java8"
tags: 
  - "datehandling"
  - "datetime"
  - "java8"
---

Prior to Java 8, you had to write complex logic to find the number of years between two dates. The DateTime API introduced from Java 8 onwards provides some methods that let you easily find the number of years between two dates.

The following code demonstrates this:

```
public static void main(String[] args) {
  LocalDate date1 = LocalDate.parse("1997-04-28");
  LocalDate date2 = LocalDate.parse("2015-11-25");
  Period period = date1.until(date2);
  int yearsBetween = period.getYears();
  System.out.println("yearsBetween:"+yearsBetween);
}
```

Java 8 has added a LocalDate class to represent a Date. So in this code, both the input Dates are held within LocalDate objects. There is a method called until on the LocalDate class. This returns a Period instance. Period has a method called getYears which returns the number of years. So this code prints the following output:

```
yearsBetween:18
```

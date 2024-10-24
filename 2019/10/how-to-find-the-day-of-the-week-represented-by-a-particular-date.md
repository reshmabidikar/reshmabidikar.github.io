---
title: "How to find the day of the week represented by a particular date"
date: "2019-10-21"
categories: 
  - "java-date-handling"
tags: 
  - "java8"
  - "java8localdate"
---

In this article, I will be demonstrating how you can find the day of the week represented by a particular date. You can use Java 8 LocalDate class for this. The following code demonstrates this:

```
LocalDate date = LocalDate.of(2019, 8, 11);
DayOfWeek dayOfWeek = date.getDayOfWeek();
System.out.println("dayOfWeek="+dayOfWeek);
```

The LocalDate class has a method called getDayOfWeek. This returns a DayOfWeek enum which corresponds to the day of the week. Here a LocalDate object corresponding to 11th August 2019 is created which corresponds to a Sunday. So when you execute this code, it prints the following output:

dayOfWeek=SUNDAY

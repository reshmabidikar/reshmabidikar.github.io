---
title: "How to add a number of days to a Date in Java"
date: "2020-03-10"
categories: 
  - "java-8-examples"
  - "java8"
---

In this article, I will be demonstrating how to add a number of days to a Date in Java

# Before Java 8

Prior to Java 8, the Date and Calendar classes were available for Date manipulation. They make operations like adding a number of days to a Date very difficult. The following code demonstrates adding days to a date using the Calendar class:

```java
String stringDate="2019-07-15";  
Date date1=new SimpleDateFormat("yyyy-MM-dd").parse(stringDate);  
Calendar cal = Calendar.getInstance();
cal.setTime(date1);
    
// manipulate date
cal.add(Calendar.DATE, 5); 
Date dateWith5Days = cal.getTime();
    
System.out.println(dateWith5Days);
```

So the above code first uses SimpleDateFormat.parse to convert a String date to a java.util.Date. It then creates a Calendar object corresponding to this date. Finally, it uses the Calendar.add method to add days to the date.

# Using Java 8

Java 8 introduced the LocalDate class which makes date manipulations like adding/subtracting days/months very easy. The following code demonstrates this:

```java
LocalDate date = LocalDate.parse("2019-07-15");
    
//add 5 days
LocalDate date2 = date.plusDays(5);
System.out.println("Date "+date+" plus 5 days is "+date2);

```

So this code first creates a LocalDate object corresponding to the String date. It then invokes the plusDays method to add 5 days to the specified date.

Not only days, the LocalDate class the several methods that allow you to add/subtract months, years from the LocalDate object.


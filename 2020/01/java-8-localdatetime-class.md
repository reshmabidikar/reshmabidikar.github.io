---
title: "Java 8 LocalDateTime class explained with code samples"
date: "2020-01-17"
categories: 
  - "java-8-features"
tags: 
  - "java-8"
  - "localdatetime"
---

Just like the [LocalDate](https://reshmabidikar.github.io/2019/06/java-8-localdate-class-explained.html) and [LocalTime](https://reshmabidikar.github.io/2019/08/java-8-localtime-class-explained.html) classes, Java 8 has also introduced the LocalDateTime class. In this article, I will be covering this class.

## What is LocalDateTime class?

The Java 8 LocalDateTime class represents a date with a time component. It has the year, month, day, hour, minute, second and nanoseconds components. So for example, you can use it to represent a date time like **12th August 1997 7:30 am**.

## LocalDateTime Creation

There are several static methods on the LocalDateTime class that can be used to create a LocalDateTime. The following code demonstrates this:

```
LocalDateTime dateTime1 = LocalDateTime.now();
System.out.println("Today's date is "+dateTime1);

LocalDateTime dateTime2 = LocalDateTime.parse("2019-07-15T10:15:30");
System.out.println("Date2 is "+dateTime2);

dateTime2 = LocalDateTime.of(2017,05,17,5,25);
System.out.println("Date3 is "+dateTime2);
```

- The **LocalDateTime.now** returns the current time.
- The **LocalDateTime.parse** parses the specified date and time and creates a LocalDateTime object out of it. It requires the DateTime to be in the specified format. So you need to separate the date and time components by using the letter "T". If you specify the time in some other format, an error will occur. If your String time is in any other format, you can use the overloaded version of the parse method that accepts a **DateTimeFormatter**
- The **LocalDateTime.of** method creates a LocalDateTime object using the specified year, month, day, hour and minute value. There are several overloaded versions of this method available.

So this code prints the following output:

```
Today's date is 2020-01-17T11:39:01.015
Date2 is 2019-07-15T10:15:30
Date3 is 2017-05-17T05:25
```

In addition to these methods, there are several other methods in the**LocalDateTime** class that you can use to create a LocalDateTime object. You can check them out via the API documentation.

## LocalDateTime Arithmetic

The LocalDateTime class allows you to easily perform time arithmetic as can be seen by the following code:

```
LocalDateTime dateTime = LocalDateTime.of(2017,05,17,5,25);


LocalDateTime dateTime2 = dateTime.plusDays(5);//add 5 days
System.out.println("Date "+dateTime+" plus 5 days is "+dateTime2);

dateTime2 = dateTime.minusMinutes(10);
System.out.println("Date "+dateTime+" minus 10 minutes is "+dateTime2);

dateTime2 = dateTime.withYear(2019);//year set to 2019
System.out.println("Date "+dateTime+" with year set to 2019 is "+dateTime2);

dateTime2 = dateTime.withHour(8);// hour set to 8
System.out.println("Date "+dateTime+" with hour set to 8 is "+dateTime2);
```

- The **LocalTime.plusDays** method adds the specified number of days to the LocalDateTime object
- The **LocalDateTime.minusMinutes** subtracts the specified number of minutes from the LocalDateTime object
- The **LocalDateTime.withYear** sets the year field to the specified value
- The **LocalDateTime.withHour** sets the hour field to the specified value

So this code prints the following output:

```
Date 2017-05-17T05:25 plus 5 days is 2017-05-22T05:25
Date 2017-05-17T05:25 minus 10 minutes is 2017-05-17T05:15
Date 2017-05-17T05:25 with year set to 2019 is 2019-05-17T05:25
=Date 2017-05-17T05:25 with hour set to 8 is 2017-05-17T08:25
```

In addition to these methods, there are several more methods on the LocalDateTime class that allow you to add or subtract the other date and time components.

## Extracting Information from LocalDateTime

The LocalDateTime class allows you to easily extract information from the LocalDateTime object. The following code demonstrates this:

```
LocalDateTime dateTime1 = LocalDateTime.of(2017,05,17,5,25);

int day = dateTime1.getDayOfYear();
System.out.println("DayOfYear="+day);

long minute = dateTime1.getMinute();
System.out.println("minute="+minute);

Month month = dateTime1.getMonth();
System.out.println("Month="+month);

LocalDate date = dateTime1.toLocalDate();
System.out.println("Date="+date);
```

- The LocalDateTime.getDayOfYear returns the day of the year in the LocalDateTime object
- The LocalDateTime.getMinute returns the minute component in the LocalDateTime object
- The LocalDateTime.getMonth returns the month component in the LocalDateTime object
- The LocalDateTime.toLocalDate returns the LocalDate component in the LocalDateTime object

So this code prints the following output:

```
DayOfYear=137
minute=25
Month=MAY
Date=2017-05-17
```

In addition to these methods, there are many other methods in the LocalDateTime class that you can use to retrieve the other components in the LocalDateTime class.

## LocalDateTime Comparison

The LocalDateTime class allows you to easily perform comparison as can be seen by the following code:

```
LocalDateTime dateTime1 = LocalDateTime.of(2017,05,17,5,25);
LocalDateTime dateTime2 = LocalDateTime.of(2014,06,12,8,40);
LocalDateTime dateTime3 = LocalDateTime.of(2017,05,17,5,25);

boolean isAfter= dateTime1.isAfter(dateTime2);
System.out.println("Is after:"+isAfter);

boolean isEqual = dateTime1.isEqual(dateTime3);
System.out.println("Is Equal:"+isEqual);

```

- The isAfter method returns true if the datetime object on which the method is invoked is **after** the datetime object passed in
- The isEqual method returns true if both datetime objects are **equal**

So this code prints the following output:

```
Is after:true
Is Equal:true


```

## Conclusion

In this blog post, we saw what is Java 8 LocalDateTime. We also saw a Java 8 LocalDateTime example, with code for time creation, datetime extraction, time arithmetic, and time comparison.

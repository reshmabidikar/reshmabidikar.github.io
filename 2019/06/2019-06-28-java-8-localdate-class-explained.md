---
title: "Java 8 LocalDate Class explained with code samples"
date: "2019-06-28"
categories: 
  - "java-8-features"
tags: 
  - "java8"
  - "java8datetime"
  - "java8localdate"
---

Another new feature by Java 8 is the DateTime API. Some of the important classes in the DateTime API are the LocalDate, [LocalTime](https://learnjava.co.in/java-8-localtime-class-explained/) and [LocalDateTime](https://learnjava.co.in/java-8-localdatetime-class/). In this article, I will be explaining the Java 8 LocalDate class in detail.

\[table id=24 /\]

## Introduction

The LocalDate class represents a date. It is present in the java.time package. It has several methods that allow you to perform date manipulation easily.

## Creating LocalDate

There are several static methods on the LocalDate class that allow you to obtain a LocalDate instance. The following code demonstrates this:

```
public class LocalDateDemo {

  public static void main(String[] args) {
    LocalDate date1 = LocalDate.now();
    System.out.println("Today's date is "+date1);
    
    LocalDate date2 = LocalDate.parse("2019-07-15");
    System.out.println("Date2 is "+date2);
    
    LocalDate date3 = LocalDate.of(2017,05,17);
    System.out.println("Date3 is "+date3	);
    
    LocalDate date4 = LocalDate.ofYearDay(2017,8);
    System.out.println("Date4 is "+date4);

  }

}
```

- The LocalDate.now returns the current date.
- The LocalDate.parse parses a Date in **String** format and creates a **LocalDate** object out of it. It requires the Date to be in **yyyy-MM-dd** format. If you specify the date in some other format, an error will occur. If your String date is in any other format, you can use the overloaded version of the parse method that accepts a DateTimeFormatter
- The LocalDate.of method creates a **LocalDate** object by specifying the **month**, **date** and **year**
- The LocalDate.ofYearDay creates a **LocalDate** object by specifying the **year** and the **day in the year**.

So when this code is executed, it will print the following output:

```
Today's date is 2019-06-26
Date2 is 2019-07-15
Date3 is 2017-05-17
Date4 is 2017-01-08
```

In addition to these methods, there are several other methods in the **LocalDate** class that you can use to create a Date. You can check them out via the API documentation.

## Date Arithmetic

The **LocalDate** allows you to easily perform date arithmetic. The following code demonstrates this:

```
LocalDate date = LocalDate.parse("2019-07-15");
  
LocalDate date2 = date.plusDays(5);//add 5 days
System.out.println("Date "+date+" plus 5 days is "+date2);

date2 = date.minusMonths(4); //subtract 4 months
System.out.println("Date "+date+" minus 4 months is "+date2);

date2 = date.plusWeeks(3);
System.out.println("Date "+date+" plus 3 weeks is "+date2);

date2 = date.withYear(2019);//year set to 2019
System.out.println("Date "+date+" with year set to 2019 is "+date2);
```

When you execute this code, it will print the following output:

```
Date 2019-07-15 plus 5 days is 2019-07-20
Date 2019-07-15 minus 4 months is 2019-03-15
Date 2019-07-15 plus 3 weeks is 2019-08-05
Date 2019-07-15 with year set to 2019 is 2019-07-15
```

- The LocalDate.plusDays method **adds** the specified number of **days** to the **LocalDate** object
- The LocalDate.minusMonths **subtracts** the specified number of **months** from the **LocalDate** object
- The LocalDate.plusWeeks **adds** the specified number of **weeks** from the **LocalDate** object
- The LocalDate.withYear sets the **year** field to the specified **value**

In addition to these methods, there are several methods that allow you to perform Date arithmetic easily. You can refer to the API documentation

## Extracting Information from Date

The **LocalDate** class allows you to easily extract information from the Date object. The following code demonstrates this:

```
LocalDate date = LocalDate.parse("2019-07-15");

int day = date.getDayOfYear();
System.out.println("DayOfYear="+day);

int dayOfmonth = date.getDayOfMonth();
System.out.println("DayOfmonth="+dayOfmonth);

Month month = date.getMonth();
System.out.println("Month="+month);

DayOfWeek dayOfWeek = date.getDayOfWeek();
System.out.println("DayOfWeek="+dayOfWeek);
```

When you execute this code, it will print the following output:

```
DayOfYear=196
DayOfmonth=15
Month=JULY
DayOfWeek=MONDAY
```

- The LocalDate.getDayOfYear returns the **day of the year** that the date corresponds to
- The LocalDate.getDayOfMonth returns the **day of the month** that the date corresponds to
- The LocalDate.getMonth returns an enum Month that specifies the **name of the month** 
- The LocalDate.getDayOfWeek returns an enum DayOfWeek that specifies the name of the **day of the week**

In addition to these methods, there are several methods that allow you to easily extract the information you need from the **LocalDate** object. You can refer to the API documentation

## Date Comparison

The **LocalDate** class allows you to easily perform Date comparison. The following code demonstrates this:

```
LocalDate date1 = LocalDate.parse("2017-05-17");

LocalDate date2 = LocalDate.parse("2014-09-14");
boolean isAfter= date1.isAfter(date2);
System.out.println("Is after:"+isAfter);

LocalDate date3 = LocalDate.of(2017, 05, 17);
boolean isEqual = date1.isEqual(date3);
System.out.println("Is Equal:"+isEqual);

boolean isLeapYear = date1.isLeapYear();
System.out.println("Is LeapYear:"+isLeapYear);
```

When you execute this code, it will print the following output:

```
Is after:true
Is Equal:true
Is LeapYear:false
```

- The LocalDate.isAfter method returns true if the date object on which the method is invoked is **after** the date object passed in
- The LocalDate.isEqual method returns true if both dates are **equal**
- The LocalDate.isLeapYear returns true if the date object is a **Leap Year**

In addition to these methods, there are several methods that allow you to perform Date comparison. You can refer to the API documentation

## Calculating Duration

The **LocalDate** class allows you to easily calculate the duration between dates. The following code demonstrates this:

```
LocalDate date1 = LocalDate.parse("2017-05-17");
  LocalDate date2 = LocalDate.parse("2017-08-17");
  Period period = date1.until(date2);
  System.out.println("Duration between "+date1+" and "+date2+" is "+  period.getMonths()+" months");
```

The LocalDate.untill method returns the duration between 2 dates as a Period object. Period is another class in java.time. It has several methods which can be used to extract the desired information. Here the period.getMonths method is used which returns the duration in months. So when you run this code, it will print the following output:

```
Duration between 2017-05-17 and 2017-08-17 is 3 months
```

## Conclusion

So, in this article, we learnt about the Java 8 LocalDate class. We learnt how to create a LocalDate, how to perform date arithmetic and date comparison.

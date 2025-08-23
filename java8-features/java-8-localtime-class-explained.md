---
title: "Java 8 LocalTime class in with code samples"
date: "2019-08-05"
categories: 
  - "java-8-features"
tags: 
  - "java8datetimeapi"
  - "java8localtime"
---

## What is LocalTime class?

The [Java 8](https://reshmabidikar.github.io/blog.html#java-8-new-features) `LocalTime` class represents a time. It has the hour, minute, second and nanoseconds components. So for example, you can use it to represent a time like 7:30. It does not have a date, year or month component.

## LocalTime Creation

There are several static methods on this class that can be used to create a LocalTime object. The following code demonstrates this:

```java
LocalTime time1 = LocalTime.now();
System.out.println("Current time is "+time1);

LocalTime time2 = LocalTime.parse("12:30");
System.out.println("time2 is "+time2);

LocalTime time3 = LocalTime.of(5, 30);
System.out.println("time3 is "+time3);
```

- The LocalTime.now returns the current time.
- The LocalTime.parse parses the specified time and creates a LocalTime object out of it. It requires the Time to be in hh-mm format. If you specify the time in some other format, an error will occur. If your String time is in any other format, you can use the overloaded version of the parse method that accepts a DateTimeFormatter
- The LocalTime.of method creates a LocalTime object using the specified hour and minute value. There are overloaded versions of this method available that can accept the seconds and nanoseconds value as well.

In addition to these methods, there are several other methods in the**LocalTime** class that you can use to create a LocalTime object. You can check them out via the API documentation.

## Time Arithmetic

The LocalTime class allows you to easily perform time arithmetic as can be seen by the following code:

```java
LocalTime time1 = LocalTime.parse("10:30");
System.out.println("Time is "+time1);

LocalTime time2 = time1.plusHours(2);//add 2 hours
System.out.println("Plus 2 hours is "+time2);

time2 = time1.minusMinutes(10); //subtract 10 minutes
System.out.println("Minus 10 minutes is "+time2);

time2 = time1.withHour(8);//year set to 8
System.out.println("With hours set to 8 is "+time2);
```


- The LocalTime.plusHours method adds the specified number of hours to the LocalTime object
- The LocalTime.minusMinutes subtracts the specified number of minutes from the LocalTime object
- The LocalTime.withHour sets the hour field to the specified value

## Extracting Information from Time

The LocalTime class allows you to easily extract information from the Time object. The following code demonstrates this:

```java
LocalTime time = LocalTime.parse("11:45:15");
System.out.println("Time is "+time);

int hour = time.getHour();
System.out.println("Hour="+hour);

int second = time.getSecond();
System.out.println("second="+second);
```

- The LocalTime.getHour returns the hour component in the LocalTime object
- The LocalTime.getSecond returns the second component in the LocalTime object

## Time Comparison

The LocalTime class allows you to easily perform time comparison as can be seen by the following code:

```java
LocalTime time1 = LocalTime.parse("10:30:45");
LocalTime time2 = LocalTime.parse("11:15");
boolean isAfter = time1.isAfter(time2);
System.out.println(time1+" Is after "+time2+"=" + isAfter);

time2 = LocalTime.of(10,30,45);
boolean isEqual = time1.equals(time2);
System.out.println(time1+" Is equal "+time2+"=" + isEqual);
```

- The[isAfter](https://docs.oracle.com/javase/8/docs/api/java/time/LocalDate.html#isAfter-java.time.chrono.ChronoLocalDate-) method returns true if the time object on which the method is invoked is**after** the time object passed in
- The[isEqual](https://docs.oracle.com/javase/8/docs/api/java/time/LocalDate.html#isEqual-java.time.chrono.ChronoLocalDate-) method returns true if both time objects are**equal**

## Conclusion

In this blog post, we saw what is Java 8 LocalTime. We also saw a learnt how to perform time arithmetic and time comparison.

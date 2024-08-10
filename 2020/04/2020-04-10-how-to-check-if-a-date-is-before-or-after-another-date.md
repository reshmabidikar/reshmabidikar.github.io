---
title: "How to check if a Date is before or after another Date"
date: "2020-04-10"
categories: 
  - "java-date-handling"
---

In this article, I will be covering how to can check if a date is before or after another Date. You can achieve this using the **java.util.Date**, **java.util.Calendar** classes or the new Java 8 **java.util.LocalDate** class.

# Using Date class

Using the **java.util.Date** class, there are two ways to check if a date is before or after another Date. You can either use the before/after method or the compareTo method.

## Using Before/After

The `java.util.Date`class has methods `before()`and `after()`. You can use these methods to compare two dates. These methods work as follows:

- The `before`method returns true if the date on which is it invoked is before the specified date, otherwise it returns false.
- The `after`method returns true if the date on which is it invoked is after the specified date, otherwise it returns false.

The following code demonstrates this:

```
SimpleDateFormat simpleDateFormat = new SimpleDateFormat("yyyy-MM-dd");

Date date1 = simpleDateFormat.parse("2014-08-08");
Date date2 = simpleDateFormat.parse("2018-12-21");

boolean isBefore = date1.before(date2);
boolean isAfter = date1.after(date2);

System.out.println("isBefore:" + isBefore);
System.out.println("isAfter:" + isAfter);
```

So this code prints the following output:

```
isBefore:true
isAfter:false
```

## Using CompareTo

The `java.util.Date`class has a method `compareTo`. You can also use this to compare dates.  `compareTo`works as follows:

- Returns 0 if both dates are equal
- Returns a value less than 0 if the date on which it is invoked is before the date passed in
- Returns a value greater than 0 if the date on which it is invoked is after the date passed in

The following code demonstrates this:

```
SimpleDateFormat simpleDateFormat = new SimpleDateFormat("yyyy-MM-dd");

Date date1 = simpleDateFormat.parse("2014-08-08");
Date date2 = simpleDateFormat.parse("2018-12-21");

boolean before = date1.compareTo(date2) < 0 ? true : false;
System.out.println("isBefore:" + before);

boolean after = date1.compareTo(date2) > 0 ? true : false;
System.out.println("isAfter:" + after);
```

So this code prints the following output:

```
isBefore:true
isAfter:false
```

# Using Calendar class.

The `java.util.Calendar`also has methods `before()`and `after()`. You can use these methods to compare two dates.These methods work as follows:

- The `before` method returns true if the Calendar instance on which is it invoked is before the specified Calendar instance, otherwise it returns false.
- The `after` methods returns true if the Calendar instance on which is it invoked is after the specified Calendar instance, otherwise it returns false.

The following code demonstrates this:

```
Calendar cal1 = new GregorianCalendar(2018, Calendar.AUGUST, 8);
Calendar cal2 = new GregorianCalendar(2014, Calendar.DECEMBER, 21); 

boolean isBefore = cal1.before(cal2);
boolean isAfter = cal1.after(cal2);

System.out.println("isBefore:" + isBefore);
System.out.println("isAfter:" + isAfter);
```

So this code prints the following output:

```
isBefore:true
isAfter:false
```

Just like `java.util.Date`, there is a `compareTo` method on the **Calendar** class. You can also use this method to compare dates.

# Using LocalDate

[java.util.LocalDate](https://learnjava.co.in/java-8-localdate-class-explained/) is a new class added by Java 8. It makes Date manipulation/Date arithmetic very easy. It also has methods `isBefore`and `isAfter`.  These methods work as follows:

- The `isBefore`method returns true if the date on which is it invoked is before the specified date, otherwise it returns false.
- The `isAfter`method returns true if the date on which is it invoked is after the specified date, otherwise it returns false.

You can use these methods to compare two dates. The following code demonstrates this:

```
LocalDate date1 = LocalDate.of(2018,Month.AUGUST,8);
LocalDate date2 = LocalDate.of(2014,Month.DECEMBER,21);

boolean isBefore = date1.isBefore(date2);
boolean isAfter = date1.isAfter(date2);

System.out.println("isBefore:"+isBefore);
System.out.println("isAfter:"+isAfter);
```

So this code prints the following output:

```
isBefore:false
isAfter:true
```

Just like `java.util.Date`, there is a `compareTo` method on the **LocalDate** class. You can also use this method to compare dates.

\[table id=30 /\]

# Conclusion

So in this article, we saw how you can check if a date is before/after another date. We saw how to achieve this via the java.util.Date class, java.util.Calendar class and the new Java 8 java.util.LocalDate class.

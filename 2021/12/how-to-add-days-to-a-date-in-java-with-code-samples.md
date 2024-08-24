---
title: "How to add Days to a Date in Java with code samples"
date: "2021-12-04"
categories: 
  - "java-date-handling"
coverImage: "Date.png"
---

Very often, when programmers perform date manipulation, they are required to add a specified number of days to a given date. In this article, we will learn how to add days to a Date in Java.

## Using LocalDate

The [LocalDate](https://learnjava.co.in/java-8-localdate-class-explained/) class makes it very easy to add days to a Date. Let us take a look at a few examples.

### Adding days to a LocalDate

The following code sample demonstrates adding days to a LocalDate:

```
LocalDate date1 = LocalDate.of(2018, 05, 10);
System.out.println("Before adding days:"+date1);
LocalDate date2 = date1.plusDays(6);
System.out.println("After adding days:"+date2);
```

So in this case, the code above invokes the `LocalDate.plusDays` method. This adds the specified number of days to the LocalDate object on which it is invoked and returns and updated LocalDate.

So, this code prints the following output:

```
Before adding days:2018-05-10
After adding days:2018-05-16
```

Similarly, the LocalDate class has a `minusDays` method, that subtracts the specified number of days from a LocalDate object. The following code demonstrates this method:

```
LocalDate date1 = LocalDate.of(2018, 05, 10);
System.out.println("Before adding days:"+date1);
LocalDate date2 = date1.minusDays(6);
System.out.println("After adding days:"+date2);
```

This code prints the following output:

```
Before adding days:2018-05-10
After adding days:2018-05-04
```

### Adding/Subtracting other components

Similarly, the [LocalDate](https://learnjava.co.in/java-8-localdate-class-explained/) class has other methods that can be used to add/subtract months, years, weeks from a LocalDate. The following code demonstrates some of these methods:

```
LocalDate date1 = LocalDate.of(2018, 05, 10);
System.out.println("Before adding months:"+date1);
System.out.println("After adding 5 months:"+date1.plusMonths(5));
System.out.println("After substracting 4 months:"+date1.minusMonths(4));
System.out.println("After adding 2 weeks:"+date1.plusWeeks(2));
System.out.println("After substracting 1 week:"+date1.minusWeeks(1));
System.out.println("After adding 6 years:"+date1.plusYears(6));
System.out.println("After substracting 5 years:"+date1.minusYears(5));
```

This code prints the following output:

```
Before adding months:2018-05-10
After adding 5 months:2018-10-10
After substracting 4 months:2018-01-10
After adding 2 weeks:2018-05-24
After substracting 1 week:2018-05-03
After adding 6 years:2024-05-10
After substracting 5 years:2013-05-10
```

## Using the Calendar/Date class

LocalDate is a new class added by Java 8. However, if you have legacy code, there are chances that this code might be using the `java.util.Date` or `java.util.Calendar` classes. Let us now take a look at what it takes to add a number of days to a Date represented using one of these classes.

### Adding a number of days to a Calendar instance

The following code demonstrates adding days to a Date represented as a Calendar instance:

```
String strDate = "2018-05-10";
SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd");
Calendar cal = Calendar.getInstance();
cal.setTime(sdf.parse(strDate));
System.out.println("Before adding days:"+cal.getTime());
cal.add(Calendar.DAY_OF_MONTH, 6);
System.out.println("After adding 6 days:"+cal.getTime());
```

So in this case, the code above first creates a Calendar instance corresponding to a Date in String format. It then invokes the `add` method. This adds 6 days to the **DAY\_OF\_MONTH** field.

This code displays the following output:

```
Before adding days: Thu May 10 00:00:00 IST 2018
After adding 6 days: Wed May 16 00:00:00 IST 2018
```

### Adding a number of days to a Date instance

In order to add a number of days to a `java.util.Date` instance, you need to convert it to Calendar and use the same code as above. The following code demonstrates this:

```
String strDate = "2018-05-10";
SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd");
Date date = sdf.parse(strDate);
Calendar cal = Calendar.getInstance();
cal.setTime(date);
System.out.println("Before adding days:"+cal.getTime());
cal.add(Calendar.DAY_OF_MONTH, 6);
Date newDate = cal.getTime();
System.out.println("After adding 6 days:"+newDate);
```

The code above first creates a Date object. It then converts it to a Calendar object cal and invokes the `add` method on it.  This code produces the same output as before.

## Further Reading

- [Java Programming Masterclass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-the-complete-java-developer-course%2F)
- [Core Java Made Easy](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fcorejavamadeeasy%2F)

## Conclusion

In this article, we saw how to add days to a date in Java.

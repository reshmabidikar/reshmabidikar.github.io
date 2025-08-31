---
title: "How to find the number of days between two Dates"
date: "2018-08-29"
categories: 
  - "java-date-handling"
tags: 
  - "core-java"
  - "java-8"
  - "java-date-handling"
---

In this post, I am going to demonstrate how you can find the number of days between two dates. The following code snippet demonstrates this:



#### Code snippet

````java

public static void main(String[] args) { 
    try { 
        DateFormat df = new SimpleDateFormat("yyyy-MM-dd"); 
        Date today = df.parse("2018-08-24"); 
        Date future = df.parse("2018-09-04"); 
        Date future = getFutureDate(); 
        int daysBetween = daysBetween(today,future); 
        System.out.println("days between = "+daysBetween); 
    } catch (ParseException e) { printStackTrace(); 
    }

}

private static int daysBetween(Date date1, Date date2){ 
    
    long time1 = date1.getTime(); //Returns no of milliseconds since January 1, 1970, 00:00:00 GMT
        long time2 = date2.getTime();

        long diffInMs = time2-time1; int numOfMsInOneDay = 1000 \* 60 \* 60 \* 24;

        int daysBetween = (int) (diffInMs / numOfMsInOneDay); 
        return daysBetween;

} 

````

#### Explanation

The [Date.getTime](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html#getTime--) method is first used for each Date object. This method returns the number of milliseconds elapsed since January 1, 1970, 00:00:00 GMT for each Date object.The difference in the milliseconds since January 1, 1970, 00:00:00 GMT is then calculated.

Next, the number of milliseconds in one day is calculated. Finally, the number of days between the two dates is calculated by dividing the difference in milliseconds with the number of milliseconds in one day.


#### Output

So if you run the code above, you will see the following output:

```
days between = 11
```

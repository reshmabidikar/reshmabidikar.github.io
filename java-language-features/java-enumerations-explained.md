---
title: "Java Enumerations explained"
date: "2018-12-24"
categories: 
  - "java_language_features"
tags: 
  - "core-java"
  - "enum"
---

Just like the primitive data types, there is another data type supported by Java which is the enumerated type. In this blog post, I will be explaining Java enumerations in detail.

#### Enum definition

An enumerated type is a type whose values consist of a fixed set of constants. Common examples are days of the week which take the values _Sunday,Monday, Tuesday,Wednesday,Thursday,Friday and Saturday_. Another example could be Colors which could take values like _Red,Blue,Yellow, Green_ corresponding to the colors.

In Java, you can define an enumerated type by using the **enum** keyword. The syntax is as follows:

````java
enum NameOfEnum {value1,value2,value3.......,valuen}
````

You can have as many values as you wish. For example, you can define an enum for the days of the week as follows:

````

enum Days {Sunday,Monday, Tuesday,Wednesday,Thursday,Friday,Saturday}
````

The values Sunday,Monday, etc are called enumeration constants. For the **enum** Days, these are the only values that are allowed.

You should use enumerated types when you need to represent a fixed set of constants where you know all possible values at compile time.

The values of an **enum** are static values and you can retrieve them using the dot operator. So to fetch a value from the Days **enum**, you can write **Days.Sunday**;

#### Enum as DataType

An **enum** is a datatype. So the way you require an int variable to store an int value, you require an **enum** of type Days to store a value of **Enum** days. So for example, to retrieve and store the value "Saturday" from the **enum** Days, you need to declare a variable of type Days as:

````java
Days today = Days.Saturday;
````

To be specific, you cannot assign an **enum** variable of one type with a value of another type, it will result in a compilation error. So if you declare another **enum** called Colors and try to write something like this:

````
Days today = Colors.BLUE;
````

This will result in a compilation error because the left side **enum** is Days while the right side is Colors.

#### Values as Numbers

The **enum** internally stores the enumeration constant as numerical values. So in the Days example above, the **enum** Days will have the values 0,1,2,3,4,5,6 internally. However, while using the enumeration constants, they are output as descriptive values.

#### Enum declaration scope

You cannot declare an **enum** in any method of a class. So you need to declare an enum outside the main method.

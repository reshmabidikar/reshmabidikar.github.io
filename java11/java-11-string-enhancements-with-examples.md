---
title: "Java 11 String enhancements with examples"
date: "2020-12-09"
categories: 
  - "java-11"
coverImage: "String-imporvements-scaled.jpg"
---

Java 11 has made some significant improvements to the String class. In this article, we will be exploring the Java 11 String enhancements

## strip

Java 11 has added a new `strip` method to the String class. This method removes all the leading and trailing whitespaces in a String. Consider the following code:

```java
String input = "   Hello   World   ";
System.out.println(input);
String output = input.strip();
System.out.println(output);
```

This code produces the following output:

```
Hello World
Hello World
```

In addition to `strip`, the String class also has a `trim` method which also removes all leading and trailing whitespaces. This method exists right from the early versions of Java and so has some limitations. Earlier, the **ASCII** character set was used. So, `trim` can only remove whitespaces represented by **ASCII** characters. However, later on Java adopted the **Unicode** character set.  **Unicode** has some additional characters that represent whitespace. The `trim` method cannot remove these whitespaces. So, the `strip` method was added to overcome this limitation.

For example consider the following code:

```java
String input = " Hello ";
System.out.println("Strip output:" + input.strip());
System.out.println("Trim output:" + input.trim());
```

```java
input = '\u2001' + "Hello" + '\u2001';
System.out.println("Strip output:" + input.strip());
System.out.println("Trim output:" + input.trim());
```

This code produces the following output:

```
Strip output:Hello
Trim output:Hello
Strip output:Hello
Trim output:?Hello?
```

## stripLeading

The `stripLeading` method removes all the leading whitespaces in a String. The following code demonstrates this method:

```java
 String input = " Hello World ";
System.out.println(input);
String output = input.stripLeading();
System.out.println(output);
```

This code produces the following output:

```
Hello World
Hello World
```

## stripTrailing

The `stripTrailing` method removes all the trailing whitespaces in a String. The following code demonstrates this method:

```java
String input = " Hello World ";
System.out.println(input);
String output = input.stripTrailing();
System.out.println(output);
```

This code produces the following output:

```
Hello World 
Hello World
```

## isBlank

The `isBlank` method checks if the String is empty or contains only whitespaces and returns a boolean value accordingly. The following code demonstrates this method:

```java
String input = "";
System.out.println("input.isBlank:"+input.isBlank());
input=" ";
System.out.println("input.isBlank:"+input.isBlank());
input = " Hello World ";
System.out.println("input.isBlank:"+input.isBlank());
```

This code produces the following output:

```java
input.isBlank:true
input.isBlank:true
input.isBlank:false
```

The String class also has a `isEmpty` method. While the `isBlank` method returns true if the String is empty or contains only whitespaces, the isEmpty method returns true only if the String is empty that is its length is 0.

Consider the following code:

```java
String input = "";
System.out.println("input.isBlank:" + input.isBlank());
input = " ";
System.out.println("input.isBlank:" + input.isBlank());
input = " Hello World ";
System.out.println("input.isBlank:" + input.isBlank());
```

This code produces the following output:

```java
input.isBlank:true
input.isEmpty:true
input.isBlank:true
input.isEmpty:false
```

## lines

The `lines` method returns a [Stream](https://reshmabidikar.github.io/2019/05/java-8-stream-api.html) of String values which are separated by line terminators like **\\n**, **\\r** or **\\n\\r.** The following code demonstrates this method:

```java
 String input = "I am line 1.\nI am line 2. \rI am line 3.";
Stream<String> lines = input.lines();
lines.forEach(str -> System.out.println(str));
```

This code uses the [Java 8 forEach](https://reshmabidikar.github.io/2019/04/java-8-foreach.html) method to iterate over the [Stream](https://reshmabidikar.github.io/2019/05/java-8-stream-api.html) . It produces the following output:

```
I am line 1.
I am line 2. 
I am line 3.

```

If the input String does not have any line terminator characters, it simply returns a [Stream](http://localhost/learnjava/java-8-streams/) having the input String. So consider the following code:

````java
String input = "I am line 1.I am line 2. I am line 3.";` `Stream<String> lines = input.lines();` `lines.forEach(str -> System.out.println(str));`
````

This code produces the following output:

```
I am line 1.I am line 2. I am line 3.
```

## repeat

The `repeat` method accepts as parameter an int value and creates a String that consists of the input String repeated the specified number of times. The following code demonstrates this method:

```java
 String input = "Hello ";
String output = input.repeat(3);
System.out.println(output);
```

This code produces the following output:

```
Hello Hello Hello
```

If the input String is empty or if you specify 0 as the input parameter, then this method returns an empty String. So consider the following code:

```java
 String input = "Hello ";
System.out.println("Output:"+input.repeat(0));
input = "";
System.out.println("Output:"+input.repeat(2));
```

This code produces the following output:

```
Output:
Output:
```

## Conclusion

So, in this article, we saw some of the Java 11 String enhancements. We took a look at the strip, stripLeading, stripTrailing, isBlank, lines and repeat methods

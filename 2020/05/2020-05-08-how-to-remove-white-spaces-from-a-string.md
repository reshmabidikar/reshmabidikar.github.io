---
title: "How to remove white spaces from a String"
date: "2020-05-08"
categories: 
  - "strings"
---

Very often, you will come across programming scenarios where you will need to remove all white spaces from a String.  In this article, we will see how to remove whitespaces from a String in Java.

## Using String.trim

The String class has a method trim. You can use this to remove leading and trailing white spaces from a String. The following code demonstrates this:

```
String str1 = "   Hello World  ";
System.out.println(str1);
System.out.println(str1.trim());
```

This code creates a String str1 that has leading and trailing whitespaces. It then invokes the trim method. So this code prints the following output:

```
     Hello World 
Hello World
```

## Using String.replace

Note that the trim method removes only the leading and trailing white spaces. It does not remove white spaces that are in between the String. There is a replace method on the String class that replaces the specified character with some other character. You can use this method to remove the spaces in a String. The following code demonstrates this:

```
String str1 = "   Hello World  ";
String str2 = str1.replace(" ", "");
System.out.println(str2);
```

This code invokes the str.replace method. The first argument is the character that needs to be replaced, here a space (" ") is specified. The second argument is the new character, here an empty String ("") is specified. So this code prints the following output:

```
HelloWorld
```

## Using String.replaceAll

In addition to the replace method, there is also a replaceAll method on the String class. It accepts as parameters  a regular expression and a replacement value. It replaces each substring that matches the regular expression with the replacement value. The following code demonstrates this:

```
String str1 = "   Hello World  ";
String str2 = str1.replaceAll("\\s", "");
System.out.println(str2);
```

This code invokes the str.replaceAll method. The first argument is a regular expression that matches white spaces.,The second argument is an empty String ("") , which is the replacement value. So this code prints the following output:

 

```
HelloWorld
```

## Conclusion

So in this article, we saw how you can remove all the whitespaces in a String in Java. We saw how the trim(), replace() and replaceAll() methods can be used to remove whitespaces.

---
title: "How to check if a String has digits in Java"
date: "2019-01-16"
categories: 
  - "java-string-examples"
  - "strings"
tags: 
  - "core-java"
  - "java-regular-expressions-en"
  - "java-string-handling"
---

In this blog post, I will be explaining how you can check if a String has digits. There are several ways to do this. Consider the following code snippet:

````java

package learnjava.strings;

import java.util.regex.Pattern;

public class CheckIfStringHasDigits {

    public static void main(String[] args) { 
    String str = "Hello123"; String regex = ".*[0-9].*";

    //Method 1 - Using String.matches 
    boolean matches = str.matches( regex ); 
    System.out.println("Using String.matches="+matches);

    //Method 2 - Using pattern.matches 
    matches = Pattern.matches( regex , str); 
    System.out.println("Using pattern.matches="+matches);

    //Method 3 - using pattern.compile 
    matches = Pattern.compile( regex).matcher( str ).find(); 
    System.out.println("Using Pattern.compile="+matches);

    //Method 4 - Checking each character 
    boolean digitFound = false; 
    char[] characters = str.toCharArray(); 
    for(char c:characters){ 
        if(Character.isDigit(c)) { 
            digitFound = true; 
            break; 
        } 
    } 
    System.out.println("Using manual method="+digitFound);
    }
}
````

#### Method 1

This method uses the [String.matches](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#matches-java.lang.String-) method. This method returns true if the String on which it is invoked matches the regular expression passed.

#### Method 2:

This method uses the [Pattern.matches](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html#matches-java.lang.String-java.lang.CharSequence-) method. This method accepts a regular expression and String. It returns true if the regular expression matches the input String.

#### Method 3

This method uses [Pattern.compile.matcher.find](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Matcher.html#find--). This behaves in exactly the same way as [Pattern.matches](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html#matches-java.lang.String-java.lang.CharSequence-) method. However, here the regular expression is compiled separately. If you are using the same regular expression multiple times, compiling it once and using it will give some performance benefits.

#### Method 4:

This method manually checks each character in the input String. The moment it finds a digit, it returns a true to indicate that there is a digit in the input String.

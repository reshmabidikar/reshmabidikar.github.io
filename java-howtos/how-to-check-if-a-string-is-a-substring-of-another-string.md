---
title: "How to check if a String is a substring of another String"
date: "2019-01-17"
categories: 
  - "java-string-examples"
  - "strings"
tags: 
  - "core-java"
  - "java-string-handling"
---

In this blog post, I will be explaining how you can check if a String is a substring of another String. Consider the following code snippet:

````java
package learnjava.strings;

public class CheckSubstringDemo {

    public static void main(String[] args) { 
        String strToCheck = "Hello World"; 
        String valueToCheck = "Hello";

        //Method 1 - Use Contains 
        if(strToCheck.contains(valueToCheck)) 
            System.out.println(valueToCheck+" is present in "+strToCheck); 
        else 
            System.out.println(valueToCheck+" is NOT present in "+strToCheck);

        //Method 2 - Use startsWith and indexOf 
        if(strToCheck.startsWith(valueToCheck) || strToCheck.indexOf(valueToCheck) > 0)     System.out.println(valueToCheck+" is present in "+strToCheck); 
        else 
            System.out.println(valueToCheck+" is NOT present in "+strToCheck);
    }
}
````
This code snippet demonstrates two ways to check if a String is a substring of another String.

#### Method 1:

This method uses the [String.contains](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#contains-java.lang.CharSequence-) method. This returns true if the String on which it is invoked contains the String that is specified. It accepts a [CharSequence](https://docs.oracle.com/javase/8/docs/api/java/lang/CharSequence.html) as input. [CharSequence](https://docs.oracle.com/javase/8/docs/api/java/lang/CharSequence.html) is an interface. The [String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html) class implements this interface and so you can pass in a String value to this method.

#### Method 2:

This method uses the [String.indexOf](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#indexOf-java.lang.String-) and [String.startsWith](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#startsWith-java.lang.String-) method. The [String.indexOf](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#indexOf-java.lang.String-) method returns the position in the String on which it is invoked of the first occurrence of the String passed in. So if the String passed in is a substring, this method returns a non zero value. However, there is a small catch to this. If the String passed is is at the start, then this method will return a 0 since it just returns the position at which the String is present. So if we just use the [String.indexOf](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#indexOf-java.lang.String-) method, our code will print a wrong output when the specified String is at the starting position. So to avoid this situation, the [String.startsWith](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#startsWith-java.lang.String-) method is also used. This method returns a true if the String on which it is invoked starts with the specified String. So our code uses the [String.indexOf](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#indexOf-java.lang.String-) and [String.startsWith](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#startsWith-java.lang.String-) to check for both conditions.

When the above code snippet is run, it will produce the following output:

```
Hello is present in Hello World
Hello is present in Hello World
```

Note that both these methods are case sensitive. So for ex. if the valueToCheck is changed to "HELLO", the following output will be printed:

```
HELLO is NOT present in Hello World
HELLO is NOT present in Hello World
```

If you want to perform a case insensitive search, you need to convert both the input String as well as the String to check to either lowercase or uppercase and then perform the check like this:

````java
if(strToCheck.toLowerCase().contains(valueToCheck.toLowerCase())) 
    System.out.println(valueToCheck+" is present in "+strToCheck); 
else 
    System.out.println(valueToCheck+" is NOT present in "+strToCheck);

````

This will print the following output:

```
HELLO is present in Hello World
```

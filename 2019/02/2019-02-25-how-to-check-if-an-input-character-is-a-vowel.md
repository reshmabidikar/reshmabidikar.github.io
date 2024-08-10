---
title: "How to check if an input character is a vowel"
date: "2019-02-25"
categories: 
  - "java-string-examples"
  - "strings"
tags: 
  - "java-string-handling"
---

In this blog post, I will be demonstrating how you can check if an input character is a vowel. I will be using [Enum](https://docs.oracle.com/javase/7/docs/api/java/lang/Enum.html) for this. If you'd like to study enums in detail, you can refer to [this](https://learnjava.co.in/java-enumerations-explained/) blog post.

 

Consider the following code snippet:

\[java\]

public enum Vowels { a,e,i,o,u; }

public class CheckIfVowel {

public static void main(String\[\] args) { System.out.println("Enter a character:"); Scanner scanner = new Scanner(System.in); String input = scanner.nextLine(); boolean found = false; for(Vowels vowel:Vowels.values()){

if (vowel.name().equalsIgnoreCase(input)){ found = true; break; }

} if(!found) System.out.println("Input "+input +" is NOT a vowel"); else System.out.println("Input "+input +" is a vowel"); scanner.close(); }

}

\[/java\]

#### Code explanation

First, the code declares an Enum called **Vowels**. It is assigned the vowels i.e. **a,e,i,o,u**.  We are using the **CheckIfVowel** class to check if the input character is a vowel. The input character is read using the [Scanner](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html) class. A for loop iterates through the **Vowels** enum values. It compares each enum value with the input character to check if there is a match. A **case-insensitive** comparison is done.   If there is a match, it sets the **boolean flag found** to true and breaks from the for loop. Depending on the value of the boolean flag **found**, the Sysout statement prints whether the value is found or not.

 

#### Code output

So if you run this code with the input value as **a**, the following will be printed:

```
Enter a character:
a
Input a is a vowel
```

Also, if you run this code with the input value as Z,  the following will be printed:

```
Enter a character:
Z
Input Z is NOT a vowel
```

 

You can also modify this code and add additional checks if check if the input character is an alphabet or digit, etc.

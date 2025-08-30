---
title: "How to count the number of vowels and consonants in a String"
date: "2019-05-29"
categories: 
  - "java-examples"
tags: 
  - "consonants"
  - "java-string"
  - "s-vowels"
---

In this blog post, I will be demonstrating a Java program that counts the number of vowels and consonants in a String.

Consider the following code sample:

```java
public class CountVowelsAndConsonantsDemo {
  
  private static List<Character> vowels = Arrays.asList('a','e','i','o','u','A','E','I','O','U');

  public static void main(String[] args) {
    System.out.println("Enter a String:");
    Scanner scanner = new Scanner(System.in); 
    String input = scanner.nextLine();
    char[] inputArr = input.toCharArray();
    int vowelCount = 0;
    int consonantCount = 0;
    for(char c:inputArr){
      if(vowels.contains(c)){
        vowelCount++;
      }
      else
        consonantCount++;
    }
    System.out.println("Number of vowels:"+vowelCount);
    System.out.println("Number of consonants:"+consonantCount);

  }

}
```

The code declares and initializes a list 'vowels' with all the vowels in lowercase and uppercase. It then iterates through the characters in the input String. It checks if each character is present in the vowels list, if so it increments the vowels counter, otherwise it increments the consonants counter.

When you run this code, it will print the following output:

```
Enter a String:
HELLO
Number of vowels:2
Number of consonants:3
```

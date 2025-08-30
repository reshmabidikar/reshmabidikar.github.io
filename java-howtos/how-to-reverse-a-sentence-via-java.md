---
title: "How to reverse a sentence via Java"
date: "2019-02-06"
categories: 
  - "java-string-examples"
  - "strings"
tags: 
  - "java-string-handling"
---

In this blog post, I will be demonstrating how you can reverse a sentence via Java. So if the input String is "Hello World", the program will print "World Hello".

Consider the following code snippet:

````java

package learnjava.strings;

public class ReverseASentenceDemo {

    public static void main(String[] args) { 
        String inputStr = "This is a test program"; 
        System.out.println("Input String is "+inputStr); 
        String[] words = inputStr.split(" "); 
        StringBuffer reversedString = new StringBuffer(""); 
        for(int i = words.length-1; i >= 0; i --) { 
            reversedString.append(words\[i\]); 
            if(i != 0) 
                reversedString.append(" "); 
        } 
        System.out.println("Reversed String is "+reversedString.toString());
    }
}
````

In this code, the input String is first split using the [String.split](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#split-java.lang.String-) method. It is split based on spaces, so it returns an array of words. This array is then traversed in the reverse direction. Each word in the array is appended to a new [StringBuffer](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuffer.html) object. If the current word is not the last word, a space is also added after each word.

So the above code will print the following output:

```
Input String is This is a test program
Reversed String is program test a is This
```

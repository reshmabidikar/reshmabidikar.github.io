---
title: "How to split a String via Java"
date: "2019-01-14"
categories: 
  - "java-string-examples"
  - "strings"
tags: 
  - "core-java"
  - "java-string-handling"
---

In this blog post, I will be explaining how you can split a String via Java. Consider the following code snippet:

````

package learnjava.strings;

public class SplitStringDemo {

    public static void main(String[] args) { 
        String str = "This is a test String"; 
        String[] words = str.split(" "); 
        System.out.println("There are "+words.length+" words"); 
        for(String word:words) { 
            System.out.println(word); 
        }
    }
}
````

There is a method called [String.split](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#split-java.lang.String-). It accepts any regular expression. It splits the String around matches of the specified regular expression. Here, I am simply using a space. This will split the input sentence into words. So if you run the above code, you will get the following output:

```
There are 5 words
This
is
a
test
String
```

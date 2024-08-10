---
title: "How to replace a String with another String in Java"
date: "2019-01-26"
categories: 
  - "java-string-examples"
  - "strings"
---

In this blog post, I will be demonstrating how you can replace a String with another String via Java. Consider the following code snippet:

\[java\]

package learnjava.strings;

public class ReplaceStringDemo {

public static void main(String\[\] args) { String str = "Good Morning. Another String with the word Morning."; String newStr= str.replace("Morning", "Night"); System.out.println("Original String="+str); System.out.println("new String="+newStr);

}

}

\[/java\]

 

There is a [String.replace](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#replace-java.lang.CharSequence-java.lang.CharSequence-) method.  It accepts as input the String to be replaced and the value with which it should be replaced. It then replaces each occurrence of the first String with the second String. This method actually accepts  [CharSequence](https://docs.oracle.com/javase/8/docs/api/java/lang/CharSequence.html) as input. [CharSequence](https://docs.oracle.com/javase/8/docs/api/java/lang/CharSequence.html) is an interface. The [String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html) class implements this interface and so you can pass in a String value to this method.

So when you run the code above, it will print the following output to the console:

```
Original String=Good Morning. Another String with the word Morning.
new String=Good Night. Another String with the word Night.
```

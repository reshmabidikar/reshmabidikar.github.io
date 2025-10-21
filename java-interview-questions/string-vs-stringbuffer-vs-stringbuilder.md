---
title: "String vs StringBuffer vs StringBuilder"
date: "2018-12-19"
categories: 
  - "java-interview-questions"
  - "strings"
tags: 
  - "core-java"
  - "java-string-handling"
---

A very common interview question is to ask the difference between **String, StringBuffer** and **StringBuilder**. So in this blog post, I am going to explain how they are different.

#### What is a String?

A [String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html) is a Java class. It is designed to hold a set of characters like alphabets, numbers, special characters, etc. **String** objects are constants, their values **cannot** be **changed** after they are created. So, **String** objects are also called **immutable** objects. For example, consider the following code snippet:

````java
String str = "abc"; //line 1
str = str+"xyz"; //line 2
````

When the line 2 is executed, The object "_abc_" remains as it is and a new object is created with the value "abc" appended with "xyz". The object reference "_str_" no longer points to the memory address of "_abc_", but it points to the address of "abc_xyz_". And what about "_abc_"? It continues to exist as it is until it is garbage collected.Refer [this](http://learnjava.co.in/how-are-java-strings-immutable/) blog post to read more.

#### What is a StringBuffer?

[StringBuffer](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuffer.html) is a peer class of String that provides much of the functionality of strings. While a String is immutable, a **StringBuffer** is **mutable**. For example, consider the following code snippet:

````java
StringBuffer buf = new StringBuffer("abc"); //line 1 
buf = buf.append("xyz"); //line 2
````

In this case, when line 2 of the code is executed, the String "_xyz_" is appended to the String "_abc_" in the same object called "buf". So a new object is not created when line 2 of the code is executed.

#### What is a StringBuilder?

[StringBuilder](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html) is also a **mutable** class that allows you to perform String manipulation. It was introduced in Java 1.5. It is basically an unsynchronised version of **StringBuffer**. So while the **StringBuffer** is thread-safe, the **StringBuilder** is not. Since the **StringBuilder** is **not synchronised**, it is slightly more efficient than **StringBuffer**.

#### How are they similar?

All three String classes can be used to perform String manipulation.

#### What differentiates them?

So as mentioned earlier, here are the key differences between the String, StringBuffer and StringBuilder classes

- A String is immutable, StringBuffer and StringBuilder are mutable
- StringBuffer is thread-safe while the StringBuilder is not
- StringBuilder is slightly more efficient than StringBuffer

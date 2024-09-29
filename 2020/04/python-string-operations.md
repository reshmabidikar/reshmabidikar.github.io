---
title: "Python String operations"
date: "2020-04-14"
categories: 
  - "python"
---

In my [earlier](https://learnjava.co.in/python-numeric-and-string-variables/) article, I covered Python numeric and String variables. Python supports several String operations. In this article, I will be demonstrating the Python String operations

# Introduction

You can create String variables by simply assigning a String value to the variable name. The String variable can be enclosed either in single quotes or double quotes. The following code demonstrates this:

```
a = 'Hello'
b = "world"
```

This code creates two String variables `a`and `b`

# How Python treats Strings

Python treats Strings as a sequence of character. The **first character** is at position **0** and the **last character** is at a position which is equal to the **length of the String -1**. In addition, the end of the String is considered to be at -1 position.

For example consider the String "**Hello World**". In forward direction the character '**H**' is at position **0** and the character '**d**' is at position **10**. In the backward direction, the character '**d**' is at position **\-1** and the character '**H**' is at position **\-11**.

# Slice Operator

The slice operator helps to create **substrings**. It consists of **\[\]** or **\[:\]**. In order to create sun-strings, you need to specify the position within the slice operator. The following code demonstrates this:

```
str = 'This is a Java program'

print(str[0])
print(str[0:4])
print(str[10:])
print(str[:4])
print(str[-1])
print(str[5:-1])
print(str[-7:-1])

```

This code prints the following output:

```
T
This
Java program
This
m
is a Java progra
progra
```

# Concatenation Operator

Just like in Java, the '**+**' operator acts as the **concatenation operator**. It helps in concatenating Strings. The following code demonstrates this:

```
str1='Hello'
str2 = ' World'
str3 = str1+str2
print(str3)
```

This code prints the following output:

```
Hello World
```

# Repetition Operator

The **repetition operator(\*)** helps to repeat a String. You need to specify the String to be repeated, followed by the repetition operator, followed by the number of times the String should be repeated. The following code demonstrates this:

```
str1='Hello '
str2 = str1*5
print(str2)
```

This code repeats the String "**Hello** " **5** times. So this code prints the following output:

```
Hello Hello Hello Hello Hello
```

\[table id=30 /\]

## Further Learning

[The Python Masterclass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-the-complete-python-developer-course%2F) [Everything you need to know about Python](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fthe-python-bible%2F) [Python for beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-programming-projects%2F) [Python for finance](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-for-finance-investment-fundamentals-data-analytics%2F)

# Conclusion

So in this article, we took at look at the String operations supported by Python. We understood the slice operator, concatenation operator and the repetition operator.

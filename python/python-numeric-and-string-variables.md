---
title: "Python Numeric and String variables"
date: "2020-03-27"
categories: 
  - "python"
---

In this article, I will be covering Python numeric and String variables

## Python Numeric and String Variables Introduction

Unlike Java, in Python, **variables do not have a data type**. You just need to specify a variable name. Also, unlike Java, you do not need to declare a variable to be of a particular data type. Python automatically allocates memory to a variable the moment you assign it a value.

## Creating a variable

In order to create a variable, you just need to specify the **variable name**, followed by the **assignment operator** (=) followed by the **value**. This automatically allocates memory to the variable based on the data type of the assigned value.

The following code demonstrates this:

```python
i=10
```

This code declares the variable i and assigns the value 10 to it.

## Python Numeric Variables

You can create numeric variables by simply assigning a number to the variable name. Python supports storing whole numbers and decimal numbers.

The following code demonstrates this:

```python
a = 10
b = 100.5
```

This code creates the variables '**a**', '**b**'

The variable '**a**' is of **integer** type with the value '**10**'

The variable '**b**' is of **decimal** type with the value **100.5**

## Python String Variables

You can create String variables by simply assigning a String value to the variable name. The String variable can be enclosed either in single quotes or double quotes. The following code demonstrates this:

```python
c = 'Hello'
d = "world"
```

This code creates the variables '**c**', '**d**'

The variable '**c**' is a String variable with the value '**Hello**'

The variable '**d**' is also a String variable with the value '**World**'.

Python also supports a number of String operations. You can check out my [Python String operations](https://learnjava.co.in/python-string-operations/) article to know more.

## Assigning Multiple Values

Python allows you to assign multiple values to variables at once. The following code demonstrates this:

```python
a,b=200
c=d=e=10.5
f,g=1,'Hello'
```

**a,b** are assigned the value **200**

**c,d,e** are assigned the value **10.5**

**f** is assigned the value **1** and **g** is assigned the value **Hello**

## Changing Data Type

You can change the data type even after assigning a value to it. So you can do the following:

```python
i=10
i='Hello'
```

This code first assigns the value **10** to the variable **i**. It then assigns the value '**Hello**'

## Variable Naming Rules

Python variable names must follow the following rules:

- It cannot start with a number, it must start with a **letter** or the **underscore character**
- It can only contain **alpha-numeric characters and underscores**

## More Variables

In addition, Python supports variables of the following types:

- [Lists](python-lists-and-list-operations.md)
- [Tuples](python-tuples.md)
- [Dictionary](python-dictionary.md)

You can click the links above to understand more about these types.

## Further Learning

- [The Python Masterclass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-the-complete-python-developer-course%2F) 
- [Everything you need to know about Python](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fthe-python-bible%2F) 
- [Python for beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-programming-projects%2F) 
- [Python for finance](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-for-finance-investment-fundamentals-data-analytics%2F)

## Conclusion

In this article, I covered how Python variables work and Python Numeric and String variables.

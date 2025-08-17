---
title: "Reading User Input in Python With Code Sample"
date: "2020-08-19"
categories: 
  - "python"
tags: 
  - "python"
---

In this article, I will explain how to read user input in Python. Python 2 and Python 3 differ slightly in the ways that they support reading user input. Though the main focus of this article would be to demonstrate how to read user input in Python 3, I will quickly touch upon the Python 2 approach as well and explain how it differs from Python 3

## Reading User Input in Python 3

Python 3 provides a method `input()`. You can use this to read input that a user enters. This method treats the value entered by a used as a String.

The following code demonstrates this:

```python
name = input("Enter your name:")
print("Hello ",name)

```

- The `input()` method accepts as parameter a String that it displays to the user
- It then assigns the value that the user enters to the name variable

The `input()` method converts the value entered by a user to **String**. So, if you want to read an integer type, you need to use typecasting. Python provides an in-built method `int()`that converts a value to an Integer. The following code demonstrates this:

```python
num = int(input("Enter a number:"))

if num%2==0:
    print("Number is even")
else:
    print("Number is odd")
```

- The `int()` method typecasts the value read via `input()` to an integer
- The code then checks if the number is even or odd and prints a message accordingly

Just like the `int()` method, Python supports a `float()` method. You can use this method to typecast the input that the user enters to **float**.

## Reading User Input in Python 2

Python 2 supports two in-built methods to read user input. These are as follows:

- `raw_input()`\- This is similar to the `input()` function in Python 3. It converts the value entered by a user to a String
- `input()` - This method converts the value entered by the user to the appropriate data type.

## Further Learning

- [The Python Masterclass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-the-complete-python-developer-course%2F) 
- [Everything you need to know about Python](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fthe-python-bible%2F) 
- [Python for beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-programming-projects%2F) 
- [Python for finance](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-for-finance-investment-fundamentals-data-analytics%2F)

## Conclusion

So in this article, we understood how to read user input in Python. We took at look at the input() method in Python 3. We also saw how to use typecasting to convert the user input to data of the appropriate type. Finally, we touched upon reading user input in Python 2 and how it differs from Python 3.

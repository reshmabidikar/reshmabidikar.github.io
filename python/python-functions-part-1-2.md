---
title: "Python Functions - Part 1"
date: "2020-12-23"
categories: 
  - "python"
coverImage: "Python-functions.jpg"
---

In this article, I will be giving you an introduction to Python functions.

## What is a Python function

A Python function is nothing but a block of code with a name. You can use its name to execute the code multiple times without having to write the code each time. It is similar to a method in Java except that it need not be defined within a class.

## How to define a function

In order to write the code for a function, we first need to create a Python module. You can refer to [this](how-to-create-a-basic-python-program-in-eclipse-using-pydev.md) article to understand how to create a Python module. Let us assume that we have a module `functions.py.` Within this module, you can specify your first function. Consider the following code:

```python
def add():
    num1 = int(input("Enter the first number:"))
    num2 = int(input("Enter the second number:"))
    
    result = num1+num2
    print("sum is ",result)

```

This code specifies a function `add`. You need to specify the keyword **def** before the function name. The function name is followed by empty parentheses. This indicates that the function does not accept any arguments. After the parentheses, you need to specify a colon which indicates the start of the function body. In this case, the function body consists of code that [reads input](reading-user-input-in-python-with-code-sample.md) numbers, adds them and prints the result.

## How to invoke a function

In order to invoke the function, you simply need to specify the function name. If the function accepts any parameters, you can specify these within parentheses after the function name, otherwise you need to specify empty parentheses. You can invoke a function from another function or you can directly execute it from within a Python module. In order to directly execute the function from within a module, you just need to specify it in the module. So for example, in order to invoke the add function defined above, you can specify the following in the module:

```python
add()
```

When you execute the code, it prints the following output:

```
Enter the first number:4
Enter the second number:7
sum is 11


```

## Further Learning

- [The Python Masterclass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-the-complete-python-developer-course%2F) 
- [Everything you need to know about Python](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fthe-python-bible%2F) 
- [Python for beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-programming-projects%2F) 
- [Python for finance](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-for-finance-investment-fundamentals-data-analytics%2F)

## Conclusion

So, in this article, we understood what Python functions are. We also saw how to write a function and invoke it from within a Python module. [Part 2](python-functions-arguments-with-examples.md) of this article explains about the different types of python function arguments.

---
title: "Python While Loop with code samples"
date: "2021-04-22"
categories: 
  - "python"
coverImage: "Python-while-loop-scaled.jpg"
---

Much like a Java while loop, you can use a Python while loop to repeatedly execute a block of code as long as a condition is true. In this article, we will learn more about the Python while loop.

## Python While loop Syntax

A while loop in Python has the following syntax:

```python
while <condition>:
  loop body
```

The while keyword is followed by a condition. If the condition evaluates to true, the body of the loop is executed. Once the body of the loop is completed, the condition is checked again and this is repeated until the condition evaluates to false at which point the loop is exited.

## While loop Sample Code

The following code demonstrates how you can use the while loop:

```python
num=10
counter=1
total=0
while counter<=num:
 total += counter
 counter+=1
print("sum of first 10 numbers is",total)
```

This code adds the numbers from 1 to 10 and prints the sum. It uses a while loop to iterate from 1 to 10. The while loop checks the condition counter <= num and if so adds the current value of counter to total. It then increments counter. It again checks the condition and this is continued till the condition becomes false after which the loop is exited.

This code produces the following output:

```
sum of first 10 numbers is 55
```

## While loop with else

The while loop can optionally be followed with an else statement. Within the else statement, you can specify the code that you want to execute when the condition in the while loop becomes false.

It has the following syntax:

```python
while <condition>: 
 loop body
else:
 code to be executed when condition is false
```

## While loop with else sample code

The following code demonstrates a while loop with else statement:

```python
num=10
counter=1
total=0
while counter<=num:
 print(counter)
 total += counter
 counter+=1
else:
    print("counter reached:",counter," so loop exited")
print("sum of first 10 numbers is",total)
```

This code specifies an else statement after the while loop. The code within the else block is executed once the condition in the while statement is false.

This code produces the following output:

```
1
2
3
4
5
6
7
8
9
10
counter reached: 11
sum of first 10 numbers is 55

```

## Further Learning

- [The Python Masterclass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-the-complete-python-developer-course%2F) 
- [Everything you need to know about Python](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fthe-python-bible%2F) 
- [Python for beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-programming-projects%2F) 
- [Python for finance](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-for-finance-investment-fundamentals-data-analytics%2F)

## Conclusion

So, in this article, we learnt about the Python while loop. We saw how it can be used to repeatedly execute a block of code. We also saw how to use the while loop with an else statement.

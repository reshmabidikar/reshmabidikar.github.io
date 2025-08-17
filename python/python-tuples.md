---
title: "Python Tuples Explained With Code Samples"
date: "2020-06-09"
categories: 
  - "python"
---

In my [earlier](python-lists-and-list-operations.md) article, I had covered Python Lists. In this article, I will be covering Python tuples.

## What is a Tuple

Just like a Python list, a tuple is a set of values. Unlike a List, a tuple is **immutable**, so you cannot modify it after it is created. Also, the values in a **List** are **enclosed in square brackets**, a **tuple** on the other hand, **uses parentheses**.

## Creating a Tuple

You can create a tuple by specifying comma separated values directly or within parentheses. The following code demonstrates this:

```python
mytuple1 = (1,"two",2.5,"three")

mytuple2 = 1,5,7

print(mytuple1)
print(mytuple2)
```

As you can see from the code above, a Python tuple can contain values of different data types. The above code creates a tuple `mytuple1` that has values of type Integer, Decimal and String. It also creates `mytuple2` using simple comma separated values. So this code prints the following output:

```
(1, 'two', 2.5, 'three')
(1, 5, 7)
```

## Accessing values in a Tuple

You can access the values in a tuple via the slice operator. It consists of **\[\]**or **\[:\]**. You can access Python tuples both in the **forward** as well as **backward** direction. In the forward direction,tuples start from position **0** for the first element in the tuple. In the backward direction, tuples start at position **\-1** for the last value in the list.

The following code demonstrates this:

```python
mytuple = (2,4,'Hello',10.5,"World")
print (mytuple) 
print(mytuple[2]) 
print(mytuple[0:2]) 
print(mytuple[2:]) 
print(mytuple[:3])
print(mytuple[-1])
```

This code prints the following output:

```
(2, 4, 'Hello', 10.5, 'World')
Hello
(2, 4)
('Hello', 10.5, 'World')
(2, 4, 'Hello')
World
```

## Updating a Tuple

As mentioned earlier, a tuple is **immutable**. So you cannot update a value from a tuple. If you try to update a value in a tuple, an error occurs. The following code demonstrates this:

```python
mytuple = ("cat","dog","cow","monkey")
mytuple[2] = "horse"
print(mytuple)
```

This code tries to update the value at position 2. So an error occurs as follows:

```
Traceback (most recent call last):
File "tupledemo.py", line 20, in <module>
mytuple[2] = "horse"
TypeError: 'tuple' object does not support item assignment
```

## Removing a value from a Tuple

You cannot delete an individual value from a tuple. However, you can delete the entire tuple. The following code demonstrates this:

```python
mytuple = ("cat","dog","cow","monkey")
del mytuple
print(mytuple)
```

The above code deletes `mytuple` and then tries to print it. So it causes an exception as follows:

```
Traceback (most recent call last):
File "tupledemo.py", line 21, in <module>
print(mytuple)
NameError: name 'mytuple' is not defined
```

## Concatenating Tuples

You can concatenate tuples using the **concatenation operator(+ operator)**. The following code demonstrates this:

```python
mytuple1 = ('apple','orange')
mytuple2 = ('banana','mango','cherry')

mytuple3 = mytuple1+mytuple2
print(mytuple3)
```

This code concatenates `mytuple1` and `mytuple2` and creates `mytuple3`. So it prints the following output:

```
('apple', 'orange', 'banana', 'mango', 'cherry')
```

## Using Repetition Operator

You can use the **repetition operator(\*)** with tuples. The following code demonstrates this:

```python
mytuple1 = ('apple','orange')
mytuple3 = mytuple1*3;
print(mytuple3)
```

This code creates a new tuple `mytuple3` which repeats the contents of `mytuple1` 3 times. So it prints the following output:

```
('apple', 'orange', 'apple', 'orange', 'apple', 'orange')
```

## Obtaining length of a tuple

Python has a built-in function **len**. This returns the length of the object passed in. You can use this function to obtain the length of a tuple. The following code demonstrates this:

```python
mytuple1 = ('apple','orange')
print(len(mytuple1))
```

So this code prints the following output:

```
2


```

## Further Learning

- [The Python Masterclass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-the-complete-python-developer-course%2F) 
- [Everything you need to know about Python](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fthe-python-bible%2F) 
- [Python for beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-programming-projects%2F) 
- [Python for finance](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-for-finance-investment-fundamentals-data-analytics%2F)

## Conclusion

So in this article, we understood what Python tuples are. We also understood how you can create a tuple, access an element from a tuple, concatenate tuples, use the repetition operator with tuples and obtain the length of a tuple. We also saw that tuples cannot be modified once they are created.

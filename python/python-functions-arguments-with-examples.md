---
title: "Python functions arguments with examples"
date: "2021-03-25"
categories: 
  - "python"
coverImage: "Python-functions.jpg"
---

In [Part 1](python-functions-part-1-2.md) of the Python functions article, I gave you an introduction to Python functions. In this article, we will take a look at Python functions with arguments. Arguments allow passing some data to a function so that the function then operates on the data.

Python functions arguments are mainly of 4 types: positional, default, keyword, and arbitrary. Let us now take a look at each type of argument

## Positional Arguments

Positional arguments are arguments whose values are passed in the same order in which they are specified in the function definition.

Consider the following code:

```python
def showMarks(name,marks):
    print("Hello", name,"you have scored",marks,"marks!")
```

This code specifies a **showMarks** function. It accepts arguments **name** and **marks** and simply prints a message with these values.

You can now invoke this function as follows:

```python
showMarks("Jane",97)
```

This assigns the value **"Jane"** to the first argument that is **name** and the value **97** to the second argument that is **marks**. So, this code produces the following output:

```
Hello Jane you have scored 97 marks!
```

## Keyword Arguments

Keyword arguments are those in which a keyword corresponding to the parameter name is specified in the method call. So, in the example above, you can invoke the **showMarks** function as follows:

```python
showMarks(marks=97,name="Jane")
```

This code specifies the name of the method parameter (**marks**) along with the value **97** to assign to **marks**. Similarly, it also specifies the **name** keyword with the value **"Jane"**. As is obvious, when you use keyword parameters, the order does not matter, so you can specify the parameters in any order.

## Default

Default arguments refer to default values given to an argument. When a default value is given to an argument, you need not specify an explicit value in the method call.

We can re-write the **showMarks** function as follows:

```python
def showMarks(name,marks=100):
    print("Hello", name,"you have scored",marks,"marks!")
```

In this case, the **marks** argument is given a default value of 100. So, when you invoke **showMarks**, there is no need to specify a value for **marks**. So, you can invoke it as follows:

```python
showMarks(name="Jane")
```

Since this code does not pass any value for **marks**, the default value is used. so, this code produces the following output:

```
Hello Jane you have scored 100 marks!
```

You can also specify an explicit value for a default argument as follows:

```python
showMarks(name="Jane", marks=97)
```

This code specifies the value **97** corresponding to the **marks** parameter. So, this code produces the following output:

```
Hello Jane you have scored 97 marks!
```

In addition, even when you use default arguments, you need not specify argument keywords in the method call, you can still pass in arguments by position as follows:

```python
showMarks("Jane")
```

This assigns the value **"Jane"** to the first argument that is **name**. Since only one argument is specified, the default value for **marks** is used.So, this code produces the following output:

```
Hello Jane you have scored 100 marks!
```

Finally, you can also use a positional argument to override a default argument value as follows:

```python
showMarks("Jane",97)
```

This assigns the value **"Jane"** to the first argument that is **name** and the value **97** to the second argument that is **marks**. So, this code produces the following output:

```
Hello Jane you have scored 97 marks!
```

## Arbitrary

Python allows specifying a variable number of arguments to a method. These are known as **arbitrary arguments**. Arbitrary argument can be positional or keyword based.

### Arbitrary Positional Arguments

Arbitrary positional arguments are specified with an asterisk symbol (*) in the method definition. In the method call, values are specified based on position.

We can re-write the **showMarks** function as follows:

```python
def showMarks(name,*marks):
    print("Hello", name,"you have scored",marks,"marks!")
```

This code designates **marks** as an arbitrary positional argument. Thus, you can now invoke **showMarks** with any number of values corresponding to **marks** as follows:

```python
showMarks("Jane",97,78)
```

This code produces the following output:

```
Hello Jane you have scored (97, 78) marks!
```

You can also invoke **showMarks** as follows:

```python
showMarks("Jane",97,78,89,90)
```

This code produces the following output:

```
Hello Jane you have scored (97, 78, 89, 90) marks!
```

### Arbitrary Keyword Arguments

Arbitrary keyword arguments are specified with a double asterisk symbol (**) in the method definition. In the method call, you need to specify a keyword corresponding to each arbitrary parameter value.

We can re-write the **showMarks** function as follows:

```python
def showMarks(name,**marks):
    print("Hello", name,"you have scored",marks,"marks!")
```

This code designates **marks** as an arbitrary keyword argument. Thus, you can now invoke **showMarks** with any number of key-values corresponding to **marks** as follows:

```python
showMarks(name="Jane",English=97,Maths=89)
```

This code specifies a different keyword ( the name of the subject) corresponding to each **marks** value. So, it specifies **English** with the value **97** and **Maths** with the value **89**. Similarly, it also specifies the **name** keyword with the value **"Jane"**. Like ordinary keyword parameters, the order does not matter, so you can specify the parameters in any order.

This code produces the following output:

```
Hello Jane you have scored {'english': 97, 'maths': 89} marks!


```

## Further Learning

- [The Python Masterclass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-the-complete-python-developer-course%2F) 
- [Everything you need to know about Python](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fthe-python-bible%2F) 
- [Python for beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-programming-projects%2F) 
- [Python for finance](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-for-finance-investment-fundamentals-data-analytics%2F)

## Conclusion

So just to summarize, Python supports 4 different type of arguments. These are positional (values are passed by position), keyword-based (keyword corresponding to each parameter name is specified), default (in which a default value is given to each argument) and arbitrary (in which a variable number of values can be passed to an argument).

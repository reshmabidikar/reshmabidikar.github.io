---
title: "Python Lists With Code Samples and List operations"
date: "2020-05-12"
categories: 
  - "python"
---

In my [earlier](https://learnjava.co.in/python-numeric-and-string-variables/) article, I had covered Python numeric and String data types. In this article, I will be covering Python Lists. As the name indicates, you can use a Python list to store a set of values.

## Creating a Python List

You can create a list by specifying comma separated values within square brackets. The following code demonstrates this:

```
mylist = [2,4,'Hello',10.5,"World"]
print (mylist)
```

As you can see from the code above, a Python list can contain values of different data types. The above code creates a list mylist that has values of type Integer, decimal and String.

## Accessing Values in Python Lists

You can access the values in a List via the slice operator. It consists of **\[\]** or **\[:\]**. You can access Python lists both in the **forward** as well as **backward** direction. In the forward direction,lists start from position **0** for the first element in the list. In the backward direction, lists start at position **\-1** for the last value in the list.

The following code demonstrates this:

```
mylist = [2,4,'Hello',10.5,"World"] 
print (mylist) 
print(mylist[2]) 
print(mylist[0:2]) 
print(mylist[2:]) 
print(mylist[:3])
print(mylist[-1])
print(mylist[-3:-1])
```

This code prints the following output:

```
[2, 4, 'Hello', 10.5, 'World']
Hello
[2, 4]
['Hello', 10.5, 'World']
[2, 4, 'Hello']
World
['Hello', 10.5]
```

## Updating Python Lists

You can update a value in a List. You just need to specify the list name, followed by its position in square brackets and assign it a new value. The following code demonstrates this:

```
mylist = ["cat","dog","cow","monkey"]
mylist[2] = "horse"
print(mylist)
```

So this code updates the value at position _2_ to "_horse_". So this code prints the following output:

```
['cat', 'dog', 'horse', 'monkey']
```

## Adding to a Python List

There are several ways in which you can add a value to a List.

### append

The `append`method adds a value at the end of the list. The following code demonstrates this:

```
mylist = ["cat","dog","cow","monkey"]
mylist.append("horse")
print(mylist)
```

This code adds the value "_horse_" to the end of the list. So it prints the following output:

```
['cat', 'dog', 'horse', 'monkey']
```

### insert

The `insert`method adds a value at the specified position. The following code demonstrates this:

```
mylist= ["cat","dog","cow","monkey"]
mylist.insert(2, "horse")
print(mylist)
```

This code inserts the value "_horse_" at position _2_. So it prints the following output:

```
['cat', 'dog', 'horse', 'cow', 'monkey']
```

## Removing from a Python List

There are several ways in which you can remove a value from a List.

### remove

The `remove`method removes the specified element from the List. The following code demonstrates this:

```
mylist = ["cat","dog","cow","monkey"]
mylist.remove("dog")
print(mylist)
```

This code removes the value "_dog_" from the list. So it prints the following output:

```
['cat', 'cow', 'monkey']
```

### pop

The `pop`method removes the element at the specified index or the last element if no index is specified. The following code demonstrates this:

```
mylist = ["cat","dog","cow","monkey"]
mylist.pop(1)
print(mylist)

mylist = ["cat","dog","cow","monkey"]
mylist.pop()
print(mylist)
```

The first code snippet removes the value at position _1_ which is _dog_. In the second code snippet, the index is not specified, so the last value is removed. So this code prints the following output:

```
['cat', 'cow', 'monkey']
['cat', 'dog', 'cow']
```

### clear

The `clear`method empties a list. The following code demonstrates this:

```
mylist = ["cat","dog","cow","monkey"]
mylist.clear();
print(mylist)
```

So this code empties the list. So it prints the following output:

```
[]
```

## Sorting Python Lists

The `sort`method sorts a list. The following code demonstrates this:

```
mylist = [5,1,8,12,9];
mylist.sort()
print(mylist)
```

This code sorts the list in ascending order. So it prints the following output:

```
[1, 5, 8, 9, 12]
```

## Obtaining Length of a Python List

Python has a built-in function `len`. This returns the length of the object passed in. You can use this function to obtain the length of a list. The following code demonstrates this:

```
mylist = ["cat","dog","cow","monkey"]
print(len(mylist))
```

So this code prints the following output:

```
4
```

## Concatenating two Python lists

The ‘**+**‘ operator acts as the **concatenation operator**. It helps in concatenating Lists. The following code demonstrates this:

```
mylist1 = ["cat","dog","cow","monkey"]
mylist2 = ["lion","tiger"]
mylist3 = mylist1+mylist2
print(mylist3)
```

So this code appends the values in `myList1`and `myList2`and assigns the resultant list to `myList3`. So it prints the following output:

```
['cat', 'dog', 'cow', 'monkey', 'lion', 'tiger']


```

## Further Learning

[The Python Masterclass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-the-complete-python-developer-course%2F) [Everything you need to know about Python](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fthe-python-bible%2F) [Python for beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-programming-projects%2F) [Python for finance](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-for-finance-investment-fundamentals-data-analytics%2F)

## Conclusion

So in this article, we understood what Python Lists are. We also understood some of the methods that you can use on lists for adding/removing elements from a list, sorting lists, etc.

---
title: "Python Dictionary"
date: "2020-07-10"
categories: 
  - "python"
---

In my[earlier](https://learnjava.co.in/python-tuples/) article, I had covered Python Tuples. In this article, I will be covering Python dictionary.

## What is a Python dictionary?

A Python dictionary stores a List of key-value pairs.

## Creating a Python dictionary

You can create a dictionary by specifying key-value pairs in curly brackets separated by commas. The following code demonstrates this:

```
employeeDict = {'name':'John Doe','salary':5000.00,'department':'HR'}
```

This code creates a dictionary `employeeDict` with some key value pairs. The key and value need to be separated by a colon symbol(:)

## Accessing values in a Python dictionary

You can access a value from a dictionary by specifying the key in square brackets. The following code demonstrates this:

```
employeeDict = {'name':'John Doe','salary':5000.00,'department':'HR'}

print(employeeDict['name'])
```

## Updating a Python dictionary

You can update the value for an existing key, add a new key-value pair or delete a key value pair.

```
employeeDict = {'name':'John Doe','salary':5000.00,'department':'HR'}
employeeDict['department'] = 'Admin'
print(employeeDict['department'])
```

### Updating value of an existing key

You can update the value of a key by specifying the key in square brackets and the value as shown below:

```
employeeDict = {'name':'John Doe','salary':5000.00,'department':'HR'}
employeeDict['department'] = 'Admin'

```

This code updates the **department** key to the value **Admin**

### Adding a new key-value pair

You can also add a new key-value pair to the dictionary as shown below:

```
employeeDict = {'name':'John Doe','salary':5000.00,'department':'HR'}
employeeDict['manager'] = 'Sam Rocket'

```

This adds the key-value Manager:Sam Rocket to the dictionary.

### Deleting a key-value pair

You can delete a key-value pair by using the **del** statement with the key name as shown below:

```
employeeDict = {'name':'John Doe','salary':5000.00,'department':'HR'}
del employeeDict['department']
```

This deletes the key-value corresponding to **department**

### Deleting the entire dictionary

You can also delete the entire dictionary as shown below:

```
employeeDict = {'name':'John Doe','salary':5000.00,'department':'HR'}
del employeeDict
```

This deletes the entire `employeeDict` .So any attempt to access `employeeDict` after this would result in an error

### Emptying a dictionary

You can clear a dictionary without deleting it by invoking the `clear`method as shown below:

```
employeeDict = {'name':'John Doe','salary':5000.00,'department':'HR'}
employeeDict.clear()
```

So, this empties the `employeeDict` dictionary but does not delete it. You can still add more values to the dictionary

## Obtaining the length of a Python dictionary

Python has a built-in function **len**. This returns the length of the object passed in. You can use this function to obtain the length of a dictionary. The following code demonstrates this:

```
employeeDict1 = {'name':'John Doe','salary':5000.00,'department':'HR'}
print(len(employeeDict1))
```

## Dictionary Methods

There are several dictionary methods that are useful. The following code demonstrates some of these methods:

```
employeeDict = {'name':'John Doe','salary':5000.00,'department':'HR'}
print('Keys:')
print(employeeDict.keys()); 

print('values:')
print(employeeDict.values());

print('Value for Salary:')
print(employeeDict.get('salary', 0))

print('Value for Manager:')
print(employeeDict.get('manager', 'Sam Rocket'))
```

- The `keys()`method returns the keys in the dictionary
- The `values()`method returns the values in the dictionary
- The `get()`method returns the value corresponding to the specified key if present, otherwise it returns a default value.

So, this code prints the following output:

```
Keys:
dict_keys(['name', 'salary', 'department'])
values:
dict_values(['John Doe', 5000.0, 'HR'])
Value for Salary:
5000.0
Value for Manager:
Sam Rocket
```

## Further Learning

[The Python Masterclass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-the-complete-python-developer-course%2F) [Everything you need to know about Python](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fthe-python-bible%2F) [Python for beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-programming-projects%2F) [Python for finance](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fpython-for-finance-investment-fundamentals-data-analytics%2F)

## Conclusion

So in this article, we understood what a Python dictionary is and how you can store key-value pairs in a dictionary. We also saw some of the common operations that you can perform on a dictionary. Finally, we saw some of the in-built dictionary methods.

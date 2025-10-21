---
title: "Java TreeSet and HashSet similarities and differences"
date: "2019-07-04"
categories: 
  - "java-interview-questions"
  - "java-collection-examples"
tags: 
  - "collectionapi"
  - "hashset"
  - "javainterviewquestions"
  - "treeset"
---

Java TreeSet and HashSet are implementations of the Set interface. Often you may have wondered whether to choose HashSet or TreeSet and which is faster. In this article, I will be comparing the HashSet and TreeSet classes in Java.

## HashSet and TreeSet Similarities

### Duplicates not allowed

Since both HashSet and TreeSet implement the Set interface, they do not allow duplicates. So consider the following code:

```java
Set<String> hashSet = new HashSet<String>();
    hashSet.add("Mango");
    hashSet.add("Mango");

    
    Set<String> treeSet = new TreeSet<String>();
    treeSet.add("Mango");
    treeSet.add("Mango");

    
    System.out.println("Number of elements in Hashset:"+hashSet.size());
    System.out.println("Number of elements in Treeset:"+treeSet.size());
```

When you execute this code, it will print the following output:

```
Number of elements in Hashset:1
Number of elements in Treeset:1
```

### Not Thread-Safe

Both HashSet and TreeSet are not synchronized and are not thread-safe. So you need to write code to explicitly synchronize them.

So you will need to write code similar to the following:

```java
Set<String> synHashSet = Collections.synchronizedSet(hashSet);

Set<String> synTreeSet = Collections.synchronizedSet(treeSet);
```

## HashSet and TreeSet Differences

### Ordering

A TreeSet is sorted, whereas a HashSet is not sorted. When you insert elements into a HashSet, no order will be maintained. On the other hand, when you insert elements into a TreeSet, they will be ordered according to their natural order. The following code demonstrates this:

**HashSet example**

```java
Set<String> hashSet = new HashSet<String>();
hashSet.add("Mango");
hashSet.add("Banana");
hashSet.add("Apple");
hashSet.add("Pear");

hashSet.forEach(str -> System.out.println(str));
```

The code above creates a HashSet of String values, inserts some data and then prints it. When you execute this code, it will print the following output:

```
Apple
Pear
Mango
Banana


```

So you can see that the Strings in the HashSet are not sorted.

**TreeSet example**

```java
Set<String> treeSet = new TreeSet<String>();
treeSet.add("Mango");
treeSet.add("Banana");
treeSet.add("Apple");
treeSet.add("Pear");


treeSet.forEach(str -> System.out.println(str));
```
When you execute this code, it will print the following output:

```
Apple
Banana
Mango
Pear
```

So you can see that the Strings in the TreeSet are sorted alphabetically.

### Allowing Null Objects

A HashSet allows null objects, a TreeSet does not allow null objects. So you can insert a null value in a HashSet, but you cannot do this in a TreeSet. The following code demonstrates this:

```java
hashSet.add("Mango"); 
hashSet.add("Banana"); 
hashSet.add(null); 
hashSet.forEach(str -> System.out.println(str));
```

The above code will not cause any issues. So when you execute this code, the following will be printed to the console:

```
null
Mango
Banana
```

However, consider the following code:

```java
treeSet.add("Mango"); 
treeSet.add("Banana"); 
treeSet.add(null);
 treeSet.forEach(str -> System.out.println(str));
```

When you run this code, a NullPointerException will occur as follows:

```java
Exception in thread "main" java.lang.NullPointerException
at java.util.TreeMap.put(Unknown Source)
at java.util.TreeSet.add(Unknown Source)
at learnjava.collections.HashSetTreeSetDemo.main(HashSetTreeSetDemo.java:15)
```

### Internal Data Structure

HashSet internally uses a HashTable. TreeSet on the other hand internally uses a Red-Black Tree.

### Performance

Since HashSet internally uses a HashTable, it is faster as compared to a TreeSet. So most operations like add, remove, etc are faster in a HashSet.

## When to use which?

If you want to store the data in sorted order and don't care about the performance then you should use a TreeSet. If performance is critical for your application, you should use a HashSet.

## Conclusion

So, in this article, we learned about the similarities and differences between Java TreeSet and HashSet.

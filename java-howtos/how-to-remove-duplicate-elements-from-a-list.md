---
title: "How to remove duplicate elements from a List"
date: "2018-09-02"
categories: 
  - "collections-framework"
  - "java-collection-examples"
tags: 
  - "core-java"
  - "java-collections-framework-en"
---

In this blog post, I will demonstrate how to remove the duplicates from a List.

There are several ways to do this.


#### Looping throw the List and creating new List

The following code snippet demonstrates this approach:

```java
public static List<String> removeDuplicates1(List<String> list){ 
    List<String> newList = new ArrayList<String>(); 
    for(String s:list){ 
        if(!newList.contains(s)) newList.add(s); 
    } 
    return newList; 
}
````

A new List is created. A for loop is used to iterate throw the input List. An if condition is used to check if the new List has each element in the input List and if not, it is added to the new List.

#### Using a Set

The following code snippet demonstrates this approach:

```java

public static List<String> removeDuplicates2(List<String> list){ 
    Set<String> set = new HashSet<String>(); 
    set.addAll(list); 
    List<String> newList = new ArrayList<String>(); 
    newList.addAll(set); 
    return newList; 
}
```

Here, a Set is created. This is added all the elements in the List. Since a Set does not allow duplicates, only the unique elements are added to the Set. A new list is then created using the Set and that is returned.

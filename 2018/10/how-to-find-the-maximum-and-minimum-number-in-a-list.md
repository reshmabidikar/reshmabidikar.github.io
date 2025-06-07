---
title: "How to find the maximum and minimum number in a List"
date: "2018-10-15"
categories: 
  - "collections-framework"
  - "java-collection-examples"
tags: 
  - "java-collections-framework-en"
---

In this blog post, I will be demonstrating how you can find the largest and smallest number in an array. Consider the following code snippet:

```java

package learnjava.collections;

import java.util.ArrayList; 
import java.util.Collections; 
import java.util.List;

public class MaxMinDemo {

public static void main(String[] args) { List<Integer> input = new ArrayList<Integer>(); 
    input.add(3); 
    input.add(9); 
    input.add(5); 
    input.add(15); 
    input.add(11);

System.out.println("Biggest element in the list is:"+Collections.max(input)); 
System.out.println("Smallest element in the list is:"+Collections.min(input));

} 
}

```

This code uses the [Collections.max](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#max-java.util.Collection-) and [Collections.min](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#min-java.util.Collection-) methods. The [Collections](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html) class contains static utility methods that operate on collections like List, Set etc. The [Collections.max](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#max-java.util.Collection-) method returns the greatest element in the list according to the natural order or sorting. Similarly, the [Collections.min](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#min-java.util.Collection-) returns the smallest element in the list according to the natural order of sorting. When this code is executed, it will print the following output:

```
Biggest element in the list is:15
Smallest element in the list is:3
```

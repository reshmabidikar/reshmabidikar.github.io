---
title: "How to sort a List via Java"
date: "2019-02-08"
categories: 
  - "collections-framework"
  - "java-collection-examples"
tags: 
  - "java-collections-framework-en"
---

In this blog post, I will be explaining how you can sort a list via Java.  Consider the following code snippet:

\[java\]

package learnjava.collections;

import java.util.ArrayList; import java.util.Collections; import java.util.List;

public class SortDemo {

public static void main(String\[\] args) { List<Integer> input = new ArrayList<Integer>(); input.add(3); input.add(9); input.add(5); input.add(15); input.add(11);

System.out.println("Before sorting:"+input); Collections.sort(input); System.out.println("Before sorting:"+input);

}

}

\[/java\]

 

This code uses the [Collections.sort](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#sort-java.util.List-) method. The [Collections](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html) class contains static utility methods that operate on collections like List, Set etc.  When the [Collections.sort method](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#sort-java.util.List-) is invoked, it sorts the input list in ascending order. The return type of this method is void, so the input list is modified for sort. This code will print the following output:

```
Before sorting:[3, 9, 5, 15, 11]
Before sorting:[3, 5, 9, 11, 15]
```

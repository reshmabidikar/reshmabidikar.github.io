---
title: "How to shuffle the elements in a List via Java"
date: "2018-11-25"
categories: 
  - "collections-framework"
  - "java-collection-examples"
tags: 
  - "java-collections-framework-en"
---

In this blog post, I will be explaining how you can shuffle list via Java. Consider the following code snippet:

````

package learnjava.collections;

import java.util.ArrayList; 
import java.util.Collections; 
import java.util.List;

public class ShuffleDemo {

    public static void main(String[] args) { 
        List<Integer> input = new ArrayList<Integer>(); 
        input.add(3); 
        input.add(9); 
        input.add(5); 
        input.add(15); 
        input.add(11);
        System.out.println("Before shuffling:"+input); 
        Collections.shuffle(input); 
        System.out.println("After shuffling:"+input);
    }
} 
````
This code uses the [Collections.shuffle](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#shuffle-java.util.List-) method. The [Collections](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html) class contains static utility methods that operate on collections like List, Set etc. When the [Collections.shuffle](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#shuffle-java.util.List-) is invoked, it shuffles the input list randomly. The return type of this method is void, so the input list is modified. When you run this code, it will print output similar to the following:

```
Before shuffling:[3, 9, 5, 15, 11]
After shuffling:[15, 11, 3, 9, 5]
```

Note that since the shuffling is random, each time you run the code a different output will be printed.

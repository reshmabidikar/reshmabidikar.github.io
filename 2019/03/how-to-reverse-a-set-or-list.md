---
title: "How to reverse a List in Java"
date: "2019-03-31"
categories: 
  - "collections-framework"
  - "java-collection-examples"
tags: 
  - "java-collections-framework-en"
---

In this blog post, I will be explaining how you can reverse a Set or List via Java. Consider the following code snippet:


````

package learnjava.collections;

import java.util.ArrayList; 
import java.util.Collections; 
import java.util.List;

public class ReverseDemo {

public static void main(String[] args) { 
List<Integer>inputList = new ArrayList<Integer>(); 
inputList.add(5); 
inputList.add(15); 
inputList.add(20); 
inputList.add(25);

List<Integer>reverserdList1 = reverseList1(inputList); 
List<Integer>reverserdList2 = reverseList2(inputList);

System.out.println("Input List is "+inputList); 
System.out.println("reverserdList using method1 "+reverserdList1); 
System.out.println("reverserdList using method2 "+reverserdList2); }

private static List<Integer> reverseList2(List<Integer>inputList ){ 
List<Integer> reverserdList = new ArrayList<Integer>();

for(int i =inputList.size()-1;i >=0;i--){ 
reverserdList.add(inputList.get(i)); 
} 
return reverserdList; 
}

private static List<Integer> reverseList1(List<Integer>inputList ){ 
Collections.reverse(inputList); 
return inputList; 
}

} 

````

This code snippet demonstrates two ways to reverse a List.


#### Method 1 - Using Collections.reverse

The [Collections](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html) class has a number of useful utility methods for collections. One such method provided by this class is the [Collections.reverse](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#reverse-java.util.List-) method. This method accepts a Collection and reverses its contents. So any Collection like Set, List, etc can be passed to this method. It has no return value, it returns a void. So the Collection that is passed in is modified by this method.

#### Method 2 - Using Manual method

In the manual method, the code iterates through the input List in the reverse order. It then adds each element in the List to a new List and returns the new List object.

So when you run this code, it will produce the following output:

```
Input List is [25, 20, 15, 5]
reverserdList using method1 [25, 20, 15, 5]
reverserdList using method2 [5, 15, 20, 25]
```

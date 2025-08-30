---
title: "How to find if two lists are exactly the same"
date: "2019-02-27"
categories: 
  - "collections-framework"
  - "java-collection-examples"
---

In this blog post, I will be explaining how you can check if 2 lists are exactly the same. Consider the following code snippet:

````java
public class CompareLists {

    public static void main(String[] args) { 
        List<Integer> list1 = Arrays.asList(3,9,5,15,11); 
        List<Integer> list2 = Arrays.asList(3,9,5,15,11);

        boolean matches = false; 
        if(list1.size() == list2.size()) { 
            matches = list1.containsAll(list2); 
        }

        if(matches) 
            System.out.println("List1 and List2 are the same"); 
        else 
        System.out.println("List1 and List2 are different"); 
    } 
}
````


Here, we have 2 lists, **list1** and **list2**. First, we are comparing the size of the lists. If they are different, then it means that the two lists are different. However, if the sizes are the same, then the code invokes the [list.containsAll](https://docs.oracle.com/javase/8/docs/api/java/util/List.html#containsAll-java.util.Collection-) method. This method returns true if the list on which it is invoked contains all the elements in the list passed in.

So when you run this code, it will print the following output:

```
List1 and List2 are the same
```

Now lets try modifying the input lists as follows:

````
List<Integer> list1 = Arrays.asList(3,9,5,15,11); 
List<Integer> list2 = Arrays.asList(5,3,11);
````

The code now prints the following output:

```
List1 and List2 are different
```

Now, let's try modifying the input lists as follows:

````
List<Integer> list1 = Arrays.asList(3,9,5,15,11); 
List<Integer> list2 = Arrays.asList(5,3,11,12,15,1);
````

The code now prints the following output:

```
List1 and List2 are different
```

Note that this code does not check for order. So even if the 2 lists contain exactly the same elements but in a different order, it will consider the lists to be the same.

So if you modify the code as follows:

````
List<Integer> list1 = Arrays.asList(3,9,5,15,11); 
List<Integer> list2 = Arrays.asList(5,3,11,15,9);
````

It will print the following output:

```
List1 and List2 are the same
```

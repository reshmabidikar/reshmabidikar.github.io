---
title: "How to sort a List in Descending order"
date: "2020-02-07"
categories: 
  - "collections-framework"
  - "java-collection-examples"
tags: 
  - "javacollections"
  - "javasortlist"
---

In this article, I will be demonstrating how you can sort a List in descending order. In order to see how to sort a List, you can refer to [this](https://learnjava.co.in/how-to-sort-a-list-via-java/) blog post.

# Approach 1 - Using Collections.reverse

The Collections class has a utility method called reverse. You can use this to sort a List in descending order. The following code demonstrates this:

```
private static void usingCollectionsReverse() {
  List<Integer> input = Arrays.asList(15,12,34,11,93,21,64);
  System.out.println("Before sorting:"+input);
  Collections.sort(input);
  Collections.reverse(input);
  System.out.println("After sorting:"+input);
}
```

Here, the code first invokes the `Collection.sort`. This sorts the List in ascending order. Then the code invokes the `Collections.reverse`

method to reverse the List. So this code prints the following output:

```
Before sorting:[15, 12, 34, 11, 93, 21, 64]
After sorting:[93, 64, 34, 21, 15, 12, 11]
```

# Approach 2 - Using Collections.reverseOrder

There is an overloaded version of the `Collections.sort`method. This accepts a Comparator instance in addition to the Collection that needs to be sort. Also, the Collections class has a static method called `Collections.reverseOrder()`. This returns a Comparator that imposes the reverse of the natural ordering. So you can use both these methods to sort a List in descending order. The following code demonstrates this:

```
private static void usingCollectionsReverseOrder() {
  List<Integer> input = Arrays.asList(15,12,34,11,93,21,64);
  System.out.println("Before sorting:"+input);
  Collections.sort(input,Collections.reverseOrder());
  System.out.println("After sorting:"+input);
}
```

Here, the code invokes the Collections.sort method with the input List and a Comparator that imposes the reverse of the natural ordering. So this code prints the same output as before:

```
Before sorting:[15, 12, 34, 11, 93, 21, 64]
After sorting:[93, 64, 34, 21, 15, 12, 11]
```

# Approach 3 - Using List.sort

Java 8 has added a sort method to the List interface. You can use this to sort a List. The `List.sort` method accepts as parameter a Comparator instance. You can use the `Collections.reverseOrder()` seen earlier to obtain a Comparator that imposes the reverse of the natural ordering and pass this Comparator to the List.sort method. The following code demonstrates this:

```
private static void usingListSortComparatorReverseOrder() {
  List<Integer> input = Arrays.asList(15,12,34,11,93,21,64);
  System.out.println("Before sorting:"+input);
  input.sort(Comparator.reverseOrder());
  System.out.println("After sorting:"+input);
}
```

Here, the code invokes the List.sort method. It uses the `Comparator.reverseOrder` to obtain a Comparator that imposes the reverse of the natural ordering. So this code prints the same output as before:

```
Before sorting:[15, 12, 34, 11, 93, 21, 64]
After sorting:[93, 64, 34, 21, 15, 12, 11]
```

In the above examples, you can also implement the Comparator interface using a lambda expression as follows:

```
input.sort((num1,num2) -> num2-num1);
```

This will also produce the same output as before.

# Conclusion

So in this article, we saw three different ways in which you can sort a List in descending order. We saw how you can use the Collections.sort method to sort the List. We also saw how the Collections.reversed and Collections.reverseOrder methods work. Finally, we took a look at how you can also use the Java 8 List.sort method.

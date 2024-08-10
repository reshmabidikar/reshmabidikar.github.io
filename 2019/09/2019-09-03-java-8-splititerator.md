---
title: "Java 8 SplitIterator Explained with code samples"
date: "2019-09-03"
categories: 
  - "java-8-features"
  - "java8"
---

Another new feature in Java 8 is the SplitIterator interface. This article will explain what a SplitIterator is and how you can use it.

\[table id=24 /\]

## What is a SplitIterator?

Just like a normal Iterator, you can use a SplitIterator to iterate over the elements in a Collection. A new method called `splitIterator`has been added to all the Collection interfaces. This returns a SplitIterator instance. The following code demonstrates this:

```
public class SplitIteratorDemo {

  public static void main(String[] args) {
    List<Integer> input = Arrays.asList(5, 3, 21, 15, 9, 2, 12, 11);
    
    Spliterator<Integer> sitr1 = input.spliterator();
    sitr1.forEachRemaining(num -> System.out.println(num));
  }

}
```

The above code obtains a SplitIterator over the input list. Just like the Iterator interface, the forEachRemaning method is also available on the SplitIterator interface. This can be used to iterate through the elements in the input collection. So when you execute the above code, it prints the following output to the console:

```
5
3
21
15
9
2
12
11
```

## Why is the use of SplitIterator?

The additional benefit that SplitIterator provides over Iterator is that it can be used for parallel iteration. It does this by splitting the iteration into two parts. The following code demonstrates this:

```
public class SplitIteratorDemo {

  public static void main(String[] args) {
    List<Integer> input = Arrays.asList(5, 3, 21, 15, 9, 2, 12, 11);
    
    Spliterator<Integer> sitr1 = input.spliterator();
    Spliterator<Integer> sitr2 = sitr1.trySplit();
    
    System.out.println("SplitIterator 1:");
    sitr1.forEachRemaining(num -> System.out.println(num));
    
    System.out.println("SplitIterator 2:");
    sitr2.forEachRemaining(num -> System.out.println(num));

  }

}
```

 

There is a method called trySplit available on the SplitIterator. This returns a SplitIterator with some of the elements in the original SplitIterator.  So when you execute the above code, it will print the following output:

```
SplitIterator 1:
9
2
12
11
SplitIterator 2:
5
3
21
15
```

Although SplitIterator supports parallel execution, you can also use it for sequential execution

## Other SplitIterator methods

In addition, SplitIterator has several other methods. The following code demonstrates these methods:

```
List<Integer> input = Arrays.asList(5, 3, 21, 15, 9, 2, 12, 11);

Spliterator<Integer> sitr1 = input.spliterator();
long estimatedSize = sitr1.estimateSize();
System.out.println("EstimatedSize:"+estimatedSize);
long exactSize = sitr1.getExactSizeIfKnown();
System.out.println("exactSize:"+exactSize);
```

- The estimateSize method returns an estimate of the number of elements remaining.
- The getExactSizeIfKnown method returns the estimateSize if the SplitIterator represents a finite collection, otherwise, it returns -1.

## Conclusion

In this article, we saw what is a SplitIterator in Java 8. We saw some of the important methods in the SplitIterator and how to iterate using a SplitIterator.

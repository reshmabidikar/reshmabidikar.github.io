---
title: "Iterator and Enumeration - Differences Explained"
date: "2020-03-31"
categories: 
  - "collections-framework"
  - "java-interview-questions"
---

In this article, I will be comparing the Iterator and Enumeration interfaces. I will be explaining the similarities and differences between Iterator and Enumeration.

## Definitions

Both Iterator and Enumeration are interfaces defined in the Java Collection framework. You can use both to loop through the elements of a Collection. Let us first understand how they work

### Iterator

Iterator is an interface defined in the Java Collection framework. You can use it to loop through the elements of a collection. The following code demonstrates this:

```
List<Integer> numbers = Arrays.asList(2,4,6,8,10);
  Iterator<Integer> itr = numbers.iterator();
  while (itr.hasNext()) {
    System.out.print(itr.next()+" ");
  }
```

This code uses an Iterator to loop through the elements in a List and print them. `Iterator.hasNext()`method returns true if there are more elements in the collection. The `iterator.next()`method returns the next element in the collection. So this code prints the following output:

```
2 4 6 8 10
```

### Enumeration

Enumeration is also an interface in the java.util.package. Just like Iterator, you can use it to loop through values. However, Enumeration is a legacy interface you can only use it for legacy classes like Vector and HashTable, The following code demonstrates this:

```
Vector vector = new Vector();
vector.add(2);
vector.add(4);

Enumeration e = vector.elements();
while (e.hasMoreElements()) {
  System.out.println(e.nextElement());
}
```

This code uses an Enumeration to loop through the elements in a Vector and print them.`Enumeration.hasMoreElements()`method returns true if there are more elements in the collection. The `enumeration.nextElement`method returns the next element in the collection. So this code prints the following output:

```
2 4
```

## Differences

### Type of Collection

As seen earlier, you can use Iterator to loop through any Collection. However you can use an Enumeration only for legacy collections like Vector and HashTable.

### Methods

The methods in the Iterator and Enumeration interfaces differ slightly. While Iterator has methods `hasNext`and `next`, Enumeration has the methods `hasMoreElements`and `nextElement`

### Direction of iteration

You can use an Iterator to navigate in forward as well as backwards direction. Iterator has a sub-interface `ListIterator`. This has methods `hasPrevious`and `previous`.

The following code demonstrates this:

```
List<Integer> numbers = Arrays.asList(2,4,6,8,10);
ListIterator<Integer> itr = numbers.listIterator();
System.out.println("Navigating forward............");
while (itr.hasNext()) {
  System.out.print(itr.next()+" ");
}
System.out.println();
System.out.println("Navigating backward............");
while (itr.hasPrevious()) {
  System.out.print(itr.previous()+" ");
}
```

So this code uses the `hasNext`and `next` methods to navigate forwards and the `hasPrevious`and `previous` methods to navigate backwards.

However, you can only use an Enumeration to navigate in the forward direction.

### Removal of elements

Iterator can modify the Collection on which it operates. It has a `remove`method which removes an element from the Collection. The following code demonstrates this:

```
List<Integer> numbers = new ArrayList<Integer>();
numbers.add(2);
numbers.add(4);
numbers.add(6);
Iterator<Integer> itr = numbers.iterator();
while (itr.hasNext()) {
  int num = itr.next();
  if(num == 4) {
    itr.remove();
  }
}
System.out.println("List with element removed:");
for(int i = 0; i < numbers.size();i++) {
  System.out.print(numbers.get(i)+" ");
}
```

So this code checks if the input list has the element 6 and if so, uses the `iterator.remove`method to remove it. It then uses a separate for loop to print the elements in the list. So this code will print the following output:

```
List with element removed:
2 6



```

Enumeration on the other hand cannot modify the input collection, so you cannot remove an element from the Collection using Enumeration.

## Summary

The following table summarizes the differences between Iterator and Enumeration:

|Iterator|Enumeration  |
|--|--|
| Can be used on all collection classes | Can be used only on legacy collection classes like Vector and HashMap |
| Uses methods hasNext() and next() |Uses methods hasMoreElements() and nextElement()  |
| Can be used to navigate in both forward and backward direction | Can only be used to navigate in forward direction |
| Can also be used to remove the elements in the collection | Cannot be used to remove elements, can only be used to retrieve elements |

## Conclusion

So to summarize, you can use both Iterator and Enumeration to loop through the elements in a Collection. While you can use Iterator on any Collection, you can use Enumeration only for legacy collections. Iterator also supports features like navigating in both directions and modifying the input Collection, which are not supported by Enumeration.

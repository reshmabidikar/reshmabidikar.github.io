---
title: "Java 8 Comparator Changes"
date: "2020-12-02"
categories: 
  - "java8"
---

Java 8 has made many improvements to the Comparator interface. In this article, I will be explaining the Java 8 Comparator changes.

## Comparator.compare

From Java 8 onwards, Comparator is designated as a [functional](http://localhost/learnjava/what-is-a-functional-interface/) interface. So, you can implement the **Comparator.compare** method via a [lambda expression](http://localhost/learnjava/java-8-lambda-expressions-explained/).

Consider the following `Book` class:

```
public class Book {

  String name;
  int numPages;
  
  public Book(String name, int numPages) {
    this.name = name;
    this.numPages = numPages;
  }
  //getters and setters
}
```

And suppose you have a List of Book objects which needs to be sorted on the basis of the `numPages` field. Prior to Java 8, you had to create a class that implements the `Comparator` interface and use it to sort the `Book` List.

The following code demonstrates this:

```
public class BookCompartor implements Comparator<Book> {

  public int compare(Book book1, Book book2) {
    return book1.getNumPages() - book2.getNumPages();
  }
}

public class ComparatorBeforeJava8Demo {

  public static void main(String[] args) {
    List<Book> books = new ArrayList<>();
    
    books.add(new Book("The Complete Reference",743));
    books.add(new Book("Head First Java",451));
    books.add(new Book("Design Patterns",612));
    
    System.out.println("Before sorting:");
    books.forEach(book -> System.out.println(book.getName()+","+book.getNumPages()));
    books.sort(new BookCompartor());
    System.out.println("After sorting:");
    books.forEach(book -> System.out.println(book.getName()+","+book.getNumPages()));
  }
}
```

So, this code uses the `List.sort` method and passes the `BookComparator` to it.

This code is cumbersome since you need to create a class that implements the `Comparator` interface and then use it.

The code above can be written using a [lambda expression](http://localhost/learnjava/java-8-lambda-expressions-explained/) as follows:

```
public class ComparatorAfterJava8Demo {

  public static void main(String[] args) {
    List<Book> books = new ArrayList<>();

    books.add(new Book("The Complete Reference", 743));
    books.add(new Book("Head First Java", 451));
    books.add(new Book("Design Patterns", 612));

    System.out.println("Before sorting:");
    books.forEach(book -> System.out.println(book.getName() + "," + book.getNumPages()));

    books.sort((book1, book2) -> book1.getNumPages() - book2.getNumPages());

    System.out.println("After sorting:");
    books.forEach(book -> System.out.println(book.getName() + "," + book.getNumPages()));
  }
}

```

So, there is no need to create a `BookComparator` class as done earlier. This code is much simpler and easier to read.

## Comparator.comparing

Java 8 has added a new [static](http://localhost/learnjava/java-8-static-interface-methods/) method called `Comparator.comparing` to the Comparator interface.  This accepts as parameter a [Function](http://localhost/learnjava/java-8-function-interface-example/) that specifies the sort key and returns a Comparator that sorts on the specified key.

The following code demonstrates this method:

```
List<Book> books = new ArrayList<>();
books.add(new Book("The Complete Reference", 743));
books.add(new Book("Head First Java", 451));
books.add(new Book("Design Patterns", 612));

Comparator<Book> bookComparator = Comparator.comparing(book -> book.getName());
books.sort(bookComparator);

System.out.println("After sorting:");
books.forEach(book -> System.out.println(book.getName() + "," + book.getNumPages()));
```

This code invokes the `Comparator.comparing` method with a lambda expression that accepts a `Book` object and returns the `name` field. So, this returns a Comparator that sorts the `Book` objects on the basis of the `name` field.

So, this code displays the following output:

```
After sorting:
Design Patterns,612
Head First Java,451
The Complete Reference,743
```

## Comparator.comparingInt

The `Comparator.comparingInt` is another new static method on the Comparator interface. It is similar to the `Comparator.comparing` method. Instead of accepting a [Function](http://localhost/learnjava/java-8-function-interface-example/) as a parameter, it accepts a [ToIntFunction](http://localhost/learnjava/tointfunction-in-java-8-with-code-sample/) as a parameter. It returns a Comparator that sorts on the basis of an **int** key returned by the [ToIntFunction](http://localhost/learnjava/tointfunction-in-java-8-with-code-sample/) . For example,  in order to sort the `Book` objects on the basis of the `numPages` field, we can use this method as follows:

```
List<Book> books = new ArrayList<>();
books.add(new Book("The Complete Reference", 743));
books.add(new Book("Head First Java", 451));
books.add(new Book("Design Patterns", 612));

Comparator<Book> bookComparator = Comparator.comparingInt(book -> book.getNumPages());
books.sort(bookComparator);

System.out.println("After sorting:");
books.forEach(book -> System.out.println(book.getName() + "," + book.getNumPages()));
```

```
This code prints the following output:

After sorting: 
Head First Java,451 
Design Patterns,612 
The Complete Reference,743
```

Just like `comparingInt`, Java 8 has added static methods called `comparingLong` and `comparingDouble` which can sort based on a **long** key and **double** key respectively.

## Comparator.naturalOrder

`Compator.naturalOrder` is another new [static](http://localhost/learnjava/java-8-static-interface-methods/) method on the Comparator interface. It returns a Comparator that sorts in the natural order of the underlying Collection.

```
List<String> fruits = Arrays.asList("StrawBerry", "Apple", "Cherry", "Banana");
Comparator<String> fruitComparator = Comparator.naturalOrder();
fruits.sort(fruitComparator);
System.out.println("After sorting:");
fruits.forEach(fruit -> System.out.println(fruit));
```

This code creates a List of String values. For Strings, the natural order of sorting is alphabetical order. So, Comparator.naturalOrder sorts the fruits List in alphabetical order.

So, this code displays the following output:

```
After sorting:
Apple
Banana
Cherry
StrawBerry
```

## Comparator.reversed

Compator.reversed is a [default](http://localhost/learnjava/java-8-default-method-in-interface-explained/) method on the Comparator interface. It returns a Comparator that sorts in the reverse order of the Comparator on which it is invoked.

```
List<Book> books = new ArrayList<>();
books.add(new Book("The Complete Reference", 743));
books.add(new Book("Head First Java", 451));
books.add(new Book("Design Patterns", 612));

Comparator<Book> bookComparator = Comparator.comparingInt(book -> book.getNumPages());
Comparator<Book> bookComparatorReverse = bookComparator.reversed();
books.sort(bookComparatorReverse);

System.out.println("After sorting:");
books.forEach(book -> System.out.println(book.getName() + "," + book.getNumPages()));
```

This code first uses the `Comparator.comparingInt` method which returns a Comparator that sorts in the ascending order of the `numPages` field. It then invokes the `reversed` on this Comparator.  The code then uses this to sort the Book List. So, this results in the Book List being sorted in the descending order of the numPages field.

So, this code displays the following output:

```
After sorting:
The Complete Reference,743
Design Patterns,612
Head First Java,451
```

 

## Conclusion

So, in this article, we saw some of the Java 8 comparator changes. We saw how to implement the compare method using a lambda expression. We also saw some of the new static and default methods on the Comparator interface.

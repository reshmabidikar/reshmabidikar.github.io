---
title: "Java 8 Function Interface Example"
date: "2019-04-09"
categories: 
  - "java-8-examples"
tags: 
  - "functional-interface"
  - "interfaces"
  - "java8"
---

In this blog post, I will be explaining how the Java 8 functional interface Function works. To know more about functional interfaces, you can refer [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

\[table id=24 /\]

The [Function](https://docs.oracle.com/javase/8/docs/api/java/util/function/Function.html) interface provides a method called apply. It accepts a single parameter of any data type and returns a result of any data type. So it basically applies the logic in the apply method to the input parameter and returns the result.

#### Function Interface Example with String Input and Integer return type

Consider the following code snippet:

\[java\]

public class FunctionDemo { public static void main(String\[\] args) { Function<String,Integer> lengthChecker = (str) -> {return str.length();}; String input = "Hello World"; System.out.println("Length of "+input+" is "+lengthChecker.apply(input) ); input = "Test"; System.out.println("Length of "+input+" is "+lengthChecker.apply(input) );

}

}

\[/java\]

Here, we have written a Function implementation that accepts a String value and returns its length. The Function.apply method is implemented using a lambda expression. This expression accepts a _String_ value and returns its _length_. So when you execute this code, it will print the following output:

```
Length of Hello World is 11
Length of Test is 4
```

Function Interface Example with Object input and String output

Suppose there is a Book class as follows:

\[java\]

public class Book {

private String bookName; private String bookDesc;

public Book(String bookName,String bookDesc){ this.bookName = bookName; this.bookDesc = bookDesc; }

//Getter and setter methods

}

\[/java\]

And consider the following code snippet:

\[java\]

public class FunctionDemoWithBook {

public static void main(String\[\] args) { List<Book> books = new ArrayList<Book>(); books.add(new Book("Book1","Book Desc1")); books.add(new Book("Book2","Book Desc2")); books.add(new Book("Book3","Book Desc3"));

Function<Book,String> bookNameRetriever = (book) -> {return book.getBookName();};

List<String> bookNames = new ArrayList<String>(); for(Book book:books){ bookNames.add(bookNameRetriever.apply(book)); } System.out.println("Book names are:"+bookNames); }

}

\[/java\]

Here, we are creating a List of _Book_ objects and adding them to the _books_ list.  We are then defining a _bookNameRetriever_ function. This accepts a _Book_ object and returns its name.

We are then using the _bookNameRetriever_ to generate a List of _Book_ names. So we are iterating through the _Books_ list and invoking the [apply](https://docs.oracle.com/javase/8/docs/api/java/util/function/Function.html#apply-T-) method on each book to retrieve the name of the _Book_. When you run this code, it will print the following output:

```
Book names are:[Book1, Book2, Book3]
```

You can get the source code for this example along with the code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

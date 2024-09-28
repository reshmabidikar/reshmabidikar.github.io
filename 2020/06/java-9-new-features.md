---
title: "Java 9 New Features Explained in Detail"
date: "2020-06-23"
categories: 
  - "java-9"
---

In this article, I will be summing up all the new features introduced by Java 9.

## Modules

Modules are basically **groups of packages**. Just like you put a set of related classes into a package, you can put a set of related packages into a module. This helps to organize code better and to follow the Single Responsibility Principle (SRP). You can deploy a module by itself. So modules help to reduce the size of an application. In order to read more about modules, you can refer to [this](https://learnjava.co.in/java-9-modules-introduction/) article. You can also see some of my other articles about [module internals](https://learnjava.co.in/java-9-module-internals/) and [how to create modules](https://learnjava.co.in/creating-a-java-9-module/) .

## Stream Improvements

Java 9 has made several improvements on the Stream interface. These are as follows (You can click the article link for an in-depth explanation of each feature):

- [Stream.ofNullable](https://learnjava.co.in/java-9-ofnullable-stream-improvement/) - Helps to create a Stream with a null value.
- [Stream.iterate](https://learnjava.co.in/java-9-stream-api-iterate-method-example/) - Helps to create a new finite Stream. The Stream is terminated when the specified condition is true
- [Stream.dropWhile](https://learnjava.co.in/java-9-stream-dropwhile-method-with-examples/) - Helps to filter a Stream. Drops the elements in the Stream that match the specified condition
- [Strean.takeWhile](https://learnjava.co.in/java-9-stream-takewhile-with-examples/) - Helps to filter a Stream. Creates a new Stream with the elements in the Stream that match the specified condition

## Collection Factory Methods

Java 9 has added static factory methods to all the Collection interfaces. You can use these methods to create the corresponding Collection using some values. You can refer to [this](https://learnjava.co.in/collection-factory-methods-in-java-9-explained/) article to understand how this feature works

## Private Interface Methods

Prior to Java 9, Interfaces could not have private methods. Private methods help to reuse the code in default/static methods in an interface. You can refer to [this](https://learnjava.co.in/java-9-private-interface-methods/) article to understand how this feature works

## JShell

JShell provides REPL capabilities to Java. REPL stands for Read Evaluate Print Loop. Many languages like Python also provide REPL capabilities. REPL allows you to write Java code and test it without the need to compile it. You can refer to [this](https://learnjava.co.in/jshell-in-java-9/) article to understand how this feature works

## Conclusion

In this article, we saw the various new Java 9 features like Java 9 Modules, Java 9 Stream Improvements, Java 9 Collection Factory methods, Java 9 Private Interface Methods, Java 9 JShell.

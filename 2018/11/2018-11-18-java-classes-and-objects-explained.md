---
title: "Java classes and objects explained"
date: "2018-11-18"
categories: 
  - "java-interview-questions"
  - "java_language_features"
tags: 
  - "classes"
  - "core-java"
  - "objects"
  - "oops"
---

In this blog post, I will be explaining the distinction between classes and objects. The most important thing to understand about a class is that it defines a new data type. Once defined, this new type can be used to create objects of that type.

\[java\]

public class Book {

String bookName;

String bookAuthor; } \[/java\]

This is a very simple class called Book. This class keyword is used to declare a class.You can see here that I’ve declared some variables in the class. These variables are called **instance variables** or **fields**. This Book class acts as a template and we can create many books using this class. Now consider the following code snippet:

\[java\]

public class Demo {

public static void main(String args\[\]){

Book book = new Book(); }

}

\[/java\]

The first line creates a new object of type **Book** and assigns it to the variable **book**. This object **book** will have its own copies of the variables bookName and bookAuthor. Each object contains its own copy of each instance variable defined by the class. A class acts like a template, it has no memory allocated to it,the objects of the class occupy actual memory.

The **new** operator dynamically allocates memory for the object. It should be followed by the name of the class whose instance is being created. The class name followed by parentheses specifies the _**constructor**._

So to summarize,  a class creates a new data type that can be used to create objects. That is, a class creates a logical framework.When you declare an object of a class, you are actually allocating memory. Thus, a class is a logical construct. An object has physical reality.

---
title: "JPA vs Hibernate - An In-depth comparison"
date: "2019-02-28"
categories: 
  - "java-interview-questions"
  - "hibernate"
tags: 
  - "hibernate"
  - "jpa"
---

Often, we come across the terms JPA and Hibernate. Quite often, they are used interchangeably as well. Also, if you try to read up some tutorial to JPA, there will be a reference to Hibernate in it. So also, when you are studying Hibernate, you will come across references to JPA too. So it is often confusing for developers. In this post, I will attempt to clear this confusion.

#### What is Hibernate?

Hibernate is an ORM tool. ORM is nothing but a programming technique that allows you to map Java objects to database tables and vice versa. In addition to Hibernate, there are several other ORM tools.

Before Hibernate came into existence, JDBC was widely used to access a relational database from Java code. The downside of JDBC is that it is not very object oriented.  It is very hard to map database tables to the code. Hibernate allows you to directly map your database tables to Java classes. So compared to JDBC, Hibernate provides a much cleaner approach.

However, there is a disadvantage to using a proprietary framework like Hibernate. It makes switching to a different framework difficult. Since all the code is specific to Hibernate, if you want to switch to a different framework it would involve changing your code totally.

#### What is JPA?

JPA stands for Java Persistence API. The JPA specification was developed by Java as a standard way to map objects to relational tables. JPA just provides the specification, it does not provide the implementation. So you cannot use JPA by itself, you will need to use a JPA provider that implements the JPA framework. EclipseLink and TopLink are some frameworks that implement the JPA specification, that is they are JPA providers. The advantage of using a framework that implements the JPA specification is that you can easily switch the framework. So for example if your code uses TopLink, you can easily change your framework to EclipseLink without having to change your code.

#### Hibernate was made JPA compatible

Hibernate was initially a proprietary framework. After the release of the JPA specification Hibernate was made JPA compatible i.e. it implements the JPA specification. So now Hibernate not only has its own proprietary methods, but it also implements methods defined by the JPA Spec. So you might find some duplicate methods in Hibernate. For example to save a record to the database, there is a method save, as well as a method called persist. The save method is Hibernate's own method while persist is part of the JPA specification.

#### What should I use?

As stated earlier, you cannot use JPA by itself, you need to use it with some JPA provider. Hibernate is a JPA provider. When you use Hibernate in your code, you can use the proprietary methods of Hibernate or you can use the JPA methods implemented by Hibernate. If you use the JPA methods in your code, you will be easily able to switch to some other JPA provider like EclipseLink or TopLink. However, if you use Hibernate proprietary methods, you will need to modify your code to a great deal if you want to switch to some other JPA provider.

So if you plan to change your framework from Hibernate to something else, I would recommend that you use the JPA methods implemented by Hibernate.

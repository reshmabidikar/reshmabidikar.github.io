---
title: "Introduction to JPA - The Why, What and How of JPA"
date: "2020-09-03"
categories: 
  - "hibernate"
---

In this article, I will be giving you an Introduction to JPA.. I will be explaining what was the need for JPA, what JPA is and how it works.

## Need for JPA

In the early days of programming, JDBC was widely used to access a database table from Java code.  It allows [querying/updating](http://localhost/learnjava/how-to-query-a-database-table-via-jdbc/) database tables from Java code.  The downside of JDBC is that is is very verbose. You need to directly write SQL statements in the code. Secondly, it is not object-oriented, so it becomes difficult to map database tables to Java classes and vice versa. Also, since it uses SQL directly in the code, developers may tend to use database specific SQL and thus make the code database dependent.

To overcome all these limitations, ORM frameworks were developed.  ORM stands for Object Relational Mapping.  An ORM framework helps to map a database table to a Java class and vice versa and thus does away with all the boilerplate code associated with JDBC. Some popular ORM frameworks are [Hibernate](https://www.udemy.com/course/hibernate-from-scratch/?referralCode=E61D23C12F80BB22873F) and TopLink.

However, over time a lot of proprietary ORM frameworks came into existence.  Each framework had its own API. So, an application using a particular framework had to use framework specific code and so migrating to a different framework was cumbersome.  Thus, there was a need for a standard API used by all ORM frameworks. JPA provides this standard API.

## What is JPA

JPA stands for Java Persistence API. It is a standard provided by Java to access database tables from Java code.  It is just a specification. Any ORM framework that wants to adhere to the JPA standard needs to implement the specification. So an application that needs to use JPA needs to use it in conjunction with a framework that implements the JPA specification. Such a framework is also known as a JPA provider.  When an application uses JPA, it thus become easy to change the underlying JPA provider. without changing the code.

Though Hibernate was initially developed as a proprietary ORM framework, it was made JPA compliant.  So, it implements the JPA specification and you can use it as a JPA provider.  Like Hibernate, there are other JPA providers like TopLink, EclipseLink, etc. So, if an application uses an ORM framework that is JPA compatible, it is easy to replace it with some other ORM framework.

The following diagram explains how it all fits together:

[![](images/JPA.png)](http://localhost/learnjava/wp-content/uploads/2020/12/JPA.png)

 

## How JPA Works

The application that wants to use JPA needs to provide a **simple class (POJO)** corresponding to each database table. The class should have instance fields corresponding to the database columns. In addition, it needs to provide **configuration information** (information about the database URL, user name, password, etc.) and **mapping information** (information that specifies how to map each class to the corresponding database table). It then needs to write code that uses JPA calls. JPA uses the mapping and configuration information to translate the JPA calls to SQL statements.

## Further Learning

[Master JPA and Hibernate with Spring Boot](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fhibernate-jpa-tutorial-for-beginners-in-100-steps%2F) [Spring Data JPA with Hibernate](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-data-jpa-using-hibernate%2F) [Hibernate and JPA Fundamentals](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fhibernate-and-java-persistence-api-jpa-fundamentals%2F)

## Conclusion

So, in this article, we understood what was the need for JPA, what JPA is at a high level and how JPA works.

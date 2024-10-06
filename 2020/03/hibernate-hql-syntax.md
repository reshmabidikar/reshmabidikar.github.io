---
title: "Hibernate HQL Syntax with code examples"
date: "2020-03-20"
categories: 
  - "hibernate"
---

HQL stands for Hibernate Query language. It is similar to SQL, but instead of the database table and column names, it uses the class and field names. So whenever we need to query the database, we write HQL queries in Hibernate. Based on the underlying database, Hibernate automatically converts **HQL** into equivalent SQLs statements. HQL has a very rich syntax and I will be covering the Hibernate HQL syntax in detail in this article.

## From Clause

The from clause consists of the from keyword followed by an entity name. It specifies the entity from which Hibernate needs to retrieve data. So if we have a Person entity, we can specify the from clause as follows:

```
String queryStr = "from Person";
Query<Person> query = session.createQuery(queryStr);
List<Person> books = query.getResultList();

```

## Select Clause

The select clause can also be used to retrieve data from the database. The select clause is more powerful than the from clause. It provides more control over the resultset. It allows you to select only a few fields from the database. You can do this by specifying the field names that you want to retrieve.

The following code demonstrates this:

```
String queryStr = "select name from Person";
Query<String> query = session.createQuery(queryStr);
List<String> names = query.getResultList();

```

## As Clause

Hibernate allows us to assign a name to a class in a query using the “AS” clause. Such a name given to a class is called an alias. Aliases are specified just for ease of use and are optional although it is a good practice to use them. If you have long queries, using an alias makes the query more readable.

The following code demonstrates this:

```
String queryStr = "from Person as person"; 
Query<Person> query = session.createQuery(queryStr);
List<Person> books = query.getResultList();

```

## Where Clause

The where clause is used to limit the results obtained in a query. It can be used in a from clause or a select clause. In addition, it can also be used with the update and delete clause to limit the scope of the update or delete.

The following code demonstrates this:

```
String queryStr = " from Person where age > 21
Query<Person> query = session.createQuery(queryStr);
List<Person> books = query.getResultList();

```

## Order by

The Order by clause is used to sort the results obtained from a query. You can order the results by any field of the class which is present in the result set either in ascending (ASC) or descending (DESC) order.

The following code demonstrates this:

```
String queryStr = "from Person order by age";
Query<Person> query = session.createQuery(queryStr);
List<Person> books =query.getResultList();
```

## Further Learning

[Master JPA and Hibernate with Spring Boot](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fhibernate-jpa-tutorial-for-beginners-in-100-steps%2F) [Spring Data JPA with Hibernate](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-data-jpa-using-hibernate%2F) [Hibernate and JPA Fundamentals](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fhibernate-and-java-persistence-api-jpa-fundamentals%2F)

## Conclusion

So in this article, we took a look at the Hibernate HQL syntax and the various clauses supported by HQL.

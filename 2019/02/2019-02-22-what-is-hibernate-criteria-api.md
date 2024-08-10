---
title: "What is Hibernate Criteria API"
date: "2019-02-22"
categories: 
  - "java-interview-questions"
  - "hibernate"
tags: 
  - "criteria-api"
  - "hibernate"
---

In this blog post, I will be explaining what is the Hibernate Criteria API.

There are 3 ways in which you can query a database via Hibernate:

- Methods like load/get
- HQL (Hibernate Query Language)
- Criteria API

#### Approach 1 - Methods like load/get

Hibernate provides methods like [load](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#load-java.lang.Class-java.io.Serializable-) and [get](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#get-java.lang.Class-java.io.Serializable-org.hibernate.LockOptions-). You can use these to load a specific record from the database. The downside is that you can use these methods to only load a single record corresponding to an id. So if you want to retrieve all records that have a certain value, you cannot use these methods

#### Approach 2 - Using HQL

HQL stands for **Hibernate Query Language**. It has syntax similar to SQL.So whenever you need to query the database, you can write HQL queries in Hibernate. Instead of the database table and column names, you need to specify the class and field names in an HQL query. Based on the underlying database being used, Hibernate automatically converts HQL into equivalent SQLs statements. The downside to using HQL is that it is not a very object oriented approach and can tend to get messy

#### Approach 3 - Criteria API

In addition to HQL, Hibernate provides another way to retrieve the data from the database .This is by using the Criteria API.  The Criteria API uses a [CriteriaQuery](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/criterion/CriteriaQuery.html). A [CriteriaQuery](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/criterion/CriteriaQuery.html) uses a model of the information that you need to find. For example, suppose there is a database table "Person". Suppose we want to retrieve all the records from the Person table whose name is "John". For this, we can create a Person object, set the name field to "John" and use that in the [CriteriaQuery](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/criterion/CriteriaQuery.html).

Querying the database using the Criteria API is a more object oriented approach compared to HQL. So you don’t need to write any query or remember any syntax. However, you can only use the Criteria API to retrieve data, to perform save, update or delete, you will still have to use HQL.

Hibernate supports Criteria API in 2 ways. Hibernate has it's own native Criteria API and it also supports the criteria API exposed by JPA. Hibernate’s native criteria API has been deprecated since Hibernate 5 and it is recommended to use the criteria API exposed by JPA.

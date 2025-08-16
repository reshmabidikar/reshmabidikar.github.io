---
title: "Hibernate Association Mappings with code samples"
date: "2019-06-24"
categories: 
  - "java-interview-questions"
  - "hibernate"
tags: 
  - "association-mappings"
  - "hibernate"
---

[Hibernate](https://reshmabidikar.github.io/blog.html#jpa-hibernate-and-jdbc) supports associations that help you to model the relationship between database tables. In this article, I will be covering Hibernate association mappings.

## Introduction

Most real-world applications have tables that have dependencies on each other i.e. the primary key of a table will be the foreign key in another table. Hibernate associations help us to represent the relationships between the tables.

## Types of association mappings

Hibernate supports 4 types of associations as follows

### One to One

You can use a One To One association mapping to represent a one-to-one relationship between database tables. A one-to-one relationship occurs between tables when one record from the main table corresponds to only one record in the second table. For example, a Person can have only one address. So one record in a Person table will correspond to only one record in the address table.

### One To Many

You can use a One To Many association mapping to represent a one to many relationships between tables. A one-to-many relationship occurs between tables when one record from a table can correspond to many records from another table. So for example, a Person can have many email ids. So one record in the Person table will correspond to many records in the Email table.

### Many To One

You can use a Many To One association mapping to represent a many to one relationship between tables. A many-to-one relationship occurs when many records from the main table correspond to only one record from the second table. So for example, many cities belong to the same state, so many records from the city table will correspond to the same record from the state table.

### Many To Many

You can use a Many To Many association mapping to represent a many-to-many relationship between tables. A many-to-many relationship occurs when many records from one table correspond to many records from another table. So for example, many students can belong to a class and a class can have many students. So many records from the student table can correspond to many records from the class table.

## Direction of Associations

An association can be unidirectional or bidirectional. This specifies the direction in which navigation can occur in the classes corresponding to the tables. So association mappings can be Unidirectional or Bidirectional

### Unidirectional Association

In a Unidirectional association, navigation access is only in one direction. So for example, if there is a Person class and an Address class, a person class will have an Address object but the other way will not be true i.e. the Address class will not have a person object.

### Bidirectional Association

In a Bidirectional association, navigation access is in both directions. So the Person class will have an address object and the address class will have a person object. Irrespective of whether the mapping is unidirectional or bidirectional, the database tables remain the same. But bidirectional mapping will make it easy to access the other side without explicit queries

## Implementing Association Mappings in Hibernate

Finally, associations can be implemented via annotations as well as mapping files. If you use annotations, you need to specify annotations in your entity classes corresponding to the mapping that you want to implement. Hibernate supports annotations like **@OneToOne, @ManyToOne**,**@OneToMany, and @ManyToMany** for this.

You can also specify the associations in the mapping file. Hibernate provides mapping XML elements like **OnetoOne, ManyToOne, OneToMany, and ManyToMany** for this.

## Conclusion

So, in this article, we understood Hibernate Association Mappings. We saw the different types of association mappings and also saw how to write code that uses association mappings.

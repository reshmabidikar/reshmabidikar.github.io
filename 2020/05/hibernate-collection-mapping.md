---
title: "Hibernate Collection Mapping"
date: "2020-05-22"
categories: 
  - "hibernate"
---

In this article, I will be going over how Hibernate Collection Mapping works

## What is Collection Mapping?

Sometimes, you will have a Collection of values associated with an entity. You may want to persist the values in the Collection but may not want to create a separate Entity corresponding to the Collection. You can achieve this via Hibernate/JPA Collection mapping. Hibernate Collection Mapping feature allows you to map any type of Collection like List, Set or Map.

## How Collection Mapping works

JPA provides an annotation called `@ElementCollection` in order to support collection mapping. You need to specify this annotation on the Collection that you want to persist to the database. Using collection mapping, you can map a collection having primitive type of data as well as non-primitive type (object) data

### Mapping a Primitive Type

In order to map a collection having primitive type of data, you just need to specify the `@ElementCollection` annotation on the field corresponding to the collection. When you try to persist the main entity, Hibernate will automatically persist the collection along with the main entity.  Hibernate creates a new table that has the values in the Collection. You can use this approach to map a List, Set or Map. I will be providing a detailed code sample in a separate article

### Mapping an Object Type

Just like a primitive type collection, you need to specify the `@ElementCollection` annotation on the field corresponding to the collection in case the collection has objects. In addition, you also need to specify the `@Embeddable` annotation on the class whose objects are present in the Collection. When you try to persist the main entity, Hibernate will automatically persist the collection along with the main entity. Hibernate creates a new table that has columns corresponding to all the fields in the `@Embeddable` class. It inserts records corresponding to the objects in the Collection. You can use this approach to map a List, Set or Map. I will be providing a detailed code sample in a separate article

## How Collection Mapping is different from association mapping

If you think about it, collection mapping is similar to a One to Many association. The only difference is that in a one to many association, the target class is also an entity and can be queried by itself. In a Collection mapping, the target class is not an entity. It cannot be queried by itself.

## When should you use Collection Mapping

Although collection mapping looks easy to use, it has some disadvantages. For one, the elements in the collection cannot be saved or queried individually. Secondly, if the collection is modified and the entity is saved, Hibernate deletes all the records from the corresponding table and inserts them all over again. so this is not very efficient So you should use collection mappings only for very small collections. In all other cases, a one-to-many association is the better approach.

## Further Learning

[Master JPA and Hibernate with Spring Boot](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fhibernate-jpa-tutorial-for-beginners-in-100-steps%2F) [Spring Data JPA with Hibernate](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-data-jpa-using-hibernate%2F) [Hibernate and JPA Fundamentals](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fhibernate-and-java-persistence-api-jpa-fundamentals%2F)

## Conclusion

So in this article, I gave an overview of Hibernate/JPA collection mappings. I covered how you can use the `@ElementCollection` annotation to map a collection to the database.

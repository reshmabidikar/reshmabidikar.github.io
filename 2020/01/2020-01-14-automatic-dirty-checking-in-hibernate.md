---
title: "Automatic Dirty Checking in Hibernate"
date: "2020-01-14"
categories: 
  - "hibernate"
tags: 
  - "automatic-dirty-checking"
  - "hibernate"
---

Hibernate provides as feature called Automatic Dirty checking whereby changes to a persistent object are automatically saved to the database when the session is flushed or the transaction is committed. So the code does not need to invoke an explicit save or update. In this article, I will be covering this feature in detail.

## Introduction

Hibernate supports 3 entity states, transient, persistent and detached. In order to understand more about entity states, you can refer to [this](https://learnjava.co.in/hibernate-persistence-life-cycle/) article.

So basically, an object can move into the persistent state when any one of the following happens:

- When the code invokes session.save, session.persist or session.saveorUpdate
- When the code invokes session.load or session.get

Any changes to a persistent object are automatically saved to the database when the session in flushed. _Flushing_ is the process of synchronizing the underlying database with the objects in the session. There is a session.flush method available but you generally don’t need to invoke it explicitly. A session gets flushed when the transaction is commited. The process of automatically updating the database with the changes to the persistent object when the session is flushed is known as **automatic dirty checking**.

## An Example

Suppose we have a database table **'Person'** which fields corresponding to 'id', 'name' and 'age'. Suppose it has some records as follows:

\[table id=18 /\]

Now consider the following code:

```
SessionFactory  sessionFactory = HibernateUtil.getSessionFactory();
Session session = sessionFactory.openSession();
Transaction tx = session.beginTransaction();
Person person  = session.load(Person.class, 2); //loads Person object for id 2
person.setAge(32);
tx.commit();
session.close();
HibernateUtil.closeSessionFactory();
```

So this code invokes the **session.load** method to load the person object corresponding to the id '2'. So this moves the person record with id 2 to the persistent state.  It then invokes the **setAge** method and updates the value of the age field to 32.  Then the code directly invokes the **tx.commit** method without invoking the **session.save** or **session.update**. Since the person object is in the persistent state, the change to the age field will automatically get saved to the database.

## Further Learning

[Master JPA and Hibernate with Spring Boot](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fhibernate-jpa-tutorial-for-beginners-in-100-steps%2F) [Spring Data JPA with Hibernate](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-data-jpa-using-hibernate%2F) [Hibernate and JPA Fundamentals](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fhibernate-and-java-persistence-api-jpa-fundamentals%2F)

## Conclusion

So in this article, we saw what is the automatic dirty checking feature in Hibernate and how you can use it to save changes to persistent objects.

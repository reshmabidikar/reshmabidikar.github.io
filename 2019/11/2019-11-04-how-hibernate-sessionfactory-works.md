---
title: "How Hibernate SessionFactory works"
date: "2019-11-04"
categories: 
  - "hibernate"
tags: 
  - "hibernate"
  - "sessionfactory"
---

In this article, I will be explaining what is Hibernate SessionFactory and how it works.

Consider the following code that demonstrates a typical Hibernate application:

```
SessionFactory  sessionFactory = new Configuration().configure().buildSessionFactory();
Session session = sessionFactory.openSession();
Transaction tx = session.beginTransaction();
session.save(person);
tx.commit();
session.close();
sessionFactory.close();
```

 

- This code first creates a  **SessionFactory** object.  The sessionFactory contains all the data in the hibernate configuration file. The code uses the Configuration class to create the SessionFactory instance.
- The **configuration.configure** method reads the hibernate.cfg.xml file and sets up the **Configuation** object using the properties in this file.
- The **buildSessionFactory** method builds the sessionFactory object using this configuration data.
- The **SessionFactory** object is usually created only once at the start of the application and kept for later use.
- The **SessionFactory** corresponds to the database config file. So you will need different **SessionFactory** instances if your application connects to different databases.
- You can then use the SessionFactory instance to obtain a **Session** and interact with the database

So I hope this blog post was useful to understand how the SessionFactory works internally. Happy learning!!

## Further Learning

[Master JPA and Hibernate with Spring Boot](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fhibernate-jpa-tutorial-for-beginners-in-100-steps%2F) [Spring Data JPA with Hibernate](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-data-jpa-using-hibernate%2F) [Hibernate and JPA Fundamentals](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fhibernate-and-java-persistence-api-jpa-fundamentals%2F)

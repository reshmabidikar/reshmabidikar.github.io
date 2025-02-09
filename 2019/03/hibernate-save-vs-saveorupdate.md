---
title: "Hibernate save vs saveOrUpdate"
date: "2019-03-26"
categories: 
  - "java-interview-questions"
  - "hibernate"
tags: 
  - "hibernate"
  - "hibernate-save-method"
  - "hibernate-saveorupdate-method"
---

Hibernate provides several methods to save or modify the data into a database table. Two such methods are [save](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#save-java.lang.Object-) and [saveOrUpdate](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#saveOrUpdate-java.lang.Object-). In this blog post, I will be providing a detail comparison between the two.

#### What is save?

Hibernate provides the [save](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#save-java.lang.Object-) method on the [session](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html) interface to **save a record** into the database. So the [session.save](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#save-java.lang.Object-) **inserts a record** into the database. It **returns the id**, that is the primary key that will be assigned to the database record.

#### What is saveOrUpdate?

In addition to the save method, Hibernate also provides a method called [saveOrUpdate](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#saveOrUpdate-java.lang.Object-) on the session interface. Just as the name suggests, this method either **performs a save operation or an update operation**. If there is no record in the database corresponding to the object passed in, it inserts a record, but if there is a record corresponding to the object passed in, it just updates the existing record. This is generally useful in applications where a UI is involved. In such cases the back end might not be sure if the UI has sent a new object or an existing object with some updated fields. So instead of writing explicit code in the back end to check if a record exists, the saveOrUpdate method can be used.

#### How are they similar?

Both the [save](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#save-java.lang.Object-) and the [saveOrUpdate](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#saveOrUpdate-java.lang.Object-) methods can be **used to insert a record** to the database. Also, both methods are **Hibernate's proprietary methods** and are not part of the JPA specification.

#### How are they different?

Both the [save](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#save-java.lang.Object-) and the [saveOrUpdate](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#saveOrUpdate-java.lang.Object-) methods can be used to insert a record to the database, there are a couple of differences between the two. The save method just inserts a record into the database. So when the code invokes the **save** method , Hibernate translates it to an **SQL Insert query.** In contrast, the saveOrUpdate method can either save or update a record in the database. So when the code invokes the **saveOrUpdate** method, Hibernate translates it into either an **SQL Insert query or an SQL Update query**. Another difference is that the save method **returns the id** of the newly inserted record. The saveOrUpdate method does not return anything, it **returns a void.** Another difference is that the **save** method operates on a transient object, i.e. it moves an entity from the **transient** state to the **persistent** state. In contrast, the **saveOrUpdate** method moves an object from the **transient or detached** state to the **persistent** state. I will be covering the entity states in a separate post. The following table summarizes the differences:

| save |saveOrUpdate  |
|--|--|
| Inserts a record | Inserts or Updates a record |
| Returns the id of the inserted record |Does not return anything, returns a void  |
| Moves an entity from transient state to persistent state | Moves an entity from transient or detached state to persistent state |

#### Which should you use and when?

You should generally use the **save** method when you are sure that there is **no record** in the database corresponding to the object passed in. So for example, suppose the back end receives an object from the UI. Suppose, there is a new user registration screen in the UI. When the object is sent by this screen to the back end, you are sure that there will be no record in the database corresponding to the object passed in. In such a case, you can use the save method. On the other hand, you should use the **saveOrUpdate** if you are **not sure** if the **UI has sent a new object or an existing object with some updated fields.**

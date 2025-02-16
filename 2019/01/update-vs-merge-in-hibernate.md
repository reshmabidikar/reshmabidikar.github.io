---
title: "Update vs Merge in Hibernate"
date: "2019-01-29"
categories: 
  - "hibernate"
tags: 
  - "hibernate"
---

In this blog post, I will be comparing the [Update](https://docs.jboss.org/hibernate/orm/5.0/javadocs/org/hibernate/Session.html#update-java.lang.Object-) and [Merge](https://docs.jboss.org/hibernate/orm/5.0/javadocs/org/hibernate/Session.html#merge-java.lang.Object-) methods in Hibernate. I will be explaining how they are similar. I will also be explaining the differences between them.

#### Similarities

Both update and merge methods on the [session](https://docs.jboss.org/hibernate/orm/3.5/javadocs/org/hibernate/Session.html) interface. Both methods update a record in the database. Both move an entity from the detached state to the persistent state.

#### Differences

The following table lists the differences between the update and merge methods:

|Update|Merge  |
|--|--|
| Hibernate proprietary method |Part of the JPA specification  |
| Does not return anything, returns a void | Returns the updated object |
| Makes the original object persistent. So if the original object is changed after invoking update, changes will get saved when the session is flushed |Does not make the original object persistent, so even if the original object is changed after merge, changes will not get saved in the database. Instead, the merged object is tracked for changes  |
|Always performs an SQL update  | Only performs an SQL update if the fields of the object passed in are different from the fields in the database |

---
title: "Difference between save and persist in Hibernate"
date: "2019-01-18"
categories: 
  - "java-interview-questions"
  - "hibernate"
tags: 
  - "hibernate"
---

In this blog post, I will be explaining the difference between the [save](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#save-java.lang.Object-) and [persist](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#persist-java.lang.Object-) methods Hibernate. Both the[save](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#save-java.lang.Object-) and [persist](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html#persist-java.lang.Object-) methods insert a record into a database table. However, there are some differences between the two.



|save  |persist  |
|--|--|
|Hibernate Proprietary method  | Part of the JPA specification |
| Returns ID of the saved object | Returns a void |
| Insert happens immediately in order to return the ID |May not cause the database insert to happen immediately and the insert might happen later when the session is flushed  |

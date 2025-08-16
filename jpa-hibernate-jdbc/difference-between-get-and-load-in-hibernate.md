---
title: "Difference between Get and Load in Hibernate"
date: "2018-12-12"
categories: 
  - "hibernate"
tags: 
  - "crud-operations-in-hibernate"
  - "hibernate"
---

In this blog post, I will be explaining the difference between the Hibernate load and get methods. Both methods are used to load a record corresponding to an id. However, there are some differences between the two.

|Get|Load  |
|--|--|
| If there is no record in the database corresponding to the id passed in, the load method throws an exception | If there is no record in the database corresponding to the id passed in, the get method returns a null |
|When the load method is used, it returns a proxy object with just the id field populated. All other fields are blank. The fields are only fetched from the database when they are accessed from the code.  | When the get method is used, it fetches the complete object i.e. it fetches all the fields of the object. |

---
title: "Hibernate interfaces explained"
date: "2019-05-05"
categories: 
  - "hibernate"
---

In this blog post, I will be explaining some of the interfaces that are commonly used in a Hibernate application

# Sample Code

Consider the following code that queries a table via Hibernate:

````java
public class Main {

public static void main(String[] args) { 
Person person = new Person("Mickey Mouse",35); //This corresponds to a table called Person with name and age fields

SessionFactory sessionFactory = new Configuration().configure().buildSessionFactory(); Session session = sessionFactory.openSession(); 
Transaction tx = session.beginTransaction(); 
session.save(person); 
tx.commit(); 
session.close(); 
sessionFactory.close(); 
}

}
````

# Configuration

The [**Configuration**](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/cfg/Configuration.html) object is the **first** Hibernate object that you will need to create in any Hibernate application. It encapsulates the Hibernate configuration file i.e. **hibernate.cfg.xml**. A typical Hibernate application usually creates a [Configuration](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/cfg/Configuration.html) object only once during application initialization. The [configuration.configure](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/cfg/Configuration.html#configure--) method reads the **hibernate.cfg.xml** file and sets up the [Configuration](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/cfg/Configuration.html) object using the **properties** in this file. The [Configuration](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/cfg/Configuration.html) object is required to create the [SessionFactory](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/SessionFactory.html) object.

# SessionFactory

The [SessionFactory](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/SessionFactory.html) contains all the data in the hibernate **configuration** file. The code creates a [SessionFactory](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/SessionFactory.html) using a **Configuration** object. The [configuration.buildSessionFactory](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/cfg/Configuration.html#buildSessionFactory--) method sets up the **SessionFactory** object with the configuration data in the **config** file. A typical Hibernate application create the **SessionFactory** object only once at the start of the application and keeps it for later use. The **SessionFactory** corresponds to the database **config** file, so if your application connects to several databases with different config files, you will need to have separate **SessionFactory** objects corresponding to each database.

# Session

Next, the code creates a [**session**](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Session.html) object. The code uses the [sessionFactory.openSession](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/SessionFactory.html#openSession--) method to create a **Session** object. The **session** represents the **physical connection** with the database, so whenever a session is created, internally a **connection** is established to the database. The code uses the **session** object to actually save data and retrieve data from the database.

# Transaction

Next, the code creates a [**transaction**](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Transaction.html). As you might be aware, in database terminology, a **transaction** represents a unit of work. So if you want to execute several database operations as a single unit, you can club them into a **transaction**. A **transaction** ensures that either all the operations will be executed. If one operation fails the entire transaction will fail. So the database will be reverted to the state that it was before the transaction began. Hibernate defines the [**transaction**](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Transaction.html) interface to represent a **transaction**. A **transaction** is associated with a **Session** and is usually instantiated by a call to [session.beginTransaction()](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/SharedSessionContract.html#beginTransaction--). This gives an instance of the [Transaction](http://docs.jboss.org/hibernate/orm/5.4/javadocs/org/hibernate/Transaction.html) object. The code can then use the transaction object for committing the changes to the database.

---
title: "JPA Interfaces explained with code samples"
date: "2021-02-11"
categories: 
  - "hibernate"
coverImage: "database-scaled.jpg"
---

In my [earlier](how-to-create-a-standalone-jpa-application.md) article, we had learnt how to create a basic JPA application. In this article, I will be explaining the important JPA interfaces.

## Persistence Unit

As seen [earlier](how-to-create-a-standalone-jpa-application.md#Creating_Configuration_File), we need to create a configuration file called **persistence.xml** that contains the database configuration details as follows:

```xml
<persistence xmlns="http://xmlns.jcp.org/xml/ns/persistence"
             xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
             xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence
             http://xmlns.jcp.org/xml/ns/persistence/persistence_2_1.xsd"
             version="2.1">
    <persistence-unit name="PERSISTENCE">
        <description>JPA Demo</description>
        <provider>org.hibernate.jpa.HibernatePersistenceProvider</provider>
        <properties>
            <property name="hibernate.dialect" value="org.hibernate.dialect.MySQLInnoDBDialect"/>
            <property name="javax.persistence.jdbc.driver"
                      value="com.mysql.jdbc.Driver"/>
            <property name="javax.persistence.jdbc.url"
                      value="jdbc:mysql://localhost/jpademo"/>
            <property name="javax.persistence.jdbc.user" value="user"/>
            <property name="javax.persistence.jdbc.password" value="password"/>
        </properties>
    </persistence-unit>
</persistence>
```

The **persistence.xml** file specifies a **persistence unit**. A **persistence unit** encapsulates database details. So, it includes the JPA Provider, mapping information & database configuration details. The **persistence.xml** file above specifies a persistence unit **PERSISTENCE**. It specifies Hibernate as the persistence provider and includes various other database connection details. JPA uses the information in the persistence unit to configure the database connection. If your application uses multiple databases, you need to create a separate persistence unit corresponding to each database.

## Entity

An Entity is a simple POJO class that corresponds to a database table. It needs to have fields corresponding to the database table columns. [Earlier](https://learnjava.co.in/how-to-create-a-standalone-jpa-application/#Creating_POJO_class), we had created a **Fruit** entity class as follows:

```java
@Entity
public class Fruit {
 @Id
 @GeneratedValue(strategy = GenerationType.IDENTITY)
 private int id;
 private String name;
 private String colour;
 private int calories;
 //getters and setters
}
```

The **Fruit** class has the **@Entity** annotation. This designates the **Fruit** class as a JPA entity. So, this class corresponds to a **Fruit** table having columns corresponding to **name**, **colour** and **calories**. Each object of the **Fruit** class corresponds to a record in the **Fruit** table.

## JPA Interfaces

Just to [recap](how-to-create-a-standalone-jpa-application#Writing_JPA_Code), we had written the following JPA Code:

```java
@Test
 public void testSave() {
  EntityManagerFactory emf = Persistence.createEntityManagerFactory("PERSISTENCE");
  EntityManager em = emf.createEntityManager();
  EntityTransaction et = em.getTransaction();
  et.begin();
  Fruit apple = new Fruit();
  apple.setName("apple");
  apple.setColour("red");
  apple.setCalories(5);
  em.persist(apple);
  et.commit();
  System.out.println("Fruit record saved successfully");
  em.close();
  emf.close();
}
  
  @Test
  public void testQuery() {
    EntityManagerFactory emf = Persistence.createEntityManagerFactory("PERSISTENCE");
    EntityManager em = emf.createEntityManager();
    TypedQuery<Fruit> query = em.createQuery("from Fruit",Fruit.class);
    List<Fruit> fruits = query.getResultList();
    System.out.println("Fruit table has "+fruits.size()+" records");
  }
}
```

Let us now break down this code.

### EntityManagerFactory

**EntityManagerFactory** is an in-built JPA interface. It can be created via the **Persistence** class by specifying the name of the persistence unit from the **persistence.xml** file. The code above creates an **EntityManagerFactory** **emf** by referring to the **PERSISTENCE** persistence unit. An **EntityManagerFactory** is specific to a database. So, if you'd like to connect to a different database, you need to create a different **EntityManagerFactory** instance. An **EntityManagerFactory** can be used to created **EntityManager** instances.

### EntityManager

**EntityManager** is also an in-built JPA interface. It can be created via an **EntityManagerFactory** instance. The code above creates an **EntityManager** instance **em** via the **EntityManagerFactory** instance **emf**. An **EntityManager** represents a database connection. You can use it to perform database operations like insert/update/delete or to query a table. The code above invokes the **persist** method to save a **Fruit** record into the **Fruit** table.

### EntityTransaction

**EntityTransaction** is also an in-built JPA interface. It can be created via an **EntityManager**. The code above creates an **EntityTransaction** instance **et** via the **EntityManager** instance **em**. An **EntityTransaction** encapsulates a database transaction. A call to the **begin** method starts the transaction and a call to **commit** saves the changes in the database.

### Query

Query is also an in-built JPA interface. It can be created via an **EntityManager**. The code above creates a **TypedQuery** (which is a sub-interface of **Query**) instance **query** via the **EntityManager** instance **em**. You can use **Query** to execute a database query. The code above uses **query** to obtain all the **Fruit** records. The **Query** interface has methods that to retrieve the query execution results. The code above uses the **query.getResultList**. This returns a **List** of **Fruit** objects.

## Further Learning

- [Master JPA and Hibernate with Spring Boot](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fhibernate-jpa-tutorial-for-beginners-in-100-steps%2F) 
- [Spring Data JPA with Hibernate](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-data-jpa-using-hibernate%2F) 
- [Hibernate and JPA Fundamentals](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fhibernate-and-java-persistence-api-jpa-fundamentals%2F)

## Conclusion

So, in this class, we learnt about persistence unit and entities. We also took a look at the important JPA interfaces like EntityManagerFactory, EntityManager, EntityTransaction and Query.

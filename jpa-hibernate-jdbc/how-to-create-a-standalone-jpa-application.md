---
title: "How to create a standalone JPA application"
date: "2020-12-17"
categories: 
  - "hibernate"
coverImage: "database-scaled.jpg"
---

In this article, I will be explaining how to create a standalone JPA application. that saves data to a database table and queries a table. JPA stands for the Java Persistence API. In order to know more about JPA and how it works, you can refer to [this](introduction-to-jpa-the-why-what-and-how-of-jpa,md) article.

I will be using Hibernate as the JPA provider and MySQL database, however you can use any other JPA Provider/database.

## MySQL Installation

The first step would be to download and install MySQL. You can download MySQL from [here](https://dev.mysql.com/downloads/installer/) as per your operating system. Once the download is complete, you can follow the onscreen instructions to proceed with the installation. I recommend going with the developer default that installs MySQL, MySQLWorkbench and other utilities required for development.

## Creating Sample Database

Next, you need to create a database table. You can execute the following SQL code to create the sample database table called **Fruit**.

```java
create database jpademo;
use jpademo;
create table fruit ( id int auto_increment, name varchar(20), colour varchar(20), calories int , primary key (id) );
```

If you are using MySQL, then open MySQLWorkBench, open a new query tab and just copy and paste the SQL code given above.

## Writing Code

### Creating Eclipse Project

In this example, I will be using Eclipse and Maven. So you will need to create a new Maven project in Eclipse. You can refer [this](https://reshmabidikar.github.io/2018/10/how-to-create-a-maven-project-in-eclipse.html) post in order to understand how to create a Maven project in Eclipse. The advantage of using a dependency management tool like Maven is that it automatically downloads the necessary jar files for you, you just need to add the appropriate dependency in the Maven pom file.

### Adding Maven Dependencies

In order to create our JPA application, you need to add the following dependencies to the POM file (This includes the dependencies for the MySQL driver as well as Hibernate). I will also be using [JUNIT](../junit/how-to-use-junit-to-unit-test-code.md) to test the code, so the [JUNIT](../junit/how-to-use-junit-to-unit-test-code.md) dependency is also included:

```xml
 <dependencies>
<dependency>
<groupId>mysql</groupId>
<artifactId>mysql-connector-java</artifactId>
<version>8.0.12</version>
</dependency>
<dependency>
<groupId>org.hibernate</groupId>
<artifactId>hibernate-core</artifactId>
<version>5.3.4.Final</version>
</dependency>
 <dependency>
<groupId>junit</groupId>
<artifactId>junit</artifactId>
<version>4.13</version>
</dependency>
</dependencies>
```

### Creating Configuration File

JPA requires a configuration file with all the database connection information. So, you need to create a META-INF folder in your **src/main/resources** folder. In this you need to create **persistence.xml** as follows:

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

So, as you can see that the **persistence.xml** file includes information like the JPA provider, database URL, database username, database password among other details.

### Creating POJO class

Just to recap my [earlier](introduction-to-jpa-the-why-what-and-how-of-jpa.md) article, JPA requires a POJO class. Since we have created a **Fruit** table, we need to create a class corresponding to it as follows:

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

So, you can see that this is an ordinary Java class. It has fields corresponding to the columns in the database table. It also has some JPA specific annotations.

### Writing JPA Code

I will be writing the JPA code within a [JUNIT](junit/how-to-use-junit-to-unit-test-code.md) test case so that it is easy to test. First, you will need to create a new Test class within the **src/test/java** folder. Within this class, you can write the following code:

```java
public class JPATest {

  @Test
  public void testSave() {
    EntityManagerFactory emf = Persistence.createEntityManagerFactory("PERSISTENCE");
    EntityManager em = emf.createEntityManager();
    em.getTransaction().begin();
    Fruit apple = new Fruit();
    apple.setName("apple");
    apple.setColour("red");
    apple.setCalories(5);
    em.persist(apple);
    em.getTransaction().commit();
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

This JUNIT test case has two tests. The `testSave` simply creates a `Fruit` object, and invokes the `persist` method. This inserts a record into the **Fruit** table.

The `testQuery` method queries the **Fruit** table. Again, you do not need to write any elaborate SQL statements, just a simple JPQL statement.

You can run this test and verify the output.

You can download the complete source code for this application from my [Github repository](https://github.com/learnjavawithreshma/JPATest).

## Further Learning

- [Master JPA and Hibernate with Spring Boot](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fhibernate-jpa-tutorial-for-beginners-in-100-steps%2F) 
- [Spring Data JPA with Hibernate](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-data-jpa-using-hibernate%2F) 
- [Hibernate and JPA Fundamentals](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fhibernate-and-java-persistence-api-jpa-fundamentals%2F)

## Conclusion

So, in this article, we saw how to create a simple standalone JPA application from scratch. We also saw how you can use this to save data into a table and to query a table.

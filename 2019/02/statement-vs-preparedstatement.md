---
title: "Statement vs PreparedStatement"
date: "2019-02-21"
categories: 
  - "jdbc"
tags: 
  - "jdbc"
---

In JDBC programming, you might have come across the [Statement](https://docs.oracle.com/javase/7/docs/api/java/sql/Statement.html) and [PreparedStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html) interfaces. In this blog post, I will provide a comparison between the two.

You can use both[Statement](https://docs.oracle.com/javase/7/docs/api/java/sql/Statement.html) and [PreparedStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html)to execute a query on a database table via JDBC. However, there are several differences between the two.

#### Difference 1 - PreparedStatement is more efficient as compared to Statement

A Statement object directly executes the SQL statement. In contrast, a [PreparedStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html)is a pre-compiled SQL statement. It parses and compiles the underlying query only once. After that, the query can be executed with different parameters. So if you need to run a particular query several times but with different parameters, a [PreparedStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html) is more efficient.

Consider the following code snippet (**Code Listing 1**)

````

Class.forName("com.mysql.jdbc.Driver");

// Open a connection 
conn = DriverManager.getConnection("url", "username", "password");

//Execute a query Statement 
stmt = conn.createStatement(); 
String query = "select * from person where id="+id; 
ResultSet rs = stmt.executeQuery(query);
````

Each time the code is executed, the SQL statement will be parsed and compiled before the query is executed.

Now, consider the following code snippet: **(Code Listing 2)**

```` 
// Register JDBC driver 
Class.forName("com.mysql.jdbc.Driver");

// Open a connection 
conn = DriverManager.getConnection("url", "username", "password");

//Execute a query 
PreparedStatement stmt =conn.prepareStatement("select * from person where id=?");

stmt.setInt(1,5);

ResultSet rs = stmt.executeQuery();

````

In this case, when the [conn.prepareStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/Connection.html#prepareStatement\(java.lang.String\)) method is invoked, it will parse and compile the SQL statement. The PreparedStatement interface has several setter methods to set values for parameters. Here, the [stmt.setInt](https://docs.oracle.com/javase/7/docs/api/java/sql/Connection.html#prepareStatement\(java.lang.String\)) method is used. When the code invokes this method, it replaces the'?' at the position specified with the value specified. So, in this case it will replace the '?' at position 1 with the value 5. After that. when the code invokes the [stmt.executeQuery](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html#executeQuery\(\)) method, it will simple execute the query. So if you want to run the query for some other id values, you simple need to invoke the setter method to set that id value. So if you need to run the code several times for different values, this code is a lot more efficient since the query parsing and compilation happens only once.

#### Difference 2 - PreparedStatement prevents SQL injection attacks

SQL injection attack can occur when a user passes some malicious values to your code. Suppose that in the example in Code Listing 1, the id value is passed in from a UI by a user. In such scenarios, a user can pass in some malicious values.

In the Code Listing 1 above,if a user passes id as 5, the following query will be executed:

```
select * from person where id=5
```

This will only return the details of the person record with id 5. However, if a user passes id as 1 or 1=1 then the following query will be executed:

```
select * from person where id=1 or 1=1
```

This will return the details about all the person records in the database.

In contrast, using a [PreparedStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html) prevents SQL injection attacks. So even if a value like 1 or 1=1 is passed, the [PreparedStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html)automatically bypasses the special characters. So an SQL injection attack will not occur.

#### Summary

In addition to the above, there are several other differences between a [Statement](https://docs.oracle.com/javase/7/docs/api/java/sql/Statement.html) and [PreparedStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html). The following table summarizes the differences


|Statement  |PreparedStatement  |
|--|--|
| Parses and compiles the SQL query each time | Parses and compiles the SQL query only once, so is more efficient |
| Prone to SQL injection attacks | Escapes all special characters, so SQL injection attacks cannot occur |
| Parameters are concatenated in the query itself, so error prone and messy |Parameter values are set separately, so less error prone  |
|Difficult to set datatypes other than int and String  | Easy to set other datatypes like Date, Clob setter as setter methods are provided |

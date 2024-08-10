---
title: "Statement vs PreparedStatement"
date: "2019-02-21"
categories: 
  - "jdbc"
tags: 
  - "jdbc"
---

In JDBC programming, you might have come across the [Statement](https://docs.oracle.com/javase/7/docs/api/java/sql/Statement.html) and [PreparedStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html) interfaces. In this blog post, I will provide a comparison between the two.

You can use both [Statement](https://docs.oracle.com/javase/7/docs/api/java/sql/Statement.html) and [PreparedStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html) to execute a query on a database table via JDBC. However, there are several differences between the two.

#### Difference 1  - PreparedStatement is more efficient as compared to Statement

A Statement object directly executes the SQL statement. In contrast, a [PreparedStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html) is a pre-compiled SQL statement. It parses and compiles the underlying query only once. After that, the query can be executed with different parameters. So if you need to run a particular query several times but with different parameters, a [PreparedStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html) is more efficient.

Consider the following code snippet (**Code Listing 1**)

 

\[java\]

Class.forName(&quot;com.mysql.jdbc.Driver&quot;);

// Open a connection conn = DriverManager.getConnection(&quot;url&quot;, &quot;username&quot;, &quot;password&quot;);

//Execute a query Statement stmt = conn.createStatement(); String query = &quot;select \* from person where id=&quot;+id; ResultSet rs = stmt.executeQuery(query);

\[/java\]

 

Each time the code is executed, the SQL statement will be parsed and compiled before the query is executed.

Now, consider the following code snippet: **(Code Listing 2)**

\[java\] // Register JDBC driver Class.forName(&quot;com.mysql.jdbc.Driver&quot;);

// Open a connection conn = DriverManager.getConnection(&quot;jdbc:mysql://localhost/PersonDB&quot;, &quot;root&quot;, &quot;learnjava&quot;);

//Execute a query PreparedStatement stmt =conn.prepareStatement(&quot;select \* from person where id=?&quot;);

stmt.setInt(1,5);

ResultSet rs = stmt.executeQuery();

\[/java\]

In this case, when the [conn.prepareStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/Connection.html#prepareStatement\(java.lang.String\)) method is invoked, it will parse and compile the SQL statement. The PreparedStatement interface has several setter methods to set values for parameters. Here, the [stmt.setInt](https://docs.oracle.com/javase/7/docs/api/java/sql/Connection.html#prepareStatement\(java.lang.String\)) method is used. When the code invokes this method, it replaces the'?' at the position specified with the value specified. So, in this case it will replace the '?' at position 1 with the value 5.  After that. when the code invokes the [stmt.executeQuery](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html#executeQuery\(\)) method, it will simple execute the query. So if you want to run the query for some other id values, you simple need to invoke the setter method to set that id value. So if you need to run the code several times for different values, this code is a lot more efficient since the query parsing and compilation happens only once.

#### Difference 2 - PreparedStatement prevents SQL injection attacks

SQL injection attack can occur when a user passes some malicious values to your code. Suppose that in the example in Code Listing 1, the id value is passed in from a UI by a user. In such scenarios, a user can pass in some malicious values.

In the Code Listing 1 above, if a user passes id as 5, the following query will be executed:

```
select * from person where id=5
```

This will only return the details of the person record with id 5. However, if a user passes id as 1 or 1=1 then the following query will be executed:

```
select * from person where id=1 or 1=1
```

This will return the details about all the person records in the database.

In contrast, using a [PreparedStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html) prevents SQL injection attacks.  So even if a value like  1 or 1=1 is passed, the [PreparedStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html) automatically bypasses the special characters. So an SQL injection attack will not occur.

 

#### Summary

In addition to the above, there are several other differences between a [Statement](https://docs.oracle.com/javase/7/docs/api/java/sql/Statement.html) and [PreparedStatement](https://docs.oracle.com/javase/7/docs/api/java/sql/PreparedStatement.html) . The following table summarizes the differences

\[table id=10 /\]

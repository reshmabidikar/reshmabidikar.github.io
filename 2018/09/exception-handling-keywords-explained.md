---
title: "Exception handling keywords explained"
date: "2018-09-02"
categories: 
  - "exception-handling"
  - "java_language_features"
tags: 
  - "core-java"
  - "java-exception-handling"
---

I know many of you are confused between the difference between throw and throws or would like to know when a finally statement should be used or have some other questions related to Java's exception handling mechanism. So, in this blog post, I'm going to try and explain each keyword used in Java's exception handling mechanism.

#### Try

The **try** keyword is used to specify the code that you want to monitor for exceptions. Code should be enclosed within curly brackets i.e. {} after the **try** keyword. It is known as the try block.

#### Catch

Immediately following the try block, you need to specify a **catch** clause . The **catch** block is the exception handler code i.e. code that can process the exception. In the **catch** block, you need to specify the exception type that you wish to catch and the code that you want to be executed when an error occurs.

#### Finally

When an exception is thrown, the normal flow of execution is altered and so some code may be skipped. However, sometimes there is some code that we want to be executed under any circumstances, even if an exception occurs. Such code can be placed in the finally clause. So the code within the finally clause is always executed, irrespective of whether an exception occurs or not.

For example, suppose we are writing some database access code. In such code you normally open a connection to the database, query the database and then close the connection. However, if some exception occurs while querying the database, the code to close the connection may not be executed. Leaving a connection open is not recommended as a connection is an expensive resource, so, it must always be closed after it is used. So placing the code to close the database connection in the finally clause will ensure that it is executed even if an exception occurs.

#### Throw

The **throw** keyword is used to explicitly throw an exception. Most of the times, it is used to throw a custom exception i.e. exception created by your code. However, it can also be used to throw a built in exception. It basically specifies that you do not want to handle the error condition at the time that it occurs but want to delegate the exception handling to some other part of your code. If the exception being thrown via the **throw** keyword is a checked exception, it needs to be specified in the method's declaration via the throws clause.

#### Throws

The throws clause is used in a method's declaration and specifies the exceptions that a method might throw. The throws method needs to be specified only for checked exceptions. So if a method throws a checked exception that it does not handle, then the checked exception needs to be specified in the method's declaration via the **throws** keyword.

---
title: "Java Exception handling explained"
date: "2018-08-26"
categories: 
  - "java-interview-questions"
  - "java_language_features"
tags: 
  - "core-java"
  - "java-exception-handling"
---

In this blog post, I will explain how Java's exception handling works.

#### **What are the types of errors in Java?**

You many have encountered compilation errors several times in your code. Compilation errors are errors that are detected when the code is compiled and even before the code is executed. However, some errors are detected and can occur only when the code is run. Such errors are broadly classified into Exceptions. Java provides a built in class called Exception to handle error conditions. There are also various sub classes of this exception class that handle some specific errors.

#### What is an exception?

Whenever an error occurs while executing a statement, Java creates an object of the Exception class. The normal flow of the program then halts. The exception object contains a lot of debugging information such as method hierarchy, line number where the exception occurred, type of exception etc.

#### **How do Java exceptions work?**

When the exception occurs in a method, the process of creating the exception object and handing it over to runtime environment is called **“throwing the exception”**. The runtime environment tries to find some code that can process the exception once it receives the exception object, Such code is also referred to as exception handler code. Java first tries to look for the EH code in the method where the error occurred. If no appropriate handler found, then it looks in the method that invoked this method and so on. The handler is said to be **“catching the exception”**. If there is no appropriate exception handler found in the code then the exception is caught by the default handler provided by the Java run-time system. The default handler ultimately processes any exception that is not caught by your program.The default handler displays a string describing the exception, prints a stack trace from the point at which the exception occurred, and terminates the program.

#### What are try and catch?

Code that you want to monitor for exceptions should be included in a try block . Immediately following the try block, you need to specify a catch clause . The catch block is the exception handler code. In the catch block, you need to specify the exception type that you wish to catch. Here you can write the code that needs to be executed when an error occurs.

#### Code Snippet:

````java

try {

    int result = 10 / 0;
    System.out.println("Result is " + result);

    } catch (ArithmeticException ae) {
        System.out.println(" An arithmetic exception has occured:"+ae.getMessage());
    }

````

#### Explanation

In the above code, a number is divided by 0. This causes the Java runtime system to throw an ArithmeticException which is a subclass of the Exception class. So the line of code that prints the result will be skipped. Java begins to look for some catch block that can handle the exception. It finds the catch block that catches the Arithmetic exception and so this code within the catch block is executed.

If you run this code, you will see the following output:

```
 An arithmetic exception has occured:/ by zero
```

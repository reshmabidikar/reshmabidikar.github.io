---
title: "Spring @ExceptionHandler annotation explained"
date: "2019-08-22"
categories: 
  - "spring"
tags: 
  - "exceptionhandler"
  - "responsestatus"
  - "spring"
---

In this article, I will be explaining the Spring @ExceptionHandler annotation and how it can be used for [exception handling in Spring](https://learnjava.co.in/spring-exception-handling/).

## Introduction

You can specify the @ExceptionHandler annotation on a method in a controller class and mark the method as an exception handling method. Along with the annotation you need to specify the exceptions that the method handles. So when an exception of the specified type occurs, Spring uses the exception handler method to handle the exception.  Within the exception handler method, you can specify any exception handling code like returning an error code or redirecting to an error page, etc.

\[table id=27 /\]

The following code sample demonstrates this:

```
@RestController
public class PersonController {
  
  @GetMapping(value = "/person/{personId}", produces = { "text/plain" })
  public Person getPersonWithId(@PathVariable Integer personId) {
    // Returns hardcoded data, a real world application would return from
    // the database
    return new Person(3, "Peppa Pig", 15);
  }
  
    @ExceptionHandler(IllegalArgumentException.class)
    @ResponseStatus(HttpStatus.BAD_REQUEST)
    public void onIllegaArgumentException(IllegalArgumentException npe){
    System.out.println("In onNullPointerException exception handler ");
      
    }

}

```

Here, this code has a Controller class, PersonController. It has a method onIllegaArgumentException. This has the @ExceptionHandler annotation with the IllegalArgumentException.class. So whenever an IllegalArgumentException exception is thrown by the controller, Spring invokes this method. This method simply has a Sysout statement, but you can place any error handling code here.

## Exception handling method arguments and return types

An Exception handling method can have any type of arguments. So it can accept one or more exception objects of the type of exceptions that it can handle. It can also have the request or response object as an argument. The return type of an exception handling method can also be of any data type. It can also be a Model or ModelAndView object. If the method returns void, it means that the exception handling method directly writes to the response stream.

## ResponseStatus Annotation

You can specify the @ResponseStatus annotation on an exception handling method. Within this annotation, you can specify the status code that you want to send to the client application whenever the particular exception occurs. In the code sample above,  the @ResponseStatus annotation is specified as follows:

`@ResponseStatus(HttpStatus.BAD_REQUEST)`

So when an exception occurs, the Http Status code corresponding to Bad Request i.e. 400 will be sent to the client application.

## Limitations of @ExceptionHander annotation

The @ExceptionHandler annotation can be applied to a method in a controller class and handles only exceptions that occur in the controller class where it is specified. The downside to this is that you will need separate exception handler methods in every controller and this may result in code duplication.  In order to avoid this, Spring provides an alternate approach where you can designate a class with the @ControllerAdvice annotation. Within this class, you can have methods that handle individual exceptions with the @ExceptionHandler annotation. So exceptions thrown from anywhere in your application will be handled by the methods in this class.

## Further Learning

[Spring MasterClass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-spring-framework-masterclass%2F) [Spring Tutorial For Beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-tutorial-for-beginners%2F) [Step by Step Spring MVC Tutorial](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-mvc-tutorial-for-beginners-step-by-step%2F) [Spring Framework in Easy Steps](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspringframeworkineasysteps%2F)

## Conclusion

So in this article, you saw how you can use the Spring @ExceptionHandler annotation for exception handling. You also saw how Spring @ExceptionHander and @ResponseStatus work together to send an error code to the client application. You also saw what are the limitations of @ExceptionHander and how you can overcome these via @ControllerAdvice

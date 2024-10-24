---
title: "Spring Exception Handling With Examples"
date: "2019-10-01"
categories: 
  - "spring"
---

Spring In this article, I will be covering the various exception handling mechanisms in [Spring](https://learnjava.co.in/spring-framework-what-and-why/).

## Using an ExceptionHandler

The first approach is the [ExceptionHandler](https://learnjava.co.in/spring-exceptionhandler-annotation-explained/) approach. In this approach, you can designate a method in your controller with the @ExceptionHandler annotation. You can specify some exceptions with this annotation. When those exceptions occur, the code in the method will be executed.

The following code demonstrates this:

```
@Controller
public class PersonController {

//controller methods

@ExceptionHandler(RuntimeException.class)
public void onRunTimeException(RuntimeException e){
//exception handling code for RuntimeException
}
}
```

Here, the code specifies the @ExceptionHandler annotation on the onRuntimeException class. So this method is designated as an exception handling method. Whenever a RuntimeException occurs within any method in the PersonController, the code invokes this method.

You can specify any type and any number of arguments to a method that has the @ExceptionHandler annotation. In the above example,  only one argument which is an object of RuntimeException is specified. You may also specify the Request/Response/Model/ModelAndView objects as arguments. The method can also return data of any type. If it returns a void, it means that the exception handling method directly writes to the response stream.

The @ExceptionHandler annotation can be applied to a method in a controller class and handles only exceptions that occur in the controller class where it is specified.

The downside to this approach is that you need to have such an exception handling method in every controller in your code. So this may result in duplicate code.

## Using ControllerAdvice annotation

The second option for exception handling within Spring is to have a separate class with exception handling methods. Such a class needs to have the @ControllerAdvice annotation specified. The advantage of this approach is that exceptions thrown by any part of the code can be handled by this class. So this class acts like a global exception handler.

The following code demonstrates this:

```
@ControllerAdvice
public class CustomExceptonHandler {

@ExceptionHandler(NullPointerException.class)
@ResponseStatus(HttpStatus.INTERNAL_SERVER_ERROR)
public void onNullPointerException(NullPointerException npe){
// NullPointerException code
}

@ExceptionHandler(IllegalArgumentException.class)
@ResponseStatus(HttpStatus.BAD_REQUEST)
public void onIllegaArgumentException(IllegalArgumentException npe){
//IllegalArgumentException code here
}

}
```

Here, the CustomExceptionHandler class has the @ControllerAdvice annotation. It has two exception handling methods, onNullPointerException and onIllegaArgumentException. Each method has the @ExceptionHandler annotation and the @ResponseStatus annotation. The @ExceptionHandler annotation specifies the exception that the method handles. The @ResponseStatus annotation specifies the HTTP response code that Spring should send to the client application when the particular exception occurs. So in the above code, when a NullPointerException occurs anywhere in the code, the Response code corresponding to Internal Server error will be sent to the client application.

## Using ResponseStatusException

The third approach for Exception handling in Spring is using the ResponseStatusException. ResponseStatusException is a class that represents an exception. It is an alternative to use the @ResponseStatus annotation. Whenever an exception occurs in your code, you can create a ResponseStatusException with the appropriate HTTP error code and throw this exception. The following code demonstrates this:

```
@GetMapping(value = "/person")

public Person loadPerson() {
try {
//code here
} catch (Exception e) {
throw new ResponseStatusException(HttpStatus.INTERNAL_SERVER_ERROR, "Exception occured");

}
}
```

In the above code, if an Exception occurs in the loadPerson method, it throws a ResponseStatusException with response code corresponding to Internal Server Error.

The advantage of using ResponseStatusException is that the exception class is not tied down to any particular status code, so you can use different status codes for the same exception, depending on the context in which the exception occurs. This is much better than the ExceptionHandler approach where the exception handling method can only handle the listed exceptions and also use only a single status code which is specified in the ResponseStatus annotation. Secondly, you do not need to create any custom exception classes, you can use this class as required with appropriate status codes.

The ResponseStatusException is a base exception. It has several sub-classes which you can use to handle different types of exceptions. So for example, the MediaTypeNotSupportedException is a sub-class of the ResponseStatusException. It corresponds to the HTTP status code 415.

## Further Learning

[Spring MasterClass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-spring-framework-masterclass%2F) [Spring Tutorial For Beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-tutorial-for-beginners%2F) [Step by Step Spring MVC Tutorial](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-mvc-tutorial-for-beginners-step-by-step%2F) [Spring Framework in Easy Steps](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspringframeworkineasysteps%2F)

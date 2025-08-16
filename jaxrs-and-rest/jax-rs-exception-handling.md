---
title: "JAX-RS Exception Handling explained with code samples"
date: "2019-12-03"
categories: 
  - "rest"
tags: 
  - "exception-handling"
  - "jax-rs"
  - "rest"
---

There are several ways to perform exception handling in a JAX-RS application. In this article, I will be explaining some of the JAX-RS exception handling mechanisms.

## Using an ExceptionMapper

One way to perform exception handling in a JAX-RS application is using a custom exception mapper. The following code demonstrates a custom exception mapper:

```java
@Provider

public class MyExceptionMapper implements ExceptionMapper<MyException>{


@Override

public Response toResponse(MyException ex) {

return Response.status(Response.Status.INTERNAL_SERVER_ERROR).build();

}
}
```
This is an Exception Mapper for a custom exception called MyException. It has the @Provider annotation. The MyExceptionMapper class implements the ExceptionMapper interface and overrides the toResponse method. In this method, you can place the correct HTTP status code. In this case, the code uses the HTTP status code for Internal Server Error i.e. code 500. So this code will be sent to the client when MyException occurs.

## Throwing a WebApplicationException

Another way to handle exceptions using JAX-RS is to throw a WebApplicationException. javax.ws.rs.WebApplicationException is an in-built checked exception provided by JAX-RS. Since this is an in-built exception, the application code does not need to provide an exception mapper. WebApplicationException includes a status code and Response object. The application code needs to initialize the WebApplicationException with an appropriate status code or Response object. Once the code throws the exception, JAX-RS catches the exception and uses the Response object and status code within the exception to send an appropriate HTTP response to the client. If there is no status code or Response object within the WebApplicationException, JAX-RS sends a status code of 500 which means "Internal Server Error" to the client.

## Further Learning

- [Master Java Web Services (JAX-RS)](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Frest-api-using-java%2F)
- [Develop RESTful Java web services using JAX-RS and Jersey](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fdevelop-restful-java-web-services-using-jax-rs-and-jersey%2F)

## Conclusion

So, in this article, we saw the different JAX-RS exception handling mechanisms.

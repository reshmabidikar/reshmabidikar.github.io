---
title: "Important JAX-RS annotations explained"
date: "2019-09-23"
categories: 
  - "rest"
tags: 
  - "get"
  - "post"
  - "jax-rs"
  - "rest"
---

In this article, I will be explaining some important annotations in JAX-RS

# What is JAX-RS

JAX-RS is a Java API that you can use for building a REST service. JAX-RS stands for Java API for RESTful Web Services (JAX-RS). It is part of the Java EE since Java 6. The latest version of JAX-RS is JAX-RS 2.0 and is part of Java EE 7. JAX-RS is just an API; it has some annotations that you can use to build a REST application.  JAX-RS does not include an implementation. Jersey framework is the reference implementation of JAX-RS specification and implements JAX-RS 2.0. There are other implementations of JAX-RS like RESTEasy, etc.

# Important JAX-RS annotations

## @Get/@Post/@Put/@Delete/@Head

You need to specify these annotations on a JAX-RS method. These annotations indicate the HTTP method that the JAX-RS method maps to. So when a client request comes in, JAX-RS matches the HTTP method in the client request to the method that has the appropriate annotation. If there is no annotation on a method, JAX-RS assumes that it can cater to all HTTP methods.

## @Path

You can use the @Path annotation on any class or method in your code. It identifies the URI to which the class or method maps to. So you need to specify a URI with this annotation. If you specify the annotation at the class level, JAX-RS maps all the methods in the class to the same URI. If you specify the annotation at the method level, the method level annotation overrides the class-level annotation. You need to specify a relative URI with the Path annotation.  You can also specify an expression with the Path annotation which will be matched to the incoming URL.

## @Produces and @Consumes

You can specify the @Produces annotation on a JAX-RS service class or method. It defines the media type that a JAX-RS class or method is capable of producing. Similarly, you can use the @Consumes annotation to define the MIME type of the data that a JAX-RS service can accept. So it is basically used to narrow down the method that matches a client request. So when a client request comes in, JAX-RS compares the headers in the request to the metadata in these annotations. JAX-RS invokes the corresponding method only if there is a match. If you specify the annotations at the class level, the MIME type in the annotation is applicable to all the methods in the class. If you specify the annotations at the method level, the method level annotations override the class level annotations. Some of the MIME types that which you can specify with these annotations are text/plain, application/xml, application/json, etc.

 

## Variable Extraction Annotations

There are several annotations supported by JAX-RS which you can use to inject values into a JAX-RS method. These are as explained below:

### @PathParam

The @PathParam annotation can be used to specify parameters that are specified as part of the URI. So when @PathParam is used, the client application needs to send the parameters as part of the URI. Example is /url/param1/param2.

### @QueryParam

This annotation can be used to specify query parameters. So when this annotation is used, the client application needs to send parameters as query parameters in the URL. A Query parameter is of the form name=value and must be specified after a “?” symbol at the end of the URL.  Example is url?param1=value1&&param2=value2.

### @HeaderParam

Sometimes, your application may need to find out header information in the incoming request. In such cases, the @HeaderParam annotation is useful. For example, the Accept-Language header specifies the language in which content is acceptable to a client application. Suppose, your REST service needs to find the value of this header in order to send appropriate data to the client.

### @FormParam

This annotation is used to accept values which are specified in forms.

### @CookieParam

The @javax.ws.rs.CookieParam annotation allows you to inject cookies sent by a client request into your JAX-RS resource methods.

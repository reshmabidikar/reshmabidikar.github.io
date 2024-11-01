---
title: "Important Spring MVC Annotations Explained"
date: "2019-07-27"
categories: 
  - "spring"
tags: 
  - "spring"
  - "spring-mvc-annotations"
---

In this blog post, I will be explaining some of the important Spring MVC Annotations used in Spring applications.

## Controller

You can use the Controller annotation to designate a Controller class in an MVC application. Normally in such scenarios, the code maps each method in the controller to a URL specified via the RequestMapping annotation. When the UI requests a particular URL, the code invokes the appropriate method. This executes the business logic and then redirects the user to the appropriate JSP page.

## RestController

Spring 4.0 introduced the RestController annotation. So the RestController annotation is a specialization of the Controller annotation that can be used to designate a REST service. It combines the behavior of the  Controller and ResponseBody annotations. So when a method in a class is designated with this annotation, it returns the REST response directly to the client instead of redirecting the user to an HTML or JSP page

## ResponseBody

The ResponseBody annotation converts the Java object returned by a controller method into the appropriate type (XML or JSON). It uses the Content-Type specified in the HTTP request header and writes it to the Response stream. So basically, if your method returns an object, this object is converted into JSON or XML format and written to the output stream directly. It can be specified at the class level as well as the method level. It needs to be specified only if you are creating a REST service with the @Controller annotation. If you use the @RestController annotation, then the @ResponseBody annotation can be skipped since the @RestController annotation is a convenience controller which combines the behavior of the Controller and ResponseBody annotations.

## RequestBody

You should use the RequestBody annotation when the client application sends object data type as part of the HTTP request. So when you specify this annotation, Spring automatically converts the object in the request (which would be in XML or JSON format) to a Java object.

## RequestMapping

You can use the RequestMapping annotation to map a method in a Controller class to an appropriate HTTP method. It also specifies the URL that the method maps to. It can be specified at the class as well as method level. If specified at the class level, all methods in the class, map to the same URL specified with this annotation. If the annotation is specified at the method level, the method level annotation overrides the class-level annotation. To know more about the RequestMapping annotation, refer to [this](https://learnjava.co.in/spring-requestmapping-getmapping-and-postmapping-annotations/#RequestMapping) blog post.

## GetMapping

The GetMapping is a specialization of the RequestMapping annotation that can be used to map to Get requests only. Just like the GetMapping, the PostMapping, the PutMapping and DeleteMapping are shortcut annotations corresponding to the HTTP POST, PUT and HTTP DELETE methods respectively. To know more about the GetMapping annotation, refer to [this](https://learnjava.co.in/spring-requestmapping-getmapping-and-postmapping-annotations/#GetMapping) blog post.

## PathVariable

You can use the PathVariable annotation to extract request parameters that are part of the URI. So if request parameters as specified as part of the URI, they need to have the @PathVariable annotation in the method declaration

## RequestParam

You can use the @RequestParam annotation to extract request parameters that are sent as query parameters. Query parameters are parameters specified using a "?" symbol after the main URL and are of the format parametername=parametervalue. So if such parameters are present in the client request, then the RequestParam annotation should be used in the method declaration.

## Further Learning

[Spring MasterClass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-spring-framework-masterclass%2F) [Spring Tutorial For Beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-tutorial-for-beginners%2F) [Step by Step Spring MVC Tutorial](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-mvc-tutorial-for-beginners-step-by-step%2F) [Spring Framework in Easy Steps](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspringframeworkineasysteps%2F)

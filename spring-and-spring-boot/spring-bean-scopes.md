---
title: "Spring Bean Scopes Explained With Code Samples"
date: "2020-07-01"
categories: 
  - "spring"
---

The Spring Framework![icon](https://ad.linksynergy.com/fs-bin/show?id=MnzIZAZNE5Y&bids=507388.1&type=10) allows defining scopes for a Spring Bean. Spring Bean scopes define the lifetime of a Spring bean. In this article, we will take a look at bean scopes.

## What is Spring Bean Scope?

A Spring Bean scope specifies the lifetime of a Spring bean. So it specifies when the bean will be created and how long it will exist in the system.

## What are the different bean scopes?

Spring supports the following bean scopes:


### Singleton

This is the **default** bean scope. As per this scope, only one instance of a bean is created. Each time the bean is requested, the same instance is returned.

### Prototype

As per this scope, a new instance of a bean is created each time the bean is requested.

### Request

This bean scope is valid only for a web application. As per this bean scope, a new instance of the bean is created for each HTTP request. The bean stays alive until the HTTP request completes. If you use this bean scope for a standalone application, your code will result in an error

### Session

This bean scope is also valid only for a web application. As per this bean scope, a new instance of the bean is created for each HTTP session. The bean stays alive as long as the session is alive. If you use this bean scope for a standalone application, your code will result in an error

### Global Session

This bean scope is only valid for a portlet application. As per this bean scope, a new instance of the bean is created for each HTTP global session. It is similar to session scope used in a servlet based application.

## How to define bean scopes?

Spring supports a **@Scope** annotation. You can use it to specify a Spring bean scope. As mentioned earlier, the default scope is **singleton**. However, if you want to specify the **prototype** scope for a bean, you can do it as follows:

```java
@Service
@Scope("prototype")
public class MessageService {
  //code here
}
```

So this code defines a **MessageService** bean with **prototype** scope.

## Further Learning

* [Spring MasterClass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-spring-framework-masterclass%2F) 
* [Spring Tutorial For Beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-tutorial-for-beginners%2F) 
* [Step by Step Spring MVC Tutorial](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-mvc-tutorial-for-beginners-step-by-step%2F) 
* [Spring Framework in Easy Steps](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspringframeworkineasysteps%2F)

## Conclusion

So, this article demonstrates the various Spring bean scopes like **singleton**, **prototype**, **request**, **session** and **globalsession**. It also demonstrates how you can define a bean scope.

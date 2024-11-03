---
title: "Controller Vs RestController annotation in Spring"
date: "2019-06-12"
categories: 
  - "rest"
  - "spring"
---

In this blog post, I will be explaining the Controller and RestController Spring annotations and also their differences.

## MVC V/s REST

Before diving into the Controller and RestController annotations, it is important to understand the difference between a normal MVC web application and a REST application. An MVC Web application returns HTML which is rendered in a browser and displayed to end users. A REST application, on the other hand, returns an XML or JSON response.

## Controller Annotation

You can use the [Controller](https://learnjava.co.in/important-spring-mvc-annotations/#Controller) annotation to designate a Controller class in an MVC application. Normally in such scenarios, the code maps each method in the controller to a URL specified via the `RequestMapping`annotation. When the UI requests a particular URL, the code invokes the appropriate method. This executes the business logic and then redirects the user to the appropriate JSP page.

Consider the following code:

```
@Controller
public class HelloWorldController {

  @RequestMapping("/hello")
  public ModelAndView helloWorld() {
 
    System.out.println("In HelloWorldController");
    String message = "<h1>Hello World</h1>";
    return new ModelAndView("hello", "message", message);
  }
}
```

This specifies that the class `HelloWorldController`is a Controller class. The code executes the method `helloWorld`

when the UI requests the URL _**/hello**_. It returns a `ModelAndView` object which specifies that the jsp with name "hello" should be displayed to the UI with the message specified.

## Using Controller for REST service

You can also use the Controller annotation to create a REST service. As you probably know, a REST service returns am XML or JSON response, it does not return HTML. So when you use the Controller annotation for a REST service, you need to also specify the `ResponseBody`annotation. This directly writes the values returned by the method to the Response stream.

Consider the following code snippet:

```
@Controller
@ResponseBody
public class HelloWorldController {

  @GetMapping("/hello")
  public String sayHello() {
    return "Hello World";
  }
}
```

The `ResponseBody`annotation is specified along with the `Controller`annotation. In this case, too, the code maps the URL **_/hello_** to the `sayHello`method. However, this method no longer returns a `ModelAndView`object and does not redirect the user to a JSP page. Instead, this method directly returns a String value. The `ResponseBody`annotation converts the Java object returned by the method into the appropriate type (XML or JSON) based on the Content-Type specified in the HTTP request header and writes it to the Response stream.

Instead of using the `ResponseBody`annotation on the Controller class, you can also use it along with each method in the Controller too.

## RESTController annotation

As seen above, you can use the `Controller`and `ResponseBody` annotations to create a REST service. Instead of using two annotations, Spring 4.0 introduced the [RestController](https://learnjava.co.in/important-spring-mvc-annotations/#RestController) annotation. So the `RestController`annotation is a convenience controller which combines the behavior of the `Controller`and `ResponseBody`annotations.

So the above code can be re-written as follows:

```
@RestController
public class HelloWorldController {

  @GetMapping("/hello")
  public String sayHello() {
    return "Hello World";
  }
  
}
```

This specifies that the class `HelloWorldController`is a Rest Controller. The code behaves exactly the way it would have if a `Controller`and `ResponseBody`annotation was used. So the String value returned by the method is converted into the appropriate type (XML or JSON) and written to the Response stream.

## Differences


| Controller |RestController  |
|--|--|
| Normally used for an MVC controller, ut can be used for a REST service in conjunction with the ResponseBody annotation |Used for a RestController i.e. a Controller for a REST service  |
| Methods in a Controller return a ModelAndView |Methods in a RestController directly return Java Objects which are written to the Response stream  |
| Methods in a controller look for a view to display HTML to the UI | Methods in a RestController directly write the Java objects into the Response stream which is converted to JSON or XML format |
| Present in Spring right from the start | Added in Spring 4.0 |

## Further Learning

[Spring MasterClass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-spring-framework-masterclass%2F) [Spring Tutorial For Beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-tutorial-for-beginners%2F) [Step by Step Spring MVC Tutorial](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-mvc-tutorial-for-beginners-step-by-step%2F) [Spring Framework in Easy Steps](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspringframeworkineasysteps%2F)

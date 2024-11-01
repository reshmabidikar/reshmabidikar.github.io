---
title: "Spring RequestMapping, GetMappin, PostMapping annotations"
date: "2019-07-07"
categories: 
  - "spring"
tags: 
  - "getmapping"
  - "postmapping"
  - "requestmapping"
  - "spring"
---

In this blog post, I will be explaining the RequestMapping, GetMapping and PostMapping annotations in Spring. In order to know more about other Spring annotations, you can refer to [this](https://learnjava.co.in/important-spring-mvc-annotations/) article. In order to learn about the Spring framework from scratch, I recommend that you enroll in this [Spring masterclass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-tutorial-for-beginners%2F).

You can use the RequestMapping, GetMapping and PostMapping annotations to map a URL to a particular Controller method. However, there are some differences between them. Let's check them out.

## RequestMapping

The RequestMapping annotation can be used to map both GET and POST requests. Consider the following code:

```
@RequestMapping(value="/person/{personId}",method=RequestMethod.GET)
  public Person getPersonWithId(@PathVariable Integer personId){
  
  }
```

Here, the RequestMapping annotation is used on the getPersonWithId method. It maps to the `/person/{personId}`

URL. The method attribute is also specified. This indicates that this method maps to an HTTP GET request.

Now consider the following code:

```
@RequestMapping(value="/person/newperson",method=RequestMethod.POST)
public void addPerson(@RequestBody Person person){
 
  
}
```

Here, the RequestMapping annotation is used on the addPerson method. It maps to the `/person/newperson`

URL. The method attribute is also specified. This indicates that this method maps to an HTTP POST request.

So basically, you can use the RequestMapping annotation for specifying both HTTP GET and HTTP POST requests.

## GetMapping

The GetMapping is a specialization of the RequestMapping annotation that can be used to map to Get requests only. So the above code can be re-written as follows:

```
@GetMapping("/person/{personId}")
public Person getPersonWithId(@PathVariable Integer personId){ 
}
```

So here, this code uses the GetMapping annotation instead of the RequestMapping annotation. The method attribute is not specified since the GetMapping always maps to an HTTP Get method

## PostMapping

The PostMapping is a specialization of the RequestMapping annotation that can be used to map to POST requests only. So the above code can be re-written as follows:

```
@PostMapping("/person/newperson") 
public void addPerson(@RequestBody Person person){ 
}
```

So here, this code uses the PostMapping annotation instead of the RequestMapping annotation. The method attribute is not specified since the PostMapping always maps to an HTTP POST method

## Other Shortcut annotations

Just like the GetMapping and PostMapping, the PutMapping and DeleteMapping are shortcut annotations corresponding to the HTTP Put and HTTP Delete method respectively.

## Further Learning

[Spring MasterClass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-spring-framework-masterclass%2F) [Spring Tutorial For Beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-tutorial-for-beginners%2F) [Step by Step Spring MVC Tutorial](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-mvc-tutorial-for-beginners-step-by-step%2F) [Spring Framework in Easy Steps](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspringframeworkineasysteps%2F)

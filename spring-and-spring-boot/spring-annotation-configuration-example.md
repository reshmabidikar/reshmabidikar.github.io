---
title: "Spring Annotation-Based Configuration Example"
date: "2020-05-05"
categories: 
  - "spring"
---

In this article, I will be demonstrating how to configure a **standalone Spring application using annotation-based configuration**. I will be using [**Eclipse and Maven**.](https://reshmabidikar.github.io/2019/06/how-to-create-a-maven-web-project-in-eclipse.html) In order to get a basic introduction to [Spring](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspringframeworkineasysteps%2F), you can check out [this](spring-framework-what-and-why.md) article. In order to understand how to configure a standalone Spring application using XML configuration, you can refer to [this](https://learnjava.co.in/spring-xml-configuration-example/) article. In order to understand how to configure a standalone Spring application using Java configuration, you can refer to [this](https://learnjava.co.in/spring-java-configuration-example/) article.

# Project Set-up

Step 1 - Create a new Maven Project in Eclipse. You can refer to [this](https://learnjava.co.in/how-to-create-a-maven-project-in-eclipse/) article on how to create a Maven project in Eclipse.

Step 2 - Add Spring dependencies to the maven pom file. You can add the following:

```xml
<dependencies>
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-core</artifactId>
      <version>5.2.2.RELEASE</version>
    </dependency>
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-context</artifactId>
      <version>5.2.2.RELEASE</version>
    </dependency>
  </dependencies>
```

# Creating Beans

Create the following bean classes:

**MessageDAO:**

```java
@Repository
public class MessageDAO {
  
  public String getMessage() {
    return "Hello World";
  }

}
```

MessageDAO is a simple class that has only one method `getMessage()`This returns a String value. It has the `@Repository`annotation. This extends from the `org.springframework.stereotype.Component`annotation. So it indicates that MessageDAO is a Spring component.

**MessageService:**

```java
@Service
public class MessageService {
  
  private MessageDAO messageDAO;

  public void printMessage() {
    String message = messageDAO.getMessage();
    System.out.println(message);
  }

  public MessageDAO getMessageDAO() {
    return messageDAO;
  }

  public void setMessageDAO(MessageDAO messageDAO) {
    this.messageDAO = messageDAO;
  }

}
```

MessageService has a method `printMessage`. It uses the `MessageDAO`to obtain the message and prints it. It has a private field corresponding to `MessageDAO`and getter/setter methods for it.It has the `@Service`annotation. Like `@Repository`this also extends from the `org.springframework.stereotype.Component`annotation and indicates that MessageService is a Spring component.

The`messageDAO`field has the `@Autowired`annotation. This tell Spring that the container should configure this dependency. So Spring tried to find a bean of `MessageDAO`type. If it finds a matching bean, it injects it by invoking the setter method.

# Configuration File

Create a file **ApplicationContext.xml** in the **src/main/resources** folder as follows:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xmlns:context="http://www.springframework.org/schema/context"
	xsi:schemaLocation="
	 http://www.springframework.org/schema/context
    http://www.springframework.org/schema/context/spring-context.xsd
	http://www.springframework.org/schema/beans
http://www.springframework.org/schema/beans/spring-beans.xsd">
	<context:component-scan base-package="learnjava.demo"/>
</beans>
```

This **ApplicationContext.xml** is the spring configuration file. Since we are using annotation based configuration, the configuration file does not contain any bean definitions as explained [here](https://learnjava.co.in/spring-xml-configuration-example/). Instead, it has the `<context:component-scan>`tag. So Spring automatically scans all the packages under the base-package, which in this case is the "**learnjava.demo**" package. It identifies all classes that have the `@Component`annotation and its derivatives. These are treated as beans and created by the Spring container. So since the `MessageDAO`

has the `@Repository`annotation, Spring treats it as a bean and injects it into the `MessageService`class. Similarly, the `MessageService`

has the `@Service`annotation and so that is created as a bean as well.

# Writing Main Code

Create a class **Main.java** with the following code:

```java
ClassPathXmlApplicationContext applicationContext = new ClassPathXmlApplicationContext("ApplicationContext.xml");
MessageService messageService = applicationContext.getBean("messageService", MessageService.class);
messageService.printMessage();

```

The `org.springframework.context..ApplicationContext`interface represents the Spring Container. This code first creates a `ClassPathXmlApplicationContext`instance which is an implementation of the `ApplicationContext`interface. There are several other implementations too. The `ClassPathXmlApplicationContext`is used in case of an XML configuration.

`ApplicationContext`has a method `getBean`. The code invokes this method in order to obtain the`MessageService`. The code then invokes the `printMessage`method.

So on execution, this code prints the following output:

```
Hello World
```

## Further Learning

* [Spring MasterClass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-spring-framework-masterclass%2F) 
* [Spring Tutorial For Beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-tutorial-for-beginners%2F) 
* [Step by Step Spring MVC Tutorial](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-mvc-tutorial-for-beginners-step-by-step%2F) 
* [Spring Framework in Easy Steps](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspringframeworkineasysteps%2F)

# Conclusion

So in this article, we saw a Spring Java annotation configuration example. We saw how to configure a standalone Spring application via annotation-based class configuration.

---
title: "Spring Java-Based Configuration Example"
date: "2020-04-03"
categories: 
  - "others"
---

In this article, I will be demonstrating how Spring Java-Based Configuration works. I will be using **Eclipse and Maven**. In order to get a basic introduction to Spring, you can check out [this](https://learnjava.co.in/spring-framework-what-and-why/) article. In order to understand how to configure a standalone Spring application using XML configuration, you can refer to [this](https://learnjava.co.in/spring-xml-configuration-example/) article.

## Project Set-up

Step 1 - Create a new Maven Project in Eclipse. You can refer to [this](https://learnjava.co.in/how-to-create-a-maven-project-in-eclipse/) article on how to create a Maven project in Eclipse.

Step 2 - Add Spring dependencies to the maven pom file. You can add the following:

```
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

## Creating Beans

Create the following bean classes:

**MessageDAO:**

```
public class MessageDAO {
  
  public String getMessage() {
    return "Hello World";
  }

}
```

MessageDAO is a simple class that has only one method `getMessage()`This returns a String value.

**MessageService:**

```
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

MessageService has a method `printMessage`. It uses the `MessageDAO`to obtain the message and prints it. It has a private field corresponding to `MessageDAO`and getter/setter methods for it.

## Configuration Class

Create a class called **MyConfiguration** as follows:

```
@Configuration
public class MyConfiguration {
  @Bean
  public MessageDAO messageDAO() {
    MessageDAO bean = new MessageDAO();
    return bean;

  }

  @Bean
  public MessageService messageService() {
    MessageService bean = new MessageService();
    bean.setMessageDAO(messageDAO());
    return bean;
  }

}
```
The `MyConfiguration`class has the `@Configuration`annotation. This indicates that this class contains the configuration metadata. This has two methods marked with the `@Bean`annotation. The names of the method are the same as the bean names. Spring uses these methods to create the beans at startup.

## Writing Main Code

Create a class **Main.java** with the following code:

```
	public static void main(String args[]) {
		AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext(
				MyConfiguration.class);
		MessageService messageService = applicationContext.getBean("messageService", MessageService.class);
		
		messageService.printMessage();
	}

```

The `org.springframework.context..ApplicationContext`interface represents the Spring Container. This code first creates a `AnnotationConfigApplicationContext`instance which is an implementation of the `ApplicationContext`interface. There are several other implementations too. The `AnnotationConfigApplicationContext` is used in case of Java/annotation configuration.

`ApplicationContext`has a method `getBean`. The code invokes this method in order to obtain the`MessageService`. The code then invokes the `printMessage`method.

So on execution, this code prints the following output:

```
Hello World
```
## Further Learning

- [Spring MasterClass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-spring-framework-masterclass%2F)
- [Spring Tutorial For Beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-tutorial-for-beginners%2F)
- [Step by Step Spring MVC Tutorial](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-mvc-tutorial-for-beginners-step-by-step%2F)
- [Spring Framework in Easy Steps](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspringframeworkineasysteps%2F)

## Conclusion

So in this article, we saw a Spring Java-Based configuration example. We saw how to configure a standalone Spring application via a Java class configuration. We used Eclipse and Maven in this example.

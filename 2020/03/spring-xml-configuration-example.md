---
title: "Spring XML Configuration Example"
date: "2020-03-24"
categories: 
  - "spring"
---

In this article, I will be demonstrating how to configure a **standalone Spring application using XML configuration**. I will be demonstrating both **setter and constructor injection**. I will be using **Eclipse and Maven**. In order to get a basic introduction to Spring, you can check out [this](https://learnjava.co.in/spring-framework-what-and-why/) article.

# Project Set-up

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

\[table id=27 /\]

# Creating Beans

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

# Configuration File (With Setter Injection)

Create a file **ApplicationContext.xml** in the **src/main/resources** folder.Add the following:

```
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://www.springframework.org/schema/beans
http://www.springframework.org/schema/beans/spring-beans.xsd">
  <bean id="messageService"
    class="learnjava.demo.MessageService">
    <property name="messageDAO" ref="messageDAO" />
  </bean>
  <bean id="messageDAO"
    class="learnjava.demo.MessageDAO">
  </bean>
</beans>
```

This **ApplicationContext.xml** is the spring configuration file. It specifies each bean in the application via the "**bean**" tag. Since the `messageService`requires the `messageDAO`, it specifies this via a `property`tag.

# Writing Main Code

Create a class **Main.java** with the following code:

```
public class Main {
  public static void main(String[] args) {
    ClassPathXmlApplicationContext applicationContext = new ClassPathXmlApplicationContext("ApplicationContext.xml");
    MessageService messageService = applicationContext.getBean("messageService", MessageService.class);
    messageService.printMessage();
    
  }
}

```

The `org.springframework.context..ApplicationContext`interface represents the Spring Container. This code first creates a `ClassPathXmlApplicationContext`instance which is an implementation of the `ApplicationContext`interface. There are several other implementations too. The `ClassPathXmlApplicationContext`is used in case of an XML configuration.

`ApplicationContext`has a method `getBean`. The code invokes this method in order to obtain the`MessageService`. The code then invokes the `printMessage`method.

So on execution, this code prints the following output:

```
Hello World
```

# Using Constructor Injection

In order to use constructor injection you need to make the following modifications:

## Beans

The MessageService bean needs to have a constructor instead of getter/setter methods as follows:

```
public class MessageService {
  
  private MessageDAO messageDAO;

  public MessageService(MessageDAO messageDAO) {
    super();
    this.messageDAO = messageDAO;
  }

  public void printMessage() {
    String message = messageDAO.getMessage();
    System.out.println(message);
  }
}

```

## Configuration file

The configuration file needs to specify that constructor injection is being used as follows:

```
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://www.springframework.org/schema/beans
http://www.springframework.org/schema/beans/spring-beans.xsd">
  <bean id="messageService"
    class="learnjava.demo.MessageService">
    <constructor-arg ref="messageDAO"/>
  </bean>
  <bean id="messageDAO"
    class="learnjava.demo.MessageDAO">
  </bean>
</beans>
```

Here, instead of specifying the `property`tag for the `messageService`bean, the `constructor-arg`is specified.

Rest of the code remains the same. So when you execute the code with these changes, it will print the same output as before.

## Further Learning

[Spring MasterClass](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fjava-spring-framework-masterclass%2F) [Spring Tutorial For Beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-tutorial-for-beginners%2F) [Step by Step Spring MVC Tutorial](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-mvc-tutorial-for-beginners-step-by-step%2F) [Spring Framework in Easy Steps](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspringframeworkineasysteps%2F)

# Conclusion

So in this article, we saw what is XML configuration in Spring. We saw how to configure a standalone Spring application using setter and constructor injection.

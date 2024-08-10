---
title: "How to create a Jar file from a Spring Boot Application using Maven"
date: "2023-07-27"
categories: 
  - "spring-boot"
coverImage: "git-vs-github.jpg"
---

In this article, we will learn how to create a JAR file from a Spring Boot application using Maven.

## Introduction

The spring-boot-maven-plugin allows packaging a Spring Boot application as a JAR/WAR file. It needs to be specified in the project  `pom.xml` along with the type of packaging (`jar`/`war`).

## Project Creation and Setup

Step 1 - Let us use an existing project as a starting point. Clone the code from this [Spring Boot Thymeleaf](https://github.com/reshmabidikar/learnjava-springbootthymeleaf-demo) project.

Step 2 - Update the `pom.xml` to specify the packaging and the \`spring-boot-maven-plugin\` configuration. So the pom file should look as follows:

```
<project xmlns="http://maven.apache.org/POM/4.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.learnjava</groupId>
  <artifactId>learnjava-springbootthymeleaf-demo</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  <packaging>jar</packaging>
  <parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>2.1.2.RELEASE</version>
  </parent>
  <dependencies>
    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-thymeleaf</artifactId>
    </dependency>
  </dependencies>
  <build>
    <plugins>
      <plugin>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-maven-plugin</artifactId>
      </plugin>
    </plugins>
  </build>

</project>
```

## Creating the JAR File

Execute the following Maven command:

```
mvn clean package
```

This creates the JAR file in the target directory of your project.

 

## Further Reading

- [Learn Spring and Spring Boot](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-springboot-jpa-hibernate-zero-to-master%2F)
- [Learn Spring Boot in Easy Steps](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fspring-boot-tutorial-for-beginners%2F)
- [Build Rest APIs with Spring Boot](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fbuilding-real-time-rest-apis-with-spring-boot%2F)

## Conclusion

So to summarize, the spring-boot-maven-plugin can be used to create a Jar file from a Spring Boot Application using Maven.

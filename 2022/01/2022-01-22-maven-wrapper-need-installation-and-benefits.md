---
title: "Maven Wrapper - Need, Installation and Benefits"
date: "2022-01-22"
categories: 
  - "eclipse_and_maven"
coverImage: "mavenwrapper-scaled.jpg"
---

Maven is a build management system. The Maven wrapper can be used to install the right version of Maven. In this article, we will be learning about the wrapper and its benefits.

## Need for Maven Wrapper

Normally, applications require specific Maven versions for the application to run successfully. So, developers need to ensure that the right Maven version is installed and available on the path. The Maven wrapper solves this issue. Using the wrapper, you just need to specify the desired Maven version. The wrapper then automatically installs the specified Maven version and makes it available on the path.

## Wrapper Installation Steps

Let us first learn about the steps to install the wrapper.

1. Open a command prompt/terminal window and navigate to the directory where you want to install the wrapper
2. Run the following command:

```
mvn -N io.takari:maven:wrapper
```

3\. This command installs files related to the wrapper. So, you will see the following files/folders:

- .mvnw - This folder contains wrapper-specific files as follows:
    -  maven-wrapper.jar - This is responsible for downloading Maven if it is not present.
    - maven-wrapper.properties - This specifies the Maven version and the location from where to download Maven.
- mvnw - This is the executable unix shell script and can be used to run the wrapper in a Unix environment
- mvnw.cmd - This is a Windows batch file and can be used to run the wrapper in a Windows environment

4\. If you would like to specify a different Maven version, you can run the following command while installing the wrapper:

```
mvn -N io.takari:maven:wrapper -Dmaven=3.8.1
```

This will result in version 3.8.1 being specified in the properties file.

## Using the Maven Wrapper

Once you install the wrapper, you can run any command that you would ordinarily run via Maven but by specifying the `mvnw` command instead of the `mvn` command.

So, for example, you can run the following command:

```
mvnw clean install
```

If the Maven version specified in the properties file above is not present, this command will first install the Maven version and then execute the `clean` and `install` phases.

## Benefits of the Wrapper

Some of the benefits of the wrapper are:

- Developers do not need to explicitly install Maven and make it available on the path
- It makes it easy to build the code on any machine
- If the wrapper is included along with the project files, developers can directly get started with the project

## Conclusion

So, in this article, we understood about the Maven wrapper and how you can use it to install Maven.

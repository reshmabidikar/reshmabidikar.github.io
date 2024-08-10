---
title: "TestNG Annotations Explained In Detail"
date: "2022-01-01"
categories: 
  - "unit-tests"
coverImage: "study-box_1.jpg"
---

In this article, I will be explaining some of the important TestNG annotations.

## Introduction

TestNG is a popular [unit testing](https://learnjava.co.in/unit-testing/) framework. It allows creating and running tests. Though largely inspired by JUNIT, it has many advanced features like generating HTML reports, running parametrized tests, and so on.

One of the key features of TestNG is its ability to be configured via annotations. Annotations can be embedded within the TestNG code and help to control the flow of test execution.

## TestNG Annotations

Let us now take a closer look at the TestNG annotations.

### @Test

Designates a method as a TestNG test. Thus, you need to specify this annotation on any method that you want to run as a TestNG test. The @Test annotation has several attributes. Some of these are as follows:

- group: Specifies the group that the test belongs to. (TestNG allows creating test groups, so you can group related tests and run them in one go)
- description: Specifies the test description
- enabled: Specifies whether tests are enabled or not. By default, tests are enabled. A false value disables the test
- timeout: Specifies the maximum time that the test should run. If the test does not complete within the specified time, a `ThreadTimeoutException` is thrown.
- priority: Specifies a priority for this test. If not specified, tests are executed in the sequence in which they occur
- dependsOnMethod: Specifies the test that this test depends on. So, this test will only be executed after the specified test is executed successfully.
- dependsOnGroups: Specifies the group that this test depends on. So, this test will only be executed after the specified group is executed successfully.
- alwaysRun: Specifies that the test should always run, even if the method that it depends on fails

### @BeforeMethod

Can be used to specify code that needs to be executed before each test. Thus, a method that has this annotation is executed before every test method.

### @AfterMethod

Can be used to specify code that needs to be executed after each test. Thus, a method that has this annotation is executed after every test method.

### @BeforeClass

Can be used to specify code that needs to be executed before executing all the tests in a class. Thus, a method that has this annotation is executed before executing the first test method of the class.

### @AfterClass

Can be used to specify code that needs to be executed after executing all the tests in a class. Thus, a method that has this annotation is executed after executing the last test method of the class.

### @BeforeTest

Can be used to specify code that needs to be executed before executing all the tests in a package. Thus, a method that has this annotation is executed before executing the first test method of the first class.

### @AfterTest

Can be used to specify code that needs to be executed after executing all the tests in a package. Thus, a method that has this annotation is executed after executing the last test method of the last class.

### @BeforeGroups

Can be used to specify code that needs to be executed before executing a particular test group. Thus, a method that has this annotation is executed before executing tests within the specified test group.

### @AfterGroups

Can be used to specify code that needs to be executed after executing a particular test group. Thus, a method that has this annotation is executed after executing all the tests within the specified test group.

### @BeforeSuite

Can be used to specify code that needs to be executed before executing a particular test suite.  (TestNG allows creating a test suite that is nothing but a list of tests. You can create a test suite via the TestNG XML configuration file). Thus, a method that has this annotation is executed before executing tests within the specified test suite.

### @AfterSuite

Can be used to specify code that needs to be executed after executing a particular test suite. Thus, a method that has this annotation is executed after executing tests within the specified test suite.

## Code Sample

The following code demonstrates all the TestNG annotations:

```
public class Test1 {
  
  @BeforeSuite
  public void beforeSuite() {
    System.out.println("Before suite");
  }	

  @AfterSuite
  public void afterSuite() {
    System.out.println("After suite");
  }	
  
  @BeforeGroups("group1")
  public void beforeGroups() {
    System.out.println("Before groups group1");
  }
  
  @AfterGroups("group1")
  public void afterGroups() {
    System.out.println("after groups group1");
  }	
  
  @BeforeClass
  public void beforeClass() {
    System.out.println("Before class");
  }
  
  @AfterClass
  public void afterClass() {
    System.out.println("After class");
  }	
  
  @BeforeMethod
  public void beforeMethod() {
    System.out.println("Before method");
  }
  
  @AfterMethod
  public void afterMethod() {
    System.out.println("After method");
  }
  
  @Test(groups="group1")
  public void test1() {
    System.out.println("This is test1");
  }
  
  
  @BeforeTest
  public void beforeTest() {
    System.out.println("Before test");
  }	
  
  @AfterTest
  public void afterTest() {
    System.out.println("After test");
  }	
  
  @Test(groups="group2")
  public void test2() {
    System.out.println("This is test2");
  }

}
```

This code produces the following output:

```
Before suite
Before test
Before class
Before groups group1
Before method
This is test1
After method
after groups group1
Before method
This is test2
After method
After class
After test
PASSED: test1
PASSED: test2
```

 

## Further Learning

- [TestNG Complete Bootcamp](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Ftestng-complete-bootcamp%2F)
- [Learn TestNG from scratch](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Flearn-testng-testing-framework-from-scratch%2F)
- [Selenium WebDriver with Java for beginners](https://click.linksynergy.com/deeplink?id=MnzIZAZNE5Y&mid=39197&murl=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fselenium-for-beginners%2F)

## Conclusion

So, in this article, we learned about the different TestNG annotations like @Test, @BeforeMethod, @AfterMethod, and so forth.

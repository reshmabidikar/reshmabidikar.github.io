---
title: "NullPointerException explained"
date: "2019-02-14"
categories: 
  - "exception-handling"
  - "java-interview-questions"
tags: 
  - "java-exception-handling"
  - "nullpointerexception"
---

How many times has a NullPointerException in your code caused the code to break? In this blog post, I will be explaining what a NullPointerException is and what you can do to prevent it.

 

#### What is a NullPointerException?

A [NullPointerException](https://docs.oracle.com/javase/8/docs/api/java/lang/NullPointerException.html) is a [RuntimeException](https://docs.oracle.com/javase/8/docs/api/java/lang/RuntimeException.html). It is an unchecked exception and so does not need to be handled by the code. It occurs when you try to manipulate an object that has a null value.

 

#### When does it occur ?

A [NullPointerException](https://docs.oracle.com/javase/8/docs/api/java/lang/NullPointerException.html) can occur in several scenarios.

##### Scenario 1 - Invoking a method on an object that has a null value.

The most common scenarios where a [NullPointerException](https://docs.oracle.com/javase/8/docs/api/java/lang/NullPointerException.html) occurs is when you invoke a method on an object that has a null value. Consider the following code snippet:

 

\[java\]

String str = "Hello World"; System.out.println("Length of the String is "+str.length()); str = null; System.out.println("Length of the String is "+str.length());

\[/java\]

 

A variable called "_str_" is initialized to the value "**Hello World**". Its length is then printed using the [String.length](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#length--) method. Then the variable _str_ is set to null . The [str.length](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#length--) method is invoked again. When you run this code, it will print the following output:

 

```
Length of the String is 11
Exception in thread "main" java.lang.NullPointerException
at learnjava.exceptions.NullPointerExceptionDemo.main(NullPointerExceptionDemo.java:9)
```

 

This error occurs since the [str.length](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#length--) method is invoked after the variable _str_ is initialized to **null**. So a method is invoked on a **null** object.

 

##### Scenario 2 - Accessing fields of an object that has a null value

A [NullPointerException](https://docs.oracle.com/javase/8/docs/api/java/lang/NullPointerException.html)  can also occur when you invoke the fields of an object with **null** value. Consider the following code snippet:

\[java\]

public class Rectangle {

int length; int width;

}

public class RectangleDemo {

public static void main(String\[\] args) { Rectangle r = null; int length = r.length; System.out.println("Length of the Rectangle is "+length);

}

}

\[/java\]

 

In this code, there is a class called _Rectangle_ with fields for _length_ and _width_. There is another class called _RectangleDemo_. Here a _Rectangle_ object called _r_ is defined and initialized to **null**. Then, the _length_ field of the _Retangle r_ is accessed via the **dot operator**. Since the variable "_r_" has a **null** value, a  [NullPointerException](https://docs.oracle.com/javase/8/docs/api/java/lang/NullPointerException.html) will occur. When you run this code, it will print the following output:

```
Exception in thread "main" java.lang.NullPointerException
at learnjava.exceptions.nullpointerdemo.RectangleDemo.main(RectangleDemo.java:7)


```

##### Scenario 3 - Accessing fields of an array with null value

A [NullPointerException](https://docs.oracle.com/javase/8/docs/api/java/lang/NullPointerException.html)  can also occur when you access the fields of an **array** that has a **null** value. Consider the following code snippet:

\[java\]

public static void main(String\[\] args) { int\[\] arr = null; System.out.println(arr\[2\]);

\[/java\]

In the code above, an _array_ called _arr_ is defined. It is set to **null**. Then the 3rd element in the array is accessed using **arr\[2\]**. Since the array has a **null** value, this will cause a [NullPointerException](https://docs.oracle.com/javase/8/docs/api/java/lang/NullPointerException.html)  exception to occur. When you run this code, it will print the following output:

```
Exception in thread "main" java.lang.NullPointerException
at learnjava.exceptions.nullpointerdemo.NullPointerArrayDemo.main(NullPointerArrayDemo.java:7)
```

#### How can you prevent it?

[NullPointerException](https://docs.oracle.com/javase/8/docs/api/java/lang/NullPointerException.html) is an unchecked exception and so does not need to be handled by the code. You can prevent your code from breaking due to a  [NullPointerException](https://docs.oracle.com/javase/8/docs/api/java/lang/NullPointerException.html) by adding appropriate null checks.

So in Scenario 1 above, the error can be avoided using the following code snippet:

\[java\]

String str = "Hello World"; if(str != null) System.out.println("Length of the String is "+str.length()); str = null; if(str != null) System.out.println("Length of the String is "+str.length());

\[/java\]

 

So now, a null check is added for the _str_ object. If the _str_ object has a **null** value, the [str.length](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#length--) method will not be invoked. When this code is executed, it will print the following output:

```
Length of the String is 11
```

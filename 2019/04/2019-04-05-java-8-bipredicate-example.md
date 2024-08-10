---
title: "Java 8 BiPredicate Example"
date: "2019-04-05"
categories: 
  - "java-8-examples"
tags: 
  - "functional-interface"
  - "interfaces"
  - "java8"
---

In this blog post, I will be explaining how the Java 8 functional interface BiPredicate works. To know more about functional interfaces, you can refer to [this](https://learnjava.co.in/what-is-a-functional-interface/) blog post.

\[table id=24 /\]

The BiPredicate interface provides a method called test. This method accepts two parameters of any data type and returns a boolean. The BiPredicate interface is a specialization of the Predicate interface. While the Predicate interface accepts a single argument of any data type, the BiPredicate interface accepts two parameters of any data type. To see an example of the Predicate interface, refer to [this](https://learnjava.co.in/java-8-predicate-example/) blog post.

#### BiPredicate method with Two Integer arguments

Consider the following code snippet:

\[java\]

public class BiPredicateDemo { public static void main(String\[\] args) { BiPredicate<String,String> isSubString = (str1,str2) -> {return (str1.indexOf(str2)>0 || str1.startsWith(str2));}; System.out.println("Hello World has substring as Hello = "+isSubString.test("Hello World","Hello")); System.out.println("Hello World has substring as Test = "+isSubString.test("Hello World","Test"));

} }

\[/java\]

Here, the BiPredicate.test method accepts two string arguments. It checks if the second String is a substring of the first string. If so, it returns true, otherwise, it returns a false. when the above code is executed, it will print the following output:

```
Hello World has substring as Hello = true
Hello World has substring as Test = false
```

#### BiPredicate method with a String and Integer argument

Consider the following code snippet:

\[java\]

public class BiPredicateDemo { public static void main(String\[\] args) { BiPredicate<String,Integer> checkStringLength = (str,length) -> {return (str.length() > length) ;};

System.out.println("Hello World has length greater than 5 = "+checkStringLength.test("Hello World",5)); System.out.println("Hello World has length greater than 12 = "+checkStringLength.test("Hello World",12));

} }

\[/java\]

Here, the BiPredicate.test method accepts a String and an Integer argument. It checks if the length of the input String is greater than the Integer argument. If so it returns true, otherwise, it returns false.  When the above code is executed, it will print the following output:

```
Hello World has length greater than 5 = true 
Hello World has length greater than 12 = false
```

You can get the source code for this example along with the code for other Java 8 examples at the Github repository [here](https://github.com/learnjavawithreshma/Java8Demo).

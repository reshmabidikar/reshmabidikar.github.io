---
title: "JSON Syntax and Benefits explained with code samples"
date: "2019-05-17"
categories: 
  - "rest"
---

In this blog post, I will be explaining JSON Syntax and benefits. We will be taking a look at how it compares to XML as well.

## What is JSON

JSON stands for JavaScript Object Notation. It is a lightweight transfer protocol. It is based on the JavaScript language. JSON is used primarily in web services to transfer data. Data sent via JSON is concise and easy to read.

## Why was JSON required?

Prior to JSON, XML was used to transfer data between web services. The downside of using XML is that it is very verbose. For example, suppose you have a Person class as follows:

```java
public class Person { 

private String firstName; 
private String lastName; 
private int age; 
//Getter and setter methods 

}
```

And suppose we create a Person list with 3 Person objects as follows:

```java
List<Person> personList = new ArrayList<Person>(); 
personList.add(new Person("Mickey","Mouse",35)); 
personList.add(new Person("Donald","Duck",30)); 
personList.add(new Person("Peppa","Pig",10));
```

In order to send this data via XML we will need to create an XML file as follows:

```xml
<personlist> 
<person> 
<firstname>Mickey</firstname> 
<lastname>Mouse</lastname> 
<age>35</age> 
</person> 
<person> 
<firstname>Donald</firstname> 
<lastname>Duck</lastname> 
<age>30</age> 
</person> 
<person> 
<firstname>Peppa</firstname> 
<lastname>Pig</lastname> 
<age>10</age> 
</person> 
</personlist>
```

So basically we need to do the following:

- Create a top-level tag
- Create a tag for each object
- Create a tag for each field in the class.

The same information can be represented in JSON as follows:

```json
{ "personList":
[ {"firstName":"Mickey", "lastName":"Mouse","age":"35"}, 
{"firstName":"Donald", "lastName":"Duck","age":"30"}, 
{"firstName":"Peppa", "lastName":"Pig","age":"10"} 
] }
```

So when you compare this to the XML version. this code is concise and easy to read.

## JSON Syntax

JSON represents each field name and its value is as a **name-value pair** separated by a **colon**. So in the above example **firstname:Mickey** indicates that the field name is **firstName** and its value is **Mickey**

An **object** is enclosed in **curly brackets**. So in the above example **{"firstName":"Mickey", "lastName":"Mouse","age":"35"}** is an **object** with **3 fields**. Each field is separated by a comma.

Finally, an **array** is enclosed in **square brackets**. So the above example denotes an array with 3 objects. Each object in the array is separated by a comma.

## Conclusion

So, in this article, we understood JSON syntax and benefits. We took a look at how JSON is better than XML.

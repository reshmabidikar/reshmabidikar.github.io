In Java development, dealing with JSON is a common task, and Jackson is one of the most widely used libraries for serializing and deserializing JSON objects. The Jackson ObjectMapper class is the heart of Jackson. It offers powerful features to easily convert between Java objects and JSON. In this article, we’ll dive into the key functionalities of ObjectMapper and explore various use cases with practical examples.

## What is Jackson ObjectMapper?
ObjectMapper is a core class in the Jackson library responsible for parsing JSON content and converting it to and from Java objects. It handles all aspects of JSON processing, including reading from and writing to JSON files, strings, and streams. Additionally, `ObjectMapper` can be customized with different configurations to cater to various needs such as handling complex types, formatting, and ignoring unknown fields.

## Getting Started with Jackson

To begin using `ObjectMapper`, you need to include the Jackson dependencies in your project. If you are using Maven, add the following dependencies to your `pom.xml`:

````xml
<dependency>
    <groupId>com.fasterxml.jackson.core</groupId>
    <artifactId>jackson-databind</artifactId>
    <version>2.13.3</version>
</dependency>
````

## Serializing Java Object to JSON

Consider the following Person class:

````java
public class Person {
    private String name;
    private int age;
    
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    public Person() {
    }

    //getters and setters
}
````

The following code demonstrates how you can serialize a Java object with JSON:

````java
ObjectMapper objectMapper = new ObjectMapper();
// Sample object
Person person = new Person("Jane Doe", 27);
// Convert object to JSON string
String jsonString = objectMapper.writeValueAsString(person);
System.out.println(jsonString);
````

This coverts the person object into a JSON and prints the JSON string

## Deserializing JSON to Object

The following code demonstrates how you can deserialize a JSON string to an object:

````java
ObjectMapper objectMapper = new ObjectMapper();
// Read person.json from classpath
URI uri = DeserializeExample.class.getClassLoader().getResource("person.json").toURI();
String jsonString = Files.readString(Path.of(uri));
// Convert JSON string to Java object
Person person = objectMapper.readValue(jsonString, Person.class);
System.out.println(person.getName());
````

## Handling Lists

`ObjectMapper` handles more than just simple classes; it can manage collections, arrays, and complex nested objects as well.

````java
ObjectMapper objectMapper = new ObjectMapper();
// List of persons
List<Person> persons = List.of(new Person("John", 30), new Person("Jane", 25));
// Convert list to JSON
String jsonString = objectMapper.writeValueAsString(persons);
System.out.println(jsonString);
// Convert JSON back to list
List<Person> deserializedPersons = objectMapper.readValue(jsonString, new TypeReference<List<Person>>(){});
deserializedPersons.forEach(person -> System.out.println(person.getName()));
````

The complete source code for this example is available on [GitHub](https://github.com/reshmabidikar/learnjava-jackson-demo).

## Conclusion

The Jackson `ObjectMapper` is an extremely powerful and flexible tool for working with JSON in Java. Whether you need to serialize complex objects or customize how your Java classes map to JSON, ObjectMapper provides the necessary tools to get the job done efficiently. By understanding its core features and advanced capabilities, you can leverage Jackson to handle a wide range of data processing tasks in your Java applications.
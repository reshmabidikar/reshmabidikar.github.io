---
title: "Introduction to Swagger"
date: "2020-02-12"
categories: 
  - "rest"
---

Recently, I got an opportunity to understand a bit about Swagger and how it works. So in this article, I will be explaining what swagger is, how it works. This article is for those readers who have heard about Swagger but wish to know about it further.

Swagger is a tool that developers can use to document REST services. It is based on the Open API specification.

# Challenges in documenting a REST application

SOAP web services use a WSDL file for documenting the web service. However, when it comes to REST services, there are no established standards for documentation.  So developers need to create documents manually. This method is tedious and error prone.

# Open API Specification

OPEN API is a specification that developers can use to document REST services. It helps in documenting the following:

1. Available HTTP methods(GET, POST, PUT, etc) supported by each REST method,
2. Input/outputs that the REST service accepts/produce
3. Authentication information

Open API specification files can be written in JSON, XML or YAML format.

YAML stands for “YAML Ain’t Markup Language.” YAML is similar to JSON but unlike JSON. However, it does not have curly brackets, square brackets, etc. and so it is more readable than JSON. YAML uses colons to denote an object’s properties and hyphens to denote an array. YAML is hierarchical and uses spaces to denote levels. Each level can store a key-value pair.

# What is Swagger?

Swagger provides a set of tools that use the Open API specification. Developers can use these tools to produce interactive documentation for web services. Not only that, You can use Swagger to automatically generate documentation for your REST services.

It includes a set of tools as follows:

## Swagger Editor

Swagger editor is an online editor. Developers can use it to create the Open API specification file. It can create the Specification file in both YAML and JSON format. The advantage of using the Swagger editor is that it automatically validates the document that you are creating. So you can quickly fix syntax errors if any. This is as against typing the resource file in a simple text editor, where there is no syntax checking and so it is more error prone. You can create the specification file in both JSON and YAML format in the swagger editor.

## Swagger UI

Developers can use the Swagger UI to automatically generate interactive documentation from the Open API specification file. Interactive means you can actually run the REST requests and view the JSON/XML response sent. The Open API specification file is in JSON or YAML format and not very easily readable for humans. The swagger UI converts this to an HTML format which can be accessed via a browser and so it is easy to read and understand for humans.

## Swagger Codegen

Developers can use Swagger Codegen to generate server code stubs and client libraries from an Open API specification file.

# Documenting REST services

As mentioned earlier,developers can use Swagger to automatically generate documentation for REST services. Swagger supports both JAX-RS as well as Spring REST services.

## JAX-RS Documentation

Swagger provides a library called swagger-core. Developers need to add the dependency for this library in order to automatically generate documentation for JAX-RS REST services. The swagger-core library analyses the JAX-RS annotations in the code and generates the Open API specification file. In addition, swagger-core also provides its own annotations which can be used to customize the documentation.

## Spring Integration

Developers can use the Springfox library in order to generate documentation for a Spring based REST service. This not only generates the Open API specification file, but it can also generate interactive UI documentation. Springfox library also provides its own annotations which can be added to your code to customize the generated documentation.

# Conclusion

So in this article, we understood what Swagger is and why it is used. We saw how Swagger can be used to document REST services. We also understood about the Open API specification.

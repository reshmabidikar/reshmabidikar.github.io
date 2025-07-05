Containerizing applications has become a critical skill in modern software development. In this article, we’ll walk through the process of containerizing a Spring Boot application using Docker.

## Step 1 – Create a simple SpringBoot project


You can create a simple SpringBoot application as explained here. Ensure that your pom file has the spring-boot-maven-plugin specified as follows:

````xml
<build>
    <plugins>
      <plugin>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-maven-plugin</artifactId>
      </plugin>
    </plugins>
  </build>
````

## Step 2: Add Dockerfile to the Project

A `Dockerfile` is a text file that contains all the commands to assemble an image. Let’s create a `Dockerfile` in the root directory of the Spring Boot project.

````
# Use an official lightweight JDK base image
FROM openjdk:17-jdk-slim
# Set the working directory inside the container
WORKDIR /app
# Copy the JAR file from the target directory into the container
COPY target/SpringBootDemo-0.0.1-SNAPSHOT.jar app.jar
# Expose port 8080 to the outside world
EXPOSE 8080
# Command to run the JAR file
ENTRYPOINT ["java", "-jar", "app.jar"]
````

This Dockerfile does the following:

* **Base Image**: Using openjdk:17-jdk-slim, a smaller base image, to keep the Docker image size minimal.
* **WORKDIR**: Sets the working directory inside the container to /app where all commands run.
* **COPY**: Only copies the built JAR file into the container (you can adjust the JAR name based on your project).
* **EXPOSE**: Explicitly exposes port 8080, the default port for Spring Boot apps.
* **ENTRYPOINT**: Starts the Spring Boot application by running the JAR file.

## Step 3: Build the Spring Boot JAR

Before we can create a Docker image, we need to package our Spring Boot application into a JAR file. To do this, run the following command in your project directory:

````
mvn clean package
````

After this, a JAR file will be generated in the `target/` directory (e.g., `target/SpringBootDemo-0.0.1-SNAPSHOT.jar`

## Step 4: Build the Docker Image

Once the JAR file is generated, you can build the Docker image using the `Dockerfile`. In the project root directory (where the Dockerfile is located), run the following command:

````
docker build -t springboot-docker .
````

This does the following:

* `docker build` creates a Docker image from the `Dockerfile`.
* `-t` springboot-docker tags the image with the name `springboot-docker`.
* The `.` at the end specifies the build context (the current directory).

## Step 5: Run the Docker Container

After building the image, you can run the container with this command:

````
docker run -p 8080:8080 springboot-docker
````

* `-p 8080:8080` maps port 8080 of the container to port 8080 on your local machine.
* `springboot-docker` is the name of the image we built in the previous step.

* At this point, your Spring Boot application is running inside a Docker container, and you can access it by visiting `http://localhost:8080` in a browser.

## Step 6: Push the Docker Image to Docker Hub (Optional)

If you want to share your image with others or deploy it to a remote server, you can push it to Docker Hub.

````
docker login
docker tag springboot-docker your_dockerhub_username/springboot-docker
docker push your_dockerhub_username/springboot-docker
````

This does the following:

* Logs in to Docker
* Tags your image for Dockerhub
* Pushes your image to Dockerhub

* Now, your image is available on Docker Hub and can be pulled on any machine using:

````
docker pull your_dockerhub_username/springboot-docker
````

## Conclusion
Containerizing a Spring Boot application with Docker is a powerful way to ensure your app runs consistently across environments, from development to production. With a simple Dockerfile and a few commands, you can package your Spring Boot app into a Docker container, run it locally, and even deploy it to cloud environments.

Docker makes it easier to scale, isolate dependencies, and streamline the deployment process. Whether you’re working on a microservice architecture or a monolith, Docker and Spring Boot work together seamlessly.
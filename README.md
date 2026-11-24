# Exp_2_Simple-Spring-Boot-MVC-Application
### Name: Dharunyadevi S
### Register Number: 212223220018
## AIM:
To develop a Simple Spring Boot MVC (Model-View-Controller) Application that uses a Controller to handle HTTP requests, a Model to pass data, and a View (Thymeleaf) to render dynamic HTML pages.

## ALGORITHM:
Create a New Spring Boot Project:

Use Spring Initializr

Add dependencies:

Spring Web

Thymeleaf

Set Up Project Structure:

Create the main class annotated with @SpringBootApplication

Create a Controller class using @Controller

Add HTML templates under src/main/resources/templates

Create a Controller:

Define a method to handle HTTP GET requests using @GetMapping

Return a view name (HTML page name) from the controller

Pass data to the view using Model object

Create a Model (Optional):

Define a simple POJO class if you need to pass structured data to the view

Create View Pages (HTML using Thymeleaf):

Create an HTML file inside the templates folder

Use Thymeleaf syntax (e.g., ${name}) to render dynamic content

Run the Application:

Run the Spring Boot application from your IDE or command line

Access the Application:

Open a browser and navigate to http://localhost:8081/
## PROGRAM
spring-mvc-demo/
├── src/
│   └── main/
│       ├── java/
│       │   └── com.example.mvc/
│       │       ├── MvcApplication.java
│       │       └── HomeController.java
│       └── resources/
│           ├── templates/
│           │   └── index.html
│           └── application.properties
├── pom.xml

### pom.xml :
```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>4.2.0</version>
        <relativePath/> <!-- lookup parent from repository -->
    </parent>
    <groupId>com.example</groupId>
    <artifactId>SpringBootMVC</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <name>SpringBootMVC</name>
    <description>SpringBootMVC</description>
    <url/>
    <licenses>
        <license/>
    </licenses>
    <developers>
        <developer/>
    </developers>
    <scm>
        <connection/>
        <developerConnection/>
        <tag/>
        <url/>
    </scm>
    <properties>
        <java.version>17</java.version>
    </properties>
    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-thymeleaf</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-webmvc</artifactId>
        </dependency>

        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-thymeleaf-test</artifactId>
            <scope>test</scope>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-webmvc-test</artifactId>
            <scope>test</scope>
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
### SpringBootMvcApplication.java (Main Class):
```java
package com.example.springbootmvc;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class SpringBootMvcApplication {

    public static void main(String[] args) {
        SpringApplication.run(SpringBootMvcApplication.class, args);
    }

}

```
### HomeController.java (Controller):
```java
package com.example.springbootmvc;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class HomeController {

    @GetMapping("/")
    public String home() {
        return "index";
    }
}

```
### index.html (View – inside src/main/resources/templates/):
```html
<!DOCTYPE html>
<html>
<head>
    <title>Spring Boot MVC</title>
    <link rel="stylesheet" href="/style.css">
</head>
<body>
<div class="container">
    <h1>Welcome to Spring Boot MVC!</h1>
    <p id="message">
        Welcome to our first MVC app!
    </p>
    <button onclick="showAlert()">
        Click for Alert
    </button>
    <button onclick="changeText()">
        Change Text
    </button>
</div>
<script>
    function showAlert() {
        alert("Welcome to Spring Boot MVC!");
    }
    function changeText() {
        document.getElementById("message").innerHTML =
            "Text Changed Successfully!";
    }
</script>
</body>
</html>
```
### application.properties:
```
 spring.application.name=SpringBootMVC
server.port=8081
```
### Output:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/53bd2107-3d83-4353-ab52-84dc26e6f562" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c08ff3e6-7562-4d9c-9011-7912474c3f28" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0bf35143-5164-4c76-af22-456e694a504e" />

### Result:
Thus, the Spring Boot MVC application was successfully created and executed in IntelliJ IDEA. The webpage displayed the heading "Welcome to Spring Boot MVC!" along with the message "Welcome to our first MVC app!". The Click for Alert button displayed a JavaScript alert, and the Change Text button successfully changed the paragraph text.

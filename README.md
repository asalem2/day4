Q1. What is the Spring Boot?
Spring Boot is an opinionated framework for building and running Spring applications. Spring Boot is not a framework for writing applications, think of Spring Boot as a tool which can do these initial tasks for us automatically.

While working on big enterprise projects involving several frameworks, it is complex to handle all configurations and making sure required dependencies are in place. Spring Boot focuses on developer productivity by providing smart auto configuration modules and handling all configurations and dependencies for us.

Read What is Spring Boot for more detail.

 

Q2. What are the advantages of Spring Boot?
It simplifies Spring dependencies by taking the opinionated view.
Spring Boot provides a pre-configured set of technologies/framework to reduces error-prone configuration so we as a developer focused on building our business logic and not thinking of project setup.
It reduces development code by avoiding a lot of boilerplate code.
Easier to integrate Spring Boot Application with Spring Ecosystem like Spring JDBC, Spring ORM, Spring Data, Spring Security, etc.
You really don’t need those big XML configurations for your project.
Embed Tomcat, Jetty or Undertow directly.
Provide opinionated Maven POM to simplify your configuration.
 

Q3. What are the different Spring Boot Components?
Boot Initializer
Spring Boot Starter
Auto Configurator.
Spring Boot CLI.
Actuator.
Spring Boot Modules
 

Q4. What is Spring Boot Starters?
Spring Boot Starters are the set of convenient dependency descriptors which can be easily included in any level of application. These starters work as a bootstrapping process for the Spring related technologies, we no longer need to worry about the dependencies and they will be automatically managed by Spring Boot Starters.

The starters contain a lot of the dependencies you need to get a project up and running quickly and with a consistent, supported a set of managed transitive dependencies. To summarize, Spring Boot Starters are just JAR files used by Spring Boot for auto-dependency.

 Read Spring Boot Starters for more detail.

 

Q5. Name some starter provided by Spring Boot?
spring-boot-starter-web: Web and RESTful applications
spring-boot-starter-security : Spring Security
spring-boot-starter-data-jpa – Spring Data JPA
spring-boot-starter-test – Unit testing
spring-boot-starter-hateoas – Add HATEOAS features
spring-boot-starter-data-jpa – Spring Data JPA with Hibernate
For a complete list, read Spring Boot Starters List

 

Q6. What is Auto-Configuration in Spring Boot?
It takes a lot of configurations and boilerplate code create a simple Spring MVC application without Spring Boot. Spring Boot Auto Configuration provides an opinionated approach to bootstrap your application. Auto-Configuration will attempt to automatically try to set up our application with default behavior based on the jars in the classpath. For example, if Spring Boot finds HSQLDB in out classpath, it will automatically configure an in-memory database for us. Think of the auto-configuration as an intelligent system which can provide ready to use the application to us based on the configured jars in our classpath.

For detail information please read our article Spring Boot Auto Configuration

 

Q7. Can we use Spring Boot for non-Spring application?
No, Spring Boot has limited to Spring based application only. We can not use Spring Boot for non Spring applications.

 

Q8. What are the different options for creating the Spring Boot application
There are multiple options to create a Spring Boot application. We can use any of the following approaches

Spring Initializer
Boot CLI.
Using Maven
IDE project wizard
Read Building an Application with Spring Boot for detail.

 

Q9. What is the Spring Boot Initilizr?
Spring Boot Initilizr is a Spring Boot tool to bootstrap Spring Boot or Spring Applications easily. Spring Initializr is also integrated with all major Java IDEs along with CLI.

 

Q10. What are the advantages of Spring Boot Initializr?
Spring Boot Initializr provides a simple interface to quickly bootstrap a Spring Boot application. Here are benefits or advantages of using Initilizr.

Spring Initializr provides an extensible API to generate quick start projects.
Reduce time to create an application setup. We can create application setup using a few clicks.
It increases Productivity
Initializr offers a configuration structure to define all the aspects related to the project to generate: list of dependencies, supported java and boot versions.
For more detail, read Spring Initializr Reference Guide

 

Q11. How can I reload my Spring Boot changes without restarting the server?
This is achievable by Spring Boot Dev Tools module.it’s a powerful tool for development. It helps developers to shorten the development cycle and enable easy deployment and testing during development.

To enable this feature, add the following dependency to Maven POM file.

<dependencies>
    <dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-devtools</artifactId>
    </dependency>
</dependencies>
Copy
Read Spring Boot Dev Tools for different features of Dev Tools.

 

Q12. How can we override default properties in Spring Boot?
Spring Boot advocate convention over configuration. Spring Boot externalize application configurations through application.properties file. These properties work as default values for the Spring Boot application.

To override these default values, Spring Boot provides the following options.

Create an application.properties file in the classpath for overriding specific properties for Spring Boot.
For Maven based project, this file will be under /src/main/resource.
application.yml file in the classpath for overriding specific properties for Spring Boot.
For Maven based project, this file will be under /src/main/resource.
Through command line switches
e.g. Server HTTP port default to 8080 in the default application.properties file. To change this port to 9090, add below entry in the custom application.properties file

server.port=9090
Copy
 

Q13. What are the embedded containers supported by Spring Boot?
Spring Boot includes support for the following embedded containers

Tomcat
Jetty
Undertow.
Use the right “Starter” to configure the embedded container. 

 

Q14. What is the Spring Boot Actuator?
The actuator provides production-ready features for Spring Boot application. It will help us check and manage our application in the production environment. We need none code to get these features since they are available once the actuator dependency is in the class-path. The actuator provides features like auditing, health, metrics, environment information, thread dump etc. using HTTP endpoints. Read Spring Boot Actuator for more detail.

 

Q15. How can we create a custom endpoint in Spring Boot Actuator?
To create a custom endpoint using Spring Boot 1.x, we should expose the instance of the custom endpoint class as a bean. We need to implement Endpoint<T> interface.

@Component
public class CustomEndpoint implements Endpoint {
 //method implimentation
}
Copy
Spring Boot 2.x changed it by introducing @Endpoint annotation. Spring Boot expose endpoints with @Endpoint@WebEndpointor @WebEndpointExtension over HTTP using Jersey, Spring MVC, or Spring WebFlux.Read Custom Endpoint in Spring Boot Actuator for more detail.

 

Q16. How to run Spring Boot application to custom port?
Use the application.properties file to configure a custom port for Spring Boot application. To change the server port, use server.port property.

server.port=9001
Copy
Read Spring Boot Web Application Configuration for more detail.

 

Q17. What logging support provided by Spring Boot? How can we control logging level in Spring Boot?
Spring Boot provides options to use all popular logging API using the relevant starter, by default Spring Boot use Commons Logging for its internal logging. If we are using Spring Boot Starters for our application, Logback will be used for logging by default unless we want to use any other logging API. To use any other logging API, we need to add the correct starter in our application. In case we like to use Log4j2 for logging configuration, all you have to add the log4j2 starter in your application (You may have to exclude logback using  pom.xml file).

Spring Boot provides an easy way to configure and set logging levels for your application. We can use application.properties file to configure the desired Logging level for our application by using ‘logging.level.*=LEVEL’. Here is an example for the same

logging.level.com.javadevjournal.rest=WARN
Copy
Read Spring Boot Logging for more detail.

 

Q18. How to implement security for Spring boot application?
Use the spring-boot-starter-security starter to enable the Spring security support in your Spring Boot application.

<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-starter-security</artifactId>
</dependency>
Copy
 

Q19. How to configure database using Spring Boot?
The Spring Framework provides extensive support for working with SQL databases, from direct JDBC access using JdbcTemplate to complete “object-relational mapping” technologies such as Hibernate. To connect configure the database for your Spring Boot application, use the spring-boot-starter-jdbc or spring-boot-starter-data-jpa “starters”.To configure datasource configuration, use the application.properties file in your application.

spring.datasource.url=jdbc:mysql://localhost/javadevjournal
spring.datasource.username=root
spring.datasource.password=
spring.datasource.driver-class-name=com.mysql.jdbc.Driver
Copy
Above example is to configure MySQL in your application. For more information, read Configuring MySQL for Spring Boot Application

 

Q20. How can we use Jetty instead of the tomcat in our web application?
Spring Boot web starters use Tomcat as the default embedded servlet container. When switching to a different HTTP server, we need to exclude the default dependencies besides including the one we need. Spring Boot provides separate starters for HTTP servers to help make this process as easy as possible. To use Jetty, we need to exclude Tomcat and include Jetty in our application’s pom.xml file.

<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-web</artifactId>
	<exclusions>
		<!-- Exclude the Tomcat dependency -->
		<exclusion>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-tomcat</artifactId>
		</exclusion>
	</exclusions>
</dependency>
<!-- Use Jetty instead -->
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-jetty</artifactId>
</dependency>
Copy
 

Q21. Why do we need spring-boot-maven-plugin?
Spring Boot Maven plugin provides Spring Boot support in the maven. This plugin provides options to create an executable jar or war files. Here are goals for this plugin.

boot: run runs your Spring Boot application.
spring-boot:repackage repackages your jar/war to be executable.
spring-boot:start and spring-boot:stop to manage the lifecycle of your Spring Boot application (i.e. for integration tests).
spring-boot:build-info generates build information that can be used by the Actuator.
To include this plugin in your project, add XML in the plugins section of your pom.xml

<plugins>
	<plugin>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-maven-plugin</artifactId>
		<version>2.0.5.RELEASE</version>
		<executions>
			<execution>
				<goals>
					<goal>repackage</goal>
				</goals>
			</execution>
		</executions>
	</plugin>
</plugins>
Copy
 

Q22. How to disable specific auto-configuration in spring boot?
To exclude specific auto-configuration classes, use the exclude attribute of @EnableAutoConfiguration to disable them. Here is a sample code for the same.

@Configuration
@EnableAutoConfiguration(exclude={DataSourceAutoConfiguration.class})
public class CustomConfiguration {
}
Copy
 

Q23. What is the use of YAML in Spring Boot?
YAML is a superset of JSON.Spring Boot YAML as an alternative to the application.properties file to define your project properties. The SpringApplication class automatically supports YAML as an alternative to properties whenever you have the SnakeYAML library on your classpath.

Let’s take the following example of the application.properties file.

environments.dev.url=https://dev.javadevjournal.com
environments.dev.name=Developer Setup
Copy
It can represent the YAML files as follows.

environments:
   dev:
       url: https://dev.javadevjournal.com
       name: Developer Setup
Copy
 

Q24. What is new in Spring Boot 2.0?
Spring Boot 2.0 brings several features changes to the Spring Boot framework.

Spring Boot 2.0 is a baseline to Java 8. Therefore, Spring Boot 2.0 requires Java 8 or later. It doesn’t support Java 6 and Java 7 anymore.
It supports Java 9.
Spring Boot 2.0 requires Spring Framework 5.0 with Reactive support.
Embedded servlet containers support got upgraded
Minimum Tomcat version is 8.5
Jetty is 9.4
Spring Boot 2.0 supports HTTP/2 with the help of server.http2.enabledproperty.
The framework requires Gradle 4.x in case you are using Gradle as your build tool.
Security configuration simplified in Spring Boot 2.0.
A brand new actuator architecture, with support for Spring MVC, WebFlux and Jersey.
For more details, please read.

 

Q25. What is @SpringBootApplication annotation?
This is one of the most important and core annotation from Spring Boot. We use this annotation to mark the main class of our Spring Boot application.

@SpringBootApplication
public class SpringOrderAnnotationApplication {
 public static void main(String[] args) {
  SpringApplication.run(SpringOrderAnnotationApplication.class, args);
 }
}
Copy
@SpringBootApplication is a convenience annotation equal to declaring @Configuration, @EnableAutoConfigurationand @ComponentScan with their default attributes.

You have the option to use @Configuration, @EnableAutoConfiguration, and @ComponentScan individually but the recommendation is to @SpringBootApplication annotation.

For more detail, please read Spring Boot Annotations.

 

Q26. How to include custom static content in Spring Boot application (e.g custom JS code)?
Spring Boot search specific location in the project for serving static contents. By default, Spring Boot serves static content from a directory called /static (or /public or /resources or /META-INF/resources) in the classpath or from the root of the ServletContext.

We can put our custom static content in any of the above folders. For example, put the custom.js file under /resources/static/custom.js. To refer to this file in the view use the following code

<script src = “/js/test.js”></script>
Copy
 

Q27. How to use a profile with Spring Boot?
Spring Boot provides multiple ways to active profile. We can pass profile information through the command line or use application.properties, Spring Boot also provide a way to set profile programmatically.

Use profile specific configuration files in our Spring Boot application.we need to the naming convention of application-{profile}.properties where profile defines the name of the intended profile. Profile specific files will be loaded from the same location as application.properties file.

Read Introduction to Spring Profiles Using Spring Boot for more detail.

 

Q29. How to set the active profile in Spring Boot?
There are two ways to set the active profile in Spring Boot.

Pass in the active profile as an argument while launching the application.
Use the application.properties file to set the active profile.
java -jar -Dspring.profiles.active=production application-1.0.0-RELEASE.jar //pass as command line argument
spring.profiles.active=production
Copy
 

Q29. How to generate a WAR file with Spring Boot?
We can control the package type generation in our Spring Boot project usingspring-boot-maven-plugin To build a war file, we need to follow these 2 steps.

Set the packaging type as a war in our pom.xml file.
Mark the embedded container dependencies as “provided” (To build a war file that is both executable and deployable into an external container.)
Here is a snapshot from pom.xml

<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
   <!-- ... -->
   <packaging>war</packaging>
   <!-- ... -->
   <dependencies>
      <dependency>
         <groupId>org.springframework.boot</groupId>
         <artifactId>spring-boot-starter-web</artifactId>
      </dependency>
      <dependency>
         <groupId>org.springframework.boot</groupId>
         <artifactId>spring-boot-starter-tomcat</artifactId>
         <scope>provided</scope>
      </dependency>
      <!-- ... -->
   </dependencies>
</project>
Copy
 

Q30. How to disable the web server configuration in your Spring Boot application?
Spring Boot automatically starts an application in web server mode if it finds the web module in the classpath. To disable the web server configuration, set the webApplicationType to none in the application.properties file.

spring.main.web-application-type=none
Copy
 

Q31. How to configure and enable SSL for your Spring Boot application?
Use the server.ssl.* properties in the application.properties or yml file to configure and enable SSL for your Spring Boot application. Here are typical SSL configurations for your application.

server.port=8443 //SSL port
server.ssl.key-store=classpath:keystore.jks //You can also configure it to external location
server.ssl.key-store-password= //password for your key
server.ssl.key-password=//key password
Copy
Remember, Spring Boot does not support configuration of both HTTP and HTTPS through the property file. Configure other port programmatically if you need to use both ports.

 

Q32. Can we create a Non-web application in Spring Boot?
Yes, Spring Boot support creating both web and non-web applications. To create a non-web application, you need to remove web dependencies from your classpath along with changing the way Spring Boot create the application context. Please read Standalone Application Using Spring Boot for more details.

 

Q33. How the ApplicationContext created by Spring Boot?
Spring Boot creates the ApplicationContext once we execute the SpringApplication.run() command.Spring Boot returns the ConfigurableApplicationContext which extends ApplicationContext. This is how Spring Boot creates and return the context.

public ConfigurableApplicationContext run(String...args) {
 //preparation
 ConfigurableApplicationContext context = null;

 //create and return application context
 context = createApplicationContext();
}

protected ConfigurableApplicationContext createApplicationContext() {
 Class << ? > contextClass = this.applicationContextClass;
 if (contextClass == null) {
  try {
   switch (this.webApplicationType) {
    case SERVLET:
     contextClass = Class.forName(DEFAULT_SERVLET_WEB_CONTEXT_CLASS);
     break;
    case REACTIVE:
     contextClass = Class.forName(DEFAULT_REACTIVE_WEB_CONTEXT_CLASS);
     break;
    default:
     contextClass = Class.forName(DEFAULT_CONTEXT_CLASS);
   }
  } catch (ClassNotFoundException ex) {
   throw new IllegalStateException(
    "Unable create a default ApplicationContext, " +
    "please specify an ApplicationContextClass",
    ex);
  }
 }
 return (ConfigurableApplicationContext) BeanUtils.instantiateClass(contextClass);
}
Copy
For more information, refer to the SpringApplication

 

Q34. How can we externalize SpringApplication configuration?
The SpringApplication class provides setters method to configure and customize its behavior. For example, to switch off the banner (displaying on startup), we can use the .bannelMode(boolean) method.

new SpringApplicationBuilder()
	.bannerMode(Banner.Mode.OFF)
	.run(args);
Copy
This can be easily externalized by using the spring.main.*properties in application.properties

spring.main.banner-mode=off
Copy
Properties defined in the external configuration override the values specified with the Java API with some exceptions.

 

Q35. How to enable HTTP Response Compression in Spring Boot?
Spring Boot supports the HTTP response compression for the following application servers:

Tomcat
Jetty
Undertow
To enable this feature, set the server.compression.enabled property to true in the application.properties

server.compression.enabled=true
Copy
Use the server.compression.min-response-size property to set the compression length. By default Spring Boot perform compression for the following context type:

    text/html
    text/xml
    text/plain
    text/css
    text/javascript
    application/javascript
    application/json
    application/xml
Copy
use the server.compression.mime-types property to customize this list.

 

Q36. What is Spring Boot Admin?
Spring Boot admin is a community project used to manage and monitor your Spring Boot applications. The client application gets register themselves with the admin server (via HTTP) or is discovered using Spring Cloud discover server like Eureka, Consul.Each client application needs to have Spring Actuator jars in it. The endpoints provided by the Actuator jar is polled by the Spring Boot Admin server to get the metrics of that application.

Actuators endpoints let you monitor and interact with your application. Spring Boot includes several built-in endpoints and lets you add your own. To know more details about these endpoints read Spring Boot Actuator.

 

Q37. Can we configure Spring Boot to use multiple data sources?
No, Spring Boot does not provide an out of the box solution in case our application needs multiple DataSources (e.g. multi-tenant system). Spring Boot provides multiple extension point to enable support for multiple data sources. Read multiple data sources with Spring Boot for more detail.

 

Q38. What is application.properties file in Spring Boot?
 This property file is the central control system for your Spring Boot application. Spring Boot applies its typical convention over configuration approach to property files. Spring Boot provides default application.properties file for the default configurations. When Spring Boot application starters, it refer to this configuration file for the default values.

Spring boot specified various common default properties inside application.properties to support Logging, AOP, Server configurations, caching, JPA, etc. We need not specify all the default properties in all the cases. We can specify them only on-demand.

For the complete list, please refer to the Common application properties

 

Q39. How to enable HTTP/2 support in Spring Boot?
We can enable HTTP/2 support by using server.http2.enabled configuration property. Please refer to the application server documentation as HTTP/2 is not supported by all web servers.
 

Q40. What is the use of starter POM in our Spring Boot application?
Spring Boot starter parent is a convenient and easy way for dependency management. With each release, Spring Boot provides a curated list of it supports. While working on the Spring Boot application, you may not need to provide the version number for the dependencies as these are automatically taken care by Spring Boot. Spring Boot manage these curated list of dependencies through the starter pom.

 

Q41. How to access a value defined in the application.properties file in Spring Boot?
Use the @Value annotation to access the properties defined in the application. properties file.

@Value("${custom.value}")
private String customVal;
Copy
For more details, read Externalized Configuration



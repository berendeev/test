# Event organizer

Event organizer is an application that makes it easier to manage events with a group of people.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

What things you need to install the software

* [JDK](https://www.oracle.com/technetwork/java/javaee/downloads/jdk8-downloads-2133151.html)
* [Maven](https://maven.apache.org/)
* [Tomcat](https://tomcat.apache.org/download-80.cgi)

### Running on local machine

You can start the application on the local machine in two ways:

1. Run on tomcat server

   To run the application on the server you need to perform the following steps:
   
   1. For the web module to work correctly, it is necessary that all jsp files be searched in the webapps/jsp directory
   
        ````
        mkdir --parents {PROJECT_ROOT}/event-organizer-web/src/main/webapp/WEB-INF/jsp/;
        mv {PROJECT_ROOT}/event-organizer-web/src/main/resources/META-INF/resources/WEB-INF/jsp/* {PROJECT_ROOT}/event-organizer-web/src/main/webapp/WEB-INF/jsp
        ````
   
   2. It is also necessary to change the properties. In core module, these are the database access settings. On the web module, this is the url where the core will work.
   3. In project root execute 
   
        ````
        mvn package
        ````
   
   4. Move event-organizer.war and event-organizer-server.war from both /target modules to tomcat/webapps directory.
   5. Application will be run on [localhost:8080/event-organizer](http://localhost:8080/event-organizer)

2. Run with java -jar
   
    To run the application with java -jar you need to perform the following steps:
   
    1. For the web module to work correctly, it is necessary that all jsp files be searched in the webapps/jsp directory
      
        ````   
        mkdir --parents {PROJECT_ROOT}/event-organizer-web/src/main/webapp/WEB-INF/jsp/;
        mv $WORKSPACE/event-organizer-web/src/main/resources/META-INF/resources/WEB-INF/jsp/* {PROJECT_ROOT}/event-organizer-web/src/main/webapp/WEB-INF/jsp
        ````
    2. In root of the project execute 
    
        ```` 
        mvn package 
        ````
    
    3. After you can run the modules. Change the necessary properties if necessary.
        ````
        java -jar {PROJECT_ROOT}/event-organizer-core/target/event-organizer-server.war
        java -jar {PROJECT_ROOT}/event-organizer-web/target/event-organizer.war
        ````
    
        Properties that can be changed
        
        In core:
        
        * spring.datasource.url
        * spring.datasource.username
        * spring.datasource.password
        * server.port
        * logging.path
        
        In web: 
        
        * logging.path
        * eventorganizer.server.url
        * eventorganizer.server.port
   
## Deployment

Deploy differs from running on a local machine only with the necessary properties.

## Links

* [Trello](https://trello.com/b/nSJOjY0C/event-organizer)
* [Google Docs](https://docs.google.com/document/d/1lE36ZYt2UKgE05sw7RjOb8uRGW951jjprWDDlz2owU8/edit)

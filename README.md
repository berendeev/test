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

You can start the application on the local machine with java -jar following this steps:

   1. For the web module to work correctly, it is necessary that all jsp files be searched in the webapps/jsp directory.
      
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

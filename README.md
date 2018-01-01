Demo Project for Jhipster

Required tools

Java 8 
Node JS 
Yarn/NPM
Yeoman

Step 1 Navigate to project folder and run 
jhipster 

Step 2 select required options, sample as below (For some cases SAAS will not work)



        ██╗ ██╗   ██╗ ████████╗ ███████╗   ██████╗ ████████╗ ████████╗ ███████╗
        ██║ ██║   ██║ ╚══██╔══╝ ██╔═══██╗ ██╔════╝ ╚══██╔══╝ ██╔═════╝ ██╔═══██╗
        ██║ ████████║    ██║    ███████╔╝ ╚█████╗     ██║    ██████╗   ███████╔╝
  ██╗   ██║ ██╔═══██║    ██║    ██╔════╝   ╚═══██╗    ██║    ██╔═══╝   ██╔══██║
  ╚██████╔╝ ██║   ██║ ████████╗ ██║       ██████╔╝    ██║    ████████╗ ██║  ╚██╗
   ╚═════╝  ╚═╝   ╚═╝ ╚═══════╝ ╚═╝       ╚═════╝     ╚═╝    ╚═══════╝ ╚═╝   ╚═╝

                            http://www.jhipster.tech

Welcome to the JHipster Generator v4.13.1
 _______________________________________________________________________________________________________________

  If you find JHipster useful consider supporting our collective https://opencollective.com/generator-jhipster
  Documentation for creating an application: http://www.jhipster.tech/creating-an-app/
 _______________________________________________________________________________________________________________

Application files will be generated in folder: /Users/nagabushankampli/git/jhispter-microservice-example/blog
WARNING! yarn is not found on your computer.

? May JHipster anonymously report usage statistics to improve the tool over time? Yes
? Which *type* of application would you like to create? Microservice gateway
? What is the base name of your application? blog
? As you are running in a microservice architecture, on which port would like your server to run? It should be unique to avoid port conflicts. 8080
? What is your default Java package name? org.jhipster.blog
? Which service discovery server do you want to use? JHipster Registry (uses Eureka, provides Spring Cloud Config support and monitoring dashboards)
? Which *type* of authentication would you like to use? JWT authentication (stateless, with a token)
? Which *type* of database would you like to use? SQL (H2, MySQL, MariaDB, PostgreSQL, Oracle, MSSQL)
? Which *production* database would you like to use? PostgreSQL
? Which *development* database would you like to use? H2 with disk-based persistence
? Do you want to use Hibernate 2nd level cache? Yes
? Would you like to use Maven or Gradle for building the backend? Maven
? Which other technologies would you like to use? Search engine using Elasticsearch
? Which *Framework* would you like to use for the client? Angular 5
? Would you like to enable *SASS* support using the LibSass stylesheet preprocessor? Yes
? Would you like to enable internationalization support? Yes
? Please choose the native language of the application English
? Please choose additional languages to install Spanish
? Besides JUnit and Karma, which testing frameworks would you like to use? Gatling, Protractor
? Would you like to install other generators from the JHipster Marketplace? No


Step 2 optional , in case if we want to skip above mentioned selection update .yo-rc.json and run jhipster 

Step 3 run ./mvnw command to start application

Step 4  you can login using user/user or admin/admin

Step 5 Generate entities using  JDL studio 
http://www.jhipster.tech/jdl-studio/
Sample code 
entity Blog{
	name String required minlength(3)
    handle String required minlength(2)  
}

entity Entry {
    title String required,
    content TextBlob required,
    date ZonedDateTime required
}
 
entity Tag {
    name String required minlength(2)
}

relationship ManyToOne {
    Blog{user(login)} to User,
    Entry{blog(name)} to Blog
}

relationship ManyToMany {
    Entry{tag(name)} to Tag{entry}
}

paginate Entry, Tag with infinite-scroll


Step 6 
jhipster import-jdl ~/Downloads/jhipster-jdl.jh

overwrite master.xml , type a to overwrite this file as well as others

Step 7 
run ./mvnw to start application 
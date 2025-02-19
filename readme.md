Spring PetClinic

Spring PetClinic is a sample application demonstrating a classic 3-layer architecture (Presentation → Service → Repository) with Spring Framework configuration.
Running PetClinic Locally

With Maven

git clone https://github.com/devopswithdayanand/petclinic-war.git
cd spring-framework-petclinic
mvn package

Deploy the generated WAR file to Tomcat:

Copy the WAR file to Tomcat's webapps directory:

cp target/petclinic.war /path/to/tomcat/webapps/

Start Tomcat:

/path/to/tomcat/bin/startup.sh

Access at: http://localhost:8080/petclinic

Database Configuration

By default, PetClinic uses an in-memory H2 database. For MySQL or PostgreSQL, configure the database and update application.properties.

MySQL

docker run -e MYSQL_USER=petclinic -e MYSQL_PASSWORD=petclinic -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=petclinic -p 3306:3306 mysql:5.7.8

PostgreSQL

docker run --name postgres-petclinic -e POSTGRES_PASSWORD=petclinic -e POSTGRES_DB=petclinic -p 5432:5432 -d postgres:9.6.0

Running Tests & Generating JaCoCo Reports

mvn clean test
mvn jacoco:report

View the report at target/site/jacoco/index.html.

Running in an IDE

Prerequisites

Java 17+

Maven 3.5+

Tomcat 10+

Eclipse / IntelliJ IDEA

Setup

Clone the repo: git clone https://github.com/devopswithdayanand/petclinic-war.git

Open in IDE:

Eclipse: File > Import > Maven > Existing Maven project

IntelliJ IDEA: File > Open → Select pom.xml

Build project:

mvn package

Deploy the WAR file to Tomcat as described in the Maven section.

➡️ Visit: http://localhost:8080/petclinic


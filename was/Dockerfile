FROM maven:3.9.2-eclipse-temurin-17 AS builder

WORKDIR /app

COPY pom.xml .
COPY src ./src

RUN mvn clean package -DskipTests -PMySQL

FROM tomcat:9.0-jdk17

COPY --from=builder /app/target/petclinic.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080










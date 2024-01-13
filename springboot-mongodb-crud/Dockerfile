#
# Build stage
#
FROM maven:3.6.3-openjdk-17-slim AS build
COPY src ./src
COPY pom.xml ./
RUN mvn clean package

#
# Package stage
#
FROM openjdk:17-jdk-slim
COPY --from=build ./target/springbootapp.jar /usr/local/lib/demo.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","/usr/local/lib/demo.jar"]
FROM maven:3.8.2-openjdk-11 AS build
COPY . .
RUN mvn clean package -DskipTests

#
# Package stage
#
FROM openjdk:11-jdk-slim
COPY --from=build /target/bookStore-0.0.1-SNAPSHOT.jar bookStore.jar
# ENV PORT=8080
EXPOSE 8080
ENTRYPOINT ["java","-jar","bookStore.jar"]

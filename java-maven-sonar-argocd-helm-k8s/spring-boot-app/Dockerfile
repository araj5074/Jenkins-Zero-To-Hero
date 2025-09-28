# Stage 1: build
FROM maven:3.9.6-eclipse-temurin-17 AS builder
WORKDIR /opt/app
COPY pom.xml .
COPY src ./src
RUN mvn clean package -DskipTests

# Stage 2: runtime
FROM eclipse-temurin:17-jre-alpine
WORKDIR /opt/app
COPY --from=builder /opt/app/target/*.jar app.jar
ENTRYPOINT ["java","-jar","app.jar"]

# Use Java 17 instead of 11
FROM eclipse-temurin:17-jre-alpine

# Path to artifact built by Maven
ARG artifact=target/spring-boot-web.jar

WORKDIR /opt/app

# Copy built artifact into image
COPY ${artifact} app.jar

# Run the app
ENTRYPOINT ["java","-jar","app.jar"]

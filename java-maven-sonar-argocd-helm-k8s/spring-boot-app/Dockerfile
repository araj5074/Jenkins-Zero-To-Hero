FROM maven:3.9.6-eclipse-temurin-17-alpine

USER root

# Install docker CLI
RUN apk add --no-cache docker-cli

# Optional: clean up
RUN rm -rf /var/cache/apk/*

# Path to artifact built by Maven
ARG artifact=target/spring-boot-web.jar

WORKDIR /opt/app

# Copy built artifact into image
COPY ${artifact} app.jar

# Run the app
ENTRYPOINT ["java","-jar","app.jar"]

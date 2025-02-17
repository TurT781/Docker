### Stage 1 builder ###

FROM maven:3.9.6-eclipse-temurin-21-alpine AS builder
WORKDIR /app
COPY pom.xml .
RUN mvn dependency:resolve
COPY . .
RUN mvn package

###Stage 2 builder ###

FROM eclipse-temurin:21-jre-alpine
WORKDIR /app
COPY --from=builder /app/target/worker-jar-with-dependencies.jar .
EXPOSE 80
CMD [ "java", "-jar", "worker-jar-with-dependencies.jar" ]
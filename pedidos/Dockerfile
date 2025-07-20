FROM maven:3.9-eclipse-temurin-21-alpine AS build
WORKDIR /app
COPY pom.xml .
COPY src ./src
RUN mvn clean package -DskipTests

FROM eclipse-temurin:21-jre-alpine-3.21
WORKDIR /app
COPY --from=build /app/target/pedidos-0.0.1-SNAPSHOT.jar .

CMD [ "java", "-jar", "pedidos-0.0.1-SNAPSHOT.jar"]

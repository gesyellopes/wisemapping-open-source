# Etapa 1: Build com Maven + Java 21
FROM maven:3.9.6-eclipse-temurin-21 as builder
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

# Etapa 2: Runtime
FROM amazoncorretto:21.0.2
WORKDIR /app
COPY --from=builder /app/target/wisemapping-api.jar wisemapping-api.jar
EXPOSE 8080
CMD ["java", "-jar", "wisemapping-api.jar"]


# Etapa 1: Construcción (Builder)
FROM maven:3.9-eclipse-temurin-17 AS builder
WORKDIR /app

# Copiamos el archivo de dependencias de Java
COPY pom.xml .
RUN mvn dependency:go-offline -B

# Copiamos el código fuente y compilamos
COPY src ./src
RUN mvn clean package -DskipTests


# Etapa 2: Producción (Runtime)
FROM eclipse-temurin:17-jre-alpine
WORKDIR /app

# Creamos un usuario sin privilegios root (Regla de la pauta)
RUN addgroup -S springgroup && adduser -S springuser -G springgroup
USER springuser:springgroup

# Copiamos el archivo compilado desde la etapa 1
COPY --from=builder /app/target/*.jar app.jar

EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
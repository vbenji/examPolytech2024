FROM maven:3.9-eclipse-temurin-8 AS builder

WORKDIR /app

COPY . .

RUN mvn clean package -DskipTests

FROM eclipse-temurin:8-jre

WORKDIR /app

COPY --from=builder /app/target/*.jar exam-back.jar

EXPOSE 8448

LABEL maintainer="Vincent R"

CMD ["java","-jar","exam-back.jar"]
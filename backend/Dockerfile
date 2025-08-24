FROM gradle:7.6 AS build

WORKDIR /home/gradle/project

COPY . .

RUN ./gradlew clean build

FROM openjdk:17

WORKDIR /app

ARG JAR_FILE=build/libs/quotes-0.0.1-SNAPSHOT.jar

COPY --from=build /home/gradle/project/${JAR_FILE} app.jar

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "app.jar"]
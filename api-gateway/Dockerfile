FROM gradle:6.9.3-jdk17-alpine AS build
COPY --chown=gradle:gradle . /home/gradle/src
WORKDIR /home/gradle/src
RUN gradle build


FROM openjdk:17-alpine
WORKDIR /app
EXPOSE 8080
COPY --from=build /app/target/*.jar app.jar
ENV JAVA_ARGS=""
ENTRYPOINT exec java $JAVA_OPTS -jar app.jar
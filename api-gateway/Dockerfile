FROM openjdk:17-alpine
WORKDIR /app
EXPOSE 8080
COPY --from=build /app/target/*.jar app.jar
ENV JAVA_ARGS=""
ENTRYPOINT exec java $JAVA_OPTS -jar app.jar
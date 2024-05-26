Docker file
-----------------

FROM eclipse-temurin:17-jdk-alpine
VOLUME /tmp
ARG JAR_FILE
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java","-jar","/app.jar"]

--------------------------------

CMDS

docker build --build-arg JAR_FILE=target/*.jar -t myorg/myapp .

docker build -t back-end .


docker run -p 8080:8080 back-end

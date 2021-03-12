From maven:3.5.4-jdk-8-alpine as maven
COPY ./pom.xml ./pom.xml
COPY ./src ./src
RUN mvn clean package

 WORKDIR /Hello
# copy the packaged jar file into our docker image
COPY --from=maven target/helloworld-0.0.1-SNAPSHOT.jar ./Hello/helloworld.jar
# set the startup command to execute the jar
CMD ["java", "-jar", "./Hello/helloworld.jar"]

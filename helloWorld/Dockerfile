From maven:3.5.4-jdk-8-alpine as maven
COPY ./pom.xml ./pom.xml
COPY ./src ./src
RUN mvn clean package

 WORKDIR /Hello
# copy the packaged jar file into our docker image
COPY target/Calculator-0.0.1-SNAPSHOT.jar ./calculator/Calculator.jar
COPY --from=maven target/Helloworld-0.0.1.jar ./adevguide/SimpleJavaProject.jar
# set the startup command to execute the jar
CMD ["java", "-jar", "./calculator/Calculator.jar"]

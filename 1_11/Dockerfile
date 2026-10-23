FROM amazoncorretto:8u504-al2-native-jdk

WORKDIR /usr/src

COPY . .

# The issue was that locally the mvnw script had Windows line endings (\r\n called CRLF).
# Replace line 8 in your Dockerfile with this line:
RUN yum update -y && yum install -y dos2unix && dos2unix mvnw && chmod +x mvnw

RUN ./mvnw package

CMD ["java", "-jar", "./target/docker-example-1.1.3.jar"]

EXPOSE 8080

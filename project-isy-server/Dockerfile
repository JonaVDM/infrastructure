FROM openjdk:18.0.2

WORKDIR /root
COPY server.jar server.jar

EXPOSE 7789
EXPOSE 8081

RUN ["java", "-jar", "server.jar", "--set-password", "secret"]
CMD ["java", "-jar", "server.jar"]

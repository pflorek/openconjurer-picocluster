FROM aarch64/openjdk:8-jdk

COPY service-monolith-1.0-SNAPSHOT.jar /opt/service-monolith-1.0-SNAPSHOT.jar

EXPOSE 8080

CMD java -jar -Dspring.profiles.active=container /opt/service-monolith-1.0-SNAPSHOT.jar

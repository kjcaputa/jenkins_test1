FROM openjdk:8-jdk-alpine
VOLUME /tmp
ARG DEPENDENCY=target/dependency
ENTRYPOINT ["java","-cp","app:app/lib/*","com.thoughtworks.test.Application"]

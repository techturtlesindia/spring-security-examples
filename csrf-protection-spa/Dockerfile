FROM openjdk:8u131-jre-alpine
MAINTAINER Maksim Kostromin <daggerok@gmail.com>
RUN mkdir -p /opt/app \
 && touch /opt/app/app.jar \
 && apk --no-cache add curl
WORKDIR /opt/app
VOLUME ["/opt/app"]
ENTRYPOINT ["java", "-jar", "/opt/app/app.jar"]
EXPOSE 8080
HEALTHCHECK --interval=1s --timeout=1s --retries=55 CMD curl -f http://127.0.0.1:8080/ || exit 1
COPY ./build/libs/*.jar ./app.jar

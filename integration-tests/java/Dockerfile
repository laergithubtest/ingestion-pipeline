FROM openjdk:8-jdk

RUN apt-get update
RUN apt-get install -y maven

RUN mkdir /root/.m2

COPY maven.settings.xml /root/.m2/settings.xml
#COPY . /code
VOLUME /code

WORKDIR /code

ADD https://github.com/ufoscout/docker-compose-wait/releases/download/2.2.1/wait /wait
RUN chmod +x /wait

CMD mvn clean install && /wait && java -cp target/integration-1.0-SNAPSHOT.jar:target/lib/* ai.laer.integration.KbAnalyzerIntegrationTests

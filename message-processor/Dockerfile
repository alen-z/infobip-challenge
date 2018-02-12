FROM openjdk:8u151-jre-stretch

ARG ARTIFACTORY_PROCESSOR_URL=http://ec2-35-177-100-87.eu-west-2.compute.amazonaws.com:8081/artifactory/libs-snapshot-local/message-processor/message-processor/1.0-SNAPSHOT/message-processor-1.0-SNAPSHOT.jar
ARG JAR_CONFIG_URL=https://raw.githubusercontent.com/alen-z/messaging-example/master/message-processor/etc/config.properties

ENV JAR_FILENAME message-processor-1.0-SNAPSHOT.jar
ENV APP_PATH /usr/src/message-processor

# Fetch .jar and create directory
RUN wget -P $APP_PATH $ARTIFACTORY_PROCESSOR_URL

WORKDIR $APP_PATH

# Fetch config as config.properties - hardcoded for easy run command
RUN wget -O config.properties $JAR_CONFIG_URL

CMD ["sh", "-c", "java -jar $JAR_FILENAME config.properties"]
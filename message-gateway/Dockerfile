FROM tomcat:7.0.84-jre8

ARG ARTIFACT_GATEWAY_URL=http://ec2-35-177-100-87.eu-west-2.compute.amazonaws.com:8081/artifactory/libs-snapshot-local/messaging-gateway/message-gateway/1.0-SNAPSHOT/message-gateway-1.0-SNAPSHOT.war

# Prepare Tomcat managing user for testing
COPY conf/tomcat-users.xml $CATALINA_HOME/conf

# Clean current ROOT application and deploy ours
RUN rm -rf $CATALINA_HOME/webapps/ROOT && wget -O $CATALINA_HOME/webapps/ROOT.war $ARTIFACT_GATEWAY_URL
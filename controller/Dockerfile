FROM jenkins/jenkins:2.319.2-lts-alpine
USER root
RUN apk update && apk -v add bash git docker
COPY plugins.yaml /tmp/
RUN chown jenkins:jenkins /tmp/plugins.yaml
USER jenkins
RUN jenkins-plugin-cli --verbose --plugin-file /tmp/plugins.yaml
USER root
RUN rm -f /tmp/plugins.yaml

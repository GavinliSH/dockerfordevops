# FROM openjdk:8u191-jdk-windowsservercore-ltsc2016
FROM openjdk:8u191-jdk-nanoserver-sac2016

ENV HOME /jenkins
ENV JENKINS_VERSION 2.0
RUN mkdir \jenkins
# RUN powershell -Command "wget -Uri https://updates.jenkins-ci.org/download/war/2.0/jenkins.war -UseBasicParsing -OutFile /jenkins/jenkins.war"
COPY package/jenkins.war /jenkins/
COPY package/Git-2.19.1-64-bit.exe /jenkins/

EXPOSE 8080
EXPOSE 50000

# Run jenkins
CMD java -jar C:\\jenkins\\jenkins.war


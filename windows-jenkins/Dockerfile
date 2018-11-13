# FROM openjdk:8u191-jdk-windowsservercore-ltsc2016
FROM openjdk:8u191-jdk-windowsservercore-ltsc2016

ENV HOME /jenkins
ENV JENKINS_VERSION 2.0
RUN mkdir \jenkins
COPY package/jenkins.war /jenkins/
# 配置git
COPY package/MinGit-2.12.2.2-64-bit.zip MinGit.zip
RUN Expand-Archive c:\MinGit.zip -DestinationPath c:\MinGit 
RUN $env:PATH = $env:PATH + ';C:\MinGit\cmd\;C:\MinGit\cmd'; \
    "& Set-ItemProperty -Path 'HKLM:\SYSTEM\CurrentControlSet\Control\Session Manager\Environment\' -Name Path -Value $env:PATH"
RUN $env:PATH
# 开放端口
EXPOSE 8080
EXPOSE 50000

# Run jenkins

CMD java -jar C:\\jenkins\\jenkins.war

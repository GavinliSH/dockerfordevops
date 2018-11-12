FROM gocd/gocd-agent-centos-7:v18.10.0
MAINTAINER xiaoguang.li

# 变量
ENV jdk_version=jdk1.8.0_181
ENV jdk_package=jdk-8u181-linux-x64.tar.gz
ENV gradle_package=gradle-3.4.1-bin.zip
ENV gradle_version=gradle-3.4.1

# 安装JDK
RUN mkdir /var/tmp/jdk
COPY "packages/${jdk_package}" /var/tmp/jdk 
# RUN wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie"  -P /var/tmp/jdk http://download.oracle.com/otn/java/jdk/8u181-b13/96a7b8442fe848ef90c96a2fad6ed6d1/jdk-8u181-linux-x64.tar.gz
RUN tar xzf "/var/tmp/jdk/${jdk_package}" -C /var/tmp/jdk
ENV JAVA_HOME "/var/tmp/jdk/${jdk_version}"
ENV PATH $PATH:$JAVA_HOME/bin
# 安装Gradle
RUN mkdir /var/tmp/gradle
COPY "packages/${gradle_package}" /var/tmp/gradle
RUN unzip -d /opt/gradle "/var/tmp/gradle/${gradle_package}"
ENV PATH $PATH:"/opt/gradle/${gradle_version}/bin"
RUN gradle -v


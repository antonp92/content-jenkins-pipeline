# Dockerfile based on the latest CentOS 7 image - non privileged user entry

FROM centos:latest
MAINTAINER antonp92

RUN echo "EXPORT 192.168.0.0/24" >> /etc/exports.list

#Add a user named "user"
RUN useradd -ms /bin/bash user

#Update packages
RUN yum update -y

#Install net-tools and wget
RUN yum install -y net-tools wget

RUN echo "EXPORT 192.168.0.0/24" >> /etc/exports.list

#Download Java, accept license, dont't check certificate/no cookies
RUN cd ~ && wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/8u60-b27/jre-8u60-linux-x64.rpm"

#Install the downloaded Java rpm using yum localinstall, which will download all the required dependencies (rpm -i will only install the package)
RUN yum localinstall -y ~/jre-8u60-linux-x64.rpm

#su user
USER user

#add JAVA_HOME directory to .bashrc of "user"
RUN cd ~ && echo "export JAVA_HOME=/usr/java/jdk1.8.0/jre" >> /home/user/.bashrc

#System wide environment variable (affects all users)
ENV JAVA_BIN /usr/java/jdk1.8.0/jre/bin

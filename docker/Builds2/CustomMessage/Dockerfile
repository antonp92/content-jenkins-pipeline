# Dockerfile based on the latest CentOS 7 image - non privileged user entry

FROM centos:latest
MAINTAINER antonp92

RUN echo "EXPORT 192.168.0.0/24" >> /etc/exports.list
RUN useradd -ms /bin/bash user
USER user

# Dockerfile based on the latest CentOS 7 image - non privileged user entry

FROM centos:latest
MAINTAINER antonp92

RUN useradd -ms /bin/bash user

#The CMD command executes a command after the container runs
CMD "echo" "This is a custom container message"

USER user

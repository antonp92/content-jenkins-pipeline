# Dockerfile based on the latest CentOS 7 image - non privileged user entry

FROM centos:latest
MAINTAINER antonp92

RUN useradd -ms /bin/bash user

#overrides other echo commands
ENTRYPOINT echo "This command will display this message on EVERY container that is run from it"

USER user

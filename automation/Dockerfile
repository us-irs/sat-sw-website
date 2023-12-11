# npm base container, we need to install some npm dependencies as part of the website build.
FROM node:latest

RUN apt-get update
RUN apt-get --yes upgrade
# Required in case tzdata is a installed, won't install otherwise
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get --yes install rsync openssh-client

# Install hugo v0.121.1
RUN curl -sSL https://github.com/gohugoio/hugo/releases/download/v0.121.1/hugo_0.121.1_Linux-64bit.tar.gz | tar -xz --directory /usr/local/bin

#ssh needs a valid user to work
RUN adduser --uid 114 jenkins

# add documentation server to known hosts
RUN echo "|1|/LzCV4BuTmTb2wKnD146l9fTKgQ=|NJJtVjvWbtRt8OYqFgcYRnMQyVw= ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBNL8ssTonYtgiR/6RRlSIK9WU1ywOcJmxFTLcEblAwH7oifZzmYq3XRfwXrgfMpylEfMFYfCU8JRqtmi19xc21A=" >> /etc/ssh/ssh_known_hosts
RUN echo "|1|CcBvBc3EG03G+XM5rqRHs6gK/Gg=|oGeJQ+1I8NGI2THIkJsW92DpTzs= ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBNL8ssTonYtgiR/6RRlSIK9WU1ywOcJmxFTLcEblAwH7oifZzmYq3XRfwXrgfMpylEfMFYfCU8JRqtmi19xc21A=" >> /etc/ssh/ssh_known_hosts

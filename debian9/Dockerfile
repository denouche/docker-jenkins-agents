FROM debian:9

RUN apt-get update \
    && apt-get install -y apt-utils

RUN apt-get install -y \
        openssh-server \
        openjdk-8-jdk \
        make \
        git-core \
        curl \
    && apt-get clean

RUN mkdir -p /var/run/sshd
RUN mkdir -p /root/tools
RUN mkdir /root/workspace

EXPOSE 22


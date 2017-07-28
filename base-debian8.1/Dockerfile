FROM debian:8.1

# Needed to get openjdk-8-jdk
RUN echo "deb http://ftp.debian.org/debian jessie-backports main" >> /etc/apt/sources.list

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


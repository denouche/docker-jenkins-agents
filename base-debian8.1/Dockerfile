FROM debian:8.1

RUN echo "deb http://ftp.debian.org/debian jessie-backports main" >> /etc/apt/sources.list

RUN apt-get update \
    && apt-get install -y apt-utils

RUN apt-get install -y \
        openssh-server \
        openjdk-8-jdk \
        make \
        git-core \
        curl \
        docker.io \
    && apt-get clean

ENV USER jenkins
ENV GROUP users

RUN useradd --create-home --shell /bin/bash --gid users --groups docker $USER \
    && mkdir /var/run/sshd \
    && mkdir -p /home/$USER/tools \
    && chown -R $USER:$GROUP /home/$USER/tools \
    && mkdir /home/$USER/workspace \
    && chown -R $USER:$GROUP /home/$USER/workspace

ADD docker-entrypoint.sh /docker-entrypoint.sh

ENTRYPOINT [ "/docker-entrypoint.sh" ]

CMD [ "/bin/bash" ]


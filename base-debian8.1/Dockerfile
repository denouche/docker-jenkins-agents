FROM debian:8.1

RUN apt-get update \
    && apt-get install -y \
        openssh-server \
        openjdk-7-jdk \
        make \
        git-core \
    && apt-get clean

ENV USER jenkins
ENV GROUP users

RUN adduser --ingroup $GROUP --disabled-password --gecos "" $USER \
    && echo "$USER:$USER" | chpasswd \
    && mkdir /var/run/sshd \
    && mkdir -p /home/$USER/tools \
    && chown -R $USER:$GROUP /home/$USER/tools \
    && mkdir /home/$USER/workspace \
    && chown -R $USER:$GROUP /home/$USER/workspace




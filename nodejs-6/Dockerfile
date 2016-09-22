FROM denouche/jenkins-agents:base-debian8.1

RUN apt-get update \
    && apt-get install -y build-essential \
        libkrb5-dev \
        curl \
        python \
    && apt-get clean

USER $USER

ENV NODE_VERSION 6.6.0

RUN cd \
    && curl -SLO "http://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.gz" \
    && tar -xzf "node-v$NODE_VERSION-linux-x64.tar.gz" -C /home/$USER/tools/ \
    && rm "node-v$NODE_VERSION-linux-x64.tar.gz" \
    && ln -s /home/$USER/tools/node-v$NODE_VERSION-linux-x64 /home/$USER/tools/nodejs

ENV PATH $PATH:/home/$USER/tools/node-v$NODE_VERSION-linux-x64/bin

RUN npm install -g npm \
    && npm install -g node-gyp grunt-cli \
    && npm update

USER root


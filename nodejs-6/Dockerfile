FROM denouche/jenkins-agents:base-debian8.1

RUN apt-get update \
    && apt-get install -y build-essential \
        libkrb5-dev \
        curl \
        python \
    && apt-get clean

ENV NODE_VERSION 6.11.1

RUN cd \
    && curl -SLO "http://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.gz" \
    && tar -xzf "node-v$NODE_VERSION-linux-x64.tar.gz" -C /root/tools/ \
    && rm "node-v$NODE_VERSION-linux-x64.tar.gz" \
    && ln -s /root/tools/node-v$NODE_VERSION-linux-x64 /root/tools/nodejs

ENV PATH $PATH:/root/tools/node-v$NODE_VERSION-linux-x64/bin

RUN npm install -g node-gyp grunt-cli

USER root


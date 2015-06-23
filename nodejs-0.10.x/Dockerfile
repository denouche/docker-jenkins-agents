FROM denouche/jenkins-agents:base-debian8.1

RUN apt-get update \
    && apt-get install -y build-essential \
        libkrb5-dev \
        curl \
        python \
    && apt-get clean

ENV USER jenkins
ENV GROUP users

ENV NODE_VERSION 0.10.39

RUN curl -SLO "http://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.gz" \
    && tar -xzf "node-v$NODE_VERSION-linux-x64.tar.gz" -C /home/$USER/tools/ \
    && rm "node-v$NODE_VERSION-linux-x64.tar.gz" \
    && chown -R $USER:$GROUP /home/$USER/tools/node-v$NODE_VERSION-linux-x64 \
    && ln -s /home/$USER/tools/node-v$NODE_VERSION-linux-x64 /home/$USER/tools/nodejs

RUN echo "export PATH=\$PATH:/home/$USER/tools/node-v$NODE_VERSION-linux-x64/bin" >> /home/$USER/.bashrc
RUN su - $USER -c "/bin/bash -i -c 'npm install -g node-gyp grunt-cli'"




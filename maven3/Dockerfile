FROM denouche/jenkins-agents:base-debian8.1

ENV MAVEN_VERSION 3.3.9

RUN cd \
    && curl -SLO "https://archive.apache.org/dist/maven/maven-3/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz" \
    && tar -xzf "apache-maven-$MAVEN_VERSION-bin.tar.gz" -C /root/tools/ \
    && rm "apache-maven-$MAVEN_VERSION-bin.tar.gz"

ENV PATH $PATH:/root/tools/apache-maven-$MAVEN_VERSION/bin


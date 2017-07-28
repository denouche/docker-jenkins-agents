FROM denouche/jenkins-agents:base-debian8.1

RUN apt-get update \
    && apt-get install -y \
        docker.io \
    && apt-get clean

ADD docker-entrypoint.sh /docker-entrypoint.sh

ENTRYPOINT [ "/docker-entrypoint.sh" ]

CMD [ "/bin/bash" ]

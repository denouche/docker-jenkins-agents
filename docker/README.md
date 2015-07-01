# Docker image

## Parameters

To be able to use host docker daemon from container we need that docker group in the container to have the same id that docker group in host

So to run this image you can try a command like:

```bash
$ docker run -e "DOCKER_GROUP_ID=$(getent group docker | cut -d':' -f3)" -v /var/run/docker.sock:/var/run/docker.sock denouche/jenkins-agents:docker
```





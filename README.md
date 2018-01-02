gcp-jenkins2
====

Google Cloud SDK enabled Jenkins2 Docker image based on Google Cloud's Jenkins 2 image, launcher.gcr.io/google/jenkins2.

For now, it has a size issue;
* launcher.gcr.io/google/jenkins2: 490MB
* cjongseok/gcp-jenkins2: 1.48GB

Because it compiles Python in itself. Google Cloud SDK has a Python dependency, but Debian package manager APT and repositories (e.g., ppa:deadsnakes/ppa) don't support Python installation on Debian jessie, which launcher.gcr.io/google/jenkins2 is based on.

Usage
---
Pull the docker image from the Docker Hub [Docker Hub](https://hub.docker.com/r/cjongseok/gcp-jenkins2/).
```sh
docker pull cjongseok/gcp-jenkins2:latest
```

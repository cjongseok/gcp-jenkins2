gcp-jenkins2
====

Google Cloud SDK enabled Jenkins2 Docker image based on launcher.gcr.io/google/jenkins2.

For now, it has a size issue;
* launcher.gcr.io/google/jenkins2: 490MB
* cjongseok/gcp-jenkins2: 1.48GB

Because it compiles Python in itself. Google Cloud SDK has a Python dependency, but default APT repositories and its 3rd party repositories (e.g., ppa:deadsnakes/ppa) don't support Python installation on Debian jessie, which launcher.gcr.io/google/jenkins2 stands on.

Usage
---
Pull and run the docker image from [Docker Hub](https://hub.docker.com/r/cjongseok/gcp-jenkins2/).
```sh
docker pull cjongseok/gcp-jenkins2:latest
docker run -d -p 8080:8080 -p 50000:50000 --name jenkins2 cjongseok/gcp-jenkins2:latest 
```

#### Ports
* 8080: web UI
* 50000: API endpoint

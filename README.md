gcp-jenkins2
====

Google Cloud SDK enabled Jenkins2 Docker image based on the Jenkins2 image of [Google Cloud Laucher](https://console.cloud.google.com/launcher/details/google/jenkins2).

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
Or run Jenkins on Kubernetes.
```sh
# Create a Deploy
kubectl create -f jenkins.yml
# Create a Service
kubectl create -f jenkins-service.yml
```

#### Ports
* 8080: web UI
* 50000: API endpoint

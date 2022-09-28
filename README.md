# MultiPaper images

MultiPaper Docker images as used in [MultiPaper Helm](https://github.com/MultiPaperK8s/MultiPaperHelm).
Contains the latest version of MultiPaper server and master backed by hardened Alpine based OpenJDK images.

### Prerequisits
- Docker (version 20.10.x and above)
- [Kind](https://kind.sigs.k8s.io/) for testing the images 
## Getting Started
- Clone the project
- navigate to the project root in your terminal  
To build the dockerfile images locally run the following commands:  

```sh
# Builds the server
docker build -t multipaper-server -f Dockerfile.server .

# Builds the master
docker build -t multipaper-master -f Dockerfile.master .
```

Note that in both the dockerfiles you can and _should_ change the version number for the build of multipaper you want to use

```dockerfile
# In the server dockerfile
ARG VERSION=1.19.2
ARG BUILD=35

# In the master dockerfile
ARG MULTIPAPER_VERSION=1.19.2
ARG MULTIPAPER_BUILD=35
ARG MASTER_VERSION=2.10.1
```
The versions must line up with the versions released on the Multipaper Downloads page here: https://multipaper.io/download.html




### Running
You will need to setup a local kind cluster to test the images locally, alternatively you can use any other kubernetes enviornment to test them. However other kubernetes enviornments for now is an exercise left for the reader. GLHF. 


To load the images into a local Kind cluster
```sh
kind load docker-image multipaper-master
kind load docker-image multipaper-server
```

To run the server clone the helm repository: https://github.com/MultiPaperK8s/MultiPaperHelm
and update the `image` fields in the `values.yaml` file
For example
```yml
  image:
    repository: "remcospigot/multipaper-master"
    # Tag of the Docker image to be used.
    # Defaults to the Chart's app version if left blank.
    tag: "2.8.8"
    pullPolicy: IfNotPresent

# The above would be changed to

  image:
    repository: "multipaper-master"
    # Tag of the Docker image to be used.
    # Defaults to the Chart's app version if left blank.
    tag: "latest"
    pullPolicy: IfNotPresent

```
for the server image section its similar

```yml
  image:
    repository: "remcospigot/multipaper"
    # Tag of the Docker image to be used.
    # Defaults to the Chart's app version if left blank.
    tag: "1.18.2-95"
    pullPolicy: IfNotPresent

# Would be changed to

  image:
    repository: "multipaper-server"
    # Tag of the Docker image to be used.
    # Defaults to the Chart's app version if left blank.
    tag: "latest"
    pullPolicy: IfNotPresent
```
Note that the repository changes must correspond to the `-t myCoolDockerBuildName` which is the reference kind uses in order to know which image to pull for. 

After changing the `values.yaml` run the helm chart from the root of the https://github.com/MultiPaperK8s/MultiPaperHelm repository.

```sh
helm install myCoolReleaseNameHere .
```

## Images
Overview of the images currently available for usage.

### Master
[Master image](https://hub.docker.com/r/remcospigot/multipaper-master/tags) based on OpenJDK Eclipse Temurin 17 Alpine 3.15.4

### Server
[Server image](https://hub.docker.com/r/remcospigot/multipaper/tags) based on OpenJDK Eclipse Temurin 17 Alpine 3.15.4

### Debug/Init
[Init image](https://hub.docker.com/r/remcospigot/multipaper-init/tags) with envsubst based on alpine 3.16.0
# MultiPaper images

> :warning: **This image has been deprecated**: MultiPaper no longer supports 1.18.2 and neither will this repository. 
> The only updates that may be patched through are security updates.
> No new releases will be made either, everything will be "unreleased" and patched over old versions on the respected Docker registries. 

MultiPaper Docker images as used in [MultiPaper Helm](https://github.com/MultiPaperK8s/MultiPaperHelm).
Contains the latest version of MultiPaper server and master backed by hardened Alpine based OpenJDK images.

## Getting Started
Before getting started, you might want to install the following dependencies:

### Prerequisits
- Docker (version 20.10.x and above)

### Running

Coming Soon.

## Images
Overview of the images currently available for usage.

### Master
[Master image](https://hub.docker.com/r/remcospigot/multipaper-master/tags) based on OpenJDK Eclipse Temurin 17.0.5+8 Alpine 3.17.0

### Server
[Server image](https://hub.docker.com/r/remcospigot/multipaper/tags) based on OpenJDK Eclipse Temurin 17.0.5+8 Alpine 3.17.0

### Debug/Init
[Init image](https://hub.docker.com/r/remcospigot/multipaper-init/tags) with envsubst based on alpine 3.17.0
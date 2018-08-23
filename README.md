Cloud9 v3 Dockerfile - Node, NVM, and PM2 Enabled
=============

**Modified by David Mallon forked from Kevin Delfour**

**Added needed tools**
- Node Version Manager (nvm)
- Node Version 8.x
- Advanced, production process manager (PM2)
 


This repository contains Dockerfile of Cloud9 IDE for Docker's automated build published to the public Docker Hub Registry.

# Base Docker Image
[kdelfour/supervisor-docker](https://registry.hub.docker.com/u/kdelfour/supervisor-docker/)

# This Docker Image
[mallond/cloud9](https://registry.hub.docker.com/u/mallond/cloud9/)

# Installation

## Install Docker.

Download automated build from public Docker Hub Registry: docker pull mallond/cloud9

(alternatively, you can build an image from Dockerfile: docker build -t="mallond/cloud9" github.com/mallond/cloud9-docker)

## Usage

    docker run -it -d -p 80:80 mallond/cloud9
    
You can add a workspace as a volume directory with the argument *-v /your-path/workspace/:/workspace/* like this :

    docker run -it -d -p 80:80 -v /your-path/workspace/:/workspace/ mallond/cloud9
    
## Build and run with custom config directory

Get the latest version from github

    git clone https://github.com/mallond/cloud9-docker
    cd cloud9-docker/

Build it

    sudo docker build --force-rm=true --tag="$USER/cloud9-docker:latest" .
    
And run

    sudo docker run -d -p 80:80 -v /your-path/workspace/:/workspace/ $USER/cloud9-docker:latest
    
Enjoy !!    

# Jitsi Meet on Docker

![](resources/jitsi-docker.png)

[Jitsi](https://jitsi.org/) is a set of Open Source projects that allows you to easily build and deploy secure videoconferencing solutions.

[Jitsi Meet](https://jitsi.org/jitsi-meet/) is a fully encrypted, 100% Open Source video conferencing solution that you can use all day, every day, for free — with no account needed.

This repository contains the necessary tools to run a Jitsi Meet stack on [Docker](https://www.docker.com) using [Docker Compose](https://docs.docker.com/compose/).

All our images are published on [DockerHub](https://hub.docker.com/u/jitsi/).

## Supported architectures

Starting with `stable-7289-1` the published images are available for `amd64` and `arm64` with the exception of `jigasi`.

## Tags

These are the currently published tags for all our images:

Tag | Description
-- | --
`stable` | Points to the latest stable release
`stable-NNNN-X` | A stable release
`unstable` | Points to the latest unstable release
`unstable-YYYY-MM-DD` | Daily unstable release
`latest` | Deprecated, no longer updated (will be removed)

## Installation

The installation manual is available [here](https://jitsi.github.io/handbook/docs/devops-guide/devops-guide-docker).


Quick start

In order to quickly run Jitsi Meet on a machine running Docker and Docker Compose, follow these steps:

    Download and extract the latest release. DO NOT clone the git repository. See below if you are interested in running test images.

    Create a .env file by copying and adjusting env.example:

    cp env.example .env

Set strong passwords in the security section options of .env file by running the following bash script

./gen-passwords.sh

Create required CONFIG directories

    For linux: 

mkdir -p ~/.jitsi-meet-cfg/{web,transcripts,prosody/config,prosody/prosody-plugins-custom,jicofo,jvb,jigasi,jibri}

    For Windows: 

echo web,transcripts,prosody/config,prosody/prosody-plugins-custom,jicofo,jvb,jigasi,jibri | % { mkdir "~/.jitsi-meet-cfg/$_" }

Run docker-compose up -d





### Kubernetes

If you plan to install the jitsi-meet stack on a Kubernetes cluster you can find tools and tutorials in the project [Jitsi on Kubernetes](https://github.com/jitsi-contrib/jitsi-kubernetes).

## TODO


* Builtin TURN server.


## DO not forget to put this in the .env
```
ENABLE_XMPP_WEBSOCKET=0 ############ !!!!!!!!
```

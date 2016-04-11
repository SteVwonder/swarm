# Notes in reference to ISC 2016 Paper
## Relevant Commits
Commit Description | Commit Links
----------- | ------------
Added I/O types and functions | [04e5604](https://github.com/SteVwonder/dockerclient/commit/04e5604), [e715dd0](https://github.com/SteVwonder/dockerclient/commit/e715dd0)
Merge from upstream repo | [853fb6b](https://github.com/SteVwonder/dockerclient/commit/853fb6b)
Update I/O stats periodically (with /info) | [bebad5c](https://github.com/SteVwonder/dockerclient/commit/bebad5c)
Added I/O to scheduler weight function | [2727c84](https://github.com/SteVwonder/dockerclient/commit/2727c84)


## Relevant Files:
* [types.go](Godeps/_workspace/src/github.com/samalba/dockerclient/types.go)
* [node.go](cluster/node.go)
* [swarm/node.go](cluster/swarm/node.go)
* [cluster.go](cluster/swarm/cluster.go)
* [weighted_node.go](scheduler/strategy/weighted_node.go)

## Paper Information
Stephen Herbein, Ayush Dusia, Aaron Landwehr, Sean McDaniel, Jose Monsalve, Yang Yang, Seetharami R. Seelam, and Michela Taufer. Resource Management for Running HPC Applications in Container Clouds. In _Proceedings of 31st International Supercomputing Conference_, ISC, Leipzig, Germany, June 2016.
```
@inproceedings{Docker-ISC,
author = {Stephen Herbein and Ayush Dusia and Aaron Landwehr and Sean McDaniel and Jose Monsalve and Yang Yang and Seetharami R. Seelam and Michela Taufer},
title={Resource Management for Running HPC Applications in Container Clouds},
booktitle={Proceedings of 31st International Supercomputing Conference},
series = {ISC},
year={2016},
month={June},
address = {Leipzig, Germany},
}
```

# Swarm: a Docker-native clustering system

[![Build Status](https://travis-ci.org/docker/swarm.svg?branch=master)](https://travis-ci.org/docker/swarm)
[![Coverage Status](https://coveralls.io/repos/docker/swarm/badge.svg)](https://coveralls.io/r/docker/swarm)

![Docker Swarm Logo](logo.png?raw=true "Docker Swarm Logo")

Docker Swarm is native clustering for Docker. It turns a pool of Docker hosts
into a single, virtual host.

Swarm serves the standard Docker API, so any tool which already communicates
with a Docker daemon can use Swarm to transparently scale to multiple hosts:
Dokku, Compose, Krane, Flynn, Deis, DockerUI, Shipyard, Drone, Jenkins... and,
of course, the Docker client itself.

Like other Docker projects, Swarm follows the "batteries included but removable"
principle. It ships with a set of simple scheduling backends out of the box, and as
initial development settles, an API will be developed to enable pluggable backends.
The goal is to provide a smooth out-of-the-box experience for simple use cases, and
allow swapping in more powerful backends, like Mesos, for large scale production
deployments.

## Installation and documentation

Full documentation [is available here](http://docs.docker.com/swarm/).

## Development installation

You can download and install from source instead of using the Docker image.

Ensure you have golang, godep and git client installed. For example, on Ubuntu you'd run:

```bash
apt-get install golang git
go get github.com/tools/godep
```

You may need to set `$GOPATH`, e.g `mkdir ~/gocode; export GOPATH=~/gocode`.

Then install the `swarm` binary:

```bash
mkdir -p $GOPATH/src/github.com/docker/
cd $GOPATH/src/github.com/docker/
git clone https://github.com/docker/swarm
cd swarm
godep go install .
```

From here, you can follow the instructions [in the main documentation](http://docs.docker.com/swarm/),
replacing `docker run swarm` with just `swarm`.

## Participating

We welcome pull requests and patches; come say hi on IRC, #docker-swarm on freenode.

Our planning process and release cycle are detailed on the [wiki](https://github.com/docker/swarm/wiki)

## Creators

**Andrea Luzzardi**

- <http://twitter.com/aluzzardi>
- <http://github.com/aluzzardi>

**Victor Vieux**

- <http://twitter.com/vieux>
- <http://github.com/vieux>

## Copyright and license

Code and documentation copyright 2014-2015 Docker, inc. Code released under the
Apache 2.0 license.

Docs released under Creative commons.

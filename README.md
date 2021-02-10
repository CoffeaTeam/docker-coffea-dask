# Dask Docker image for Coffea Columnar Object Framework For Effective Analysis

![CI/CD status](https://github.com/CoffeaTeam/docker-coffea-dask/workflows/PullRequest/badge.svg)
![GitHub issues](https://img.shields.io/github/issues/coffeateam/docker-coffea-dask)
![GitHub pull requests](https://img.shields.io/github/issues-pr/coffeateam/docker-coffea-dask)

Latest DockerHub Images: https://hub.docker.com/orgs/coffeateam/repositories

| Image           | Description                                   |  Size | Pulls | Version | Layers |
|-----------------|-----------------------------------------------|--------------|-------------|-------------|-------------|
| coffea-dask     | Dask Coffea image with latest XrootD and CA certicates            | ![](https://img.shields.io/docker/image-size/coffeateam/coffea-dask?sort=date) | ![](https://img.shields.io/docker/pulls/coffeateam/coffea-dask?sort=date) | ![](https://img.shields.io/docker/v/coffeateam/coffea-dask?sort=date) | ![](https://img.shields.io/microbadger/layers/coffeateam/coffea-dask)

## TL;DR

```console
$ docker run -it --name docker-coffea-dask coffeateam/coffea-dask
```
or, if using singularity and [CVMFS](https://cernvm.cern.ch/fs/) is available,
```console
$ singularity shell -B ${PWD}:/work /cvmfs/unpacked.cern.ch/registry.hub.docker.com/coffeateam/coffea-dask:latest
```

## Get this image

The recommended way to get the Coffea Dask Docker image is to pull the prebuilt image from the [Docker Hub Registry](https://hub.docker.com/r/coffeateam/coffea-dask).

```console
$ docker pull coffeateam/coffea-dask:latest
```

To use a specific version, you can pull a versioned tag. You can view the [list of available versions](https://hub.docker.com/r/coffeateam/coffea-dask/tags) in the Docker Hub Registry.

```console
$ docker pull coffeateam/coffea-dask:[TAG]
```

The latest image is also distributed as a singularity image on the [unpacked.cern.ch](https://indico.cern.ch/event/764570/contributions/3173502/attachments/1735975/2807816/CVMFS-unpacked.pdf) service:

```
/cvmfs/unpacked.cern.ch/registry.hub.docker.com/coffeateam/coffea-dask:latest
```

If you wish, you can also build the image yourself.

```console
$ sudo docker build -t coffeateam/coffea-dask dask
```

## Releasing

Building and releasing new image versions is done automatically via Github CI.

When new commits are pushed to the master branch, images with the recent Coffea and Dask/Distributed `tag` and as well with `latest` tag are built and pushed to Docker Hub.

How it work: when a new version of Dask/Distributed is released a PR should be raised to bump the versions in the `Dockerfile`s and then once that has been merged a new tag matching the Coffea version should be pushed.

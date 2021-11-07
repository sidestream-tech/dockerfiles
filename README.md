# Dockerfiles

Repository for a collection of `Dockerfile`s that have helped us during development and during projects. Useful for local development, deployments and CI/CD pipelines.

Currently, we offer:
- `python-poetry` images and files, where `poetry` is the amazing [python package manager](https://python-poetry.org/). So far other images we found were outdated and unmaintained. We wanted to change that, as we believe in `poetry` as the future of python package management,
- `aws-cli` + `chamber`  + `helm` images and files in order to support our continuous delivery, where:
    - `aws-cli` is used to connect to AWS infrastructure
    - `chamber` is used to securely inject secrets into the deployment,
    - `helm` is used to deploy the application

You can find and pull [the images on docker hub](https://hub.docker.com/r/sidestream).

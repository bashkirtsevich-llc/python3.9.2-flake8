# Flake8 linter for python 3.9.2

Docker image based on `python:3.9.2-alpine` docker image, contains only `flake8` tool for using in CI/CD scripts.

[Dockerhub link](https://hub.docker.com/r/bashkirtsevich/python3.9.2-flake8)

Example usage with gitlab docker runner:
```
stages:
  - lint
  - build
  - etc
  
lint merge request:
  stage: lint
  image: bashkirtsevich/python3.9.2-flake8:alpine
  tags:
    - runner-tag
  script:
    - flake8 --ignore=E501,F401 .
  only:
    - merge_requests

...
```

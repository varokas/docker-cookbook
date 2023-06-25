# Docker Cookbook

## Prerequisite
download and install docker -- https://www.docker.com/

## Links
* Dockerhub - https://hub.docker.com/

## Commands
```
$ docker build . -t "ubuntu-hello"
$ docker image ls
$ docker run -it --rm ubuntu-hello /bin/bash
$ docker run --rm ubuntu-hello echo hello

$ docker build . -t python-fastapi-lambda
$ docker buildx build --platform linux/amd64 . -t python-fastapi-lambda
$ docker run --rm python-fastapi-lambda uvicorn main:app
$ docker run --rm -p 8000:8000 python-fastapi-lambda uvicorn --host 0.0.0.0 main:app
```

## ECR
https://ap-southeast-1.console.aws.amazon.com/ecr/repositories?region=ap-southeast-1

```
$ aws sso login --profile bedrock_nonprod
$ aws ecr get-login-password --region ap-southeast-1 --profile bedrock_nonprod | docker login --username AWS --password-stdin 654934115675.dkr.ecr.ap-southeast-1.amazonaws.com

$ docker buildx build --platform linux/amd64 . -t 654934115675.dkr.ecr.ap-southeast-1.amazonaws.com/python-fastapi-lambda 
$ docker push 654934115675.dkr.ecr.ap-southeast-1.amazonaws.com/python-fastapi-lambda 
```
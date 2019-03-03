# Install Fest 2019 - Docker Workshop

    Ondrej Sika <ondrej@ondrejsika.com>

## Installation

```
curl -fsSL https://ins.oxs.cz/docker.sh | sudo sh
```

## Check if Docker running

```
docker run hello-world
```

## Basic Usage

### `docker run`

```
docker run hello-world
```

```
docker run hello-seatle
```

```
docker run debian cat /etc/os-release
docker run debian:8 cat /etc/os-release
docker run ubuntu cat /etc/os-release
docker run centos cat /etc/os-release
docker run fedora cat /etc/os-release
```

Interactive mode

```
docker run -ti debian
```

```
docker run -ti centos
```

### docker ps

Show running containers

```
docker ps ls
```

Show all containers

```
docker ps ls -a
```

### docker rm

Remove stopped container

```
docker rm <container>
```

Remove running container

```
docker rm -f <container>
```

### `docker run` parameters

Name container

```
docker run --name debian -ti debian
```

Port forwarding

```
docker run -p 8000:80 nginx
```

Run container in background

```
docker run -d -p 8000:80 nginx
```

Remove container after stops

```
docker run --name debian --rm -ti debian
```

### Stop, start, restart containers

```
docker stop <container>
```

```
docker start <container>
```

```
docker restart <container>
```

### Images

List images

```
docker image ls
```

Download image from registry

```
docker pull python:3.7-slim
```

## Build own image

### Dockerfile

```
FROM <base image>
COPY <source> <image path>
RUN <run shell command>
CMD <scrip which will start on docker run>
```

For example

`app.py`:

```
import sys
print(sys.version)
```

`Dockerfile`:

```
FROM python:3.7-slim
COPY app.py /
CMD ["python", "app.py"]
```

### Build & run

```
docker build -t my-image .
```

```
docker run my-image
```

More exaples on: <https://github.com/ondrejsika/docker-training-exaples>
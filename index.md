#  Taller de Docker

Este repositorio trata de explicar el uso de contenedores con Docker

## Requisitos

- Linux / Mac
    - Docker
    - Docker Compose
- Windows
    - Docker
    - Git Bash
    - Putty
- [Play Whit Docker](http://play-with-docker.com)
- [Plugin Chrome PWD](https://chrome.google.com/webstore/detail/play-with-docker/kibbhpioncdhmamhflnnmfonadknnoan)
- [Cuenta docker](https://www.docker.com/)

## Comandos

### image

Lista las imagenes
```console
$ docker image ls
```

Descarga una imagen
```console
$ docker image pull [image-name:tag]
```

Construye una imagen
```console
$ docker image build -t [image-name] .
```

Elimina una imagen
```console
$ docker image rm [image-id/name]
```

### container

Lista contenedores
```console
$ docker container ls
```

Muestra el detalle
```console
$ docker container inspect [container-id / nombre]
```

Muestra el log
```console
$ docker container logs [container-id / nombre]
```

Inicia un contenedor de una imagen base
```console
$ docker container run [image-name]
```

Detiene un contenedor
```console
$ docker container stop [container-id / nombre]
```

Arranca un contenedor
```console
$ docker container start [container-id / nombre]
```

Elimina un contenedor
```console
$ docker container rm [container-id / nombre]
```

### network

Lista redes
```console
$ docker network ls
```

Revisa el detalle de una red
```console
$ docker network inspect [network-name]
```

### volume

Lista volumenes
```console
$ docker volume ls
```

Elimina un volumen
```console
$ docker volume rm [volume-name]
```

## docker-compose

```docker-compose
version: "3.5"
services:
 jenkins:
   container_name: jenkins
   image: jenkins/jenkins:2.122-alpine
   ports:
     - 8080:8080
 artifactory:
   container_name: artifactory
   image: docker.bintray.io/jfrog/artifactory-oss:5.10.4
   ports:
     - 8081:8081
 sonar:
   container_name: sonar
   image: sonarqube:7.1-alpine
   environment:
     - SONARQUBE_JDBC_URL=jdbc:postgresql://sonar_bd:5432/sonar
   ports:
     - 9000:9000
     - 9092:9092
 sonar_bd:
   container_name: sonar_bd
   image: postgres:10.3
   environment:
     - POSTGRES_USER=sonar
     - POSTGRES_PASSWORD=sonar
```

```console
$ docker-compose up
```
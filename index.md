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

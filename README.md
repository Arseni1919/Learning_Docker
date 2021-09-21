# Learning [Docker](https://docs.docker.com/get-started/)

## Part 1 - Commands 

To see all commands just type:
```shell
$ docker
```

List of only running containers:
```shell
$ docker container ls
```

To show all the containers:
```shell
$ docker container ls -a
```

To show all the images:
```shell
$ docker images
```

To remove images or containers:
```shell
$ docker image rm <ID>
$ docker container rm <ID>
```

Version:
```shell
$ docker version
```

Information of how many containers and images:
```shell
$ docker info
```

Run the container:
```shell
$ docker run -d -p 80:80 --name <YOUR NAME> -e <GLOBAL VARIABLES> <CONTAINER NAME>
```

To stop container:
```shell
$ docker container <NAME>
```

To enter the shell of a container:
```shell
$ docker container exec -it <NAME> /bin/sh
```


Build the image:
```shell
$ docker image build -t arseni_perchik_user/nginx-website .
```

Run a new image as a container:
```shell
$ docker container run -d -p 8082:80 arseni_perchik_user/nginx-website
```

---

## Part 2 - Commands 

```shell

```

```shell

```

```shell

```

```shell

```

```shell

```

```shell

```

```shell

```

## Pitfalls & Tricks

- `darwin` it is Mac OS


## Credits

- [YouTube | Exploring Docker (1) - Getting Started](https://www.youtube.com/watch?v=Kyx2PsuwomE)
- [YouTube | Exploring Docker (2) - Docker Compose With Node & MongoDB](https://www.youtube.com/watch?v=hP77Rua1E0c)
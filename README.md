# Learning [Docker](https://docs.docker.com/get-started/)

Some Docker-specific terms:

- A **Dockerfile** is a file that contains a set of instructions used to create an image.
- An **image** is used to build and save snapshots (the state) of an environment.
- A **container** is an instantiated, live image that runs a collection of processes.

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

...

## Pitfalls & Tricks

- `darwin` it is "Mac OS"


## Credits

- [YouTube | Exploring Docker (1) - Getting Started](https://www.youtube.com/watch?v=Kyx2PsuwomE)
- [YouTube | Exploring Docker (2) - Docker Compose With Node & MongoDB](https://www.youtube.com/watch?v=hP77Rua1E0c)
- [RealPython | Docker in Action – Fitter, Happier, More Productive](https://realpython.com/docker-in-action-fitter-happier-more-productive/)
- [Heroku | Container Registry & Runtime (Docker Deploys)](https://devcenter.heroku.com/articles/container-registry-and-runtime#release-phase)
- [Docker Docs | Build your Python image](https://docs.docker.com/language/python/build-images/)
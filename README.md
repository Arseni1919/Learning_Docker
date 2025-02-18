# Learning [Docker](https://docs.docker.com/get-started/)

Some Docker-specific terms:

- An **image** is used to build and save an environment's snapshots (the state) - a simple blueprint.
- A **container** is an instantiated, live image that runs a collection of processes - basically a running server/computer.
- A **Dockerfile** is a file that contains a set of instructions used to create an image - it is just a list of layers (maybe other images) and volumes that this image contains.
-  **Volumes** are a mechanism for storing data outside containers.

## Basic Commands

To see all commands just type:
```shell
$ docker
```

### --- Images ---

To show all the images:
```shell
$ docker image ls
```
or:
```shell
$ docker images
```
To download image from the registry:
```shell
$ docker image pull <image>
```
Example:
```shell
$ docker image pull ros:humble
```
or
```shell
$ docker pull
```
To remove image:
```shell
$ docker image rm -f <image>
```

### --- Containers ---

Run the container:
```shell
$ docker run -d -p 80:80 --name <YOUR NAME> -e <GLOBAL VARIABLES> <CONTAINER NAME>
```
or:
```shell
$ docker run <image>
```
better (for dev):
```shell
$ docker run -it <image>
```
even more better:
```shell
$ docker run --rm --name <container name> <image name>
```

To stop a container:
```shell
$ docker container stop <name of the container>
```
or:
```shell
$ docker stop <name of the container>
```
or:
CNTRL+D

or:
```shell
quit
```

To start or restart the container: 
```shell
$ docker container start -i <name of the container>
```
or: 
```shell
$ docker start -i <name of the container>
```

List of only running containers:
```shell
$ docker container ls
```
or: 
```shell
$ docker ps
```

To show all the containers (even if they are stopped):
```shell
$ docker container ls -a
```
or:
```shell
$ docker ps -a
```

To remove containers:
```shell
$ docker container rm <ID>
```
or to remove all stopped containers:
```shell
$ docker container prune
```

To open a new terminal in the same container:
```shell
$ docker exec -it <NAME> /bin/bash
```
### --- Dockerfile ---

Here, we create our own image based on some other image (`FROM` parameter).
First, create a project or directory where you will store the Dockerfile.

Dockerfile:
```Dockerfile
FROM ros:humble
RUN apt-get update && apt-get install ...
COPY config/ /site_config/
```

Inside the terminal go the directory and out of the dir build the image:
```shell
$ docker image build -t my_image . 
```
or: 
```shell
$ docker build -t my_image . 
```

Now check if your image is there:
```shell
$ docker images
```

Now create a container out of your image:
```shell
$ docker run -it my_image
```


### --- Volumes ---

First, create a directory where you want to save files.

To specify the volume:
```shell
$ docker run -it -v <path in host>:<path in container>
```

Example:
```shell
$ docker run -it -v $PWD/:/my_source_code my_image
```
Then type `ls` and see your source dir there.

### --- Other Commands ---

To create file
```shell
$ touch aaaa.txt
```

Version:
```shell
$ docker version
```

Information of how many containers and images:
```shell
$ docker info
```


## Pitfalls & Tricks

- `darwin` it is "Mac OS"


## Credits

- [YouTube | Docker 101](https://www.youtube.com/watch?v=SAMPOK_lazw)
- [YouTube | Exploring Docker (1) - Getting Started](https://www.youtube.com/watch?v=Kyx2PsuwomE)
- [YouTube | Exploring Docker (2) - Docker Compose With Node & MongoDB](https://www.youtube.com/watch?v=hP77Rua1E0c)
- [YouTube | Docker Volumes explained in 6 minutes](https://www.youtube.com/watch?v=p2PH_YPCsis&ab_channel=TechWorldwithNana)
- [YouTube | Docker Tutorial for Beginners (FULL COURSE in 3 Hours)](https://www.youtube.com/watch?v=3c-iBn73dDE&ab_channel=TechWorldwithNana)
- [RealPython | Docker in Action – Fitter, Happier, More Productive](https://realpython.com/docker-in-action-fitter-happier-more-productive/)
- [RealPython | Run Python Versions in Docker: How to Try the Latest Python Release](https://realpython.com/python-versions-docker/)
- [Heroku | Container Registry & Runtime (Docker Deploys)](https://devcenter.heroku.com/articles/container-registry-and-runtime#release-phase)
- [Docker Docs | Build your Python image](https://docs.docker.com/language/python/build-images/)

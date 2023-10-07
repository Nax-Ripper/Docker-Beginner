# Docker-Beginner

This is my docker project by learning docker and container

![Alt text](/images/image-3.png)

## Concepts and terms

![Alt text](/images/image-5.png)

### Images

- It like CD/DVD that has a lot of information and we can run them.

### Container

- Installed system from Images/CD/DVD

### Tags

- Versions of images

## Commands

- **docker --version** - To check current version

- **docker pull [image nme]** - Download an image from a registry (not running the image)

- **docker image ls** - To list image

> ![Alt text](/images/image-1.png)

- **docker ps** - To list containers

- **docker run [image_name]** - Create and run a **new** container from an image

- **docker run --name [xyz] -e [var_name=abc] -d [image_name]**

- **docker run --name [xyz] -p [host_port]:[container_port] -d [image_name]**

> --name = give sample name to the container

> -e = environment variable

> -d = detach mode ( to run the container in background and print its id to the terminal)

> -p = publish => host_post -> your machine , container_port -> container

- **docker stop [container_name / container_id]** - to stop running container

- **docker stop $(docker ps -a -q)** - to stop all running container

- **docker rm -f $(docker ps -a -q)** - to delete all containers

> -a = show all container

> -q = show only container id

- **docker container prune** - to remove all the stopped container

- **docker volume ls** - to list all the volume

- **docker logs [container_name]** - to list log of the container

## Container to Container communications

![Alt text](/images/image-2.png)

### Networking in docker

#### Using mongo and mongo-express example

- **docker network create [network_name]** - to create a network

- **docker network ls** - to list all the available networks

##### To set up mongo and it network

```
docker run -p [host_port:container_port] -e MONGO_INITDB_ROOT_USERNAME=admin MONGO_INITDB_ROOT_PASSWORD=password --name mongodb --net mongo-network -d mongo
```

##### To set up mongo-express to mongo-network

```
 docker run -p 8081:8081 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=password -e ME_CONFIG_MONGODB_SERVER=mongodb --net mongo-network --name mongo-express -d mongo-express
```

### Building Docker image and push

```
docker build -t [username/preferred_image_name]:[tag] .
```

```
docker push [imaga_name]
```

- Example

```
docker build -t narendran/hey-python:0.0.1.RELEASE .
```

```
docker push narendran/hey-python:0.0.1.RELEASE
```

### Images That pushed

- <https://hub.docker.com/u/narendranrammudo>


### Additional Resources

- <https://docs.docker.com/engine/reference/run/>
## Commands

### Display version of docker

```bash
docker version
```

### Display list of container

```bash
docker ps -a
```

### Display only running containers

```bash
docker ps
```

### Display all images

```bash
docker images
```

### Creating container

```bash
docker run hello-world
```

!!! note

    If the image is not installed locally it will be downloaded from the Docker Hub. In this case `hello-world` it is image of object.


### Remove container
```bash
docker rm <id or name of container>
```

### Environment run

```bash
docker run -it bysybox
```
!!! note

    `-it` option is necessary so that the container is not closed after launching, because we do not send the data anywhere.

### To run the container in the background

```bash
docker run -d <id or name>
```

### To view detailed information about the container

```bash
docker container inspect <id or name>
```

optional you can add `grep`

```bash
docker container inspect <id> | grep IPAddress
```

### How to run an additional process inside the container
```bash
docker exec -it <id> bash
```

- *`exec` - executes a command in the running container*<br>
- *`it` -   interactive terminal connection options*<br>
- *`bash` - the name of the process we want to run*<br>
- *`hostname` -i показывает ip адрес внутри контейнера*<br>

For the server to be accessible e.g. by running nginx
you need to configure port mapping

```bash
docker run -p 8080:80 nginx
```

In order to run your html file on the server
there is a command.

```bash
docker run -v ${PWD}:/user/share/nginx/html  nginx
```

### Delete container after stopping
```bash
docker run -it --rm busybox
```



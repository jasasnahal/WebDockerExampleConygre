# Instructions

This application requires port 80.

You can use the following command to pull the docker image:

```
docker pull  docker.conygre.com:5000/jaspreetnahal
```

An example of running the image on port 8080 with the default name:

```
docker run --detach -p 8080:80 docker.conygre.com:5000/jaspreetnahal
```

To access one of the pages in this application (if for example you're running
on port 8080), you could navigate to

```
[IP_OF_CONTAINER]:8080/api/values
```

# pulling nginx image

docker pull nginx

# view the images

docker images

# running containers

docker run nginx: latest (this is in the format: docker run image_name: tag_name) {processes hang}

# list of all running containers

1. docker container ls
2. docker ps

# running container in detach mode

docker run -d nginx:latest

# stop container

docker stop container_id
or
docker stop vibrant_liskov

# exposing ports

docker run -d -p 8080:80 nginx:latest
{0.0.0.0:8080->80/tcp} <br/>{Baiscally we are mapping the host port 8080 to container port 80}<br/>
`Now open any browser and write localhost:8080 as the url`<br/>
![Broswer Screenshot localost:8080](image.png)

# exposing multiple ports

docker run -d -p 3000:80 -p 8080:80 nginx:latest

# managing containers

docker stop vibrant_liskov
<br/> or <br/>
docker start vibrant_liskov

# docker ps options

docker ps --help

# forcefully remove a container before stopping it

docker rm -f $(docker ps -aq)

# naming a container

docker run --name website -d -p 3000:80 -p 8080:80 nginx:latest

# formatting the way in which dtails of container should appear

docker ps --format="ID\t{{.ID}}\nNAME\t{{.Names}}\nIMAGE\t{{.Image}}\nPORTS\t{{.Ports}}\nCOMMAND\t{{.Command}}\nCREATED\t{{.CreatedAt}}\nSTATUS\t{{.Status}}\n"

# giving the format a name

$env:FORMAT = "ID\t{{.ID}}\nNAME\t{{.Names}}\nIMAGE\t{{.Image}}\nPORTS\t{{.Ports}}\nCOMMAND\t{{.Command}}\nCREATED\t{{.CreatedAt}}\nSTATUS\t{{.Status}}\n"
<br/>
docker ps --format $env:FORMAT

# Volumes

Allows sharing of data. Files or Folders.<br/>
Between Host and containers.<br/>
Between containers.

![Alt text](image-1.png)

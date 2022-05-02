# Commands
- Run **[IMAGE](https://hub.docker.com/)**
  - **-d** | It don't block the terminal
  - **-p** | It's make a mapping port
  - **-v** | Bind folder between container and host
  - **--mount** | Map folder between container and host
  - **--name** | Create Container name
  - **--network** | Define de brigde

```shell
docker run [-d] [-p CONTAINERPORT:PORT] [-v path/host:path/container] [--name CONTAINERNAME] [--network NETWORKNAME] IMAGE_NAME
docker run IMAGE_NAME
```

- Download **[IMAGE](https://hub.docker.com/)**

```shell
docker pull IMAGE_NAME
```

- Show the **CONTAINERS** running
  - **-a** | Show ALL containers 
  - **-s** | Show size column

```shell
docker ps [-a] [-s]
docker container ls [-a]

```

- Stop all **CONTAINER**

```shell
docker stop $(docker container ls -q)
```

- Stop **CONTAINER**

```shell
docker stop [NAME | ID]
```

- Start **CONTAINER**

```shell
docker start [NAME | ID]
```

- Pause **CONTAINER**

```shell
docker pause [NAME | ID]
```

- Continue **CONTAINER**

```shell
docker unpause [NAME | ID]
```

- Execute command Interactive

```shell
docker exec -it [NAME | ID] bash
```

- Remove **CONTAINER**

```shell
docker rm [NAME | ID]
```

- Show the container **PORT**
  - container > host
```shell
docker port [NAME | ID]
```

- List all images on HOST
```shell
docker images
```

- Describe informations about the container
```shell
docker inspect [ID]
```

- Show history about the container; layers
```shell
docker history [ID]
```

- Create **VOLUME**
```shell
 docker volume create VOLUMN-NAME
```

- List all **NETWORK**

```shell
docker network ls
```

- Create **NETWORK**
```shell
docker network create --driver TYPE NAME
```


# Dockerfile

## Options
- FROM | The image name
- WORKDIR | Folder name inside container
- ARG | Create variables for use in **BUILD TIME**
- ENV | Create **ENVIRONMENTS** and using in code. 
- EXPOSE | Expose a PORT
- COPY | COPY FILES
- RUN | Run commands
- ENTRYPOINT | Call after run container.

```env
FROM image_name
WORKDIR ./
ARG port_build=3000
ENV port=$port_build
EXPOSE $port_build
COPY ./ ./
RUN npm i
ENTRYPOINT npm start
```


## Commands

- Build **Dockercomposer** file
```shell
docker build -t NAMECONTAINER .
```

# Obs





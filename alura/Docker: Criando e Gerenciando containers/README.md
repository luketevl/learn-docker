# Commands
- Run **[IMAGE](https://hub.docker.com/)**
  - **-d** | It don't block the terminal
  - **-p** | It's make a mapping port

```shell
docker run [-d] [-p CONTAINERPORT:PORT] IMAGE_NAME
docker run IMAGE_NAME
```

- Download **[IMAGE](https://hub.docker.com/)**

```shell
docker pull IMAGE_NAME
```

- Show the **CONTAINERS** running
  - **-a** | Show ALL containers 

```shell
docker ps [-a]
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

## Dockerfile

- Build **Dockercomposer** file
```shell
docker build -t NAMECONTAINER .
```

# Obs





# Links
- https://www.docker.com/
- https://hub.docker.com/


- **Cria container(faz download) e executa comando**
```shell
docker run imgNAME /command
``` 

- Cria container com um **NOME**
```shell
docker run --name
```

- RODA em **BACKGROUND**
```shell
docker run -d
```

- Seta **variavel de ambiente**
```shell
docker run -e
```

- Seta **PORTA** do container, porta da máquina local : porta do container
```shell
docker run -p localPORT:containerPORT
```

- Vincula um **CONTAINER** a outro **CONTAINER**
```shell
docker run --link nameCONTAINER:aliasNAME
```

- Faz **download** da imagem para nosso sistema
```shell
docker pull imgNAME
```

 - Lista as **imagens**
```shell
docker images
```

 - Lista container em **EXECUCAO**
```shell
docker ps
```

- **Lista TODOS** container
```shell
docker ps -a
```
- **Lista TODOS IDS** container
```shell
docker ps -qa
```

- **ACESSA(exec | run)** um _container_
  - **-i** | Forma _interativa_
  - **-t** | Acesso ao _terminal_ tty
  - **bash** | Comando bash
```shell
docker exec | run  -i -t containerName command
```
- **REMOVE** _TODOS_ **CONTAINER**
```shell
docker rm $(docker os -qa)
```
- **REMOVE** _um_ **CONTAINER**
```shell
docker rm containerName | containerID
```
- **PARA** um **container**
```shell
docker stop containerNAME | containerID
```

# Containers
## MYSQL
- Pull

```shell
docker pull mysql
```
- Criar

```shell
docker run --name databse -e MYSQL_ROOT_PASSWORD=root -d mysql
```




# Observações
  - DOCKER cria **CONTAINERS**
  - Ele baixa la no _docker hub_, repositorio publico
  - **RUN** baixa a imagem _caso nao tenha_

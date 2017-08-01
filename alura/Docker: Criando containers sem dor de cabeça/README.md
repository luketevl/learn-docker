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
- **INICIA** um **container**
```shell
docker start containerNAME | containerID
```
- **REMOVE** _uma_ **IMAGEM**
```shell
docker rmi imageName | imageID
```
- **DELETE** _um_ **PROCESSO**
```shell
docker kill imageName | imageID
```

- **NAO PERSISTENTE** cria um container que vai ser **deletado** no final do comando
 - **--rm**
```shell
docker run --rm it imageName command
```

- **COMMIT** persiste alteracoes do container
```shell
docker commit -m "msg" containerName imageName
```

- **BUILD** executa arquivo **Dockerfile**
```shell
docker build -t imagemName pathDockerFile
```

- **DOCKER INSPECT** mostra informações do **container**
```shell
docker inspect containerName
```

- **COMPOSER UP** executa arquivo **docker-composer.yml**
```shell
docker-compose up
```

- **COMPOSER UP** executa arquivo **docker-composer.yml** e **libera** o _TERMINAL_
```shell
docker-compose up -d
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

# DOCKERFILE
- Criar aquivo com nome **Dockerfile**
- Arquivo com as configuraes comandos para criar imagens
 - **from** | Imagem base
 - **run** | Executa comando dentro da imagem base
 - **add** | Passa aplicação para o _container_, copia os ARQUIVOS dentro da pasta informada
 - **copy** | Copia aplicação para o _container_, copia a pasta inteira
 - **expose** | Libera uma porta
 - **cmd** | Executa comandos
```
FROM imageName
RUN command
ADD dirBase pathContainer
EXPOSE portNumber
CMD ["/usr/bin/sbin/apache2ctl", -D", "FOREGROUND"]
```

# DOCKERCOMPOSER
- Criar aquivo com nome **docker-composer.yml**
 - **containerName** | Nome do container
  - **imageName** | Nome da imagem
  - **environment** | Variaveis de ambiente
  - **links** | Link containers
  - **ports** | Mapeamento de portas
```yml
containerName: 
 image: imageName
 environment: 
  - VARIABLE_NAME=VALUE
 links:
  - containerName:aliasName
 ports:
  - 80:80
```

# Observações
- DOCKER cria **CONTAINERS**
- Ele baixa la no _docker hub_, repositorio publico
- **RUN** baixa a imagem _caso nao tenha_
- **CONTAINERS** são **processos com status**
- **COMMIT**
 - CUIDADO ele sobreescreve a imagem. Para nao acontecer coloque imagemName/name, com isso ele faz um **fork** da imagem.
- **DOCKER BUILD**
 - Utiliza **cache**

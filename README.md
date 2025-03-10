## docker-series

- Pegar uma imagem do docker hub
```cmd
docker pull <image_name>
```

- Checa todas as images no meu PC
```cmd
docker images
```

- Criando um container executando a image. Se a imaagem não existir, ele pega do docker hub (pull).
```cmd
docker run <image_name>
```

- Também pode-se colocar a versão da imagem.
```cmd
docker run <image_name>:<version>
```

- Lista todos os containers em execução.
```cmd
docker ps
```

- Criando um container executando a image com o -d (detached). Executa o container por debaixo dos panos. Retorna só o id do container.
```cmd
docker run -d <image_name>
```

- Parar o container
```cmd
docker stop <container_id>
```

- Startar o container
```cmd
docker start <container_id>
```

- List running and stopped container
```cmd
docker ps -a
```

- Binding the pc port with the container port
```cmd
docker run -p<pc_port>:<cont_port> <image_name>
```

- Verificando os logs do container
```cmd
docker logs <container_id>
docker logs <container_name>
```

- Criando um container em detached mode (-d) baiding port(-p) e nomeando o container
```cmd
docker run -d -p<pc_port>:<cont_port> --name <container_name>
```

- Acessando o terminal do container. Entra dentro do container como um root user. Use o comando exit para sair do terminal.
```cmd
docker exec -it <container_id> /bin/bash
docker exec -it <container_name> /bin/bash
```

- Docker networks
```cmd
docker network ls
```

- Criar uma network
```cmd
docker network create <network_name>
```

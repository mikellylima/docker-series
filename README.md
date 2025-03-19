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

---------------
## Treinamento DevOps
```cmd
docker container run hello-world

# Listar todos os containers
docker container ls -a

docker container run -e POSTGRES_PASSWORD=Pg@123 -e POSTGRES_USER=desafiodocker -e POSTGRES_DB=desafiodocker -d -p 5432:5432 postgres

# o -f força a exclusão do container quando ele tiver rodando
docker container rm -f ba37f3e0756e
```

- Dockerfile
  - FROM: define qual é a minha imagem base.
  - WORKDIR: cria um diretório de trabalho e entra dentro dele (mkdir + cd).
  - COPY: pega um arquivo ou diretório e coloca para dentro da imagem.
  - RUN: Comando de construção, executa uma instrução dentro da imagem.
  - CMD: instrução de inicialização, na hora que executa o container.

- Construção da imagem
```cmd
# -t para nomear a imagem. O contexto é o direrótio que vai ser utilizado para construir a minha imagem.
docker build -t conversao-distancia .
```
```cmd
# ver a imagem
docker image ls

# Executar o container
docker container run -d -p 5000:5000 conversao-distancia
```

- Construção da imagem versionada.
```cmd
docker build -t mikellylima/conversao-distancia-desafio:v1 .
```

- Autenticação, push da imagem criada e criação da latest
```cmd
docker login

docker push mikellylima/conversao-distancia-desafio:v1

docker tag mikellylima/conversao-distancia-desafio:v1 mikellylima/conversao-distancia-desafio:latest

docker push mikellylima/conversao-distancia-desafio:v1
```

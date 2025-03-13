# TodoListDockerAula

Aula de monolito com docker, docker-compos e nginx.

## Instruções

1. Faça um fork deste repositório.
2. Clone o repositório para a sua máquina.
3. Siga as instruções do arquivo [Tutorial.md](Tutorial.md) para realizar a atividade.
4. Após finalizar a atividade, faça um commit e um push para o seu repositório.
5. Envie o link do seu repositório para o professor.

## Detalhes

O serviço web estará disponível nas portas:
- **80**: porta default para o serviço http porém o ngnix está configurado para sempre redirecionar para a https
- **443**: porta default para o serviço https, esta sim estará disponibilizando a todo-list

## Guia de comandos docker

### Como iniciar

Abra um terminal na pasta raiz do projeto (TodoListDockerAula) pois é nesta pasta que está localizado o arquivo docker-compose.yml e execute o comando:

```bash
docker compose up -d --build
```

As flags do comando fazer o seguinte: 

-   -d: _detach_ faz com que os containers sejam executados de forma independente ao terminal que os iniciou 
-   --build: indica que a imagem vai ser construida antes de iniciar os containers

### Como visualizar

Para visualizar os containers em execução é possível utilizar o comando:

```bash
docker compose ps
```

Ou

```bash
docker ps
```

E para visualizar o projeto compoes que está rodando usa-se: 

```bash
docker compoes ls
```

### Como inicializar o banco de dados

### Como ver os logs

É preciso abrir um terminal na raiz do projeto (TodoListDockerAula) e então a partir dai há dois meios:

1. Visualizar o log do projeto compose

```bash
docker compose logs
```

3. Visualizar o log do container individualmente

```bash
docker compose logs container
```

E para visualizar de forma contínua é utilizado a flag _-f_

### Como conectar-se ao container

Para utilizar o terminal dentro do container roda-se o seguinte comando:
```bash
docker exec -it [container] /bin/bash
```

### Como parar

É preciso abrir um terminal e estar na pasta raiz do projeto (TodoListDockerAula) e utilizar o comando:

```bash
docker compose down
```

### Como "limpar" o docker

Quando os containers são parados e buildados novamente então as imagens antigas podem continuar lá apenas ocupando espaço, para limpar isso é utilizado o comando:

```bash
docker image prune -f
```

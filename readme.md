# Redis com RedisInsight usando Docker Compose

Este projeto configura um ambiente Redis com RedisInsight, uma ferramenta poderosa para visualizar e gerenciar dados no Redis. Usando Docker Compose, você pode subir rapidamente o Redis e a interface gráfica do RedisInsight.

## Pré-requisitos

- Docker
- Docker Compose

## Configuração

O `docker-compose.yml` configura dois serviços:

- **Redis**: Um banco de dados em memória NoSQL que oferece alta performance e suporte a várias estruturas de dados.
- **RedisInsight**: Uma interface gráfica que permite monitorar, gerenciar e visualizar os dados armazenados no Redis.

### Serviços Configurados

- **redis**: 
  - Porta: `6379`
  - Volume: `redis-data` para persistência de dados.

- **redisinsight**: 
  - Porta: `5540`
  - Interface gráfica acessível via `http://localhost:5540`.

## Como Usar

### 1. Subir os Contêineres
Para iniciar o Redis e o RedisInsight, execute o comando abaixo:
```bash
docker-compose up -d
```

### 2. Acessar o RedisInsight
Após os contêineres estarem em execução, você pode acessar o RedisInsight no seu navegador via:
```
http://localhost:5540
```

### 3. Parar os Contêineres
Se você precisar parar os contêineres, use:
```
docker-compose down
```

### 4. Verificar os Logs
Para monitorar os logs dos serviços em execução, utilize:
```
docker-compose logs -f
```

### 5. Reconstruir os Contêineres
Caso você faça alterações no docker-compose.yml ou nas imagens, pode reconstruir os contêineres com:
```
docker-compose up -d --build
```

### 6. Listar Contêineres em Execução
Para listar os contêineres que estão em execução, use:
```
docker ps
```

### 7. Acessar o Redis via CLI
Se você precisar acessar o terminal do contêiner Redis, execute:
```
docker exec -it redis redis-cli
```

### Volumes
O volume redis-data é utilizado para persistir os dados do Redis, garantindo que os dados não sejam perdidos ao reiniciar ou parar os contêineres.

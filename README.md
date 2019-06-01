# Instalação e Inicialização

* Instalar o [Docker](https://docs.docker.com/install/)

* Instalar o [Docker Compose](https://docs.docker.com/compose/install/)

* Iniciar o docker;

* Ir para a pasta onde existe o arquivo "docker-compose.yml";

* Executar (e deixar rodando) o comando: 

```
docker-compose up;
```
* Executar em outro terminal o comando para iniciar a interface com o container que deseja trabalhar;

---

# Arquivos

A pasta "/src" está montada para cada container e todos os arquivos dos projetos ou exercícios podem ser salvos diretamente nesta pasta.

---

# Rede

Todos os containers estão em rede e acessíveis entre si, podendo ser acessados diretamente pelo seu nome.

Ex.: 

Estando dentro do container do python é possível se conectar com o mongo:

```
ping mongo
```

---

# Python

Iniciar interface para executar comandos dentro do container:  

```
docker exec -it python /bin/zsh
```

Obervações:

Para instalar uma biblioteca específica no python é necessário adicionar o comando de instalação no arquivo "/python/Dockerfile" e executar o comando para  recriar o container:

```
docker-compose up --force-recreate --build
```

---

# MongoDB

Iniciar interface para executar comandos dentro do container:  

```
docker exec -it mongo /bin/bash
```

Autenticar: 

```
mongo admin -u admin -p '12345'
```

---

# Redis

Iniciar interface para executar comandos dentro do container:  

```
docker exec -it redis /bin/bash
```

Ex. de uso: 

```
redis-cli --version
```

---

# Cassandra

Iniciar interface para executar comandos dentro do container:  

```
docker exec -it cassandra /bin/bash
```

Iniciar CLI do Cassandra: 

```
cqlsh
```

Ex. de uso: 

```
create keyspace aulas with replication = {'class':'SimpleStrategy','replication_factor':3};

use aulas;

CREATE TABLE aulas.materias ( id UUID PRIMARY KEY, nome text);

describe tables;

insert into materias (id, nome) values (uuid(), 'phyton');

select * from materias;
```

---

# Neo4j

Acessar a interface web: 

*(é normal levar alguns minutos até a interface web ficar disponível)*

http://localhost:7474/browser


Iniciar interface para executar comandos dentro do container:  


O usuário padrão e a senha padrão é ``neo4j``

```
docker exec -it neo4j /bin/bash
```

Acessar o shell do Cypher

*(usar o usuário e a senha definida na interface web para autenticar no shell do cypher)*

Exemplo: 

```
cypher-shell -u neo4j -p 12345
```
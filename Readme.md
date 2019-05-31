# Iniciar Docker

* Iniciar o docker caso já não esteja iniciado;

* Ir para a pasta onde existe o arquivo "docker-compose.yml";

* Executar (e deixar rodando) o comando: 

``
docker-compose up;
``

# Comunicação

## Arquivos

A pasta "/src" está montada para cada container e todos os arquivos podem ser salvos diretamente nesta pasta.

## Rede

Todos os containers estão em rede e acessiveis entre si, podendo ser acessado pelo seu nome.

Ex.: 

Estando dentro do container do python é possível se conectar com o mongo:

``
ping mongo
``

# Python

Iniciar interface: 

``
docker exec -it python /bin/zsh
``

# MongoDB

Iniciar interface: 

``
docker exec -it mongo /bin/bash
``

Autenticar: 

``
mongo admin -u admin -p '12345'
``

# Redis

Iniciar interface: 

``
docker exec -it redis /bin/bash
``

Ex. de uso: 

``
redis-cli --version
``

# Cassandra

Iniciar interface: 

``
docker exec -it cassandra /bin/bash
``

Iniciar CLI do Cassandra: 

``
cqlsh
``

Ex. de uso: 

``
create keyspace aulas with replication = {'class':'SimpleStrategy','replication_factor':3};
``

``
use aulas;
``

``
CREATE TABLE aulas.materias ( id UUID PRIMARY KEY, nome text);
``

``
describe tables;
``

``
insert into materias (id, nome) values (uuid(), 'phyton');
``

``
select * from materias;
``
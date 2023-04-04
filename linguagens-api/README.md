# Alura - Imersão Java

A aula 4 usa uma nuvem para criar e acessar o banco de dados mongo. Aqui fizemos um servidor local utilizando docker.

## Servidor MongoDB com Docker

```docker
docker run --name mongodb-server -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=alura --network labens-network mongo:latest
```

No computadores do laboratório IMD, a versão mais nova do MongoDB não executou. Foi necessário usar a versão `mongo:4.2.21`.

### Cliente MongoDB Express

**MongoDB Express** é uma Interface de Administração Web do MongoDB escrita em Node.js, Express e Bootstrap3. O **MongoDB Express** está disponível no repositório: https://github.com/mongo-express/mongo-express.

```docker
docker run -it --rm \
    --network labens-network \
    --name mongo-express \
    -p 8081:8081 \
    -e ME_CONFIG_MONGODB_SERVER="mongodb-server" \
    -e ME_CONFIG_MONGODB_ADMINUSERNAME="admin" \
    -e ME_CONFIG_MONGODB_ADMINPASSWORD="alura" \
    mongo-express
```



Put these configuration in your application properties file:

spring.data.mongodb.host= YOUR_HOST like 192.168.x.x
spring.data.mongodb.port=27017
spring.data.mongodb.authentication-database=admin
spring.data.mongodb.username=admin
spring.data.mongodb.password=PASSWORD
spring.data.mongodb.database=DB_NAME



## Links

### Aula 4

Primeira aula do curso [“Maven: gerenciamento de dependências e build de aplicações Java”](https://www.alura.com.br/conteudo/maven-gerenciamento-dependencias-build-aplicacoes-java) da Alura.

Alura+ [“O que é REST?”](https://www.youtube.com/watch?v=weQ8ssA6iBU&ab_channel=AluraCursosOnline).

Artigo da Alura [“Conceito e fundamentos sobre REST”](https://www.alura.com.br/artigos/rest-conceito-e-fundamentos).

Hipters.Tube [“O que é SQL e NoSQL?”](https://www.youtube.com/watch?v=aure5d3B88g&ab_channel=AluraCursosOnline).

Podcast [Hipsters.Tech sobre MongoDB](https://www.hipsters.tech/mongodb-hipsters-ponto-tech-305/).

Artigo da Alura [“Spring: Conheça esse framework Java”](https://www.alura.com.br/artigos/spring-conheca-esse-framework-java).


### Aula 5

[Dev em T: especialista x generalista](https://www.alura.com.br/dev-em-t).

Site do [Fly.io](https://fly.io/), o PaaS (plataforma como serviço) utilizado nesta segunda edição da Imersão Java. Requer cartão de crédito. É fundamental entender a precificação e as quotas gratuitas do Fly.io.

Documentação sobre a [Oracle Cloud](https://docs.oracle.com/pt-br/iaas/Content/home.htm).

Artigo: [Como elaborar um bom arquivo Readme para os seus projetos](https://www.alura.com.br/artigos/escrever-bom-readme).

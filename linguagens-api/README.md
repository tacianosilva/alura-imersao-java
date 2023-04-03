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

# Why?
Boost local development speed by eliminating the installation process of `Radis`, `RabbitMQ`, `MongoDB` etc tools. 

### To run all of the below dependencies at once fire up the `docker-compose.yml`

```
docker-compose up -d

```

```
docker run -d \\
  --name mongodb \\
  -p 27017:27017 \\
  -e MONGODB_INITDB_ROOT_USERNAME=username \\
  -e MONGODB_INITDB_ROOT_PASSWORD=password \\
  -e MONGODB_INITDB_DATABASE=admin \\
  -v mongodb:/data/db \\
  mongo:6-jammy

```

```
docker run -d \\
  --name redis \\
  -p 6379:6379 \\
  -e ALLOW_EMPTY_PASSWORD=yes \\
  bitnami/redis:7.0.13

// Do not allow empty password
// -e REDIS_PASSWORD=mysecretpassword \\

```

```
docker run -d \\
  --name rabbitmq \\
  -p 5672:5672 \\
  -p 15672:15672 \\
  -e RABBITMQ_DEFAULT_USER=guest \\
  -e RABBITMQ_DEFAULT_PASS=guest \\
  rabbitmq:3.9.29-management-alpine

```

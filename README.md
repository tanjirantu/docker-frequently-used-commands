# docker-frequently-used-commands
If you use Docker and rely on applications like `Redis`, `MongoDB`, and `RabbitMQ`, you can get started with these commands. I've included a `.yaml` file that you can use if your backend depends on all of these services. You can add more to this file as per your need.

## Run in detach mode
```
docker-compose up -d
```

## Equivalent `shell` commands are below:

```
docker run -d \
  --name mongodb \
  -p 27017:27017 \
  -e MONGODB_INITDB_ROOT_USERNAME=devops \
  -e MONGODB_INITDB_ROOT_PASSWORD=devops007 \
  -e MONGODB_INITDB_DATABASE=admin \
  -v mongodb:/data/db \
  mongo:6-jammy
```

```
docker run -d \
  --name redis \
  -p 6379:6379 \
  -e ALLOW_EMPTY_PASSWORD=yes \ 
  bitnami/redis:7.0.13

// Do not allow empty password
// -e REDIS_PASSWORD=mysecretpassword \
  

```

```
docker run -d \
  --name rabbitmq \
  -p 5672:5672 \
  -p 15672:15672 \
  -e RABBITMQ_DEFAULT_USER=guest \
  -e RABBITMQ_DEFAULT_PASS=guest \
  rabbitmq:3.9.29-management-alpine
```

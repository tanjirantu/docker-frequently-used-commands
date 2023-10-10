# docker-frequently-used-commands
Devs who are working on a backend that requires different applications installed locally can use this repo to kickstart their services with one single command. 

### redis 
### mongodb
### rabbitmq

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
  -e ALLOW_EMPTY_PASSWORD=yes \ # -e REDIS_PASSWORD=mysecretpassword \
  bitnami/redis:7.0.13

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

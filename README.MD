# Docker for node.js app with mongo and redis

## Set environment variable
```shell
cp .env.example .env
```
Customize your environment variables.

## Build
```shell
docker-compose build
```

## Exec
```shell
docker-compose up -d mongo redis node nginx
```

## Add mongodb admin user
```shell
docker-compose up -d mongo
docker-compose exec mongo mongo admin
> db.createUser({ user: 'shrimp', pwd: 'secret', roles: [ { role: "userAdminAnyDatabase", db: "admin" } ] });
```

## Add mongodb collection and user
```shell
docker-compose exec mongo mongo -u shrimp -p secret admin
> use demo
> db.createUser({ user: 'demouser', pwd: '123456', roles: [ { role: "readWrite", db: "demo" } ] });
```

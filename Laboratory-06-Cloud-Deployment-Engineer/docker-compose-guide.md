# Docker Compose Guide

## The Compose File
```yaml
version: '3'

services:
  database:
    image: mariadb:10.6
    environment:
      - MYSQL_ROOT_PASSWORD=cloudnova_root
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user

  app:
    image: nextcloud
    ports:
      - 8080:80
    environment:
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user
      - MYSQL_HOST=database
```

## What does the `services:` block do?
It defines every container that makes up the application. Each entry under
`services:` (`database` and `app`) becomes its own container with its own image,
ports, and environment variables.

## How did the Nextcloud container find the database?
Through `MYSQL_HOST=database`. Docker Compose puts all services on one shared
network and uses each service name as a hostname, so `database` resolves to the
MariaDB container.

## `docker run` vs `docker-compose up -d`
| docker run | docker-compose up -d |
|---|---|
| Starts one container per command | Starts all services defined in a YAML file |
| Options typed manually every time | Configuration saved in a file (Infrastructure as Code) |
| Hard to repeat and share | Repeatable and version-controllable |
| Networks are set up by hand | Compose creates a shared network automatically |

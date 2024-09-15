---
title: Docker Compose Networks
Date created: 2024-08-06 13:28
Aliases:
tags: 
  - Public
---

Docker Compose allows multiple containers to join a network and be reachable by other containers on that network.

By default all containers join a network named `<project_name>_default` under the service's name

Example:
```yaml
services:
  web:
    build: .
    ports:
      - "8000:8000"
  db:
    image: postgres
    ports:
      - "8001:5432"
```

On such network the code `web` container cna access the database on url `postgres://db:5432` (container port) and the host machine could connect using `postgres://<docker_ip>:8001` (host port)


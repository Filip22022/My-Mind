---
title: Docker Volumes
Date created: 2024-08-05 20:00
Aliases:
tags: 
  - Public
---

Docker containers are read-write layers working on top of a read-only images, any changes made to a container are lost when the container is stopped or deleted. To allow data to persist between container restarts it can be stored on host's filesystem using [[Docker Bind Mounts]] or volumes.

Docker volumes use subdirectories of the docker directory tree on host machine to store the files. This allows the data to be shared between containers and preserved between container restarts.

## Working with Volumes
Volumes are managed with the `docker volume` command set.

### Creating Volumes
`docker volume create <volume_name>`
The name is optional and if left empty, a random name will be generated.
### List Volumes
`docker volume ls`
`docker volume ls -f name=<name>`
### Remove Volume
`docker volume rm <volume_name>` - removes specified volume
`docker volume prune` - remove all unused volumes

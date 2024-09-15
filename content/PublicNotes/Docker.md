---
title: Docker
Date created: 2024-08-05 13:18
Aliases:
tags: 
  - Public
---
Docker is a tool using [[containers]] and [[images]] to run programs in isolated environments.
## Basic usage

To create a single container and run it on a localhost port:
1. Create `Dockerfile` in the app directory 
	1. Define starting image
	2. Set working directory and copy the program
	3. Install dependencies
	4. Run program
2. Build the container image `docker build -t <tag> .`
3. Run the image `docker run -d -p <host_port>:<container_port> <tag>`, the `-d` switch detaches the console

## Notes
[[Docker Volumes]]
[[Docker Commands]]
[[Docker Compose Networks]]





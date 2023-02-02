# Docker Compose

```
# remove images & volumes
docker-compose down --rmi all -v
```

```
# Version of Docker Compose
version: '3.8'

# Services, the projects to run
services:
  client:
    # Instructions for the project
    build: ./client
    # Tag for the Container
    container_name: poc_client
    # Lists of Ports Exposed
    ports:
      - "3000:3000"
    # Volumes, detect changes (maps the files)
    volumes:
      # [dev-relative-path]:[container-abs-path] (no dot)
      - ./client:/client
      - /client/node_modules
  server:
    build: ./server
    container_name: poc_server
    ports:
      - "4000:4000"
    volumes:
      # [dev-relative-path]:[container-abs-path] (no dot)
      - ./server:/server
      # [container-abs-path]
      - /server/node_modules
```



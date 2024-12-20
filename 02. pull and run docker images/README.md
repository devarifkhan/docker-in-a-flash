# How to Pull and Run Docker Images from Docker Hub

## Step 1: Pull a Docker Image from Docker Hub
To pull a Docker image from Docker Hub, use the `docker pull` command followed by the name of the image. For example:
```sh
docker pull ubuntu:latest
```

## Step 2: Run the Downloaded Docker Image
To run the downloaded Docker image, use the `docker run` command. For example:
```sh
docker run -it ubuntu:latest
```

## Step 3: List Running Docker Containers
To list all running Docker containers, use the `docker ps` command:
```sh
docker ps
```

## Step 4: Connect to a Docker Container Terminal
To connect to a running Docker container's terminal, use the `docker exec` command followed by the container ID and the command to run. For example:
```sh
docker exec -it <container_id> /bin/bash
```

## Step 5: Stop and Start Docker Containers
To stop a running Docker container, use the `docker stop` command followed by the container ID. For example:
```sh
docker stop <container_id>
```
To start a stopped Docker container, use the `docker start` command followed by the container ID. For example:
```sh
docker start <container_id>
```

## Step 6: Remove Docker Containers
To remove a Docker container, use the `docker rm` command followed by the container ID. For example:
```sh
docker rm <container_id>
```

## Step 7: Remove Docker Images
To remove a Docker image, use the `docker rmi` command followed by the image ID or name. For example:
```sh
docker rmi ubuntu:latest
```
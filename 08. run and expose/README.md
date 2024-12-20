# Dockerfile Instructions for Nginx with Custom Configuration

This document provides a brief overview of the Dockerfile instructions used to create a custom Nginx image with additional configurations and exposed ports.

## Base Image

The base image used for this Dockerfile is `nginx:alpine-slim`, which is a lightweight version of Nginx.

## OCI Labels

The following OCI labels are added to provide metadata about the image:
- **Author**: Ariful Islam
- **Title**: Using RUN, EXPOSE Instructions in Dockerfile
- **Description**: Illustrating the usage of RUN and EXPOSE instructions
- **Version**: 1.0

## Copying Configuration and HTML Files

- **Nginx Configuration Files**: All configuration files from the `nginx-conf` directory are copied to `/etc/nginx/conf.d/`.
- **HTML Files**: All HTML files from the `nginx-html` directory are copied to `/usr/share/nginx/html/`.

## Installing Additional Packages

- **Curl**: The `curl` package is installed using the `RUN` instruction with `apk --no-cache add curl`.

## Exposing Ports

The following ports are exposed in addition to the default port 80:
- **8081**
- **8082**
- **8083**

This setup allows Nginx to listen on multiple ports as specified.

## Building, Running, Stopping, and Deleting the Docker Container

### Build the Docker Image

To build the Docker image, navigate to the directory containing the Dockerfile and run the following command:

```sh
docker build -t custom-nginx-image .
```

### Run the Docker Container

To run the Docker container, use the following command:

```sh
docker run -d --name custom-nginx-container -p 8081:8081 -p 8082:8082 -p 8083:8083 custom-nginx-image
```

### Stop the Docker Container

To stop the running Docker container, use the following command:

```sh
docker stop custom-nginx-container
```

### Delete the Docker Container

To delete the stopped Docker container, use the following command:

```sh
docker rm custom-nginx-container
```

### Delete the Docker Image

To delete the Docker image, use the following command:

```sh
docker rmi custom-nginx-image
```

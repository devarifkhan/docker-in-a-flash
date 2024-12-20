# ARG Instruction

This example demonstrates how to use the `ARG` instruction in a Dockerfile to define build-time arguments.

## Dockerfile Overview

- Define a build-time argument for the NGINX version.
- Use the specified NGINX version as the base Docker image.
- Add OCI labels for metadata.
- Remove the existing `index.html` file.
- Copy a local `index.html` file to the NGINX HTML directory.

## Commands to Build and Run the Docker Image

### Build the Docker Image

To build the Docker image with the default NGINX version:

```sh
docker build -t my-nginx-image .
```

To override the NGINX version during the build:

```sh
docker build --build-arg NGINX_VERSION=1.21 -t my-nginx-image .
```

### Run the Docker Container

To run the Docker container:

```sh
docker run -d -p 8080:80 my-nginx-image
```

You can then access the NGINX server at `http://localhost:8080`.

## Author

Ariful Islam

## Description

This project illustrates the use of the `ARG` instruction in a Dockerfile to define and override build-time arguments.
# Docker ARG, ENV, CMD, and WORKDIR

## How to Use
### Building the Docker Image

To build the Docker image, use the following command:

```sh
docker build -t my_image .
```


### Running a Docker Container

To run a Docker container, use the following command:

```sh
docker run -it --name my_container my_image
```

### Deleting a Docker Container

To delete a Docker container, use the following command:

```sh
docker rm my_container
```

### Using ARG

`ARG` is used to define build-time variables. Example:

```dockerfile
FROM ubuntu:latest
ARG my_arg
RUN echo "The value of my_arg is $my_arg"
```

Build the Docker image with:

```sh
docker build --build-arg my_arg=value -t my_image .
```

### Using ENV

`ENV` is used to define environment variables. Example:

```dockerfile
FROM ubuntu:latest
ENV my_env=default_value
RUN echo "The value of my_env is $my_env"
```

### Using CMD

`CMD` is used to provide default commands for an executing container. Example:

```dockerfile
FROM ubuntu:latest
CMD ["echo", "Hello, World!"]
```

### Using WORKDIR

`WORKDIR` sets the working directory for any `RUN`, `CMD`, `ENTRYPOINT`, `COPY`, and `ADD` instructions. Example:

```dockerfile
FROM ubuntu:latest
WORKDIR /app
COPY . /app
```

## How This is Helpful

- **ARG**: Allows you to pass build-time variables, making your Dockerfile more flexible.
- **ENV**: Sets environment variables that can be used by the running container.
- **CMD**: Provides default commands that will run when the container starts.
- **WORKDIR**: Sets the working directory, making it easier to manage file paths within the container.

These instructions help in creating more dynamic, maintainable, and organized Docker images.


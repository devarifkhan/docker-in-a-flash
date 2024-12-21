# CMD Instruction in Docker

This repository demonstrates the use of the `CMD` instruction in a Dockerfile by deploying a simple Nginx server with a custom `index.html` page.

## Project Overview

- **Base Image**: `nginx:alpine-slim`
- **Purpose**: Illustrate the use of the `CMD` instruction in Docker.
- **Custom Page**: The container serves a custom `index.html` file that explains the `CMD` instruction.

## Features

- Lightweight Nginx server based on the `alpine-slim` variant.
- Custom HTML page with information about the `CMD` instruction.
- OCI-compliant labels for metadata.

## File Structure

```
.
├── Dockerfile
└── index.html
```

## Usage

### 1. Build the Docker Image

Run the following command to build the Docker image:

```bash
docker build -t cmd-dockerfile-example:1.0 .
```

### 2. Run the Container

Run the container using:

```bash
docker run -d -p 8080:80 cmd-dockerfile-example:1.0
```

The Nginx server will be accessible at [http://localhost:8080](http://localhost:8080).

### 3. Verify the Web Page

Open a web browser and navigate to [http://localhost:8080](http://localhost:8080). You should see the custom `index.html` page with the following content:

```html
<!DOCTYPE html>
<html>
    <body style='background-color:rgb(227, 213, 180);'>
        <h1>CMD Dockerfile</h1>
        <p>Learn technology through practical</p>
        <p>Application Version: V1</p>
        <p>CMD: Specify default commands.</p>
    </body>
</html>
```

## Key Concepts

### CMD Instruction

The `CMD` instruction in the Dockerfile specifies the default command to run when the container starts. In this example, the following `CMD` ensures that Nginx runs in the foreground:

```dockerfile
CMD ["nginx", "-g", "daemon off;"]
```

### OCI Labels

OCI-compliant labels are included in the Dockerfile to provide metadata about the image:

```dockerfile
LABEL org.opencontainers.image.authors="Ariful Islam"
LABEL org.opencontainers.image.title="CMD Instruction in Docker"
LABEL org.opencontainers.image.description="Illustrating the use of the CMD instruction"
LABEL org.opencontainers.image.version="1.0"
```
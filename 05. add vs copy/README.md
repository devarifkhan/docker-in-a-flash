# Docker COPY vs ADD Instructions

This project demonstrates the key differences between `COPY` and `ADD` instructions in a Dockerfile through a practical example using an NGINX web server.

## Project Overview

This repository contains a simple demonstration of how `COPY` and `ADD` instructions work differently in Docker, specifically showing:
- Using `COPY` to transfer a simple HTML file
- Using `ADD` to extract a compressed tarball automatically

## Project Structure

```
.
├── Dockerfile
├── copy-file.html
├── static_files.tar.xz
└── README.md
```

## Key Components

### Dockerfile
The Dockerfile uses NGINX alpine-slim as the base image and demonstrates:
- `COPY` instruction to copy a single HTML file
- `ADD` instruction to extract a compressed tarball
- Proper OCI labeling for container metadata

### copy-file.html
A simple HTML file that demonstrates the `COPY` instruction functionality. It contains:
- Basic HTML structure
- Custom background color
- Links to main page and Docker documentation

### static_files.tar.xz
A compressed tarball that demonstrates the automatic extraction capability of the `ADD` instruction.

## Key Differences Between COPY and ADD

1. **COPY Instruction**
   - Basic file copying from source to destination
   - More explicit and preferred for simple file copying
   - Cannot automatically extract compressed files
   - Used in this project to copy copy-file.html

2. **ADD Instruction**
   - More powerful but less explicit
   - Can automatically extract compressed files (tar, gzip, etc.)
   - Can fetch files from URLs (though not recommended)
   - Used in this project to extract static_files.tar.xz

## Usage

1. Build the Docker image:
```bash
docker build -t copy-vs-add-demo .
```

2. Run the container:
```bash
docker run -d -p 8080:80 copy-vs-add-demo
```

3. Access the web server:
   - Open your browser and visit `http://localhost:8080/copy-file.html`

## Author
Ariful Islam

## Version
1.0

## Additional Resources
- [Official Docker Documentation on COPY](https://docs.docker.com/engine/reference/builder/#copy)
- [Official Docker Documentation on ADD](https://docs.docker.com/engine/reference/builder/#add)
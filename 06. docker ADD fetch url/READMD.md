# Using ADD Instruction to Fetch Files from URLs in Dockerfile

This project demonstrates how to use Docker's ADD instruction to download files directly from URLs into a container image. The example uses an nginx server to host simple HTML files fetched from GitHub.

## Overview

The project showcases:
- Using the ADD instruction with remote URLs
- Proper file permission handling in nginx
- Replacing default nginx content with custom files
- Best practices for organizing static web content in nginx

## Prerequisites

- Docker installed on your system
- Internet connection (to fetch files from GitHub)

## Project Structure

```text
.
├── Dockerfile
├── README.md
└── docs/
    ├── index.html
    ├── about.html
    └── contact.html
```

## Dockerfile Explanation

```dockerfile
FROM nginx:alpine-slim

LABEL org.opencontainers.image.authors="Ariful Iskam"
LABEL org.opencontainers.image.title="Using ADD Instruction to Fetch Files from a URL in Dockerfile"
LABEL org.opencontainers.image.description="Illustrating the ADD instruction, which demonstrates how to download and add content from a GitHub Releases URL to the container."
LABEL org.opencontainers.image.version="1.0"

# Remove default nginx content
RUN rm -rf /usr/share/nginx/html/*

# Download files from GitHub
ADD https://raw.githubusercontent.com/devarifkhan/docker-in-a-flash/main/06.%20docker%20add%20fetch%20url/docs/index.html /usr/share/nginx/html/
ADD https://raw.githubusercontent.com/devarifkhan/docker-in-a-flash/main/06.%20docker%20add%20fetch%20url/docs/about.html /usr/share/nginx/html/
ADD https://raw.githubusercontent.com/devarifkhan/docker-in-a-flash/main/06.%20docker%20add%20fetch%20url/docs/contact.html /usr/share/nginx/html/

# Set proper permissions
RUN chown -R nginx:nginx /usr/share/nginx/html && \
    chmod -R 755 /usr/share/nginx/html/*.html
```

## Usage

1. Build the Docker image:
```bash
docker build -t add-file-from-url .
```

2. Run the container:
```bash
docker run -d -p 8080:80 add-file-from-url
```

3. Access the website:
- Main page: http://localhost:8080
- About page: http://localhost:8080/about.html
- Contact page: http://localhost:8080/contact.html

## Key Features

1. **Remote File Fetching**: Uses ADD instruction to download files directly from GitHub
2. **Permission Management**: Ensures proper file permissions for nginx
3. **Clean Setup**: Removes default nginx content before adding custom files
4. **OCI Labels**: Includes standard Open Container Initiative labels

## Security Considerations

- Always verify the source of remote files
- Use specific versions/commits when fetching from repositories
- Consider using COPY instead of ADD for local files
- Regularly update the base nginx image


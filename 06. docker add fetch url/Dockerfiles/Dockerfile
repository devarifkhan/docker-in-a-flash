# Use nginx:alpine-slim as base Docker Image
FROM nginx:alpine-slim

# OCI Labels
LABEL org.opencontainers.image.authors="Ariful Iskam"
LABEL org.opencontainers.image.title="Using ADD Instruction to Fetch Files from a URL in Dockerfile"
LABEL org.opencontainers.image.description="Illustrating the ADD instruction, which demonstrates how to download and add content from a GitHub Releases URL to the container."
LABEL org.opencontainers.image.version="1.0"

# Using GitHub Raw URLs to download files
ADD https://raw.githubusercontent.com/devarifkhan/docker-in-a-flash/main/06.%20docker%20add%20fetch%20url/docs/index.html /usr/share/nginx/html/
ADD https://raw.githubusercontent.com/devarifkhan/docker-in-a-flash/main/06.%20docker%20add%20fetch%20url/docs/about.html /usr/share/nginx/html/
ADD https://raw.githubusercontent.com/devarifkhan/docker-in-a-flash/main/06.%20docker%20add%20fetch%20url/docs/contact.html /usr/share/nginx/html/

# Set proper permissions for nginx to serve the files
RUN chown -R nginx:nginx /usr/share/nginx/html && \
    chmod -R 755 /usr/share/nginx/html/*.html
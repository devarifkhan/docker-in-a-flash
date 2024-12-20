# Define a build-time argument for the NGINX version
ARG NGINX_VERSION=1.26

# Use nginx:${NGINX_VERSION}-alpine-slim as base Docker Image
FROM nginx:${NGINX_VERSION}-alpine-slim

# OCI Labels
LABEL org.opencontainers.image.authors="Ariful Islam"
LABEL org.opencontainers.image.title="ARG Instruction"
LABEL org.opencontainers.image.description="Illustrating the ARG instruction"
LABEL org.opencontainers.image.version="1.0"

# Remove the existing index.html file
RUN rm /usr/share/nginx/html/index.html

# Using COPY to copy a local file
COPY index.html /usr/share/nginx/html
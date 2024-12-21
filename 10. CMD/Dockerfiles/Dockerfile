# Use nginx:alpine-slim as base Docker Image
FROM nginx:alpine-slim

# OCI Labels
LABEL org.opencontainers.image.authors="Ariful Islam"
LABEL org.opencontainers.image.title="CMD Instruction in Docker"
LABEL org.opencontainers.image.description="Illustrating the use of the CMD instruction"
LABEL org.opencontainers.image.version="1.0"

# Copy a custom index.html to the Nginx HTML directory
COPY index.html /usr/share/nginx/html

# Default CMD to start Nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]
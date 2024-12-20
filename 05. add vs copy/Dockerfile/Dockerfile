# Use nginx:alpine-slim as base Docker Image
FROM nginx:alpine-slim

# OCI Labels
LABEL org.opencontainers.image.authors="Ariful Islam"
LABEL org.opencontainers.image.title="COPY vs ADD Instructions in Dockerfile"
LABEL org.opencontainers.image.description="Illustrating the differences between COPY and ADD instructions, including copying files and extracting tarballs."
LABEL org.opencontainers.image.version="1.0"

# Using COPY to copy a local file
COPY copy-file.html /usr/share/nginx/html

# Using ADD to extract the tarball
ADD static_files.tar.xz /usr/share/nginx/html

# Move the contents of Files to the root directory
RUN mv /usr/share/nginx/html/Files/* /usr/share/nginx/html/ && \
    rmdir /usr/share/nginx/html/Files

# Set permissions
RUN chmod -R 755 /usr/share/nginx/html

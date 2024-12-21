# Nginx Docker Container

This repository contains a Dockerized Nginx web server configuration with a custom index page. The setup includes a optimized Dockerfile with comprehensive labeling and a customized index.html.

## 📋 Prerequisites

- Docker installed on your system
- Basic understanding of Docker commands


1. Create the project files:
   - Copy the `Dockerfile` and `index.html` into the project directory
   - Ensure both files have proper permissions

2. Build the Docker image:
```bash
docker build -t my-nginx .
```

3. Run the container:
```bash
docker run -d -p 80:80 my-nginx
```

4. Access the website:
   - Open your browser and navigate to `http://localhost`
   - You should see the custom welcome page

## 🏗️ Project Structure

```
dockerfile lables/
├── Dockerfile          # Docker configuration file with labels
├── index.html         # Custom landing page
└── README.md          # This file
```

## 📝 Docker Labels

The Dockerfile includes several categories of labels for better container organization and management:

- Basic Metadata
  - maintainer
  - version
  - description
  - vendor

- OCI Labels
  - org.opencontainers.image.source
  - org.opencontainers.image.licenses
  - org.opencontainers.image.title
  - org.opencontainers.image.version

- Custom Labels
  - com.example.environment
  - com.example.release-date

## 🛠️ Customization

### Modifying the Website Content
To modify the website content, edit the `index.html` file before building the Docker image.

### Changing Nginx Configuration
1. Create a custom nginx.conf file
2. Add it to the Dockerfile using:
```dockerfile
COPY nginx.conf /etc/nginx/nginx.conf
```

## 🔍 Inspection and Debugging

View container labels:
```bash
docker inspect my-nginx
```

Access container logs:
```bash
docker logs my-nginx
```

Access the container shell:
```bash
docker exec -it my-nginx /bin/sh
```

## 🔒 Security Considerations

- The container runs Nginx on Alpine Linux for a minimal attack surface
- Default configuration exposes only port 80
- Running as non-root user is recommended for production use


## ✨ Acknowledgments

- Nginx team for the base image
- Docker community for best practices
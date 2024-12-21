# Use official nginx image
FROM nginx:stable-alpine

# Add labels following best practices
LABEL maintainer="arifcse209@gmail.com"
LABEL version="1.0"
LABEL description="Nginx web server with custom index page"
LABEL vendor="Your Company"
LABEL build-date=$BUILD_DATE
LABEL org.opencontainers.image.source="https://github.com/devarifkhan/docker-in-a-flash.git"
LABEL org.opencontainers.image.licenses="MIT"
LABEL org.opencontainers.image.title="Custom Nginx Server"
LABEL org.opencontainers.image.version="1.0.0"
LABEL org.opencontainers.image.description="Nginx server with custom homepage"
LABEL com.example.environment="production"
LABEL com.example.release-date="2024-12-20"

# Create working directory
WORKDIR /usr/share/nginx/html

# Copy custom index.html
COPY index.html .

# Expose port 80
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]